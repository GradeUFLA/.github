# Sprint 3 – Modelagem do Sistema

## 1. Identificação
Número da sprint: 03

Período: 25/04/2026 a 09/05/2026

Data da entrega: 08/05/2026

## 2. Objetivo da sprint:
Representar a solução do sistema gradeUFLA por meio de modelos estruturais, comportamentais e de dados que auxiliem a compreensão arquitetural e apoiem as decisões de desenvolvimento da equipe para as próximas etapas.

## 3. Itens do Sprint Backlog:

| Planejado | Demanda (Task) | Tamanho | Situação |
| :---: | :--- | :---: | :--- |
| Sim | Modelagem de dados #18 | 5 | Concluído |
| Sim | Estudos em python #19 | 5 | Em progresso |
| Sim | Design: Tela de Montagem de grade #25 | 13 | Concluído |
| Sim | Front-end: Stepper de configuração #32 | 2 | Concluído |
| Sim | Back-end: Stepper de configuração #33 | 2 | Concluído |
| Sim | Front-end: Tela de conclusões de matérias #34 | 3 |  Concluído |
| Sim | Back-end: Tela de Conclusões de matérias #35 | 3 |  Concluído |
| Sim | Back-end: Tela de Montagem de Grade #37 | 13 |  Concluído |
| Sim | Design: Login de usuário - admin #38 | 2 |  Concluído |
| Sim | Criação dos scripts do banco de dados #52 | 3 |  Concluído |
| Sim | Criar documentação #53 | - |  Concluido |
| Sim | Diagrama de Casos de Uso para representar as funcionalidades principais #54 | - |  Concluído |
| Sim | Diagrama de Componentes para representar a estrutura da aplicação web #55 | - |  Concluído |
| Sim | Modelo de Dados para representar entidades e relacionamentos principais #56 | - |  Concluído |
| Sim | Diagrama de Sequência para representar um fluxo central do sistema #57 | - |  Concluído |
| Sim | Texto explicativo relacionando os modelos aos requisitos levantados #58 | - | Concluído |
| Sim | Atualização do backlog com refinamentos identificados durante a modelagem #59 | - |  Concluído |

## 4. Relação com o conteúdo da disciplina
Esta sprint esteve diretamente alinhada aos conceitos de Engenharia de Requisitos e Modelagem de Sistemas. Aplicamos na prática a criação de diagramas UML (Casos de Uso, Componentes e Sequência) e a elaboração do Modelo Entidade-Relacionamento (MER) para transpor os requisitos funcionais levantados na Sprint 2 para uma visão arquitetural e técnica, definindo como os módulos (Frontend, API Spring Boot e Bot Python) irão se comunicar.

## 5. Artefatos produzidos
Documentação dos Diagramas UML (Casos de Uso, Componentes e Sequência).

Modelo Entidade-Relacionamento (MER) do banco de dados.

Scripts SQL iniciais do banco de dados.

Protótipo de alta fidelidade (Design) da Tela de Montagem de Grade.

Melhoria de Processo: Implementação de Issue Templates no GitHub (bug-report.md, sprint-task.md, user-story.md) pelo Scrum Master para padronização das demandas.

Crud de todas as tabelas da área pública do sistema.

Front-end das telas inicias do sistema.


## 6. Evidências no GitHub
Arquivos criados/atualizados: sprint-03.md, diagramas anexados (imagens), scripts de banco e arquivos .yml / .md na pasta .github/ISSUE_TEMPLATE.

Commits relevantes: Commits vinculados às issues de documentação técnica e criação de templates de issues. Commits relacionados ao banco de dados. Commits relacionados ao Back-end. Commits relacionados ao front-end. 


## 7. Evolução da aplicação web
A evolução nesta sprint foi majoritariamente arquitetural. O desenvolvimento da base de código avançou com a criação das telas de "Montagem de Grade" no design e a estruturação inicial das áreas públicas do sistema (Back-end) pelo desenvolvedor Fernando. A prototipação (Front-end) seguiu sendo implementada pela Jhennifer, e o banco de dados já possui seus scripts de criação validados, preparando o terreno para a codificação pesada da próxima sprint.

## 8. Dificuldades encontradas
A principal dificuldade da equipe de forma geral foi o gerenciamento de tempo, devido ao acúmulo de demandas com outras disciplinas. De forma específica:

Bárbara: Enfrentou limitações de tempo que atrasaram seus estudos e provas de conceito com a linguagem Python (necessária para o Bot).

Jhennifer: Enfrentou desafios técnicos relacionados à estilização (CSS/Componentes) das telas no Front-end, o que impactou o tempo planejado, embora as soluções já estejam encaminhadas.

Fernando: Sofreu com problemas técnicos e lentidão na ferramenta de IA (Copilot do IntelliJ), o que diminuiu sua produtividade e aumentou o tempo necessário para codificar a área pública do Back-end.

## 9. Revisão do incremento

O que foi concluído: A equipa teve um avanço na reta final e conseguiu entregar a grande maioria do planeamento. Toda a etapa de modelagem de software (MER, Casos de Uso, Sequência e Componentes) e a criação dos scripts da base de dados foram entregues. No desenvolvimento da aplicação, foram totalmente concluídas as implementações de Front-end e Back-end para o "Stepper de configuração" e para a "Tela de conclusões de matérias". O Back-end da "Tela de Montagem de Grade" também foi finalizado. Na área de Design, concluímos as telas de Montagem de Grade e o Login de Administrador. Adicionalmente, o Scrum Master finalizou a padronização do repositório (Issue Templates) e a atualização do backlog.

O que ficou pendente: Apenas a tarefa de "Estudos em Python" (#19) permanece em progresso. Esta pendência deve-se à necessidade de um tempo de estudo mais aprofundado para garantir a construção correta do bot de extração (scraping). Esta tarefa irá transitar para o backlog da próxima sprint.

## 10. Pendências para a próxima sprint
Além de carregar as tarefas listadas como "Em desenvolvimento" e "A Fazer" do backlog atual, as seguintes pendências foram adicionadas para a próxima sprint com base na modelagem:

[Banco de Dados] Bárbara fará uma modificação no Modelo de Dados para adicionar os campos "Número de semestres" e "Matriz curricular".

[Back-end] Desenvolver o contrato da API (Swagger/OpenAPI) para os endpoints do Diagrama de Sequência.

[Bot/Scraping] Desenvolver a Prova de Conceito (PoC) em Python para extrair dados de uma matriz do SIG.


Registros das reuniões:

