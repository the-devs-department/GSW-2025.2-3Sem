### 🥅 **Meta da Sprint**

- **Capacidade estimada da equipe:** 30 Story Points  
- **Meta da Sprint:** User Stories de rank 1, 2, 3 e 4 (total de 25 Story Points)  
- **Previsão extra (não comprometida):** 0 Story Points  

---

### 🗓️ **Sprint 1**

| Rank | Prioridade | User Story | Estimativa (0-10) | Sprint |
|:---:|:---:|:---|:---:|:---:|
| 1 | 🔴 **Alta** | Como usuário, quero criar, editar e excluir atividades para organizar meu trabalho; | 7 | 1 |
| 2 | 🔴 **Alta** | Como usuário, quero anexar arquivos em tarefas ao concluir para garantir a entrega; | 4 | 1 |
| 3 | 🔴 **Alta** | Como usuário, quero atribuir atividades a membros da equipe para distribuir as responsabilidades; | 5 | 1 |
| 4 | 🔴 **Alta** | Como usuário, quero acessar a plataforma com Login próprio para maior autonomia e segurança; | 9 | 1 |
---

  

### **🧪 Cenários de Teste**

  

#### **História 1: CRUD de Tarefas**

*Como usuário, quero criar, editar e excluir atividades para organizar meu trabalho;*

  

**Cenário 1.1: Criar Atividade**

*  **Dado** que estou logado no sistema

*  **Quando** clico no botão "Nova Tarefa" e preencho o título e a descrição da atividade

*  **Então** a atividade é criada e exibida na lista.

  

**Cenário 1.2: Editar Atividade**

*  **Dado** que uma atividade existe na lista

*  **Quando** clico no ícone de "Editar" da atividade e modifico o título e/ou a descrição

*  **Então** a atividade é atualizada com as novas informações.

  

**Cenário 1.3: Excluir Atividade**

*  **Dado** que uma atividade existe na lista

*  **Quando** clico no ícone de "Excluir" da atividade e confirmo a exclusão

*  **Então** a atividade é removida da lista.

  

---

  

#### **História 2: Anexos em Tarefas**

*Como usuário, quero anexar arquivos em tarefas ao concluir para garantir a entrega;*

  

**Cenário 2.1: Anexar Arquivo ao Concluir Tarefa**

*  **Dado** que estou concluindo uma tarefa

*  **Quando** seleciono um arquivo para anexar (ex: imagem, PDF)

*  **Então** o arquivo é anexado com sucesso à tarefa concluída, e o arquivo pode ser visualizado/baixado posteriormente.

  

**Cenário 2.2: Anexar Múltiplos Arquivos**

*  **Dado** que estou concluindo uma tarefa

*  **Quando** seleciono múltiplos arquivos para anexar

*  **Então** todos os arquivos são anexados com sucesso à tarefa.

  

---

  

#### **História 3: Atribuição a Membros**

*Como usuário, quero atribuir atividades a membros da equipe para distribuir as responsabilidades;*

  

**Cenário 3.1: Atribuir Tarefa a um Membro Específico**

*  **Dado** que estou criando/editando uma atividade

*  **Quando** seleciono um membro da equipe na lista de atribuição

*  **Então** a atividade é atribuída a esse membro, e o membro atribuído é exibido na tarefa.

  

**Cenário 3.2: Filtrar Tarefas por Membro da Equipe**

*  **Dado** que tarefas foram atribuídas a diferentes membros

*  **Quando** eu filtro as tarefas por um membro específico

*  **Então** apenas as tarefas atribuídas a esse membro são exibidas.

  

---

  

#### **História 4: Autenticação Básica**

*Como usuário, quero acessar a plataforma com Login próprio para maior autonomia e segurança;*

  

**Cenário 4.1: Cadastro de Novo Usuário**

*  **Dado** que estou na tela de login/cadastro

*  **Quando** clico em "Registrar" e preencho os dados necessários (email, senha)

*  **Então** minha conta é criada com sucesso, e sou redirecionado para a tela inicial logado.

  

**Cenário 4.2: Login com Credenciais Válidas**

*  **Dado** que possuo uma conta registrada

*  **Quando** insiro meu email e senha corretos

*  **Então** sou autenticado com sucesso, e sou redirecionado para a tela inicial do aplicativo.

  

**Cenário 4.3: Login com Credenciais Inválidas**

*  **Dado** que estou na tela de login

*  **Quando** insiro email ou senha incorretos

*  **Então** o sistema exibe uma mensagem de erro, e não sou logado no sistema.

  

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
