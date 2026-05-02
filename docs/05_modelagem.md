# Sprint 3 – Modelagem do Sistema

## 1. Identificação da entrega

**Sprint:** 3  
**Título:** Modelagem do Sistema  
**Pontuação:** 4,0 pontos  
**Objetivo:** Representar o **gradeUFLA** por meio de modelos técnicos e visuais que auxiliem a compreensão do sistema, apoiem as decisões de desenvolvimento da aplicação web e reduzam riscos arquiteturais antes da fase de codificação.

---

## 2. Descrição do sistema

O gradeUFLA é uma ferramenta desenvolvida para os estudantes da Universidade Federal de Lavras (UFLA), para que durante o período de planeamento de matrículas, consigam simular grades de forma rápida e intuita. Ao final, poderão baixar uma versão .png da sua grade ou fazer uma vinculação com a sua Agenda do Google.

### 2.1. Visão geral do sistema

A aplicação é uma ferramenta web dedicada à simulação e visualização de grades horárias de alunos da UFLA. A ideia é que seja uma sistema sem necessidade de login por parte do usuário, permitindo que qualquer estudante acesse aos dados das turmas e monte o seu horário ideal de forma instantânea. O sistema consome dados diretamente do SIG-UFLA através de um bot de extração automatizado.

### 2.2. Objetivo da solução

O objetivo principal do gradeUFLA é diminuir a dificuldade durante o processo de montagem da grade semestral. A solução visa:
Proporcionar uma ferramenta de simulação que facilite a tomada de decisão do aluno antes da matrícula oficial.

Permitir a exportação da grade planejada em formato de imagem, ou vincular diretamente na agenda do google.

### 2.3. Perfis de usuário

- **Usuário:** Consulta disciplinas e turmas disponíveis por curso e período, adiciona ou remove turmas numa grade horária interativa para simular o seu semestre, visualiza conflitos de horários, exporta o resultado final da simulação.
- **Administrador:** Realiza autenticação segura, monitoriza métricas de uso e engajamento dos alunos através de analytics, gerencia manualmente dados de disciplinas ou turmas em caso de inconsistências, aciona manualmente o bot de scraping para sincronização de dados com o SIG.

---

## 3.Entregas da Sprint 3

1. **Diagrama de Casos de Uso** para representar as funcionalidades principais.
2. **Diagrama de Componentes** para representar a estrutura da aplicação web.
3. **Modelo de Dados** para representar entidades e relacionamentos principais.
4. **Diagrama de Sequência** para representar um fluxo central do sistema.
5. **Texto explicativo** relacionando os modelos aos requisitos levantados.
6. **Atualização do backlog** com refinamentos identificados durante a modelagem.

---

## 4. Eequisitos relacionados

### Requisitos funcionais

- **RF01:** O usuário deve poder criar uma conta.
- **RF02:** O usuário deve poder realizar login.
- **RF03:** O usuário deve poder visualizar serviços disponíveis.
- **RF04:** O usuário deve poder consultar horários disponíveis.
- **RF05:** O usuário deve poder realizar agendamentos.
- **RF06:** O usuário deve poder cancelar agendamentos.
- **RF07:** O administrador deve poder gerenciar serviços.
- **RF08:** O administrador deve poder gerenciar horários disponíveis.

### Requisitos não funcionais

- **RNF01:** O sistema deve estar acessível via navegador web.
- **RNF02:** O sistema deve exigir autenticação para ações restritas.
- **RNF03:** O sistema deve persistir os dados de usuários, serviços e agendamentos.

---

## 5. Vínculo entre requisitos e modelos

| Requisito | Modelo relacionado | Justificativa |
|---|---|---|
| RF01 – Criar conta | Casos de Uso / Modelo de Dados | Representa cadastro e persistência do usuário |
| RF02 – Login | Casos de Uso / Componentes | Mostra autenticação e interação entre frontend e backend |
| RF03 – Visualizar serviços | Casos de Uso / Modelo de Dados | Relaciona consulta ao catálogo de serviços |
| RF04 – Consultar horários | Casos de Uso / Modelo de Dados / Sequência | Relaciona disponibilidade e fluxo da aplicação |
| RF05 – Realizar agendamento | Casos de Uso / Sequência / Modelo de Dados | Representa o principal fluxo de negócio |
| RF07 – Gerenciar serviços | Casos de Uso / Modelo de Dados | Representa manutenção administrativa |

---

## 6. Diagramas em PlantUML

### 6.1. Diagrama de Casos de Uso

![Diagrama de Casos de Uso](https://github.com/user-attachments/assets/2014db3e-6868-4d20-a8e2-ef4fe480171a)

<img width="421" height="708" alt="Image" src="https://github.com/user-attachments/assets/b4166fc6-4d9e-4ab4-b839-702803c9bc66" />

### 6.2. Diagrama de Componentes


![Diagrama de Componentes]()

### 6.3. Modelo de Dados

![Modelo de Dados](https://github.com/user-attachments/assets/cda99a46-210e-4c99-b7fd-ba57af124f1c)


### 6.4. Diagrama de Sequência

![Diagrama Sequencia](https://github.com/user-attachments/assets/a12861bc-fbd6-45b6-8743-659a8aa8411a)

---

## 7. Descrição textual complementar dos modelos

### 7.1. Casos de uso
O diagrama de casos de uso apresenta os dois principais perfis do sistema: usuário e administrador. Ele mostra as funcionalidades centrais oferecidas pela aplicação e evidencia que algumas operações dependem de autenticação.

### 7.2. Componentes
O diagrama de componentes representa a estrutura geral da aplicação web, separando frontend, backend, serviços internos e banco de dados. Esse modelo ajuda a justificar decisões arquiteturais iniciais.

### 7.3. Modelo de dados
O modelo de dados mostra as entidades centrais do domínio e seus relacionamentos, servindo como apoio para a implementação do banco de dados e para a compreensão das regras de negócio.

### 7.4. Sequência
O diagrama de sequência detalha o fluxo de realização de agendamento, mostrando como o usuário interage com a interface e como a solicitação percorre backend e banco de dados.

---

## 8. Refinamento do backlog após a modelagem

### Antes do refinamento
- Como usuário, quero agendar atendimento.

### Após o refinamento
- Como usuário, quero visualizar horários disponíveis para escolher um atendimento.
- Como usuário, quero confirmar um agendamento online.
- Como sistema, devo impedir agendamentos em horários já ocupados.
- Como administrador, quero cadastrar novos serviços com duração definida.

### Exemplo de itens adicionados ao backlog
- Criar tela de listagem de serviços.
- Implementar endpoint de consulta de horários.
- Modelar tabela de agendamentos.
- Implementar regra de validação de conflito de horários.
- Criar tela “Meus agendamentos”.

---

