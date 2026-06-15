# Sprint 3 – Modelagem do Sistema

## 1. Identificação da entrega

**Sprint:** 3  
**Título:** Modelagem do Sistema  
**Pontuação:** 4,0 pontos  
**Objetivo:** Representar o **gradeUFLA** por meio de modelos técnicos e visuais que auxiliem a compreensão do sistema, apoiem as decisões de desenvolvimento da aplicação web e reduzam riscos arquiteturais antes da fase de codificação.

---

## 2. Descrição do sistema

O gradeUFLA é uma ferramenta desenvolvida para os estudantes da Universidade Federal de Lavras (UFLA), para que durante o período de planejamento de matrículas, consigam simular grades de forma rápida e intuitiva. Ao final, poderão baixar uma versão .png da sua grade ou fazer uma vinculação com a sua Agenda do Google.

### 2.1. Visão geral do sistema

A aplicação é uma ferramenta web dedicada à simulação e visualização de grades horárias de alunos da UFLA. A ideia é que seja um sistema sem necessidade de login por parte do usuário, permitindo que qualquer estudante acesse os dados das turmas e monte o seu horário ideal de forma instantânea. O sistema consome dados do SIG-UFLA através de um processo de ingestão em lote, utilizando arquivos `.zip` gerados por um bot de extração *offline*.

### 2.2. Objetivo da solução

O objetivo principal do gradeUFLA é diminuir a dificuldade durante o processo de montagem da grade semestral. A solução visa:
- Proporcionar uma ferramenta de simulação que facilite a tomada de decisão do aluno antes da matrícula oficial.
- Permitir a exportação da grade planejada em formato de imagem, ou vincular diretamente na agenda do Google.

### 2.3. Perfis de usuário

- **Usuário (Estudante):** Consulta disciplinas e turmas disponíveis por curso e período, adiciona ou remove turmas numa grade horária interativa para simular o seu semestre, visualiza conflitos de horários, exporta o resultado final da simulação.
- **Administrador:** Realiza autenticação segura, monitora métricas de uso e engajamento dos alunos através de *analytics*, realiza o upload de arquivos `.zip` para atualização em massa da base de dados acadêmica e gerencia manualmente dados de disciplinas ou turmas em caso de inconsistências.

---

## 3. Entregas da Sprint 3

1. **Diagrama de Casos de Uso** para representar as funcionalidades principais.
2. **Diagrama de Componentes** para representar a estrutura da aplicação web.
3. **Modelo de Dados** para representar entidades e relacionamentos principais.
4. **Diagrama de Sequência** para representar um fluxo central do sistema.
5. **Texto explicativo** relacionando os modelos aos requisitos levantados.
6. **Atualização do backlog** com refinamentos identificados durante a modelagem.

---

## 4. Requisitos relacionados

### Requisitos funcionais

Relacionados à Interação do Estudante (Casos de Uso e Sequência):

- RF02: O sistema deve guiar o estudante por um fluxo de 3 etapas sequenciais: seleção de curso, matriz curricular e semestre.
- RF06 / RF07: O sistema deve exibir matérias anteriores concluídas e permitir desmarcá-las.   
- RF12: O sistema deve permitir que o estudante adicione matérias para o calendário semanal.  
- RF13: O sistema deve detectar e sinalizar conflitos de horário ao posicionar uma matéria na grade. 
- RF17 / RF18: O sistema deve permitir exportar imagem da grade montada ou para o Google Agenda.

Relacionados à Gestão e Banco de Dados (Casos de Uso, Componentes e MER):

- RF22: O sistema deve exigir autenticação via e-mail e senha para acesso ao painel administrativo.  
- RF28: O sistema deve exibir na tela de Analytics métricas de uso.   
- RF31: O sistema deve permitir ao administrador criar, editar e deletar matérias, cursos e horários manualmente. 
- RF35: O sistema deve permitir que o administrador faça o upload de um arquivo `.zip` com os JSONs extraídos do SIG.
- RF37: O sistema deve registrar todas as ações administrativas no feed de atividades.

