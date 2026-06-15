# 01. Problema e Visão do Produto

## 1. Problema escolhido
**Título do problema:** Dificuldade na simulação e montagem da grade de horários no SIG UFLA.

**Descrição resumida do problema:**  
O processo de escolha e montagem da grade horária a cada semestre na UFLA carece de uma forma simples e visual para testar diferentes combinações de turmas antes da matrícula oficial. O sistema atual armazena as informações, mas não foca na experiência do usuário para esse planejamento prévio.

**Justificativa da escolha:**  
A fase de matrícula é burocrática e frequentemente gera estresse. A ausência de uma ferramenta visual e ágil impede que o aluno teste cenários e organize seu horário sem o risco de sobreposições, tornando o desenvolvimento dessa solução altamente relevante para facilitar a rotina acadêmica.

---

## 2. Contexto
- **Quem são os usuários?** Estudantes da UFLA (graduação) e a equipe de administração do sistema.
- **Em que ambiente o problema ocorre?** No ambiente acadêmico da universidade, especificamente durante o período de planejamento semestral e renovação de matrícula.
- **Quais dificuldades atuais existem?** O sistema oficial (SIG) é focado em armazenamento e carece de ferramentas interativas para simulação. Os alunos não conseguem visualizar claramente suas opções, pré-requisitos e possíveis conflitos de horários de forma ágil. Também há uma dificuldade de filtrar eletivas que estajam compatíveis com a disponibilidade dos alunos. 
- **Que impacto a solução pode gerar?** Tornar o processo de montagem da grade mais simples, rápido e organizado, reduzindo erros na hora da matrícula oficial e melhorando a organização pessoal do estudante.

---

## 3. Visão do produto
**Nome da solução:** gradeUFLA

**Proposta de valor:**  
Oferecer uma aplicação web intuitiva e gratuita que permite aos estudantes da UFLA simular, visualizar e exportar suas grades horárias semestrais sem conflitos de turmas.

**Objetivo geral da solução:**  
Facilitar a gestão acadêmica e o planejamento semestral dos estudantes da UFLA por meio de uma ferramenta visual de montagem de grade de horários.

**Objetivos específicos:**
- Permitir a montagem de horários de disciplinas obrigatórias, eletivas e futuras de forma visual.
- Possibilitar a exportação gratuita dos resultados em formato de imagem ou via sincronização com o Google Agenda.
- Manter uma base de dados atualizada via scraping do SIG, que pode ser gerenciada por um painel administrativo interno.

---

## 4. Stakeholders
| Stakeholder | Papel | Interesse no projeto |
|---|---|---|
| Usuário final | Estudantes da UFLA | Simular, montar e exportar a grade horária de forma rápida, visual e livre de conflitos. |
| Cliente/solicitante | Comunidade acadêmica | Ter acesso a uma ferramenta que supra a deficiência do sistema oficial na fase de planejamento. |
| Equipe do projeto | Desenvolvedores / Admins | Criar e manter a plataforma, garantir a integridade do scraping (SIG) e analisar os dados de uso (analytics). |

---

## 5. Escopo inicial
### Inclui
- Interface web pública para simulação e visualização de grades horárias.
- Ferramenta de exportação da grade (download como imagem).
- Integração para sincronização da grade com o Google Agenda.
- Painel administrativo interno (com autenticação) para gestão do sistema e analytics.
- Sistema de captura de dados (scraping) integrado ao SIG da UFLA.

### Não inclui
- Efetivação da matrícula do estudante no sistema oficial da universidade.
- Gestão de notas, faltas ou emissão de histórico escolar.

---

## 6. Restrições e premissas
**Restrições:**
- Dependência contínua do funcionamento e da estrutura de dados do sistema oficial (SIG) para o funcionamento do scraping.
- O acesso à aplicação de simulação deve ser mantido totalmente gratuito e público para os estudantes.

**Premissas:**
- Os estudantes possuem a necessidade e o interesse em planejar suas grades antes do período oficial de matrícula.
- As informações sobre turmas, disciplinas e horários no SIG permanecerão públicas ou acessíveis o suficiente para a extração (scraping) dos dados.

---

## 7. Exemplo resumido
> Problema: dificuldade e burocracia enfrentadas pelos estudantes na simulação prévia e montagem da grade horária semestral no sistema oficial.  
> Solução proposta: aplicação web (gradeUFLA) para simulação interativa de horários, com opções de exportação para Google Agenda/Imagem e um painel admin para manutenção automatizada dos dados via scraping.
