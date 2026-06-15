# 09. Entregas Incrementais

## 1. Visão geral
Este documento consolida as entregas realizadas ao longo do semestre no desenvolvimento da plataforma **gradeUFLA**. O projeto evoluiu de forma iterativa e incremental, partindo da definição do problema e modelagem, passando pela construção de interfaces e APIs, até a implementação de uma arquitetura robusta de ingestão de dados acadêmicos e deploy final.

---

## 2. Cronograma
| Entrega/Sprint | Período | Objetivo | Artefatos gerados | Status |
|---|---|---|---|---|
| Sprint 1 | 04/04/2026 a 10/04/2026 | Definição do escopo, visão do produto e setup do repositório. | `README.md`, Quadro Kanban configurado, Visão geral. | Concluída |
| Sprint 2 | 11/04/2026 a 25/04/2026 | Identidade visual, prototipação e modelagem inicial do Banco de Dados. | MER/DER, Dicionário de Dados, Guia de Identidade Visual, Componente Hero (Front-end). | Concluída |
| Sprint 3 | 25/04/2026 a 09/05/2026 | Modelagem estrutural UML e criação da grade interativa. | Diagramas UML (Casos de Uso, Componentes, Sequência), Scripts SQL, Protótipo da Montagem de Grade. | Concluída |
| Sprint 4 | 09/05/2026 a 23/05/2026 | Módulo Administrativo e documentação da API. | Swagger/OpenAPI, Login Admin (JWT), Protótipos de Dashboard e Analytics, Scripts de Scraping iniciais. | Concluída |
| Sprint 5 | 23/05/2026 a 06/06/2026 | Extração massiva de dados, testes e integração de calendário. | Relatórios de auditoria no Banco de Dados, Exportação Google Agenda, Mapeamento do SIG concluído. | Concluída |
| Sprint 6 | 06/06/2026 a 15/06/2026 | Integração final, arquitetura em lote (.zip) e deploy da aplicação. | Upload e processamento de `.zip`, Responsividade Mobile, Documentação de Entrega e Deploy. | Em andamento |

---

## 3. Resumo por sprint

### Sprint 1
**Meta da sprint:**  
Definir o problema a ser tratado, estabelecer a visão inicial do produto, organizar o projeto com base no Scrum, fazer o backlog inicial e iniciar formalmente o repositório no GitHub.

**Itens planejados:**  
- Setup do GitHub Projects.
- Definição da stack tecnológica.
- Levantamento da visão e escopo do produto.
- Escrita da documentação inicial (`README.md` e `sprint-01.md`).

**Itens entregues:**  
- Repositório GitHub estruturado com Kanban.
- `README.md` com a visão do produto consolidada.
- Stack definida (React, Spring Boot, PostgreSQL, Python).

**Dificuldades encontradas:**  
- Padronização de toda a documentação do software.
- Dificuldade inicial no mapeamento e priorização do backlog de um projeto construído do zero.

**Aprendizados:**  
- A clareza na definição do escopo inicial previne o desvio de foco (*scope creep*) nas etapas subsequentes.

### Sprint 2
**Meta da sprint:**  
Modelar a estrutura de dados (Banco de Dados), estabelecer a identidade visual, prototipar a interface do estudante e codificar a tela inicial no Front-end.

**Itens planejados:**  
- Modelagem de dados (MER/DER).
- Design: Identidade visual, Stepper, Tela de Conclusão e Montagem de Grade.
- Back-end: Estudos de arquitetura.
- Front-end: Codificação da seção Hero.

**Itens entregues:**  
- Modelagem ER e Dicionário de Dados.
- Guia de Identidade Visual e Protótipos de alta fidelidade (Figma).
- Tela inicial (Hero) implementada no Front-end em React.

**Dificuldades encontradas:**  
- **Design:** Prototipar a complexidade da grade horária demandou mais tempo do que o esperado.
- **Banco de Dados:** Estabelecer o relacionamento correto entre as tabelas e definir padrões de nomenclatura.
- **Back-end:** Delimitar as responsabilidades e permissões entre o Front e o Back.

**Aprendizados:**  
- Projetar interfaces baseadas em casos de uso reais logo no início facilita a modelagem do banco de dados, alinhando a experiência visual à estrutura técnica.

### Sprint 3
**Meta da sprint:**  
Representar a solução por meio de modelos estruturais e comportamentais (UML) e estruturar o "coração" lógico do sistema com os scripts de banco e componentes interativos.

**Itens planejados:**  
- Diagramas UML (Casos de Uso, Componentes, Sequência).
- Criação dos scripts SQL iniciais.
- Desenvolvimento de Front-end (Stepper e Conclusões) e Back-end público.
- Estudos aplicados em Python para o bot.

**Itens entregues:**  
- Documentação de Diagramas UML concluída.
- Protótipo de Montagem de Grade concluído e Login de Admin finalizado no Figma.
- Base de dados com CRUD configurado.
- Padronização do GitHub (Issue Templates).
- Integrações iniciais de Front/Back nas telas do Stepper.

**Dificuldades encontradas:**  
- Acúmulo de demandas e gestão de tempo da equipe com outras disciplinas.
- Lentidão em ferramentas de IA (Copilot) prejudicando a produtividade do Back-end.
- Complexidade na estilização CSS de componentes dinâmicos no Front-end.

**Aprendizados:**  
- A qualidade da documentação UML foi vital para alinhar o que precisava ser feito tecnicamente, diminuindo o ruído de comunicação entre o Front-end e o Back-end.

### Sprint 4
**Meta da sprint:**  
Avançar na codificação do módulo Administrativo, fechar o contrato de comunicação da API via Swagger e avançar o desenvolvimento do bot de extração de dados no SIG.

