## REQUISITOS FUNCIONAIS
### Módulo Público — Estudante
- RF01 — O sistema deve exibir uma landing page com o logotipo, propósito da ferramenta e call-to-action para iniciar a montagem de grade.
- RF02 — O sistema deve guiar o estudante por um fluxo de 3 etapas sequenciais: seleção de curso, matriz curricular e semestre.
- RF03 — O sistema deve impedir o avanço no stepper sem que a etapa atual esteja preenchida.
- RF04 — O sistema deve permitir voltar à etapa anterior sem perder as seleções já feitas.
- RF05 — As opções de curso, matriz e semestre exibidas no stepper devem vir do banco de dados.
- RF06 — O sistema deve exibir todas as matérias de semestres anteriores ao selecionado marcadas como concluídas por padrão.
- RF07 — O sistema deve permitir que o estudante desmarque individualmente as matérias que não concluiu.
- RF08 — O sistema deve manter o estado das seleções caso o estudante retorne à tela de conclusão de matérias.
- RF09 — O sistema deve listar as matérias disponíveis na sidebar separadas por obrigatórias e eletivas.
- RF10 — Cada matéria na sidebar deve exibir código, horário, créditos e número de turmas disponíveis.
- RF11 — O sistema deve permitir filtrar e pesquisar as matérias exibidas na sidebar.
- RF12 — O sistema deve permitir que o estudante arraste ou adicione matérias da sidebar para o calendário semanal.
- RF13 — O sistema deve detectar e sinalizar conflitos de horário ao posicionar uma matéria na grade.
- RF14 — O sistema deve permitir remover uma matéria da grade arrastando-a de volta para a lista ou excluindo pelo modal da matéria.
- RF15 — O sistema deve atualizar o contador de créditos em tempo real conforme matérias são adicionadas ou removidas.
- RF16 — Ao adicionar uma matéria na grade, o sistema deve exibir um card resumo contendo cor da matéria na grade para legenda, código, nome completo, turma escolhida e horário.
- RF17 — O sistema deve permitir exportar uma imagem da grade montada.
- RF18 — O sistema deve permitir exportar os horários selecionados para o Google Agenda.
- RF19 — O sistema deve disponibilizar um botão para visualizar as informações do curso.
- RF20 — O sistema deve disponibilizar um botão para alternar entre diferentes opções de grade.
- RF21 — A tela de montagem deve ser responsiva para mobile e desktop.

### Módulo Administrativo
- RF22 — O sistema deve exigir autenticação via e-mail e senha para acesso ao painel administrativo.
- RF23 — O sistema deve redirecionar o administrador para o Dashboard após login bem-sucedido.
- RF24 — O sistema deve bloquear o acesso e exibir mensagem de erro para credenciais inválidas.
- RF25 — O sistema deve exibir no Dashboard 4 cards: Última Atualização, Total de Acessos, Grades Exportadas e Volume de Dados.
- RF26 — O sistema deve exibir um gráfico de acessos dos últimos 7 dias no Dashboard.
- RF27 — O sistema deve exibir um feed cronológico de atividades recentes no Dashboard.
- RF28 — O sistema deve exibir na tela de Analytics métricas de uso: usuários ativos, sessões, grades montadas, grades exportadas e taxa de conclusão.
- RF29 — O sistema deve exibir gráfico de linha com acessos semanais e gráfico de pizza com matérias mais pesquisadas na tela de Analytics.
- RF30 — O sistema deve exibir as 5 matérias mais pesquisadas e as 5 menos pesquisadas na tela de Analytics.
- RF31 — O sistema deve permitir ao administrador criar, editar e deletar matérias, cursos e horários manualmente.
- RF32 — O sistema deve impedir a deleção de curso que ainda possua matérias vinculadas.
- RF33 — O sistema deve validar conflito de horário no cadastro manual de horários.
- RF34 — O sistema deve paginar as listagens do CRUD com no mínimo 20 itens por página.
- RF35 — O sistema deve permitir ao administrador acionar manualmente a execução dos bots de scraping.
- RF36 — O sistema deve exibir feedback visual durante a execução do bot e log resumido ao final.
- RF37 — O sistema deve registrar todas as ações administrativas no feed de atividades do Dashboard.
- RF38 — O sistema deve atualizar automaticamente o card de Última Atualização no Dashboard após execução do bot.

## REQUISITOS NÃO FUNCIONAIS
### Desempenho
- RNF01 — O sistema deve responder às requisições da API em no máximo 2 segundos em condições normais de uso.
- RNF02 — O sistema deve suportar acessos simultâneos, especialmente em períodos de pico como semana de matrícula.
### Usabilidade
- RNF03 — O sistema deve ser responsivo e utilizável em dispositivos móveis e desktops.
- RNF04 — O fluxo de montagem de grade deve ser concluível sem necessidade de cadastro ou login pelo estudante.
### Segurança
- RNF05 — O painel administrativo deve ser protegido por autenticação JWT.
- RNF06 — As rotas administrativas devem rejeitar requisições sem token válido.
- RNF07 — As senhas dos administradores devem ser armazenadas com hash.
### Disponibilidade
- RNF08 — O sistema deve estar disponível 24/7, com tolerância a falhas dos bots sem derrubar o site.
- RNF09 — Em caso de falha no scraping, o sistema deve continuar operando com os dados da última execução bem-sucedida.
### Manutenibilidade
- RNF10 — O backend deve seguir arquitetura RESTful com endpoints documentados via Swagger/OpenAPI.
- RNF11 — O código deve ser versionado no GitHub com pipeline de CI/CD via GitHub Actions.
### Dados
- RNF12 — Os dados de matérias, cursos e horários devem ser sincronizados com o SIG via bots de scraping periódicos.
- RNF13 — Os eventos de uso (grade montada, exportação, matéria selecionada) devem ser rastreados anonimamente via Google Analytics.

