# 07. Padrões de Projeto

## 1. Objetivo
Identificar oportunidades de uso de padrões de projeto e justificar a sua adoção na solução do **gradeUFLA**. O foco é analisar problemas recorrentes na arquitetura do sistema (como gerenciamento de estado na interface, múltiplas lógicas de exportação e comunicação com o banco de dados), selecionando padrões pertinentes para garantir que o software seja manutenível, flexível e escalável.

---

## 2. Padrões selecionados
| Padrão | Onde será usado | Problema que resolve | Justificativa |
|---|---|---|---|
| **Strategy** | Back-end / Front-end (Exportação da Grade) | O sistema precisa exportar a grade montada nos formatos .jgp e também no google agenda, sem criar estruturas condicionais complexas (`if/else`). | Permite isolar os diferentes algoritmos de exportação em classes separadas. Facilita a manutenção e garante o princípio "Aberto-Fechado" (Open/Closed Principle). |
| **Observer** | Front-end (React - Gerenciamento de Estado) | Necessidade de atualizar diversos componentes (contador de créditos, calendário, lista de matérias) simultaneamente quando uma matéria é arrastada para a grade. | Desacopla o estado da aplicação da renderização visual. Quando o estado central é alterado, todos os componentes "inscritos" (*subscribers*) são notificados e re-renderizados automaticamente em tempo real. |
| **Singleton** | Back-end (Spring Boot Services) | Evitar a criação contínua e custosa de múltiplas instâncias de classes de serviço (ex: `GradeService`) que não guardam estado (*stateless*). | É o padrão nativo e encorajado pelo ecossistema Spring (através da anotação `@Service`). Otimiza o uso de memória e garante ponto de acesso global e único à lógica de negócios. |
| **Repository** | Back-end (Acesso a Dados via Spring Data JPA) | Misturar lógica de acesso a dados (SQL/Consultas) com regras de negócio torna o código frágil e difícil de testar. | Abstrai e encapsula os detalhes da persistência de dados. O sistema interage com o banco de dados através de interfaces orientadas a domínio (ex: `DisciplinaRepository`), separando as responsabilidades. |

---

## 3. Exemplo de aplicação
### Padrão: Strategy
**Contexto:**  
Na funcionalidade de montagem de grade (US10), o estudante finaliza o seu horário e deseja salvá-lo. Os requisitos exigem que o sistema suporte o download do horário como uma **Imagem (.jpg)** ou a integração para o **Google Agenda**.

**Aplicação no projeto:**  
Em vez de implementar a lógica de exportação numa única classe baseada no tipo selecionado, criaremos uma interface comum chamada `ExportacaoGradeStrategy` com um método assinado `exportar(Grade grade)`. Em seguida, implementaremos classes concretas: `ExportacaoJpgStrategy` e `ExportacaoGoogleAgendaStrategy`. O controlador da aplicação apenas receberá a interface e chamará o método `exportar`, sendo o comportamento injetado dinamicamente com base na escolha do usuário.

**Benefício esperado:**  
Alta coesão e baixo acoplamento. Se a UFLA decidir adicionar um novo formato de exportação (ex: PDF), a equipe precisará apenas criar uma nova classe `ExportacaoPdfStrategy` sem tocar ou correr o risco de quebrar os códigos de exportação já existentes em JPG ou Google Agenda.

---

## 4. Alternativas consideradas
| Alternativa | Motivo para não adoção |
|---|---|
| **State** | Foi considerado para gerenciar o status das matérias (Disponível, Em Conflito, Selecionada). No entanto, foi descartado porque a lógica de negócio atual é simples o suficiente para ser tratada com variáveis booleanas e estilos condicionais no React. Implementar uma Máquina de Estados completa geraria complexidade desnecessária (overengineering). |
| **Decorator** | Foi avaliado para adicionar funcionalidades à grade exportada (ex: adicionar marca d'água na imagem). Foi rejeitado porque o objetivo principal atual é trocar algoritmos inteiros (Strategy), e não empilhar comportamentos adicionais dinamicamente. |
| **Factory Method** | Considerado para a criação de diferentes instâncias de relatórios de métricas (Analytics). Descartado temporariamente, pois a API retornará os dados em JSON padronizado e a inteligência de exibição ficará integralmente a cargo dos componentes de gráficos do Front-end (Recharts), sem necessidade de fábricas complexas no Back-end. |

---

## 5. Conclusão
A adoção destes padrões de projeto resolve problemas arquiteturais recorrentes e eleva a qualidade estrutural do **gradeUFLA**. O padrão **Repository** e o **Singleton** garantem que o Back-end (Spring Boot) seja performático, robusto e mantenha suas responsabilidades isoladas, facilitando a criação de testes unitários. No Front-end, o **Observer** resolve de forma elegante a reatividade exigida pela tela de drag-and-drop, garantindo consistência visual. Por fim, a implementação do **Strategy** evidencia o pensamento de longo prazo da equipe, entregando um sistema flexível que acomoda novos requisitos sem comprometer a estabilidade do código já entregue.