### Requisitos não funcionais

- RNF04: O fluxo de montagem de grade deve ser concluível sem necessidade de cadastro ou login pelo estudante.  
- RNF05: O painel administrativo deve ser protegido por autenticação JWT.  
- RNF08: A extração de dados do SIG (*Scraping*) deve ocorrer *offline* na máquina local do administrador, poupando recursos do servidor web.
- RNF10: O backend deve seguir arquitetura RESTful com *endpoints* documentados via OpenAPI (Swagger).

---

## 5. Vínculo entre requisitos e modelos

| Requisito | Modelo relacionado | Justificativa |
| :--- | :--- | :--- |
| **RF01 – Visualizar grades filtradas** | Casos de Uso / Protótipo / Modelo de Dados | Mostra a interação do estudante com a interface visual e a estrutura relacional de busca no banco. |
| **RF02 – Montar horário interativo** | Casos de Uso / Sequência / Protótipo | Representa o fluxo principal do aluno, detalhado passo a passo no diagrama de sequência. |
| **RF03 – Exportar horário (PDF/Imagem)** | Casos de Uso / Protótipo | Ação de entrega de valor final do ator Estudante, tangibilizada nas telas do Figma. |
| **RF04 – Acesso público sem login** | Casos de Uso / Componentes | Evidencia que o ator "Estudante" não possui ligação com a API de Autenticação. |
| **RF05 – Autenticação para administradores** | Casos de Uso / Componentes / Modelo de Dados | Mostra a segurança via API REST (Backend) e a tabela `admin` no banco de dados. |
| **RF06 – CRUD Administrativo** | Casos de Uso / Modelo de Dados | Representa as ações de manutenção do PO/Admin e define as entidades que podem ser alteradas (Cursos, Turmas). |
| **RF07 – Painel de Analytics e Logs** | Casos de Uso / Modelo de Dados | Representado pela ação de visualização gerencial e estruturado nas tabelas de `log` do sistema. |
| **RNF01 – API Backend (Java/Spring)** | Componentes | Evidencia o isolamento das rotas de negócio em um servidor de aplicação dedicado. |
| **RNF02 – Banco PostgreSQL** | Modelo de Dados / Componentes | Base tecnológica que fundamentou a criação do Modelo Entidade-Relacionamento (MER). |
| **RNF08 – Isolamento de Processo (Bot)** | Componentes | Ilustra o script em Python rodando localmente (*offline*), gerando os dados em pacote antes da interação manual via upload no painel web. |
| **RNF04 – Interface Mobile-First / IHC** | Protótipo de Interface | Justifica o design adotado nas telas de alta fidelidade para garantir baixa carga cognitiva. |
| **RNF05 – Deploy Desacoplado** | Componentes | O diagrama estrutural confirma a separação do Frontend (Netlify) e Backend (Koyeb/Heroku). |

---

## 6. Diagramas em PlantUML / Imagens

### 6.1. Diagrama de Casos de Uso

