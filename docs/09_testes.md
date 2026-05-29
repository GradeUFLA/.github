# 08. Testes

## 1. Estratégia de testes
A estratégia de testes do **gradeUFLA** baseia-se na verificação contínua das três camadas principais do sistema: a interface do utilizador em React (focada na usabilidade e interatividade da montagem de grade), a API REST em Spring Boot (focada na segurança e regras de negócio) e o Bot de Scraping em Python (focado na integridade da extração de dados). A validação ocorrerá de forma manual para fluxos complexos de interface e automatizada para a integridade de rotas e banco de dados.

### Objetivos
- verificar se os requisitos funcionais e não funcionais (ex: RF09 a RF18 sobre montagem de grade, RNF05 sobre segurança JWT) foram atendidos;
- identificar falhas de usabilidade e gargalos de performance na interação de *drag-and-drop*;
- assegurar que a integração entre o Bot de Scraping, a API e o PostgreSQL funciona sem perda de dados;
- garantir a qualidade mínima do incremento antes da liberação (deploy) para os estudantes.

---

## 2. Tipos de teste previstos
| Tipo de teste | Objetivo | Evidência esperada |
|---|---|---|
| **Teste funcional** | Validar as funcionalidades centrais (ex: montar grade, exportar imagem, login de admin, CRUD de disciplinas). | Casos de teste documentados e *prints* de sucesso/falha. |
| **Teste de interface (UI/UX)** | Verificar a interação do usuário (arrastar matérias, responsividade mobile, *feedbacks* de carregamento/spinners). | Capturas de tela (Mobile e Desktop) e observações de usabilidade. |
| **Teste de integração** | Validar a comunicação entre o Front-end (React) e o Back-end (Spring Boot), e a injeção de dados do Bot (Python) no Banco (PostgreSQL). | Registros de requisições de rede (Network tab) com status `200 OK` ou `201 Created`. |
| **Teste exploratório** | Identificar falhas não previstas no fluxo "feliz", como tentar matricular-se em horários sobrepostos ou sem pré-requisitos. | Relato de problemas (Issues/Bugs no GitHub). |

---

## 3. Casos de teste e Rastreabilidade
| ID | Requisito relacionado | Cenário | Entrada | Resultado esperado | Resultado obtido |
|---|---|---|---|---|---|
| **CT01** | RF09/RF10 (US04) | Montagem de grade com choque de horário. | Arrastar a matéria "Cálculo II" para um horário já ocupado por "Física I". | O sistema deve bloquear a ação e exibir um alerta visual vermelho de choque de horário. | [A preencher na execução] |
| **CT02** | RF22 (US06) | Autenticação do Administrador com sucesso. | Inserir E-mail e Senha válidos e ativos no painel de login. | Redirecionamento para a Dashboard e armazenamento seguro do token JWT. | [A preencher na execução] |
| **CT03** | RF17/RF18 (US10) | Exportação da grade montada em Imagem. | Clicar no botão "Exportar como .jpg" após montar a grade. | O navegador deve iniciar o download de um arquivo de imagem com a renderização exata da grade. | [A preencher na execução] |
| **CT04** | RF35 (US11) | Execução manual do Bot de Scraping. | Clicar no botão "Executar Bot" na tela de Dados do Admin. | A tela exibe "Executando...", e após o término, mostra o log de turmas atualizadas. | [A preencher na execução] |
| **CT05** | RF06/RF07 (US03) | Desmarcar matéria concluída no Stepper. | Desmarcar a *checkbox* da matéria "Introdução à Programação". | A matéria volta a aparecer na Sidebar da Tela de Montagem como "disponível para cursar". | [A preencher na execução] |
| **CT06** | RF31 (US09) | Exclusão de Curso com dependências. | Tentar deletar um curso que já possui disciplinas vinculadas a ele. | O sistema impede a exclusão e retorna erro amigável de restrição de chave estrangeira. | [A preencher na execução] |

---

## 4. Critérios de aceitação dos testes
- Todos os testes devem estar estritamente alinhados aos RFs e RNFs documentados nas Sprints 2 e 3;
- Cada funcionalidade essencial (Core: Montagem de Grade e Extração de Dados) deve ter evidência visual clara de funcionamento;
- Os testes de responsividade devem garantir que a grade possa ser visualizada sem quebra de layout em telas de *smartphones*;
- Falhas identificadas devem ser imediatamente registradas como *Issues* no GitHub, categorizadas por severidade.

---

## 5. Registro de defeitos
| ID | Defeito | Severidade | Status | Ação tomada |
|---|---|---|---|---|
| **BUG01** | Bot de Scraping abre janela gráfica do navegador (consumindo muita RAM do servidor) durante a extração. | Média | Corrigido | Configuração do Selenium/Script Python alterada para o modo *headless* (sem interface visual). |
| **BUG02** | Gráficos da Tela de Analytics (Dashboard Admin) sobrepõem os menus em telas muito pequenas (Mobile). | Baixa | Aberto | [A preencher com a resolução do Front-end] |
| **BUG03** | Adicionar matéria na grade pelo botão de "clique" (Mobile) não está validando o choque de horário, apenas o *drag-and-drop* valida. | Alta | Aberto | [A preencher com a resolução do Front-end] |

---

## 6. Evidências
*(Esta seção será preenchida durante e após a execução da bateria de testes)*

- **Capturas de tela:**
  - `[Inserir print da tela de Montagem de Grade acusando conflito]`
  - `[Inserir print do Postman / Network Tab mostrando o Token JWT gerado]`
- **Links para execução:**
  - `[Inserir URL do ambiente de homologação, se aplicável]`
- **Registros em issues:**
  - `[Inserir link para a aba de Issues do repositório no GitHub com as tags "bug"]`
- **Relatórios simples de validação:**
  - `[Link para o pull request com a correção dos bugs listados acima]`

---

## 7. Exemplo resumido
> O requisito RF09/RF10 (Prevenção de conflitos) será validado por meio do caso de teste **CT01**, no qual o testador tenta sobrepor duas aulas no mesmo horário na interface interativa. O resultado esperado é que o componente React intercepte a ação, utilize a regra de negócio local e impeça a operação visualmente, garantindo a integridade da grade que o estudante está construindo.
