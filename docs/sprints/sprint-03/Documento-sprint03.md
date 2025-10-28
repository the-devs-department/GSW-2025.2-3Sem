### 🥅 **Meta da Sprint**

- **Capacidade estimada da equipe:** 30 Story Points  
- **Meta da Sprint:** User Stories de rank 9, 10, 11, 12, 13 e 14 (total de 30 Story Points)  
- **Previsão extra (não comprometida):** 0 Story Points  

---

### 🗓️ **Sprint 3**

| Rank | Prioridade | User Story                                                                                                                                                                      | Estimativa (0-10) | Sprint |
|:----:|:----------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------:|:------:|
|  9   | 🟠 Média   | Como Usuário, quero criar e gerenciar equipes e seus membros para organizar a colaboração e a atribuição de tarefas;                                                           |         8         |   3    |
| 10   | 🟠 Média   | Como usuário, quero gerenciar minhas tarefas em um calendário integrado na plataforma, com a opção de sincronizá-las com o Google Calendar, para otimizar meu planejamento pessoal e de equipe. |         8         |   3    |
| 11   | 🟡 Baixa   | Como usuário, quero clicar em uma tarefa e visualizar um modal com seu resumo, histórico de alterações (para administradores) e a sinalização visual de prazos vencidos, para ter acesso rápido às informações importantes. |         7         |   3    |
| 12   | 🟡 Baixa   | Como administrador, quero filtrar o log de auditoria por data, usuário e tipo de alteração, para encontrar informações específicas sobre as modificações das tarefas da equipe. |         4         |   3    |
| 13   | 🟡 Baixa   | Como usuário, quero filtrar minhas tarefas por meio de uma barra de pesquisa e botão de filtro para encontrar e gerenciar minhas atividades de forma eficiente.               |         3         |   3    |
| 14   | 🟡 Baixa   | Como usuário, quero arrastar e soltar tarefas entre diferentes colunas de status para gerenciar meu trabalho de forma intuitiva.                                               |         2         |   3    |

---

### **🧪 Cenários de Teste**

#### História 1.9: Como usuário, quero criar e gerenciar equipes e seus membros para organizar a colaboração e a atribuição de tarefas.

**Cenário 1.9.1: Criação de Equipe com Sucesso**

- **Dado** que estou logado como administrador e acesso a aba "Equipes"  
- **Quando** clico no botão "Criar Nova Equipe", preencho o nome da equipe (único e válido), e confirmo a criação  
- **Então** a equipe é criada com sucesso, o administrador é automaticamente associado, e a equipe aparece na lista.  

**Cenário 1.9.2: Adicionar Membro Existente à Equipe**

- **Dado** que tenho uma equipe criada, estou logado como administrador da equipe, e existe um usuário cadastrado no sistema  
- **Quando** acesso a aba "Equipes", seleciono a equipe desejada, clico em "Adicionar Membro", informo o e-mail de um usuário existente e confirmo a adição  
- **Então** o membro é adicionado à equipe, o usuário convidado recebe uma notificação na interface e por e-mail, e a lista de membros é atualizada.  

**Cenário 1.9.3: Aceitar Convite de Equipe (via Interface)**

- **Dado** que estou logado e tenho um convite de equipe pendente na interface  
- **Quando** clico no botão de notificação de convite e, no modal, visualizo o convite e clico em "Aceitar"  
- **Então** sou adicionado à equipe, o convite é removido das notificações, e a equipe aparece na minha lista de equipes.  

**Cenário 1.9.4: Recusar Convite de Equipe (via E-mail)**

- **Dado** que tenho um convite de equipe pendente no meu e-mail  
- **Quando** abro o e-mail de convite, clico no link de redirecionamento para a página de equipes e, na página, clico em "Recusar" o convite  
- **Então** o convite é removido, e não sou adicionado à equipe.  

**Cenário 1.9.5: Edição de Equipe por Administrador**

- **Dado** que estou logado como administrador da equipe  
- **Quando** acesso a aba "Equipes", seleciono a equipe, clico em "Editar Equipe", altero o nome e/ou descrição da equipe e confirmo a edição  
- **Então** as informações da equipe são atualizadas.  

**Cenário 1.9.6: Exclusão Lógica de Equipe**

- **Dado** que estou logado como administrador da equipe  
- **Quando** acesso a aba "Equipes", seleciono a equipe, clico em "Excluir Equipe" e confirmo a exclusão  
- **Então** a equipe é marcada como inativa no banco de dados, seus membros e tarefas são desvinculados, e a equipe não aparece mais na lista de equipes ativas.  

**Cenário 1.9.7: Interação Dinâmica com Páginas ao Selecionar Equipe**

- **Dado** que estou logado, com múltiplas equipes e tarefas/logs associados  
- **Quando** acesso a aba "Equipes", seleciono uma equipe e navego para "Minhas Tarefas", "Todas as Tarefas", "Log de Auditoria" ou “Calendário”  
- **Então** as informações exibidas nas páginas são filtradas e atualizadas para mostrar apenas os dados relacionados à equipe selecionada.  

