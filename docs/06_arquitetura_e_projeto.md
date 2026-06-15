# 06. Arquitetura e Projeto

## 1. Visão arquitetural

**Estilo arquitetural adotado:** Cliente-Servidor (Client-Server) / API RESTful em camadas, integrado a um processo de ingestão de dados em lote (*Batch Processing*) gerado de forma offline.

**Justificativa:** A separação em Cliente-Servidor permite que o Frontend (interface interativa do aluno) e o Backend (regras de negócio e banco) operem e escalem de forma independente. O backend foi estruturado em camadas (Controller, Service, Repository) para isolar responsabilidades e facilitar a manutenção do código. Além disso, por questões de viabilidade financeira e técnica de infraestrutura, optou-se por isolar a extração de dados do SIG em um script Python executado localmente (offline). O servidor backend recebe os dados extraídos através de um upload em lote (arquivo `.zip`), garantindo que tarefas de processamento pesado de *web scraping* não consumam a memória e a CPU da API principal consumida pelos estudantes.

---

## 2. Estrutura em alto nível
### Camadas ou módulos
| Camada/Módulo | Responsabilidade |
|---|---|
| **Apresentação (Frontend)** | Interface do usuário em React (SPA). Responsável pela renderização do calendário, lógica visual de "drag-and-drop", validações de conflito em tempo real (lado do cliente) e interface de upload do painel administrativo. |
| **Aplicação (Backend API)** | Servidor Spring Boot que atua como API REST. Gerencia a autenticação administrativa (JWT), atende as simulações dos alunos e atua como orquestrador da importação (descompacta os `.zip` e aplica as regras de inserção no banco). |
| **Coleta de Dados (Bot Offline)** | Script Python isolado, rodando na máquina local do administrador. Responsável por acessar o SIG da UFLA via *web scraping*, estruturar os dados acadêmicos e gerar um arquivo compactado com JSONs estruturados. |
| **Persistência (Banco)** | Banco de dados relacional PostgreSQL, responsável por armazenar as entidades acadêmicas de forma normalizada, suportar inserções em lote (*Upsert*) e manter as credenciais e logs do sistema. |

---

## 3. Principais decisões de projeto
| Decisão | Motivação | Impacto |
|---|---|---|
| **Validação de conflitos no Frontend** | Evitar requisições sucessivas e sobrecarga da API a cada matéria arrastada para o calendário. | Experiência de uso fluida e em tempo real (baixa latência) para o aluno e economia drástica de recursos no servidor. |
| **Pivot do Bot de Scraping (Offline)** | Executar navegadores ocultos (*headless*) no servidor em nuvem exigia muita memória RAM e inviabilizaria o projeto financeiramente. | O scraping passou a gerar um pacote `.zip` localmente. O administrador faz o upload pelo painel web, salvando infraestrutura e garantindo que o sistema web nunca caia por culpa do bot. |
| **Acesso público sem login (Alunos)** | Reduzir a carga cognitiva e o atrito inicial para que o estudante extraia valor da plataforma rapidamente. | A autenticação e segurança JWT (RNF05) ficam restritas apenas ao módulo do Administrador, simplificando o fluxo do usuário final. |

---

## 4. Tecnologias previstas
| Tecnologia | Finalidade | Justificativa |
|---|---|---|
| **React (JS/TS)** | Interface Web (SPA) | Excelente ecossistema para interfaces reativas, componentização e gerenciamento de estado complexo (necessário para a montagem de grade interativa). |
| **Java (Spring Boot)** | API Backend | Framework robusto, escalável, com suporte nativo para criação de APIs RESTful, segurança (Spring Security) e transações robustas de banco de dados (JPA/Hibernate). |
| **Python** | Bot de Extração (Scraping) | Melhor ecossistema do mercado para extração e manipulação de dados da web (Selenium/BeautifulSoup). |
| **PostgreSQL** | Banco de Dados | Banco relacional sólido, ideal para garantir a integridade referencial dos dados acadêmicos (Cursos 1:N Disciplinas N:M Turmas) através de grandes volumes de inserção. |

---

## 5. Riscos técnicos
| Risco | Probabilidade | Impacto | Mitigação |
|---|---|---|---|
| **Timeout durante upload do `.zip`** | Alta | Alta | Como o processamento e a inserção de milhares de registros (*Upsert*) podem demorar, o Frontend deve tratar adequadamente o tempo limite de requisição e o Backend deve realizar inserções em lote otimizadas (*JDBC Batch*). |
| **Mudança estrutural no HTML do SIG UFLA** | Média | Alta | Caso a extração offline falhe devido a mudanças no SIG, a aplicação web continua 100% operante com os dados da última versão estável já armazenada no PostgreSQL. |
| **Lentidão na renderização do calendário via Drag-and-Drop** | Baixa | Média | Utilizar bibliotecas otimizadas de virtualização de listas e separar as matérias não utilizadas com paginação/filtros na sidebar do estudante. |

---

## 6. Exemplo resumido
> A solução adota uma arquitetura Cliente-Servidor com backend em camadas (MVC/REST), separando claramente a interface reativa (React), a API de regras de negócio e segurança (Spring Boot) e a persistência (PostgreSQL). Para garantir a estabilidade financeira e técnica da infraestrutura na nuvem, a atualização do catálogo acadêmico é delegada a um script offline (Python) que atua na máquina local do administrador gerando pacotes de dados (.zip), os quais são enviados à API via interface web para atualização em lote da base de dados.
