# Sprint 5

## 1. Identificação
- **Número da sprint:** 05
- **Período:** 23/05/2026 a 06/06/2026
- **Data da entrega:** 06/06/2026

## 2. Objetivo da sprint
Concluir as integrações pendentes entre o Front-end e o Back-end (telas de login, montagem de grade e stepper), refinar as interfaces de design com base nos feedbacks recebidos e finalizar o fluxo de extração de dados do SIG com o bot em Python. Além disso, a sprint focou na estabilização do sistema, realizando testes profundos nas rotas de Back-end e na persistência de dados no Banco de Dados.

## 3. Itens do Sprint Backlog

| Demanda (Task) | Responsável | Área | Situação |
| :--- | :--- | :---: | :--- |
| Exportar a grade para o Google Agenda #30 | Fernando | Back-End | 🟢 Concluído |
| Front-end: Tela de Montagem de grade #36 | Jhennifer | Front-End | 🟡 Em andamento |
| Front-end: Login de Usuário - Admin #39 | Jhennifer | Front-End | 🔴 A fazer |
| Back-end: Tela de Dashboard - admin #43 | Fernando | Back-End | 🟢 Concluído |
| Back-end: Tela de analytics - admin #46 | Fernando | Back-End | 🔴 A fazer |
| Back-end: Tela de dados - admin #49 | Fernando | Back-End | 🟢 Concluído |
| Exportar a grade em .jpg #51 | Jhennifer | Front-End | 🔴 A fazer |
| Desenvolver uma PoC em Python para extrair dados... #64 | Bárbara | scraping-bot | 🔴 A fazer |
| Banco de dados: Validar relação entre tabelas disciplina e matriz... #65 | Bárbara | Banco de Dados | 🔴 A fazer |
| Integração: tela de login #66 | Jhennifer | Front-End | 🔴 A fazer |
| Integração: Stepper e tela de matérias concluídas #67 | Jhennifer | Front-End | 🔴 A fazer |
| Integração: tela montagem de grade #68 | Jhennifer | Front-End | 🔴 A fazer |
| Banco de dados: Validar as consultas (queries) para otimização... #69 | Bárbara | Banco de Dados | 🔴 A fazer |
| Banco de dados: Escrever consultas otimizadas nas tabelas... #70 | Bárbara | Banco de Dados | 🔴 A fazer |
| Mapeamento de cursos no SIG #78 | Bárbara | scraping-bot | 🟢 Concluído |
| Extração de matrizes curriculares #79 | Bárbara | scraping-bot | 🟢 Concluído |
| Extração de disciplinas e relacionamento com matriz curricular #80 | Bárbara | scraping-bot | 🟢 Concluído |
| Extração de pré-requisitos #81 | Bárbara | scraping-bot | 🔴 A fazer |
| Extração de turmas #82 | Bárbara | scraping-bot | 🔴 A fazer |
| Extração de horários #83 | Bárbara | scraping-bot | 🔴 A fazer |
| Back-end: Criar endpoint que aciona o script Python... #85 | Fernando | Back-End | 🔴 A fazer |
| Atualização dos modelos ou diagramas #89 | Não atribuído | Documentação | 🔴 A fazer |
| Melhorias no design baseadas nos comentários #91 | Clara | Design | 🔴 A fazer |
| Pop-up compartilhar grade #92 | Clara | Design | 🔴 A fazer |

## 4. Relação com o conteúdo da disciplina
Nesta sprint, aprofundamos a **Integração de Sistemas**, **Validação e Teste de Software** e **Arquitetura de Software**. Evidenciamos isso ao realizar uma análise de viabilidade técnica (custo vs. performance) que resultou na mudança arquitetural do *bot de scraping*, desacoplando-o do servidor principal para otimizar os recursos do sistema.

## 5. Artefatos produzidos
- Relatórios de Validação e Testes no Banco de Dados (comprovando a ingestão de cursos, matrizes e disciplinas via bot).
- Endpoints administrativos de Dashboard e Dados totalmente funcionais no Back-end.
- Lógica de exportação do horário para o formato do Google Agenda concluída.
- Documentação do Plano de Testes.

## 6. Evidências no GitHub
- **Arquivos criados/atualizados:** `[Inserir link para os relatórios de DB e PDFs]`
- **Commits relevantes:** `[Inserir hash e link dos commits de Back-end e Bot]`
- **Tag da sprint:** `[Inserir tag, ex: v0.5.0]`

## 7. Evolução da aplicação web
O sistema sofreu um amadurecimento arquitetural crucial. O Back-end consolidou as rotas administrativas pesadas (Dashboard e Dados) e a integração com o Google Agenda. Em paralelo, o *bot* provou o seu valor ao conseguir extrair e mapear com sucesso o esqueleto da universidade (Cursos, Matrizes e Disciplinas). Devido a uma decisão estratégica de arquitetura (detalhada nas Dificuldades), a aplicação passará por uma alteração no seu fluxo de atualização de dados, trocando a execução em tempo real do *bot* no servidor por um sistema de processamento de ficheiros assíncrono.

## 8. Dificuldades encontradas
- **Restrição de Infraestrutura e Custos:** A equipe constatou que executar o bot de *scraping* (que exige navegadores em segundo plano e alto consumo de RAM) diretamente no servidor da aplicação tornaria a hospedagem financeiramente inviável. Foi necessário paralisar o endpoint de acionamento automático (#85) para repensar a arquitetura.
- **Gestão de Tempo:** Houve gargalos na conclusão das integrações visuais. Muitas tarefas do Front-end (Jhennifer) e ajustes de UI (Clara) não puderam ser concluídas dentro do prazo estipulado e transitarão para a próxima sprint.

## 9. Revisão do incremento
- **O que foi concluído:** Todas as tarefas de extração essenciais que estavam "Em testes" foram validadas com sucesso (cursos, disciplinas e matrizes). O Back-end entregou as rotas de exportação e os pilares das telas administrativas.
- **O que ficou pendente:** Todas as tarefas listadas com o status "A fazer" ou "Em andamento" na tabela acima (principalmente integrações de interface, extração de horários/turmas e otimização de *queries*).

## 10. Pendências para a próxima sprint
Todas as *tasks* pendentes do Backlog da Sprint 5 serão arrastadas para a **Sprint 6**. Além disso, devido à nova decisão arquitetural, as seguintes tarefas **deverão ser criadas** no planejamento da próxima sprint:

- **[Back-end / DevOps]** Realizar o Deploy da aplicação para deixar o sistema acessível online (Fernando).
- **[Bot Scraping]** Ajustar o código do bot para compactar os arquivos JSON gerados pela raspagem em um único arquivo `.zip` local (Bárbara).
- **[Design]** Modificar a prototipagem da tela de Dados (Admin), substituindo o botão de "Rodar Bot" por um componente de Upload de arquivo `.zip`.
- **[Back-end]** Criar o endpoint de *upload*, capaz de receber o `.zip`, descompactá-lo e orquestrar a inserção dos arquivos JSON no PostgreSQL.
- **[Front-end]** Implementar a lógica de envio do arquivo `.zip` na tela de Administração.
- **[Documentação]** Atualizar os diagramas de arquitetura para refletir o desacoplamento do bot.

## 11. Registros das reuniões
Planning:
<img width="1895" height="918" alt="image" src="https://github.com/user-attachments/assets/dd882bc9-0d09-4f79-a4ae-cbe28ffe4813" />