**Cenário 1.9.8: Aviso de Nenhuma Equipe Selecionada**

- **Dado** que estou logado e nenhuma equipe está selecionada  
- **Quando** acesso uma aba que depende de uma equipe (ex: "Todas as Tarefas")  
- **Então** um aviso "Selecione uma equipe para visualizar suas respectivas tarefas" é exibido, juntamente com um botão para retornar à aba "Equipes".  

---

#### História 2.0: Como usuário, quero gerenciar minhas tarefas em um calendário integrado na plataforma, com a opção de sincronizá-las com o Google Calendar, para otimizar meu planejamento pessoal e de equipe.

**Cenário 2.0.1: Visualização de Tarefas no Calendário Integrado**

- **Dado** que estou logado e tenho tarefas criadas com prazos definidos  
- **Quando** acesso a aba "Calendário" e visualizo em diferentes formatos (dia, mês, ano)  
- **Então** todas as minhas tarefas são exibidas no calendário com seus respectivos prazos, e a interação com as tarefas (clicar para ver detalhes) funciona corretamente.  

**Cenário 2.0.2: Conexão com Google Calendar**

- **Dado** que estou logado e tenho uma conta do Google Calendar disponível  
- **Quando** acesso as configurações de integração do calendário, clico em "Conectar Google Calendar" e autorizo a integração via pop-up do Google  
- **Então** o sistema exibe o status "Conectado" com o Google Calendar, e as tarefas são sincronizadas.  

**Cenário 2.0.3: Sincronização Automática de Tarefas para Google Calendar**

- **Dado** que estou logado e o Google Calendar está conectado  
- **Quando** crio uma nova tarefa com prazo de conclusão no sistema ou edito o prazo de uma tarefa existente  
- **Então** a nova tarefa aparece como um evento no Google Calendar, e as alterações de prazo são refletidas nos eventos existentes.  

**Cenário 2.0.4: Desativação da Sincronização com Google Calendar**

- **Dado** que estou logado e o Google Calendar está conectado  
- **Quando** acesso as configurações de integração do calendário e clico em "Desconectar Google Calendar"  
- **Então** o sistema exibe o status "Desconectado", e novas alterações de tarefas não são mais sincronizadas com o Google Calendar.  

---

#### História 2.1: Como usuário, quero clicar em uma tarefa e visualizar um modal com seu resumo, histórico de alterações (para administradores) e a sinalização visual de prazos vencidos, para ter acesso rápido às informações importantes.

**Cenário 2.1.1: Visualização de Modal de Tarefa (Usuário Comum)**

- **Dado** que estou logado  
- **Quando** clico em qualquer tarefa na lista  
- **Então** um modal é exibido com os detalhes da tarefa (título, descrição, prazo, responsável, status, anexos). O modal é somente leitura e pode ser fechado facilmente, e não exibe o histórico de alterações.  

**Cenário 2.1.2: Visualização de Modal de Tarefa com Histórico (Administrador)**

- **Dado** que estou logado como administrador  
- **Quando** clico em qualquer tarefa na lista  
- **Então** um modal é exibido com os detalhes da tarefa e, adicionalmente, um histórico de todas as alterações feitas naquela tarefa (quem fez, data/hora, tipo de alteração).  

**Cenário 2.1.3: Sinalização Visual de Prazo Vencido (no Card e no Modal)**

- **Dado** que estou logado e tenho uma tarefa cujo prazo de conclusão já passou  
- **Quando** visualizo a lista de tarefas e clico na tarefa com prazo vencido para abrir o modal  
- **Então** um ícone de alerta (ex: triângulo vermelho) é exibido no card da tarefa e dentro do modal. Ao passar o mouse sobre o ícone, um tooltip informa que a tarefa está atrasada.  

**Cenário 2.1.4: Remoção da Sinalização de Prazo Vencido**

- **Dado** que estou logado e tenho uma tarefa com prazo vencido e sinalização ativa  
- **Quando** concluo a tarefa ou atualizo seu prazo para uma data futura  
- **Então** o ícone de alerta de prazo vencido desaparece do card da tarefa e do modal.  

---

#### História 2.2: Como administrador, quero filtrar o log de auditoria por data, usuário e tipo de alteração, para encontrar informações específicas sobre as modificações das tarefas da equipe.

**Cenário 2.2.1: Filtrar Log de Auditoria por Período de Datas**

- **Dado** que estou logado como administrador e o log de auditoria possui registros de diferentes datas  
- **Quando** acesso a interface do log de auditoria, seleciono um período de datas específico nos filtros e aplico o filtro  
- **Então** o log exibe apenas os registros dentro do período de datas selecionado, mantendo a ordenação padrão.  

**Cenário 2.2.2: Filtrar Log de Auditoria por Usuário**

