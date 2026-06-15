# 04. Requisitos

## 1. Levantamento de requisitos
Os requisitos foram identificados e refinados através de observação direta do processo de matrícula no SIG da UFLA, discussões em grupo focadas na dor dos estudantes (dificuldade de visualização e choques de horário) e prototipação contínua. 

Houve um refinamento crítico na fase de arquitetura (Sprint 5/6): a análise de viabilidade técnica demonstrou que a execução do bot de *scraping* no servidor era inviável financeiramente. Como resultado, os requisitos administrativos foram atualizados para refletir um modelo de processamento em lote (Upload de arquivo `.zip` gerado offline) em vez de um acionamento de bot em tempo real.

---

## 2. Requisitos funcionais

### Módulo Público — Estudante
| ID | Requisito funcional | Descrição | Prioridade |
|---|---|---|---|
| RF01 | Landing Page | O sistema deve exibir uma landing page com logotipo, propósito e *call-to-action* para iniciar a montagem. | Alta |
| RF02 | Stepper de Configuração | O sistema deve guiar o estudante em 3 etapas sequenciais: seleção de curso, matriz e semestre. | Alta |
| RF03 | Validação de Etapa | O sistema deve impedir o avanço no stepper sem que a etapa atual esteja preenchida. | Alta |
| RF04 | Navegação do Stepper | O sistema deve permitir voltar à etapa anterior sem perder as seleções já feitas. | Média |
| RF05 | Carregamento Dinâmico | As opções de curso, matriz e semestre devem ser carregadas dinamicamente do banco de dados. | Alta |
| RF06 | Matérias Concluídas (Padrão) | Matérias de semestres anteriores ao selecionado devem aparecer marcadas como concluídas por padrão. | Alta |
| RF07 | Desmarcar Matérias | O sistema deve permitir que o estudante desmarque individualmente matérias não concluídas (ex: reprovações). | Alta |
| RF08 | Manutenção de Estado | O sistema deve manter o estado das seleções caso o estudante retorne à tela de conclusão. | Média |
| RF09 | Listagem na Sidebar | O sistema deve listar as matérias disponíveis na sidebar separadas por categorias (Obrigatórias, Eletivas e Futuras). | Alta |
| RF10 | Detalhamento da Matéria | Cada matéria na sidebar deve exibir código, horário, créditos e turmas disponíveis. | Alta |
| RF11 | Busca e Filtro | O sistema deve permitir filtrar e pesquisar as matérias na sidebar. | Alta |
| RF12 | Drag-and-Drop (Grade) | O estudante deve conseguir arrastar/adicionar matérias da sidebar para o calendário semanal. | Alta |
| RF13 | Prevenção de Conflitos | O sistema deve detectar e sinalizar visualmente conflitos de horário ao posicionar uma matéria. | Alta |
| RF14 | Remoção de Matéria | Deve ser possível remover uma matéria arrastando-a de volta para a lista ou pelo modal. | Alta |
| RF15 | Contador de Créditos | O contador de créditos totais deve atualizar em tempo real ao manipular a grade. | Alta |
| RF16 | Card Resumo de Grade | Ao adicionar a matéria, a grade deve exibir um card com cor de legenda, código, nome, turma e horário. | Alta |
| RF17 | Exportação de Imagem | O sistema deve permitir a exportação da grade montada em formato de imagem (.jpg/.png). | Alta |
| RF18 | Integração Google Agenda | O sistema deve permitir exportar os horários consolidados para o Google Agenda (formato iCal/API). | Alta |
| RF19 | Informações de Montagem | O sistema deve disponibilizar um botão para visualizar as instruções ou informações do curso. | Baixa |
| RF20 | Múltiplas Grades | O sistema deve permitir alternar entre diferentes opções de grade (simulações simultâneas). | Média |
| RF21 | Responsividade | A interface de montagem deve ser responsiva, adaptando interações para mobile e desktop. | Alta |

