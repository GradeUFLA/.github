# 09. Testes

## 1. Estratégia de Testes
A nossa estratégia para o **gradeUFLA** é focada no utilizador: queremos ter a certeza de que as duas partes do nosso sistema conversam perfeitamente (Front-end, Back-end) e que o Bot-scraping consiga extrair todas as grades corretamente. Vamos testar a interface em React (para garantir que a montagem do horário seja fluida e intuitiva), a API em Spring Boot (para garantir a segurança e as regras de negócio) e o Bot em Python (para confirmar que os dados do SIG são extraídos sem falhas).

Para os fluxos mais visuais e complexos (como arrastar as disciplinas), faremos testes manuais. Para a segurança das rotas e integridade da base de dados, faremos validação mais técnica.

### Objetivos:
- Garantir que cumprimos tudo o que prometemos nos requisitos (ex: não permitir choques de horário e manter a área de administração segura);
- Descobrir e corrigir problemas de usabilidade, especialmente atrasos ou falhas ao arrastar as disciplinas para a grade;
- Ter a certeza de que o Bot de extração, a API e a base de dados comunicam sem perder nenhuma informação pelo caminho;
- Assegurar que entregamos um produto estável e agradável antes de o lançarmos para os estudantes.

---

## 2. Tipos de Teste Previstos
| Tipo de Teste | O que queremos descobrir? | Como vamos provar que testamos? |
|---|---|---|
| **Teste Funcional** | As funcionalidades principais (montar a grade, exportar imagem, gerir disciplinas de modo geral) fazem exatamente o que devem? | Casos de teste documentados com capturas de tela (sucesso e falha). |
| **Teste de Interface (UI/UX)** | A experiência é agradável? Funciona bem no telemóvel? Os avisos e as telas de carregamento são claros? | Prints (Mobile e Desktop) e notas de usabilidade. |
| **Teste de Integração** | O Front-end, o Back-end e a base de dados estão funcionando corretamente? | Registos de pedidos de rede com status `200 OK` ou `201 Created` |
| **Teste Exploratório** | O que acontece se o utilizador fizer algo inesperado ("caminho infeliz")? | Relato de problemas e registo de *bugs* no GitHub. |

---

## 3. Casos de Teste e Rastreabilidade
| ID | Requisito | O Cenário | O que o utilizador faz | O que o sistema tem de fazer | O que aconteceu na realidade |
|---|---|---|---|---|---|
| **CT01** | RF09/RF10 (US04) | Montagem de horário com choque. | O estudante tenta colocar "Cálculo II" num horário onde já tem "Física I". | O sistema percebe o erro, impede a ação e mostra um aviso. | **Sucesso.** O sistema detetou o conflito, exibiu aviso visual e a disciplina não foi adicionada à grade. |
| **CT02** | RF22 (US06) | Login correto do Administrador. | Insere o E-mail e a Senha válidos na página de entrada. | Entra diretamente no Painel de administração e guarda a chave de segurança (JWT). | **Sucesso.** O utilizador foi redirecionado para a dashboard e o token JWT foi armazenado corretamente. |
| **CT03** | RF17/RF18 (US10) | Guardar a grade como imagem. | Clica em "Exportar como .jpg" depois de ter o horário pronto. | A imagem da grade é baixada para o computador ou celular. | **Sucesso.** Arquivo baixado. |
| **CT05** | RF06/RF07 (US03) | Desmarcar uma disciplina concluída. | Retira o visto da disciplina "Introdução à Programação" no guia de passos. | A disciplina volta imediatamente para a lista lateral, disponível para ser cursada. | **Sucesso.** A checkbox foi desmarcada imediatamente e a matéria retornou para a sidebar de escolhas. |
| **CT06** | RF31 (US09) | Apagar um curso em uso. | O administrador tenta apagar um curso que ainda tem várias turmas associadas. | O sistema não deixa apagar e explica o porquê de forma clara, sem prejudicar a base de dados. | **Sucesso.** O sistema bloqueou a exclusão e retornou um erro HTTP 409, exibindo um aviso a informar sobre as 47 matérias vinculadas. |

