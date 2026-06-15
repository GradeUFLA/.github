## 1. Visão geral
O Product Backlog reúne as funcionalidades, necessidades e melhorias da solução proposta, incluindo todas as histórias de usuários, subtarefas técnicas (Front-end, Back-end, Banco de Dados, Design) e itens de documentação mapeados pela equipe.

## 2. Estratégia de priorização
A priorização foi estabelecida dividindo as entregas em Sprints (1 a 6). Itens de documentação e definições de arquitetura/design foram priorizados nas primeiras sprints (1 a 3), seguidos do desenvolvimento central da aplicação (Sprints 3 a 5) e finalizando com fechamentos, integrações, refinamentos e deploy na Sprint 6. As estimativas (Story Points) foram pontuadas com base na complexidade técnica de cada tarefa.

---

## 3. Backlog do produto

| ID | Tipo | Item do backlog | Descrição / História de Usuário | Prioridade | Critérios de aceitação | Estimativa | Sprint prevista |
|---|---|---|---|---|---|---|---|
| #5 | Documentação | Planning Sprint 1 | Planejamento inicial. | Alta | - | 2 pts | Sprint 1 |
| #4 | Documentação | Escrever sprint-01.md | Documentação da primeira sprint. | Alta | - | 2 pts | Sprint 1 |
| #6 | Front-End | Definição da stack que será usada no frontend | Escolha de tecnologias do front. | Alta | - | 2 pts | Sprint 1 |
| #20 | História de Usuário | [US01] Hero - tela inicial | Como estudante da UFLA, quero acessar a página inicial do GradeUFLA e entender o propósito da ferramenta, para ter um ponto de entrada claro e intuitivo que me direcione ao fluxo de montagem de forma simples. | Alta | • A seção "Hero" deve carregar corretamente o logotipo e texto explicativo.<br>• Deve exibir botão principal em destaque.<br>• O clique não deve exigir login prévio.<br>• Layout responsivo (mobile, tablet, desktop).<br>• Deverá possuir informações de como montar a grade. | 2 pts | Sprint 2 |
| #8 | Design | Design: Hero - Tela inicial | Interface da tela inicial. | Alta | - | 2 pts | Sprint 2 |
| #22 | Front-End | Front-End: Hero - Tela inicial | Desenvolvimento visual inicial. | Alta | - | 2 pts | Sprint 2 |
| #9 | História de Usuário | [US02] Stepper de Configuração - Aluno | Como estudante da UFLA, quero selecionar meu curso, matriz curricular e semestre atual em um fluxo guiado, para que o sistema saiba quais matérias me apresentar e a experiência seja sem ambiguidade. | Alta | • Fluxo dividido em 3 etapas sequenciais.<br>• Botão "Avançar" desabilitado até que uma opção seja selecionada.<br>• Botão "Voltar" permite corrigir seleções sem perder dados anteriores.<br>• Listagens carregadas via API.<br>• Componente responsivo indicando a etapa atual. | 2 pts | Sprint 5 |
| #27 | Design | Design: Stepper de Configuração | Interface do stepper. | Alta | - | 2 pts | Sprint 2 |
| #32 | Front-End | Front-end: Stepper de configuração | Implementação do front. | Alta | - | 2 pts | Sprint 3 |
| #33 | Back-End | Back-end: Stepper de configuração | Lógica e API do stepper. | Alta | - | 2 pts | Sprint 3 |
| #67 | Front-End | Integração: Stepper e tela de matérias concluídas | Unir fluxo no front-end. | Alta | - | - | Sprint 5 |
| #10 | História de Usuário | [US03] Tela de Conclusão de Matérias - Aluno | Como estudante da UFLA, quero visualizar todas as matérias anteriores ao meu semestre marcadas como concluídas e desmarcar as que ainda não fiz, para que o sistema monte minha grade considerando apenas as matérias que ainda preciso cursar. | Alta | • Matérias de semestres anteriores marcadas como concluídas por padrão.<br>• Estudante consegue desmarcar as que não concluiu.<br>• Botão de confirmação claro para avançar.<br>• Estado das seleções deve ser mantido ao avançar/voltar. | 3 pts | Sprint 6 |
| #26 | Design | Design: Tela de Conclusão de Matérias | Protótipo visual. | Alta | - | 3 pts | Sprint 2 |
| #34 | Front-End | Front-end: Tela de conclusões de matérias | Implementação front-end. | Alta | - | 3 pts | Sprint 3 |
| #35 | Back-End | Back-end: Tela de Conclusões de matérias | Implementação back-end. | Alta | - | 3 pts | Sprint 3 |
| #65 | Banco de Dados | Banco de dados : Validar se a relação entre as tabelas disciplina e matriz possui a informação de qual semestre a matéria pertence. | Validação de relações. | Alta | - | 0 pts | Sprint 5 |
| #90 | Front-End | Integração: Tela de conclusões de matérias | Conectar front e back. | Alta | - | - | Sprint 6 |
| #11 | História de Usuário | [US04] Tela de Montagem da Grade - Aluno | Como estudante da UFLA, quero visualizar as matérias disponíveis para o meu semestre e adicioná-las a um calendário semanal, para que eu possa planejar intuitivamente sem precisar consultar o SIG e identificar conflitos de horário. | Alta | • Sidebar lista matérias por categorias.<br>• Matéria exibe código, nome, horário, créditos e turmas.<br>• Permitir filtrar e pesquisar.<br>• Arrastar/adicionar na grade.<br>• Sinalizar visualmente conflitos de horário.<br>• Remover arrastando/excluindo.<br>• Contador de créditos em tempo real.<br>• Botão exportar imagem.<br>• Botão compartilhar.<br>• Botão informações/ajuda.<br>• Alternar opções de grade (até 3).<br>• Resumo completo no card adicionado.<br>• Totalmente responsiva (drag/clique). | 13 pts | Sprint 6 |
| #25 | Design | Design: Tela de Montagem de grade | Protótipo da grade interativa. | Alta | - | 13 pts | Sprint 3 |
| #36 | Front-End | Front-end: Tela de Montagem de grade | Lógica visual da grade. | Alta | - | 13 pts | Sprint 6 |
| #37 | Back-End | Back-end: Tela de Montagem de Grade | Regras de negócio da grade. | Alta | - | 13 pts | Sprint 3 |
| #69 | Banco de Dados | Banco de dados: Validar as consultas (queries) para otimizar o tempo de resposta na busca de horários e turmas ativas.| Otimização de busca. | Alta | - | - | Sprint 5 |
| #68 | Front-End | Integração: tela montagem de grade | Integração de dados. | Alta | - | - | Sprint 6 |
| #31 | História de Usuário | [US05] Modelagem da Base de Dados e uso de Python | Como desenvolvedor do time, eu quero modelar o banco de dados usando o mysql workbench para fazer o modelo relacional/lógico e dicionário de dados, e dominar extração Python para atualizar dados do SIG. | Alta | - | 5 pts | Sprint 3 |
| #18 | Banco de Dados | Modelagem de dados | Criação do modelo ER. | Alta | - | 5 pts | Sprint 3 |
| #19 | Banco de Dados | Estudos em python | Capacitação para scraping. | Média | - | 5 pts | Sprint 3 |
| #52 | Banco de Dados | Criação dos scripts do banco de dados | Scripts SQL. | Alta | - | 3 pts | Sprint 3 |
| #17 | Back-End | Estudos da arquitetura - Backend | Definição de arquitetura. | Média | - | 2 pts | Sprint 2 |
| #7 | Design | Definição da Identidade Visual | Cores, tipografia, logo. | Alta | - | 0 pts | Sprint 2 |
| #13 | História de Usuário | [US06] Login de Usuário - Administrador | Como administrador ou candidato, quero acessar o sistema ou solicitar meu cadastro, para realizar ações exclusivas de gestão de forma segura, mediante aprovação prévia. | Alta | • Campos de e-mail e senha visíveis.<br>• Valida registros ativos no DB.<br>• Link/botão "Solicitar acesso".<br>• Coleta de dados (Nome, E-mail, Senha) status Pendente.<br>• Bloqueia dados incorretos com erro amigável.<br>• Bloqueia login com status pendente.<br>• Redireciona para Dashboard após login ativo.<br>• Link de recuperação de senha. | 2 pts | Sprint 6 |
| #38 | Design | Design: Login de usuário - admin | Tela de login. | Média | - | 2 pts | Sprint 3 |
| #39 | Front-End | Front-end: Login de Usuário - Admin | Desenvolvimento tela login. | Média | - | 2 pts | Sprint 6 |
| #40 | Back-End | Back-end: Login de Usuário - Admin | Autenticação e JWT. | Alta | - | 2 pts | Sprint 4 |
| #66 | Front-End | Integração: tela de login | Integração front e back. | Alta | - | - | Sprint 6 |
| #14 | História de Usuário | [US07] Tela de Dashboard - Administrador | Como administrador cadastrado, quero visualizar estatísticas, gráfico de acessos e log de atividades, para visualizar as métricas de engajamento e a integridade dos dados extraídos do SIG. | Média | • Acessível via rota protegida (JWT).<br>• 4 cards no topo (Última Atualização, Acessos, Grades, Volume).<br>• Gráfico de visitas dos últimos 7 dias.<br>• Feed cronológico de atividades recentes do banco. | 13 pts | Sprint 6 |
| #41 | Design | Design: Tela de Dashboard - Admin | Protótipo Dashboard. | Média | - | 13 pts | Sprint 4 |
| #42 | Front-End | Front-end: Tela de Dashboard - Admin | Implementação visual. | Média | - | 13 pts | Sprint 6 |
| #43 | Back-End | Back-end: Tela de Dashboard - admin | API do dashboard. | Média | - | 13 pts | Sprint 5 |
| #70 | Banco de Dados | Banco de dados: Escrever as consultas (queries) otimizadas... | Queries para Dashboard. | Média | - | - | Sprint 5 |
| #74 | Front-End | Integração: Tela de Dashboard - Admin | Integração front e back. | Média | - | - | Sprint 6 |
| #15 | História de Usuário | [US08] Tela de Analytics - Administrador | Como administrador cadastrado, quero visualizar métricas detalhadas de uso, identificar quais funcionalidades geram valor, detectar engajamento e embasar decisões de melhoria. | Média | • Exibir usuários ativos.<br>• Sessões no semestre.<br>• Grades exportadas (detalhando img/agenda).<br>• Gráfico evolução 7 dias.<br>• Gráfico cursos pesquisados.<br>• Proporção Mobile vs Desktop.<br>• Status e execução do bot.<br>• Ranking cursos (mais/menos).<br>• Totais absolutos do banco.<br>• KPI grades montadas.<br>• Taxa de conclusão (funil).<br>• Taxa de retenção. | 8 pts | Sprint 6 |
| #44 | Design | Design: Tela de Analytics - Admin | Protótipo Analytics. | Média | - | 8 pts | Sprint 4 |
| #45 | Front-End | Front-end: Tela de Analytics - Admin | Telas de gráficos. | Média | - | 8 pts | Sprint 6 |
| #46 | Back-End | Back-end: Tela de analytics - admin | Dados para gráficos. | Média | - | 8 pts | Sprint 5 |
| #75 | Front-End | Integração: Tela de Analytics - Administrador | Consumo de dados. | Média | - | - | Sprint 6 |
| #16 | História de Usuário | [US09] Tela de Dados - Administrador | Como administrador, quero gerenciar o catálogo (cursos, matrizes e horários) e realizar importação do arquivo .zip, para corrigir inconsistências e atualizar o sistema sem depender de execuções no servidor. | Alta | • Importação .zip: Aceitar apenas zip, feedback de upload/sucesso, modal de detalhes.<br>• Navegação: Lista expansível (Cursos > Matrizes > Matérias c/ dependências).<br>• CRUD Global: Matérias, Cursos, Matrizes.<br>• Vínculos dinâmicos de matérias e requisitos (Forte/Mínimo/Co).<br>• Oferta Turmas: Simultâneo c/ dias e horários.<br>• Exclusão/Segurança: Bloqueio da exclusão se possuir dependências. | 40 pts | Sprint 6 |
| #47 | Design | Design: Tela de dados - admin | Interface de tabelas admin. | Média | - | 40 pts | Sprint 4 |
| #48 | Front-End | Front-end: Tela de dados - Admin | Front para gestão. | Alta | - | 40 pts | Sprint 6 |
| #49 | Back-End | Back-end: Tela de dados - admin | CRUD de administração. | Alta | - | 40 pts | Sprint 5 |
| #76 | Front-End | Integração: Tela de Dados - Administrador | Conexão front e API. | Alta | - | - | Sprint 6 |
| #12 | História de Usuário | [US10] Upload da grade | Como estudante da UFLA, quero exportar minha grade para o Google Agenda e/ou fazer o download em imagem (.jpg), para acessar meu horário facilmente no dia a dia. | Alta | • Botão funcional para Imagem (.jpg).<br>• Botão funcional para Google Agenda.<br>• Imagem com visualização completa, cores, horários e disciplinas.<br>• Exportação Google Agenda preenche datas/horas corretamente.<br>• Funcional em desktop e mobile. | 5 pts | Sprint 6 |
| #97 | Front-End | Exportar grade para o google agenda | Integração de API client. | Alta | - | - | Sprint 6 |
| #30 | Back-End | Exportar a grade para o Google Agenda | Lógica de iCal/Google. | Alta | - | 5 pts | Sprint 5 |
| #51 | Front-End | Exportar a grade em .jpg | Gerar imagem canvas. | Média | - | 5 pts | Sprint 6 |
| #24 | Documentação | Sprint 02 - Planning | Registro do planning. | Média | - | - | Sprint 2 |
| #53 | Documentação | Criar documentação | Tarefa geral do PO. | Média | - | - | Sprint 3 |
| #54 | Documentação | Diagrama de Casos de Uso para representar as funcionalidades principais | Diagrama UML. | Média | - | - | Sprint 3 |
| #55 | Documentação | Diagrama de Componentes para representar a estrutura da aplicação web | Diagrama estrutural. | Média | - | - | Sprint 3 |
| #56 | Documentação | Modelo de Dados para representar entidades e relacionamentos pri cipais| Diagrama DER. | Média | - | - | Sprint 3 |
| #57 | Documentação | Diagrama de Sequência para representar um fluxo central do sistema | Diagrama comportamental. | Média | - | - | Sprint 3 |
| #58 | Documentação | Texto explicativo relacionando os modelos aos requisitos levantados | Descritivo de UML. | Média | - | - | Sprint 3 |
| #59 | Documentação | Atualização do backlog com refinamentos identificados durante a modelagem | Refinamento. | Média | - | - | Sprint 3 |
| #61 | Back-End | Configurar o banco de dados PostgreSQL em ambiente de nuvem para acesso compartilhado da equipe | Setup DB Cloud. | Cancelada | - | - | Sprint 6 |
| #63 | Back-End | Desenvolver e documentar o contrato da API (Swagger/OpenAPI) para os endpoints levantados no Diagrama de Sequência | Documentação de API. | Alta | - | - | Sprint 4 |
| #64 | Scraping-bot | Desenvolver uma Prova de Conceito (PoC) em Python para extrair dados de uma matriz curricular do SIG e inserir no banco PostgreSQL, validando o modelo de dados. | Teste de extração SIG. | Alta | - | - | Sprint 5 |
| #73 | Documentação | Criar Documentação sprint 4 | Relatório de Sprint. | Média | - | - | Sprint 4 |
| #77 | História de Usuário | [US11] Criação de um bot para coleta de dados (Scraping) | Como administrador do sistema, quero que um bot extraia automaticamente os dados acadêmicos do SIG, para garantir informações de cursos, grades e turmas precisas e atualizadas. | Alta | • Permitir upload estritamente de arquivos .zip.<br>• Validar estrutura interna (.json esperados).<br>• Rejeitar formatos inválidos e exibir erro claro. | - | Sprint 6 |
| #78 | Scraping-bot | Mapeamento de cursos no SIG | Análise de DOM do SIG. | Alta | - | - | Sprint 5 |
| #79 | Scraping-bot | Extração de matrizes curriculares | Coleta de dados. | Alta | - | - | Sprint 5 |
| #80 | Scraping-bot | Extração de disciplinas e relacionamento com matriz curricular | Estruturação dados bot. | Alta | - | - | Sprint 5 |
| #81 | Scraping-bot | Extração de pré-requisitos | Coleta regras. | Alta | - | - | Sprint 5 |
| #82 | Scraping-bot | Extração de turmas | Coleta turmas abertas. | Alta | - | - | Sprint 5 |
| #83 | Scraping-bot | Extração de horários | Relacionamento de horas. | Alta | - | - | Sprint 5 |
| #84 | Front-End | Integração: Integrar o botão de acionamento manual do bot | Botão UI. | Cancelada | - | - | Sprint 6 |
| #85 | Back-End | Back-end: Criar o endpoint de integração que aciona o script... | Endpoint executor. | Cancelada | - | - | Sprint 5 |
| #95 | Scraping-bot | Otimizar o bot | Melhoria de performance. | Alta | - | - | Sprint 6 |
| #96 | Scraping-bot | Implementar rotina de salvamento de estado do bot | Logs e checkpoint. | Alta | - | - | Sprint 5 |
| #98 | Scraping-bot | Ajustar o código do bot para compactar os arquivos JSON | Minificação de dados. | Média | - | - | Sprint 6 |
| #89 | Documentação | Atualização dos modelos ou diagramas | Revisão UML final. | Média | - | - | Sprint 6 |
| #91 | Design | Melhorias no design baseadas nos comentários | Refinamento UI. | Média | - | - | Sprint 6 |
| #92 | Design | Pop-up compartilhar grade | UI de compartilhamento. | Média | - | - | Sprint 6 |
| #93 | Design | Responsividade para telas mobile - Telas públicas | Ajustes CSS mobile. | Alta | - | - | Sprint 6 |
| #94 | Documentação | Redigir o texto explicativo de "Modo de usar o sistema" para os usuários | Copywriting. | Média | - | - | Sprint 5 |
| #99 | Back-End | Realizar o Deploy da aplicação para deixar o sistema acessível online | Deploy. | Alta | - | - | Sprint 6 |
| #100 | Design | Modificar o protótipo da tela de Dados (Admin) | Atualização visual. | Média | - | - | Sprint 6 |
| #101 | Back-End | Endpoint upload .zip - Tela de dados (Admin) | Rota de importação. | Alta | - | - | Sprint 6 |
| #102 | Front-End | Implementar a lógica de envio do arquivo .zip na tela de administração| Envio multipart. | Alta | - | - | Sprint 6 |
| #103 | Documentação | Atualizar toda a documentação para o novo modelo de tratamento do bot | Doc do bot final. | Alta | - | - | Sprint 6 |
| #104 | Documentação | Documentação - Entregas_incrementais | Fechamento disciplinas. | Alta | - | - | Sprint 6 |
| #105 | Documentação | Documentação - Apresentação | Slides de defesa. | Alta | - | - | Sprint 6 |
| #106 | Documentação | relatório sprint 06 | Ata e review final. | Alta | - | - | Sprint 6 |
| #108 | Documentação | Gravação do vídeo para apresentação - youtube | Mídia de entrega. | Alta | - | - | Sprint 6 |

