# 09. Testes

## 1. Estratégia de Testes
A nossa estratégia para o **gradeUFLA** é mais simples e focada no aluno que vai utilizar: queremos ter a certeza de que as três partes do nosso sistema conversam perfeitamente (Front-end, Back-end e Bot-scraping). Vamos testar a interface em React (para garantir que a montagem do horário seja fluida e intuitiva), a API em Spring Boot (para garantir a segurança e as regras de negócio) e o Bot em Python (para confirmar que os dados do SIG são extraídos sem falhas).

Para os fluxos mais visuais e complexos (como arrastar as disciplinas), faremos testes manuais. Para a segurança das rotas e integridade da base de dados, faremos validação mais técnica.

### Objetivos:
- Garantir que cumprimos tudo o que prometemos nos requisitos (ex: não permitir choques de horário e manter a área de administração segura);
- Descobrir e corrigir problemas de usabilidade, especialmente atrasos ou falhas ao arrastar as disciplinas para a grade;
- Ter a certeza de que o Bot de extração, a API e a base de dados comunicam sem perder nenhuma informação pelo caminho;
- Assegurar que entregamos um produto estável e agradável antes de o lançarmos para os estudantes.

---

## 2. Tipos de Teste Previstos
| Tipo de Teste | O que queremos descobrir? | Como vamos provar que testámos? |
|---|---|---|
| **Teste Funcional** | As funcionalidades principais (montar a grade, exportar imagem, gerir disciplinas de modo geral) fazem exatamente o que devem? | Casos de teste documentados com capturas de telas (sucesso e falha). |
| **Teste de Interface (UI/UX)** | A experiência é agradável? Funciona bem no celular? Os avisos e as telas de carregamento são claros? | Prints (Mobile e Desktop) e notas de usabilidade. |
| **Teste de Integração** | O Front-end, o Back-end e o banco de dados estão funcionando corretamente? | Registros de requisições de rede com status `200 OK` ou `201 Created` |
| **Teste Exploratório** | O que acontece se o utilizador fizer algo inesperado ("caminho infeliz")? | Relato de problemas e registo de *bugs* no GitHub. |

---

## 3. Casos de Teste e Rastreabilidade
| ID | Requisito | O Cenário | O que o utilizador faz | O que o sistema tem de fazer | O que aconteceu na realidade |
|---|---|---|---|---|---|
| **CT01** | RF09/RF10 (US04) | Montagem de horário com choque. | O estudante tenta colocar "Cálculo II" num horário onde já tem "Física I". | O sistema percebe o erro, impede a ação e mostra um aviso. | [A preencher na execução] |
| **CT02** | RF22 (US06) | Login correto do Administrador. | Insere o E-mail e a Senha válidos na página de entrada. | Entra diretamente no Painel de Controlo e guarda a chave de segurança (JWT). | [A preencher na execução] |
| **CT03** | RF17/RF18 (US10) | Guardar a grade como imagem. | Clica em "Exportar como .jpg" depois de ter o horário pronto. | A imagem da grade, é baixada para o computador/celular. | [A preencher na execução] |
| **CT04** | RF35 (US11) | Acionar o Bot manualmente. | O administrador clica em "Executar Bot" na área de Dados. | A tela avisa que está "A executar..." e, no fim, dá um pequeno resumo do que atualizou. | [A preencher na execução] |
| **CT05** | RF06/RF07 (US03) | Desmarcar uma disciplina concluída. | Retira o visto da disciplina "Introdução à Programação" no guia de passos. | A disciplina volta imediatamente para a lista lateral, disponível para ser cursada. | [A preencher na execução] |
| **CT06** | RF31 (US09) | Apagar um curso em uso. | O administrador tenta apagar um curso que ainda tem várias turmas associadas. | O sistema não deixa apagar e explica o porquê de forma clara, sem prejudicar o banco de dados. | [A preencher na execução] |

---

## 4. Critérios de Aceitação dos Testes
- Os testes têm de fazer sentido e validar diretamente os requisitos que definimos no início do projeto;
- As funcionalidades principais (montar a grade e extrair os dados) têm de ter provas visuais de que funcionam corretamente;
- A responsividade é obrigatória: testar se a grade de horários não fica "cortada" nas telas mais pequenas dos celulares;
- Qualquer falha ou comportamento estranho deve ser logo registado como *Issue* no nosso GitHub, com o seu grau de urgência bem definido.

---

## 5. Registro de defeitos

----------->>>> EXEMPLOOOOOO <<<<<----------------------

| ID | Defeito | Severidade | Status | Ação tomada |
|---|---|---|---|---|
| **BUG01** | Bot de Scraping abre janela gráfica do navegador (consumindo muita RAM do servidor) durante a extração. | Média | Corrigido | Configuração do Selenium/Script Python alterada para o modo *headless* (sem interface visual). |

---

## 6. Evidências
*(Esta secção será preenchida à medida que os meues os desenvolvedores forem executando os testes)*

capturas de tela;
links para execução;
registros em issues;
relatórios simples de validação.

---

## 7. Exemplo Resumido
> **Como testamos a prevenção de conflitos (RF09/RF10)?** > Através do nosso teste **CT01**. O nosso objetivo aqui é ver o que acontece quando o estudante tenta forçar a entrada de duas aulas exatamente à mesma hora. O esperado é que a interface perceba o conflito localmente, trave o movimento e dê um aviso claro ao aluno, sem sequer precisar de sobrecarregar o servidor com um pedido. Assim garantimos que o estudante nunca constrói um horário inválido por engano.