![Diagrama de Casos de Uso](https://github.com/user-attachments/assets/2014db3e-6868-4d20-a8e2-ef4fe480171a)

<img width="421" height="708" alt="Image" src="https://github.com/user-attachments/assets/b4166fc6-4d9e-4ab4-b839-702803c9bc66" />

### 6.2. Diagrama de Componentes

<img width="747" height="748" alt="image" src="https://github.com/user-attachments/assets/83022fd8-f378-40a0-99ae-442aa6d5b9f0" />

### 6.3. Modelo de Dados

<img width="1486" height="842" alt="Untitled" src="https://github.com/user-attachments/assets/7184f8bb-d998-4ee3-9a6a-74415654affd" />

### 6.4. Diagrama de Sequência

![Diagrama Sequencia](https://github.com/user-attachments/assets/a12861bc-fbd6-45b6-8743-659a8aa8411a)

---

## 7. Descrição textual complementar dos modelos

### 7.1. Casos de uso

Os diagramas de casos de uso evidenciam dois atores do sistema:

**Estudante:** Focado no consumo da plataforma. Suas ações refletem o fluxo de montagem do horário, desde a configuração inicial (seleção de curso/matriz) até a interação com a grade (visualização de conflitos, montagem) e a exportação do resultado (Google Agenda ou imagem). **Não há necessidade de login para este ator.**

**Administrador:** Focado na gestão e manutenção do sistema. Suas ações exigem autenticação prévia e englobam a visualização de métricas (dashboard, analytics), o gerenciamento pontual de dados (CRUD) e a importação massiva do catálogo acadêmico via upload do pacote `.zip` gerado pelo bot.

### 7.2. Componentes
O diagrama de componentes ilustra a arquitetura física e lógica da aplicação, destacando a separação de responsabilidades para evitar sobrecarga no servidor:

- **Frontend Web (React):** Interface do usuário dividida em módulos para o Estudante e para o Administrador, rodando no navegador.
- **Máquina Local do Administrador (Python):** Script executado *offline* para realizar o web scraping no SIG da UFLA. A extração gera um arquivo compactado (`.zip`) contendo todas as estruturas acadêmicas mapeadas em formato JSON.
- **Backend API (Spring Boot):** Servidor centralizado que expõe rotas REST. Ele gerencia a autenticação, atende às consultas do módulo público e atua como orquestrador da importação: recebe o upload do `.zip`, descompacta em memória e insere os dados de forma transacional.
- **Banco de Dados (PostgreSQL):** Centraliza as informações processadas pela API para o funcionamento de toda a aplicação.

### 7.3. Modelo de dados
O Modelo Entidade-Relacionamento detalha a estrutura relacional do banco de dados.

- **Dados Acadêmicos:** A separação entre as entidades curso, disciplina, turma e horário garante que os dados estáticos (matérias) não entrem em conflito com os dados dinâmicos (turmas e vagas oferecidas em cada semestre). O modelo também prevê tabelas associativas para lidar com pré-requisitos e matrizes curriculares (disciplina_curso).
- **Gestão:** As tabelas admin e log garantem a segurança do painel administrativo, registrando quem acessou e quais alterações manuais ou via importação em lote foram realizadas no banco.

### 7.4. Sequência
O diagrama de sequência detalha o fluxo principal de negócio do sistema: a Montagem da Grade pelo Estudante.

O fluxo demonstra uma otimização clara de performance e usabilidade. As requisições ao Backend são feitas nas etapas iniciais de configuração (Stepper e Matérias Concluídas) para buscar a carga de dados completa (payload).

Uma vez que os dados são carregados, a interação principal (adicionar/remover disciplinas, calcular créditos e detectar conflitos visuais) ocorre localmente no Frontend. Isso evita requisições excessivas ao servidor a cada clique, garantindo uma resposta em tempo real (baixa latência) para o aluno durante a simulação.

---

## 8. Refinamento do backlog após a modelagem

### Itens adicionados ao backlog
* **[Infraestrutura]** Configurar o banco de dados PostgreSQL em ambiente de nuvem para acesso compartilhado da equipe.
* **[Back-end]** Implementar a configuração inicial do Spring Security para suportar a geração e validação de tokens JWT (base para os módulos administrativos).
* **[Back-end]** Desenvolver e documentar o contrato da API (Swagger/OpenAPI) para os *endpoints* levantados no Diagrama de Sequência e criar a rota administrativa `multipart/form-data` para receber o arquivo `.zip`.
* **[Bot/Scraping]** Desenvolver o script de extração em Python focando na geração de uma camada de dados estruturada em arquivos JSON para compactação em `.zip`, garantindo compatibilidade com a API.