---

## 4. Exemplo de história de usuário
**Como** estudante da UFLA, **quero** acessar a página inicial do GradeUFLA e entender o propósito da ferramenta, **para** ter um ponto de entrada claro e intuitivo que me direcione ao fluxo de montagem de forma simples.

**Critérios de aceitação**
- A seção "Hero" deve carregar corretamente o logotipo do GradeUFLA e um texto explicativo claro sobre o sistema.
- Deve exibir um botão principal (Call-to-Action) em destaque para "Iniciar a montagem".
- O clique no botão principal não deve exigir nenhum tipo de login ou autenticação prévia.
- O layout da tela inicial deve ser responsivo (adaptável para celular, tablet e desktop).

**Tarefas Técnicas (Sub-tasks)**
Checklist prático de implementação (Front-end, Back-end, Banco, Design).
- [Design] Desenhar o protótipo de alta fidelidade da tela inicial (seção Hero) no Figma (Desktop e Mobile).
- [Front-end] Desenvolver o componente da seção Hero utilizando as variáveis de estilo (cores e tipografia) do projeto.
- [Back-end] N/A - Tela estática, não requer consumo de API neste momento.
- [Banco de Dados] N/A.

**Observações**
Esta história atende ao requisito RF01 (O sistema deve exibir uma landing page com o logotipo, propósito da ferramenta e call-to-action).
Foco total em reduzir a carga cognitiva no primeiro contato do estudante com a ferramenta.

---

## 5. Observações
- O backlog é dinâmico.
- Mudanças devem ser justificadas e registradas.
- Itens concluídos devem manter histórico.
