### 🥅 **Meta da Sprint**

- **Capacidade estimada da equipe:** 30 Story Points  
- **Meta da Sprint:** User Stories de rank 5, 6, 7 e 8 (total de 25 Story Points)  
- **Previsão extra (não comprometida):** 0 Story Points  

---

### 🗓️ **Sprint 2**

| Rank | Prioridade | User Story | Estimativa (0-10) | Sprint |
|:---:|:---:|:---|:---:|:---:|
| 5 | 🔴 **Alta** | Como usuário, quero visualizar um log de auditoria para ter melhor controle das alterações da equipe em relação às tarefas; | 9 | 2 |
| 6 | 🟠 **Média** | Como usuário, quero visualizar tanto as tarefas gerais da equipe quanto as minhas por meio de um perfil, para melhor gerenciamento; | 4 | 2 |
| 7 | 🟠 **Média** | Como usuário, quero receber notificações das minhas tarefas na interface para assim ter melhor autonomia do meu tempo; | 3 | 2 |
| 8 | 🟠 **Média** | Como usuário, quero recuperar minha senha via e-mail para garantir maior segurança da minha conta; | 5 | 2 |

---

### **🧪 Cenários de Teste**

#### **História 5: Log de Auditoria**

*Como usuário, quero visualizar um log de auditoria para ter melhor controle das alterações da equipe em relação às tarefas;*

**Cenário 5.1: Visualizar Log de Auditoria (Administrador)**

- **Dado** que estou logado como um usuário com perfil de administrador  
- **Quando** navego para a seção de Log de Auditoria  
- **Então** o sistema exibe uma lista de todas as alterações de tarefas, incluindo usuário, data/hora, tipo de alteração e dados relevantes.  

**Cenário 5.2: Acesso Negado ao Log de Auditoria (Usuário Comum)**

- **Dado** que estou logado como um usuário comum (não administrador)  
- **Quando** tento acessar a seção de Log de Auditoria diretamente pela URL  
- **Então** o sistema nega o acesso e exibe uma mensagem de erro informando que não tenho permissão.  

**Cenário 5.3: Imutabilidade dos Registros de Auditoria**

- **Dado** que um registro de auditoria foi criado para uma alteração de tarefa  
- **Quando** tento editar ou excluir este registro  
- **Então** o sistema impede a alteração/exclusão e mantém o registro original inalterado.  

---

#### **História 6: Visualização de Tarefas por Perfil**

*Como usuário, quero visualizar tanto as tarefas gerais da equipe quanto as minhas por meio de um perfil, para melhor gerenciamento;*

**Cenário 6.1: Visualizar Todas as Tarefas (Administrador)**

- **Dado** que estou logado como administrador  
- **Quando** acesso a tela de visualização de tarefas  
- **Então** o sistema exibe por padrão todas as tarefas da equipe.  

**Cenário 6.2: Alternar para Minhas Tarefas (Administrador)**

- **Dado** que estou logado como administrador e visualizando todas as tarefas  
- **Quando** clico na opção para "Minhas Tarefas"  
- **Então** o sistema filtra e exibe apenas as tarefas atribuídas a mim, e a interface indica claramente a visualização ativa.  

**Cenário 6.3: Visualizar Minhas Tarefas (Usuário Comum)**

- **Dado** que estou logado como usuário comum  
- **Quando** acesso a tela de visualização de tarefas  
- **Então** o sistema exibe apenas as tarefas atribuídas a mim, sem acesso às tarefas dos outros usuários ou da equipe geral.  

**Cenário 6.4: Ordenação Padrão por Prazo**

- **Dado** que estou visualizando uma lista de tarefas (todas ou só minhas)  
- **Quando** a lista é carregada  
- **Então** as tarefas são ordenadas por prazo (data e hora de conclusão) por padrão.  

---

#### **História 7: Notificações de Tarefas**

*Como usuário, quero receber notificações das minhas tarefas na interface para assim ter melhor autonomia do meu tempo;*

**Cenário 7.1: Receber Notificação de Tarefa Criada**

- **Dado** que estou logado no sistema  
- **Quando** uma nova tarefa é criada e atribuída a mim  
- **Então** recebo uma notificação na interface com o título da tarefa, o nome do usuário que a criou e o tipo de evento (Tarefa Criada).  

**Cenário 7.2: Receber Notificação de Prazo Próximo**

- **Dado** que tenho uma tarefa atribuída com o prazo se aproximando (24h antes do vencimento)  
- **Quando** o sistema verifica os prazos  
- **Então** recebo uma notificação na interface com o título, prazo e tipo de evento (Prazo Próximo).  

**Cenário 7.3: Acessar Tarefa pela Notificação**

- **Dado** que recebi uma notificação na interface  
- **Quando** clico na notificação  
- **Então** sou direcionado para o card da tarefa correspondente.  

**Cenário 7.4: Visualizar Histórico de Notificações**

- **Dado** que tenho várias notificações recebidas  
- **Quando** clico no ícone de sininho  
- **Então** um dropdown é exibido, mostrando as notificações mais recentes (até 30) e permitindo rolar para ver as antigas.  

**Cenário 7.5: Limite de Notificações no Histórico**

- **Dado** que recebi mais de 30 notificações  
- **Quando** verifico o histórico  
- **Então** as mais antigas (além do limite de 30) foram apagadas automaticamente.  

---

#### **História 8: Recuperação de Senha por E-mail**

*Como usuário, quero recuperar minha senha via e-mail para garantir maior segurança da minha conta;*

**Cenário 8.1: Solicitar Recuperação com E-mail Válido**

- **Dado** que estou na tela de login e clico em "Esqueci minha senha"  
- **Quando** insiro um e-mail cadastrado e clico em "Enviar"  
- **Então** o sistema exibe mensagem de sucesso, e um link para redefinição de senha é enviado para meu e-mail.  

**Cenário 8.2: Solicitar Recuperação com E-mail Não Cadastrado**

- **Dado** que estou na tela de recuperação  
- **Quando** insiro um e-mail que não está cadastrado e clico em "Enviar"  
- **Então** o sistema exibe mensagem amigável "Não foi possível encontrar uma conta para este e-mail."  

**Cenário 8.3: Redefinir Senha com Link Válido**

- **Dado** que recebi um link válido por e-mail (até 30 minutos)  
- **Quando** clico no link e insiro uma nova senha  
- **Então** sistema exibe sucesso, e consigo login com a nova senha.  

**Cenário 8.4: Redefinir Senha com Link Expirado**

- **Dado** que o link expirou após 30 minutos  
- **Quando** clico no link  
- **Então** sistema informa inválido/expirado, e sou redirecionado para nova solicitação.  

**Cenário 8.5: Redefinir Senha com Nova Senha Inválida**

- **Dado** que estou na tela de redefinição  
- **Quando** insiro senha que não atende requisitos  
- **Então** sistema exibe erros para cada requisito não atendido, e a senha não é redefinida.  

---

# **DoR & DoD**

## **DoR (Definition of Ready)**

- 📝 História clara no formato: **Como [perfil], quero [ação], para [valor]**
- 🔗 Dependências identificadas
- 🧪 Dados de teste definidos
- 🖼️ Mockups ou fluxos UX disponíveis
- ✅ Critérios de aceitação definidos

## **DoD (Definition of Done)**

- 🤝 Código revisado e mergeado
- 🧪 Testes unitários e de integração passando
- ✅ Critérios de aceitação validados em homologação
- 📊 Logs, métricas e alertas configurados
- 📜 Documentação em dia