### Módulo Administrativo
| ID | Requisito funcional | Descrição | Prioridade |
|---|---|---|---|
| RF22 | Autenticação Restrita | O sistema deve exigir login (e-mail e senha) para acesso ao painel de administração. | Alta |
| RF23 | Redirecionamento Pós-Login | O sistema deve direcionar o administrador autenticado diretamente para o Dashboard. | Alta |
| RF24 | Bloqueio de Acesso | O sistema deve bloquear acesso e exibir erro para credenciais inválidas ou cadastros pendentes. | Alta |
| RF25 | Visão Geral (Cards) | O Dashboard deve exibir cards de: Última Atualização, Total Acessos, Grades Exportadas e Volume de Dados. | Média |
| RF26 | Gráfico de Tráfego | O Dashboard deve exibir um gráfico dinâmico com os acessos dos últimos 7 dias. | Média |
| RF27 | Feed de Atividades | O Dashboard deve listar cronologicamente as últimas ações realizadas no banco de dados. | Baixa |
| RF28 | Métricas de Analytics | A tela de Analytics deve exibir usuários ativos, sessões, grades exportadas e taxas de conversão/retenção. | Média |
| RF29 | Gráficos de Engajamento | Analytics deve exibir gráficos de acesso semanal e distribuição de dispositivos (Mobile vs Desktop). | Média |
| RF30 | Ranking de Matérias | O sistema deve listar o ranking dos cursos/matérias mais e menos pesquisados. | Média |
| RF31 | CRUD Acadêmico | O admin deve poder gerenciar (Criar, Editar, Excluir) Cursos, Matrizes, Matérias e Horários. | Alta |
| RF32 | Bloqueio de Deleção | O sistema deve impedir a exclusão de um registro (ex: Curso) se ele possuir dependências ativas (Matrizes/Turmas). | Alta |
| RF33 | Validação de Turmas | O sistema deve validar conflitos e integridade no cadastro manual de turmas e horários. | Alta |
| RF34 | Paginação / Acordeão | O sistema deve organizar a exibição de dados massivos através de listas expansíveis (acordeão) ou paginação. | Alta |
| RF35 | Upload em Lote (.zip) | O sistema deve permitir que o administrador faça o upload de um arquivo `.zip` com os JSONs extraídos do SIG. | Alta |
| RF36 | Feedback de Importação | O sistema deve exibir status de carregamento e um log detalhado (sucessos/erros) após processar o arquivo `.zip`. | Alta |
| RF37 | Auditoria de Ações | O sistema deve registrar inserções manuais ou deleções no feed de atividades. | Média |
| RF38 | Sincronização de Status | A data e horário da "Última Atualização" no Dashboard devem ser atualizados após o sucesso na importação do `.zip`. | Alta |

---

## 3. Requisitos não funcionais
| ID | Requisito não funcional | Descrição | Categoria |
|---|---|---|---|
| RNF01 | Tempo de Resposta | A API deve responder em no máximo 2 segundos sob condições normais. | Desempenho |
| RNF02 | Concorrência | O sistema deve suportar picos de acessos simultâneos durante a semana de renovação de matrícula da UFLA. | Desempenho |
| RNF03 | Mobile-First | As interfaces públicas devem ser totalmente operacionais e visualmente íntegras em dispositivos móveis. | Usabilidade |
| RNF04 | Acesso Aberto (Público) | O fluxo de montagem de grade não deve exigir nenhum tipo de cadastro ou login prévio do estudante. | Usabilidade |
| RNF05 | Tokenização | As rotas administrativas (API) devem ser protegidas por autenticação via *JSON Web Token* (JWT). | Segurança |
| RNF06 | Criptografia de Senha | As senhas dos administradores devem ser guardadas com *hash* no banco de dados. | Segurança |
| RNF07 | Resiliência de Dados | Em caso de falha na importação de um novo `.zip`, a transação deve sofrer *rollback* para manter os dados anteriores íntegros. | Confiabilidade |
| RNF08 | Isolamento de Processo | A extração de dados do SIG (*Scraping*) deve ocorrer *offline* na máquina do administrador, poupando os recursos do servidor web. | Arquitetura |
| RNF09 | Padrão RESTful | O back-end deve expor uma API RESTful documentada seguindo o padrão OpenAPI (Swagger). | Manutenibilidade |
| RNF10 | Rastreamento Anônimo | Eventos de uso devem ser mensurados via Google Analytics de forma anonimizada para popular o Dashboard. | Monitoramento |

