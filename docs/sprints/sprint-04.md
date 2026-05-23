# Sprint 4

## 1. Identificação
- **Número da sprint:** 04
- **Período:** 09/05/2026 a 23/05/2026
- **Data da entrega:** 23/05/2026

## 2. Objetivo da sprint
Avançar com a codificação do sistema, focando na integração entre o Front-end e o Back-end das áreas públicas (Montagem de Grade, Stepper), no desenvolvimento completo do módulo Administrativo (Login, Dashboard, Analytics e Dados) e na implementação do bot de extração de dados (*Scraping*) no Banco de Dados.

## 3. Itens do Sprint Backlog

| Demanda (Task) | Responsável | Área | Situação |
| :--- | :--- | :---: | :--- |
| Exportar a grade para o Google Agenda #30 | Fernando | Back-End | Testes |
| Front-end: Tela de Montagem de grade #36 | Jhennifer | Front-End | Em progresso |
| Front-end: Login de Usuário - Admin #39 | Jhennifer | Front-End | A fazer |
| Back-end: Login de Usuário - Admin #40 | Fernando | Back-End | Feito |
| Design: Tela de Dashboard - Admin #41 | Clara | Design | Feito |
| Back-end: Tela de Dashboard - admin #43 | Fernando | Back-End | Testes |
| Design: Tela de Analytics - Admin #44 | Clara | Design | Feito |
| Back-end: Tela de analytics - admin #46 | Fernando | Back-End | A fazer |
| Design: Tela de dados - admin #47 | Clara | Design | Feito |
| Back-end: Tela de dados - admin #49 | Fernando | Back-End | Testes |
| Desenvolver e documentar o contrato da API (Swagger/OpenAPI) #63 | Fernando | Back-End | Feito |
| Banco de dados: Validar relação entre tabelas disciplina e curso #65 | Bárbara | Banco de Dados | A fazer |
| Integração: tela de login #66 | Jhennifer | Front-End | A fazer |
| Integração: Stepper e tela de matérias concluídas #67 | Jhennifer | Front-End | A fazer |
| Integração: tela montagem de grade #68 | Jhennifer | Front-End | A fazer |
| Banco de dados: Validar consultas (queries) para otimizar busca #69 | Bárbara | Banco de Dados | A fazer |
| Banco de dados: Escrever consultas otimizadas nas tabelas de log #70 | Bárbara | Banco de Dados | A fazer|
| Banco de dados: Implementar bot para coleta de dados (Scraping) #72 | Bárbara | scraping-bot | A fazer |
| Criar Documentação sprint 4 #73 | Jose Vitor | Documentação | Em progresso |
| Mapeamento de cursos no SIG #78 | Bárbara | scraping-bot | Em testes |
| Extração de matrizes curriculares #79 | Bárbara | scraping-bot | Em testes |
| Extração de disciplinas e relacionamento com matriz curricular #80 | Bárbara | scraping-bot | Em testes |
| Extração de pré-requisitos #81 | Bárbara | scraping-bot | A fazer |
| Extração de turmas #82 | Bárbara | scraping-bot | A fazer |
| Extração de horários #83 | Bárbara | scraping-bot | A fazer |

## 4. Relação com o conteúdo da disciplina
Nesta sprint, o foco recai sobre a **Implementação e Integração de Software**. Estaremos a aplicar os conceitos de construção de componentes, comunicação entre camadas (API RESTful ligando o Cliente ao Servidor) e persistência de dados real, materializando as decisões arquiteturais tomadas na etapa de modelagem da Sprint 3.

## 5. Artefatos produzidos
- Telas de protótipo de alta fidelidade (Design) para o painel de Administrador: Dashboard, Analytics e Dados.
- Contrato da API documentado via Swagger/OpenAPI.
- Rota de Back-end para Login de Administrador.
- Scripts iniciais do Bot de Scraping para mapeamento de cursos, matrizes e disciplinas.