- **Dado** que estou logado como administrador e o log de auditoria possui registros de diferentes usuários  
- **Quando** acesso a interface do log de auditoria, seleciono um usuário específico no filtro de usuário e aplico o filtro  
- **Então** o log exibe apenas os registros de ações realizadas pelo usuário selecionado.  

**Cenário 2.2.3: Filtrar Log de Auditoria por Tipo de Evento**

- **Dado** que estou logado como administrador e o log de auditoria possui diferentes tipos de eventos (criação, edição, exclusão)  
- **Quando** acesso a interface do log de auditoria, seleciono um tipo de evento (ex: "edição de tarefa") no filtro de tipo e aplico o filtro  
- **Então** o log exibe apenas os registros do tipo de evento selecionado.  

**Cenário 2.2.4: Combinar Múltiplos Filtros no Log de Auditoria**

- **Dado** que estou logado como administrador e o log de auditoria possui dados variados  
- **Quando** acesso a interface do log de auditoria, seleciono um período de datas, um usuário e um tipo de evento, e aplico os filtros combinados  
- **Então** o log exibe apenas os registros que atendem a todos os critérios de filtro combinados.  

---

#### História 2.3: Como usuário, quero filtrar minhas tarefas por meio de uma barra de pesquisa e um botão de filtro para encontrar e gerenciar minhas atividades de forma eficiente.

**Cenário 2.3.1: Pesquisa de Tarefas por Texto na Barra de Pesquisa**

- **Dado** que estou logado e tenho tarefas contendo títulos e descrições variados  
- **Quando** digito um termo de pesquisa na barra de pesquisa (ex: parte de um título ou descrição)  
- **Então** a lista de tarefas é atualizada dinamicamente para mostrar apenas as tarefas que correspondem ao termo de pesquisa em seus campos relevantes.  

**Cenário 2.3.2: Filtrar Tarefas por Categoria**

- **Dado** que estou logado e tenho tarefas categorizadas  
- **Quando** clico no botão de filtro, seleciono uma categoria específica no modal de filtro e aplico o filtro  
- **Então** a lista de tarefas é atualizada para mostrar apenas as tarefas da categoria selecionada.  

**Cenário 2.3.3: Filtrar Tarefas por Status**

- **Dado** que estou logado e tenho tarefas em diferentes status (Não Iniciada, Em Andamento, Concluída, Atrasada)  
- **Quando** clico no botão de filtro, seleciono um status específico (ex: "Atrasada") no modal de filtro e aplico o filtro  
- **Então** a lista de tarefas é atualizada para mostrar apenas as tarefas com o status selecionado.  

**Cenário 2.3.4: Combinar Pesquisa e Filtros**

- **Dado** que estou logado e tenho tarefas variadas  
- **Quando** digito um termo de pesquisa na barra de pesquisa, clico no botão de filtro, seleciono um ou mais critérios (ex: categoria e status) e aplico os filtros  
- **Então** a lista de tarefas é atualizada para mostrar apenas as tarefas que correspondem ao termo de pesquisa E aos critérios de filtro selecionados.  

---

#### História 2.4: Como usuário, quero arrastar e soltar tarefas entre diferentes colunas de status para gerenciar meu trabalho de forma intuitiva.

**Cenário 2.4.1: Arrastar e Soltar Tarefa entre Colunas de Status**

- **Dado** que estou logado e tenho tarefas exibidas em um quadro de colunas de status (ex: "Não Iniciada", "Em Andamento")  
- **Quando** clico e arrasto uma tarefa da coluna "Não Iniciada" para a coluna "Em Andamento" e solto a tarefa na nova coluna  
- **Então** a tarefa é movida visualmente para a nova coluna, o status da tarefa é automaticamente atualizado no sistema, e o feedback visual da ação é exibido.  

**Cenário 2.4.2: Visualizar Detalhes da Tarefa no Quadro**

- **Dado** que estou logado e tenho tarefas exibidas no quadro de status  
- **Quando** clico em uma tarefa no quadro  
- **Então** um modal com os detalhes da tarefa é exibido.  

**Cenário 2.4.3: Responsividade do Quadro de Tarefas**

- **Dado** que estou logado  
- **Quando** acesso o quadro de tarefas em diferentes tamanhos de tela (desktop, tablet, celular)  
- **Então** o quadro de tarefas se ajusta e permanece funcional em todos os tamanhos de tela, permitindo a interação de arrastar e soltar.  

---

# **DoR & DoD**

## DoR (Definition of Ready)

- 📝 História clara no formato: **Como [perfil], quero [ação], para [valor]**  
- 🔗 Dependências identificadas  
- 🧪 Dados de teste definidos  
- 🖼️ Mockups ou fluxos UX disponíveis  
- ✅ Critérios de aceitação definidos  

## DoD (Definition of Done)

- 🤝 Código revisado e mergeado  
- 🧪 Testes unitários e de integração passando  
- ✅ Critérios de aceitação validados em homologação  
- 📊 Logs, métricas e alertas configurados  
- 📜 Documentação em dia  