---

## 4. Regras de negócio
| ID | Regra | Descrição |
|---|---|---|
| RN01 | Prevenção de Choque | Duas matérias distintas não podem ocupar o mesmo slot de tempo e dia da semana na mesma grade simulada. |
| RN02 | Integridade Referencial | É proibido excluir uma entidade "pai" (ex: Curso ou Matriz) se houver entidades "filhas" (ex: Matérias ou Turmas) atreladas a ela no banco. |
| RN03 | Validação de Pacote | O endpoint de importação só deve aceitar e processar arquivos estritamente com a extensão `.zip` contendo as estruturas JSON mapeadas (`curso.json`, `turma.json`, etc.). |
| RN04 | Progresso Mínimo | Matérias listadas como "Pré-requisito (Progresso)" só são válidas na vida real se o aluno tiver a porcentagem mínima exigida; na simulação, isso atua como aviso visual. |

---

## 5. Critérios de aceitação por funcionalidade
### Funcionalidade: Importação de Dados em Lote (Upload .zip)
- O sistema deve conter uma área na tela de Dados permitindo arrastar ou clicar para selecionar um arquivo.
- O sistema deve rejeitar arquivos que não sejam `.zip`, exibindo um *toast* ou mensagem de erro clara.
- Durante o envio ao servidor, a interface deve ser bloqueada exibindo um *spinner* ou barra de progresso.
- Após o processamento pela API, deve ser exibido um modal com a contagem exata de itens salvos (Cursos, Matrizes, Matérias, Turmas, Horários) e avisos se houver falhas.
- O card de "Última Execução" deve ser atualizado imediatamente com a data e hora do processamento bem-sucedido.

---

## 6. Casos de uso ou cenários
### Caso de uso: Atualização da Base via Scraping Offline
**Atores:** Administrador, Sistema Web (API), Banco de Dados.  
**Objetivo:** Sincronizar o catálogo do SIG UFLA com o banco de dados da aplicação sem executar robôs pesados no servidor web.  
**Fluxo principal:** 1. O Administrador roda o bot em Python na sua máquina local, gerando um pacote `dados_sig.zip`.
2. O Administrador faz login no painel administrativo do GradeUFLA.
3. O Administrador acessa a aba "Dados" e realiza o upload do arquivo `.zip`.
4. O Sistema (Back-end) descompacta o arquivo em memória, lê os JSONs na ordem correta de hierarquia e realiza o *Upsert* (atualização/inserção) no Banco de Dados.
5. O Sistema retorna um relatório de sucesso e atualiza o log de atividades.

**Fluxos alternativos:** - **Erro de integridade do arquivo:** No passo 4, se faltar um arquivo JSON essencial (ex: `curso.json`), o sistema aborta a operação (rollback), não altera nada no banco e retorna um aviso de "Arquivo corrompido ou incompleto" para o administrador no passo 5.

---

## 7. Rastreabilidade
| Problema Resolvido | Backlog (Sprint) | Requisito Relacionado | Regra de Negócio |
|---|---|---|---|
| Inviabilidade financeira de rodar bot no servidor | US09 / Sprint 6 | RF35, RF36, RNF08 | RN03 |
| Dificuldade visual de montar horários | US04 / Sprint 3 | RF12, RF13, RF16 | RN01 |
| Perda de controle da grade durante o semestre | US10 / Sprint 5 | RF17, RF18 | - |
| Falta de métricas de uso da ferramenta | US08 / Sprint 4 | RF28, RF29, RNF10 | - |