---

## 4. Critérios de Aceitação dos Testes
- Os testes têm de fazer sentido e validar diretamente os requisitos que definimos no início do projeto;
- As funcionalidades principais (montar a grade e extrair os dados) têm de ter provas visuais de que funcionam corretamente;
- A responsividade é obrigatória: testar se a grade de horários não fica "cortada" nos telas mais pequenos dos celulares;
- Qualquer falha ou comportamento estranho deve ser logo registado como *BUG* no GitHub, com o seu grau de urgência bem definido.

---

## 5. Registo de Defeitos

| ID | Defeito | Severidade | Status | Ação tomada |
|---|---|---|---|---|
| **BUG01** | O Bot de Scraping abre a janela gráfica do navegador (consumindo muita RAM do servidor) durante a extração. | Média | Resolvido | Configuração do Selenium/Script Python alterada para o modo *headless* (sem interface visual). |
| **BUG02** | O Front-end não consegue carregar os cursos na visão mobile, apresentando erro de rede (`ERR_CONNECTION_REFUSED` / `AxiosError`) na aba de inspeção. | Alta | Em aberto | O Back-end precisará de validar as libertações de CORS ou o Front-end precisa de ajustar o IP base da API para testes em rede local/mobile. |

---

## 6. Evidências

- **Capturas de Tela:**
  - Telas iniciais (Desktop e Mobile) e interface do Stepper demonstrando o pleno funcionamento visual da aplicação Web.
 
<img width="1600" height="915" alt="WhatsApp Image 2026-06-03 at 23 31 32" src="https://github.com/user-attachments/assets/ab40359b-4663-40e0-b222-1d6e4113755a" />
<img width="1600" height="852" alt="WhatsApp Image 2026-06-03 at 23 31 32(1)" src="https://github.com/user-attachments/assets/10548497-55a6-441c-a9c0-26fc8387b646" />
<img width="1600" height="846" alt="WhatsApp Image 2026-06-03 at 23 31 32(2)" src="https://github.com/user-attachments/assets/c852e22b-5c18-403b-a73c-c0ac66854557" />

  - Separador "Network" capturado provando que a rota `GET /api/v1/public/cursos` retorna status `200 OK` na versão Desktop e identificando o erro de conexão local na visualização mobile.


  <img width="1600" height="835" alt="WhatsApp Image 2026-06-03 at 23 34 41" src="https://github.com/user-attachments/assets/c334da7d-b464-4938-97a1-5497ef544fee" />
  
- **Relatórios simples de validação:**

  - Relatório de validação da base de dados anexado (*Testes e Validações no Banco de Dados.pdf*), confirmando o sucesso do Bot ao inserir de forma estruturada: 56.938 horários, 35.511 pré-requisitos e 3.972 disciplinas com 0 turmas órfãs.
  
[Testes e Validações no Banco de Dados.pdf](https://github.com/user-attachments/files/28841057/Testes.e.Validacoes.no.Banco.de.Dados.pdf)

  - Documento com resultados de rotas HTTP do Back-end (*GradeUFLA_Casos_Teste-1.pdf*), a mostrar o funcionamento das travas de segurança (ex: Erro 409 ao tentar apagar um curso preenchido).

[GradeUFLA_Casos_Teste-1.pdf](https://github.com/user-attachments/files/28841061/GradeUFLA_Casos_Teste-1.pdf)

---

## 7. Exemplo Resumido
> **Como testamos a prevenção de conflitos (RF09/RF10)?** > Através do nosso teste **CT01**. O nosso objetivo aqui é ver o que acontece quando o estudante tenta forçar a entrada de duas aulas exatamente à mesma hora. O esperado é que a interface perceba o conflito localmente, trave o movimento e dê um aviso claro ao aluno, sem sequer precisar de sobrecarregar o servidor com um pedido. Assim garantimos que o estudante nunca constrói um horário inválido por engano.
