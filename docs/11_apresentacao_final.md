# 11. Apresentação Final

## 1. Objetivo da apresentação
Apresentar o problema enfrentado pelos estudantes da UFLA durante o período de matrículas, a solução tecnológica desenvolvida (o **gradeUFLA**), a evolução incremental do trabalho ao longo das 6 Sprints e a aplicação prática dos conceitos de Engenharia de Software (Scrum, Modelagem, Arquitetura e Testes).

---

## 2. Estrutura sugerida da apresentação
1. **Contexto e problema:** A dificuldade de montar horários no SIG.
2. **Justificativa da solução:** Por que uma ferramenta visual e interativa é necessária.
3. **Visão do produto:** O gradeUFLA (Front-end interativo, Admin e extração automatizada).
4. **Organização do grupo com Scrum:** Papéis, rituais e gestão via GitHub Projects.
5. **Principais requisitos:** Montagem sem conflitos (drag-and-drop) e Gestão por Scraping.
6. **Modelagem:** Diagramas UML e Banco de Dados Relacional.
7. **Arquitetura e decisões de projeto:** React (Front), Spring Boot (Back), Python (Bot) e a mudança para o upload em lote (`.zip`).
8. **Padrões utilizados:** MVC, RESTful API, Autenticação JWT.
9. **Estratégia e evidências de testes:** Testes de prevenção de choques e auditoria das 56 mil linhas de horários inseridas no banco.
10. **Demonstração do produto/incremento:** Navegação ao vivo no sistema.
11. **Lições aprendidas:** A importância de adaptar a arquitetura para viabilidade financeira.
12. **Conclusão:** Fechamento e próximos passos.

---

## 3. Roteiro de fala

### Abertura
"Olá a todos. Nós somos a equipe responsável pelo **gradeUFLA**. Todo semestre, os estudantes da universidade enfrentam um problema clássico: organizar a grade de horários no SIG. O processo atual é manual, não visual e frequentemente resulta em choques de horário que o aluno só descobre tarde demais. Para resolver isso, idealizamos o gradeUFLA: uma plataforma web focada na experiência do usuário, onde o estudante pode simular sua grade arrastando e soltando matérias em um calendário, com validação inteligente contra conflitos."

### Desenvolvimento
"Nosso trabalho evoluiu de forma bastante incremental ao longo de 6 Sprints utilizando o Scrum. 
Começamos na **Sprint 1 e 2** focando no design e na experiência do usuário, criando protótipos de alta fidelidade e estabelecendo a stack: React para o Front-end e Spring Boot para o Back-end. 
Na **Sprint 3 e 4**, fizemos a modelagem. Estruturamos o banco de dados PostgreSQL para suportar os diversos tipos de cursos, disciplinas, matrizes e pré-requisitos, e desenvolvemos as rotas administrativas com segurança JWT.
O grande diferencial tecnológico e arquitetural veio nas **Sprints 5 e 6** com o nosso Bot de Scraping em Python. Nós conseguimos extrair todo o catálogo do SIG. No meio do desenvolvimento, tivemos um grande desafio que era: rodar o bot no servidor web deixaria a infraestrutura cara e inviável. Aplicando princípios ágeis, adaptamos nossa arquitetura. O bot passou a rodar localmente, gerando um pacote `.zip` que o administrador simplesmente faz o upload pelo painel para atualizar a base de dados em lote."

### Encerramento
"Como resultado, entregamos uma solução robusta. Realizamos testes de integração provando que o Front-end intercepta erros de choque de horário e que o banco de dados suporta a inserção massiva de turmas sem perdas ou registros órfãos. Como limitações, o sistema atual demanda a execução manual offline do bot pelo administrador a cada semestre. Como próximos passos, o objetivo é liberar a plataforma para uso real da comunidade acadêmica no próximo período de matrículas."

---

## 4. Materiais de apoio
- [Slides da apresentação](https://drive.google.com/file/d/1Cdy4mfhYnRucA9N2T3gSuym5MKkTEyQW/view?usp=sharing)
- [Protótipos (Figma)](https://www.figma.com/design/eiKuAq5s1lb37Z5TEMhdLp/grade-final?node-id=0-1&t=BkKfAhfDWxiT1v0y-1)
- [Diagramas UML e Modelo Relacional do Banco de Dados](https://github.com/GradeUFLA/.github/blob/main/docs/05_modelagem.md)
- [backlog do produto no GitHub Projects](https://github.com/GradeUFLA/.github/blob/main/docs/03_product_backlog.md)
- [Evidências de testes (PDFs de auditoria do banco de dados e logs de API)](https://github.com/GradeUFLA/.github/blob/main/docs/09_testes.md)
- link do repositório contendo todo o código-fonte ([Front-end](https://github.com/GradeUFLA/front), [Back-end](https://github.com/GradeUFLA/backend) e [Bot](https://github.com/GradeUFLA/dados)).

---

## 5. Checklist final
- [ ] todos os integrantes sabem apresentar sua parte;
- [ ] slides revisados e com identidade visual do gradeUFLA aplicada;
- [ ] links do repositório e do deploy funcionando;
- [ ] demonstração preparada (base de dados populada com o `.zip` para mostrar na hora);
- [ ] tempo de apresentação ensaiado para caber no limite estipulado pelo professor.

---

## 6. Exemplo de fechamento
> O grupo conclui que a solução proposta atende ao problema selecionado em nível acadêmico e prático. O **gradeUFLA** demonstra a aplicação real dos conteúdos de Engenharia de Software, comprovando que o uso coerente de Scrum, o rigor na modelagem arquitetural e a resiliência para adaptar requisitos tecnológicos foram fundamentais para a entrega de um produto de software escalável e de alto valor para os estudantes.
