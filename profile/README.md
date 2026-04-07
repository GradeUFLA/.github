# Trabalho Final de Engenharia de Software

----
## 1. Identificação do projeto
**Nome do projeto:** `GRADE UFLA`  
**Problema escolhido:** `Simplificar o processo de escolha e organização de disciplinas na grade horária semestral dos alunos da UFLA`  
**Turma/Semestre:** `14A / 2026/1`  
**Docente:** `Johnatan Alves de Oliveira`


### Composição do grupo
- Ana Clara Rocha Gomes -  Designer <br>
- Bárbara Oliveira Fonseca - Desenvolvedora SQL <br>
- Fernando Chaves Scarabeli -  Desenvolvedor Back-End <br>
- Jennifer Hellen Campos Silva -  Desenvolvedora Front-End <br>
- José Vítor Machado de Oliveira - Product owner e Scrum Master <br>

----

## 2. Objetivo do trabalho

### Identificação do problema escolhido
O problema central está na dificuldade que os estudantes da UFLA enfrentam ao organizar suas disciplinas a cada semestre. Atualmente, o processo de escolha e montagem da grade horária não oferece uma forma simples de visualizar previamente diferentes combinações de turmas antes da matrícula oficial.
### Contextualização do problema
Para os estudantes da UFLA, a fase de matrícula e escolha de disciplinas costuma ser uma etapa burocrática do semestre. O SIG armazena as informações, mas carece de ferramentas focadas **na experiência do usuário para a simulação prévia.** É nesse cenário que o projeto se insere, com o objetivo de facilitar a montagem da grade de horários semestral dos estudantes da UFLA. A ideia da ferramenta surge da necessidade de tornar esse processo mais simples, rápido e organizado, oferecendo uma visão clara das disciplinas, pré-requisitos e possibilidades de grade. Dessa forma, preenche-se uma lacuna importante, permitindo que o aluno teste diferentes cenários e monte seu horário de maneira ágil, visual e sem o risco de sobreposições **antes de efetivar a matrícula no sistema oficial.**

### Justificativa da proposta de solução
A criação de um sistema dedicado justifica-se por oferecer uma experiência "sem complicação" ao usuário. Ao construir uma aplicação voltada para a usabilidade, removemos as barreiras de entrada: o estudante não precisa realizar login, cadastro ou cadastrar dados pessoais. Isso garante rapidez e facilita a vida acadêmica de toda a comunidade da UFLA, centralizando a simulação de horários em uma interface moderna.

## 

### Definição preliminar do produto
O gradeUFLA é uma aplicação web pública para facilitar a gestão acadêmica dos estudantes da UFLA.
- **Para o usuário final:** Permite visualizar grades horárias, montar horários de disciplinas obrigatórias e eletivas e, por fim, exportar os resultados de forma totalmente gratuita.
- **Para a administração:** Conta com um painel interno (com autenticação obrigatória) que gerencia os dados do sistema, fornece análises de uso (analytics) e controla a atualização dos dados das disciplinas por meio de scraping do SIG da universidade.


### Organização inicial do projeto em formato ágil
O projeto seguirá os preceitos ágeis (Scrum), coordenado pelo Product Owner (PO), José Vítor. A estrutura será a seguinte:
- Sprints: O desenvolvimento ocorrerá em um cronograma de 8 Sprints.
- Entregas: Cada Sprint terá uma entrega documentada  (ex: sprint-01.md), com artefatos linkados e o backlog atualizado.
- Ferramentas de Gestão: O planejamento e acompanhamento serão feitos via GitHub Projects.
- Organização das Tarefas: Serão utilizadas Issues separadas por funcionalidade, Labels para indicar prioridades e Milestones para agrupar as entregas de cada sprint.
- Evidências: Todas as reuniões e decisões da equipe exigem documentação comprobatória, como capturas de tela das reuniões anexadas ao GitHub.

---

## 3. Organização do repositório

```text
.
├── README.md
├── .gitignore
├── .github
│   └── ISSUE_TEMPLATE
│       ├── user-story.md
│       ├── sprint-task.md
│       └── bug-report.md
├── docs
│   ├── 01_problema_e_visao_do_produto.md
│   ├── 02_scrum_e_organizacao_do_grupo.md
│   ├── 03_product_backlog.md
│   ├── 04_requisitos.md
│   ├── 05_modelagem.md
│   ├── 06_arquitetura_e_projeto.md
│   ├── 07_padroes_de_projeto.md
│   ├── 08_testes.md
│   ├── 09_entregas_incrementais.md
│   └── 10_apresentacao_final.md
├── sprints
│   ├── sprint_01.md
│   ├── sprint_02.md
│   └── sprint_review_retro_template.md
└── entregas
    └── entrega_template.md
```

---

## 4. Definição do escopo inicial da aplicação web
O escopo inicial do sistema foi dividido em dois grandes blocos de funcionalidades:

`Área do aluno:`
- Visualizar grades horárias separadas por curso e período.
- Montar o próprio horário de forma personalizada.
- Exportar ou baixar o horário após a montagem.
- Acessar toda a plataforma com zero necessidade de login, registro ou pagamentos.

`Painel Admin (Foco na Gestão):`
- Realizar login seguro e exclusivo para os administradores do sistema.
- Executar operações de CRUD para as disciplinas, turmas e horários.
- Acompanhar o engajamento através de painéis de Analytics de acesso e uso.
- Acionar manualmente (via trigger de API) o bot responsável por fazer o scraping das informações atualizadas do SIG.

## 5. Entregas previstas

| Entrega | Foco principal | Arquivo-base |
|---|---|---|
| Entrega 1 | Problema, visão do produto e organização do grupo | `docs/01_problema_e_visao_do_produto.md` e `docs/02_scrum_e_organizacao_do_grupo.md` |
| Entrega 2 | Backlog e requisitos | `docs/03_product_backlog.md` e `docs/04_requisitos.md` |
| Entrega 3 | Modelagem e decisões de projeto | `docs/05_modelagem.md` |
| Entrega 4 | Arquitetura e padrões | `docs/06_arquitetura_e_projeto.md` e `docs/07_padroes_de_projeto.md` |
| Entrega 5 | Estratégia de testes e evidências | `docs/08_testes.md` |
| Entrega final | Consolidação e apresentação | `docs/09_entregas_incrementais.md` e `docs/10_apresentacao_final.md` |