## 6. Evidências no GitHub
- **Commits relevantes:**
<img width="1363" height="611" alt="image" src="https://github.com/user-attachments/assets/fe2db33e-5a2b-40f4-8f7f-d710759485b4" />
<img width="1373" height="937" alt="image" src="https://github.com/user-attachments/assets/e90688a6-b80f-4a96-9bb9-d9f32d5fe340" />
<img width="1264" height="856" alt="image" src="https://github.com/user-attachments/assets/4c14332f-62f7-49a1-b5d4-56c8070ff107" />
<img width="1102" height="849" alt="image" src="https://github.com/user-attachments/assets/722ecbf4-4b3c-4236-ad2f-e775e6e2a2b0" />


## 7. Evolução da aplicação web
Nesta sprint, a aplicação evoluiu significativamente na sua estrutura interna e visualização administrativa. A área de Design finalizou todos os fluxos administrativos. No Back-end, as rotas de segurança (Login de Admin) e o contrato da API (Swagger) foram estabelecidos, permitindo que a integração futura seja mais fluida. Além disso, o bot de coleta de dados avançou nas rotinas de extração iniciais do SIG (Cursos, Matrizes e Disciplinas), que já se encontram em fase de testes. As evoluções de Front-end e Integrações foram contidas devido a restrições de tempo da equipe.

## 8. Dificuldades encontradas
- **Clara (Design):** Relatou grande dificuldade na prototipação da tela de *Analytics*, por ser uma interface mais densa, exigindo muitos campos, gráficos e organização hierárquica das informações.
- **Bárbara (Bot/Banco):** Notou-se que o bot atual abre a interface do SIG durante a execução, o que consome recursos. Além disso, identificou-se um risco crítico: se houver queda de energia ou internet, o bot perde todo o progresso.
- **Jhennifer (Front-end):** Enfrentou falta de tempo hábil para conciliar as demandas, o que impediu a conclusão e o envio das tarefas de integração e construção de interfaces planejadas para a sprint.
- **Fernando (Back-end):** Também relatou falta de tempo, o que resultou no atraso de algumas rotas do painel administrativo (Analytics) e no represamento de tarefas em fase de "Testes".

## 9. Revisão do incremento
- **O que foi concluído:** Foram entregues 100% dos designs previstos para o módulo Administrativo (Dashboard, Dados e Analytics). No Back-end, o contrato da API (Swagger) e o Login do Administrador foram finalizados.
- **O que ficou pendente:** Devido às dificuldades de tempo relatadas, todas as tarefas de integração (Front com Back), a tela de Montagem de Grade (Front-end), além de partes do painel administrativo (Back-end) e as validações de banco de dados, não foram finalizadas e transitarão para a próxima sprint.

## 10. Pendências para a próxima sprint
As tarefas marcadas como `To do`, `In progress` e `Tests` no backlog atual serão automaticamente migradas para a Sprint 05. Além disso, a partir dos feedbacks da equipe, **novas tasks deverão ser criadas** no backlog:

- **[Design]** Criar o pop-up / modal de "Compartilhar Grade".
- **[Design]** Aplicar melhorias e corrigir erros residuais apontados nas telas entregues pela Clara.
- **[Produto/PO]** Redigir o texto explicativo de "Modo de usar o sistema" para os usuários.
- **[Bot Scraping]** Otimizar o bot (ex: rodar em modo *headless*) para não abrir a interface gráfica do navegador durante a execução no SIG.
- **[Bot Scraping]** Implementar rotina de salvamento de estado do bot (persistência), garantindo que ele retome a extração de onde parou em caso de queda de internet ou energia.

## 11. Registros das reuniões
Planning:

<img width="1895" height="875" alt="image" src="https://github.com/user-attachments/assets/d26df3d9-06f0-48fd-a22c-ffea237c68e2" />

Review:
<img width="1882" height="931" alt="image" src="https://github.com/user-attachments/assets/89b4f2ac-2169-4201-b5a4-8e440d7a3ac8" />

