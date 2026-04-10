# Sprint 1– Definição do problema, visão do produto e organização inicial do projeto



## Identificação do problema escolhido

O problema central está na dificuldade que os estudantes da UFLA enfrentam ao organizar suas disciplinas a cada semestre. Atualmente, o processo de escolha e montagem da grade horária não oferece uma forma simples de visualizar previamente diferentes combinações de turmas antes da matrícula oficial.

Contextualização do problema:

Para os estudantes da UFLA, a fase de matrícula e escolha de disciplinas costuma ser uma etapa burocrática do semestre. O SIG armazena as informações, mas carece de ferramentas focadas na experiência do usuário para a simulação prévia. É nesse cenário que o projeto se insere, com o objetivo de facilitar a montagem da grade de horários semestral dos estudantes da UFLA. A ideia da ferramenta surge da necessidade de tornar esse processo mais simples, rápido e organizado, oferecendo uma visão clara das disciplinas, pré-requisitos e possibilidades de grade. Dessa forma, preenche-se uma lacuna importante, permitindo que o aluno teste diferentes cenários e monte seu horário de maneira ágil, visual e sem o risco de sobreposições antes de efetivar a matrícula no sistema oficial.

Justificativa da proposta de solução:

A criação de um sistema dedicado justifica-se por oferecer uma experiência "sem complicação" ao usuário. Ao construir uma aplicação voltada para a usabilidade, removemos as barreiras de entrada: o estudante não precisa realizar login, cadastro ou cadastrar dados pessoais. Isso garante rapidez e facilita a vida acadêmica de toda a comunidade da UFLA, centralizando a simulação de horários em uma interface moderna.


## Definição preliminar do produto
O gradeUFLA é uma aplicação web pública para facilitar a gestão acadêmica dos estudantes da UFLA.
Para o usuário final: Permite visualizar grades horárias, montar horários de disciplinas obrigatórias e eletivas e, por fim, exportar os resultados de forma totalmente gratuita.
Para a administração: Conta com um painel interno (com autenticação obrigatória) que gerencia os dados do sistema, fornece análises de uso (analytics) e controla a atualização dos dados das disciplinas por meio de scraping do SIG da universidade.

Composição do grupo
Ana Clara Rocha Gomes - Designer
Bárbara Oliveira Fonseca - Desenvolvedora SQL
Fernando Chaves Scarabeli - Desenvolvedor Back-End
Jennifer Hellen Campos Silva - Desenvolvedora Front-End
José Vítor Machado de Oliveira - Product owner e Scrum Master


Organização inicial do projeto em formato ágil
O projeto seguirá os preceitos ágeis (Scrum), coordenado pelo Product Owner (PO), José Vítor. A estrutura será a seguinte:
Sprints: O desenvolvimento ocorrerá em um cronograma de 8 Sprints.
Entregas: Cada Sprint terá uma entrega documentada  (ex: sprint-01.md), com artefatos linkados e o backlog atualizado.
Ferramentas de Gestão: O planejamento e acompanhamento serão feitos via GitHub Projects.
Organização das Tarefas: Serão utilizadas Issues separadas por funcionalidade, Labels para indicar prioridades e Milestones para agrupar as entregas de cada sprint.
Evidências: Todas as reuniões e decisões da equipe exigem documentação comprobatória, como capturas de tela das reuniões anexadas ao GitHub.


Definição do escopo inicial da aplicação web.
O escopo inicial do sistema foi dividido em dois grandes blocos de funcionalidades:
Área do aluno:
Visualizar grades horárias separadas por curso e período.
Montar o próprio horário de forma personalizada.
Exportar ou baixar o horário após a montagem.
Acessar toda a plataforma com zero necessidade de login, registro ou pagamentos.
Painel Admin (Foco na Gestão):
Realizar login seguro e exclusivo para os administradores do sistema.
Executar operações de CRUD para as disciplinas, turmas e horários.
Acompanhar o engajamento através de painéis de Analytics de acesso e uso.
Acionar manualmente (via trigger de API) o bot responsável por fazer o scraping das informações atualizadas do SIG.

