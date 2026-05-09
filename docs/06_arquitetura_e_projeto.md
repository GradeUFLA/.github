# 06. Arquitetura e Projeto

## 1. Visão arquitetural

**Estilo arquitetural adotado:** - Cliente-Servidor (Client-Server) / API RESTful em camadas, com módulo autônomo de automação.

**Justificativa:** A separação em Cliente-Servidor permite que o Frontend (interface interativa do aluno) e o Backend (regras de negócio e banco) operem e escalem de forma independente. O backend foi estruturado em camadas (Controller, Service, Repository) para isolar responsabilidades e facilitar a manutenção do código. Além disso, optou-se por isolar a extração de dados do SIG em um "módulo autônomo" (Bot em Python) para garantir que tarefas de processamento pesado não afetem a performance ou a disponibilidade da API principal consumida pelos estudantes.

---

## 2. Estrutura em alto nível
### Camadas ou módulos
| Camada/Módulo | Responsabilidade |
|---|---|
| **Apresentação (Frontend)** | Interface do usuário em React (SPA). Responsável pela renderização do calendário, lógica visual de "drag-and-drop", validações de conflito em tempo real (lado do cliente) e consumo da API. |
| **Aplicação (Backend API)** | Servidor Spring Boot que atua como API REST. Gerencia a autenticação administrativa (JWT), orquestra as requisições do frontend e aplica as regras de negócio centrais de segurança. |
| **Automação (Bot Scraping)** | Script Python isolado responsável por acessar o SIG da UFLA, extrair os dados acadêmicos mais recentes (cursos, turmas, horários) e injetá-los diretamente no banco. |
| **Persistência (Banco)** | Banco de dados relacional PostgreSQL, responsável por armazenar as entidades acadêmicas de forma normalizada, credenciais de administradores e logs do sistema. |

---

## 3. Principais decisões de projeto
| Decisão | Motivação | Impacto |
|---|---|---|
| **Validação de conflitos no Frontend** | Evitar requisições sucessivas e sobrecarga da API a cada matéria arrastada para o calendário. | Experiência de uso fluida e em tempo real (baixa latência) para o aluno e economia de recursos no servidor. |
| **Isolamento do Bot de Scraping** | O web scraping é uma tarefa custosa e passível de falhas (ex: SIG fora do ar). | Garante alta disponibilidade (RNF08): se o bot falhar, a aplicação web continua operando normalmente com os dados do último scraping. |
| **Acesso público sem login (Alunos)** | Reduzir a carga cognitiva e o atrito inicial para que o estudante extraia valor da plataforma rapidamente. | A autenticação e segurança JWT (RNF05) ficam restritas apenas ao módulo do Administrador, simplificando o fluxo do usuário final. |

---

## 4. Tecnologias previstas
| Tecnologia | Finalidade | Justificativa |
|---|---|---|
| **React (JS/TS)** | Interface Web (SPA) | Excelente ecossistema para interfaces reativas, componentização e gerenciamento de estado complexo (necessário para a montagem de grade interativa). |
| **Java (Spring Boot)** | API Backend | Framework robusto, escalável, com suporte nativo para criação de APIs RESTful, segurança (Spring Security) e mapeamento objeto-relacional (Hibernate). |
| **Python** | Bot de Extração (Scraping) | Melhor ecossistema do mercado para extração e manipulação de dados web (ex: BeautifulSoup, Selenium, Pandas). |
| **PostgreSQL** | Banco de Dados | Banco relacional sólido, ideal para garantir a integridade referencial dos dados acadêmicos (Cursos 1:N Disciplinas N:M Turmas). |

---

## 5. Riscos técnicos
| Risco | Probabilidade | Impacto | Mitigação |
|---|---|---|---|
| **Mudança estrutural no HTML do SIG UFLA** | Média | Alta | Criar alertas de erro no painel de Logs/Analytics. Caso o bot falhe, o sistema opera com os dados em cache/última versão estável. |
| **Pico de acessos simultâneos na semana de matrícula** | Alta | Alta | Manter o processamento pesado no cliente (Front-end), otimizar as *queries* do banco e configurar cache para chamadas estáticas da API. |
| **Lentidão na renderização do calendário via Drag-and-Drop** | Baixa | Média | Utilizar bibliotecas otimizadas de virtualização de listas e separar as matérias não utilizadas com paginação/filtros na sidebar. |

---

## 6. Exemplo resumido
> Será adotada uma arquitetura Cliente-Servidor com backend em camadas (MVC/REST), separando claramente a interface reativa (React), a API de fornecimento de dados e segurança (Spring Boot) e a persistência (PostgreSQL). Para garantir a estabilidade do sistema, a atualização da base de dados será delegada a um microsserviço assíncrono de automação (Python), permitindo alta disponibilidade e manutenção facilitada de cada componente da aplicação.