**Itens planejados:**  
- Contrato da API (Swagger/OpenAPI).
- Protótipos de Dashboard, Analytics e Dados.
- Lógica de Autenticação e Login de Administrador.
- Implementação inicial do Scraping (Mapeamento de cursos e matrizes).

**Itens entregues:**  
- Módulo Administrativo 100% desenhado no Figma.
- Rota de Login funcional utilizando JWT no Back-end.
- API documentada via Swagger.
- Extração de cursos, matrizes e disciplinas entrando em fase de testes.

**Dificuldades encontradas:**  
- Protótipo de Analytics foi denso e complexo de criar no Figma.
- Gargalos no Bot: consumia muita interface gráfica, e quedas de conexão faziam perder todo o progresso da extração.
- Falta de tempo hábil para finalizar as integrações visuais planejadas (Front com Back).

**Aprendizados:**  
- Definir o contrato da API antecipadamente via Swagger permitiu que as frentes de Back-end e Front-end trabalhassem de forma isolada sem bloquear uma à outra.

### Sprint 5
**Meta da sprint:**  
Concluir integrações pendentes, finalizar rotinas de exportação, realizar testes de integridade profundos no banco e estabilizar a extração de dados (Scraping).

**Itens planejados:**  
- Testes robustos de Banco de Dados.
- Funcionalidade de Exportar grade para Google Agenda.
- Finalizar mapeamento e extração do SIG via Bot.
- Refinamentos de interface.

**Itens entregues:**  
- Relatório de validação comprovando injeção em massa de dados com sucesso e sem entidades órfãs.
- Endpoints de Dashboard e Dados operantes.
- Exportação Google Agenda (iCal) desenvolvida no Back-end.

**Dificuldades encontradas:**  
- **Restrição de Infraestrutura:** A execução do Bot de Scraping online exigia recursos de servidor insustentáveis para o orçamento do projeto, exigindo uma mudança urgente de arquitetura (Bot local gerando `.zip`).
- Tarefas de Front-end seguiram represadas devido ao escopo e tempo.

**Aprendizados:**  
- Monitorar custos de infraestrutura e performance logo cedo previne que o projeto se torne inviável na hora do Deploy. Pivotar a estratégia de dados foi vital para a saúde do software.

### Sprint 6
**Meta da sprint:**  
Realizar a entrega final do sistema, aplicando a nova arquitetura de importação (`.zip`), integrando todas as pontas (Front e Back), ajustando responsividade e realizando o deploy.

**Itens planejados:**  
- Refatoração do fluxo de importação (Upload de `.zip` no Admin).
- Conclusão das integrações Front-end e Back-end.
- Responsividade mobile nas telas públicas.
- Deploy da aplicação na nuvem.
- Documentação de encerramento, slides e vídeo.

**Itens entregues:**  
- Sistema totalmente funcional e integrado, acessível online via deploy.
- Nova tela de Gestão de Dados (Admin) capaz de processar os arquivos compactados em lote com tolerância a falhas.
- Toda a documentação e artefatos de entrega consolidados.

**Dificuldades encontradas:**  
- Lidar com *timeouts* nas requisições HTTP do Front-end durante o processamento do longo e pesado arquivo `.zip`.
- Corrida final para sanar pequenos conflitos de integração entre o repositório front e back.

**Aprendizados:**  
- O desenvolvimento ágil provou seu valor ao permitir que a equipe se adaptasse à mudança radical de arquitetura na Sprint 5, conseguindo finalizar a entrega com qualidade na Sprint 6.

---

## 4. Evolução do produto
A plataforma **gradeUFLA** teve uma evolução técnica e conceitual notável. Nas Sprints 1 e 2, tratava-se apenas de uma documentação e telas de design visuais. Na Sprint 3, estruturou-se um banco de dados complexo para refletir a realidade do SIG e a base do sistema em Spring Boot. A Sprint 4 agregou segurança com autenticação JWT e documentou APIs para consumo robusto.

O grande salto de maturidade ocorreu nas Sprints 5 e 6, onde o sistema transitou de um escopo manual/limitado para um ecossistema alimentado por extração de dados automatizada (Python/Scraping). O que antes seria um Bot rodando em tempo real passou por uma reengenharia para atuar via arquivos em lote (`.zip`), demonstrando que o produto evoluiu não apenas em código, mas em resiliência e viabilidade arquitetural para se manter de pé em um ambiente de produção real.

---

## 5. Mudanças relevantes no escopo
| Mudança | Motivo | Impacto |
|---|---|---|
| **Mudança de acionamento do Bot (Servidor > Lote Offline)** | O alto custo computacional de rodar navegadores web ocultos (*headless*) no servidor para realizar o web scraping em tempo real inviabilizou a arquitetura original. | O Bot foi removido do servidor principal e passou a operar localmente. Isso exigiu a criação urgente de um endpoint de processamento de arquivos `.zip` no Back-end e a reestruturação da tela de "Dados" no Painel Administrativo. |

---

## 6. Conclusão
O desenvolvimento do **gradeUFLA** ao longo das 6 sprints é um exemplo claro da aplicação prática da Engenharia de Software. A equipe iniciou com uma visão de simplificar a vida acadêmica e materializou essa ideia em uma aplicação Full-Stack. O uso do framework Scrum permitiu rastrear os atrasos, priorizar a construção do núcleo do sistema (Grade e Banco de Dados) e, crucialmente, adaptar a arquitetura a um modelo assíncrono (importação em lote) sem perder o escopo. O produto gerado ao final do ciclo cumpre os requisitos propostos, oferecendo uma interface ágil para os alunos e um painel de gestão consistente e independente para os administradores.
