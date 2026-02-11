# Trabalho Prático: Git & Algoritmos de Busca - O Entregador

**Disciplina:** Inteligência Artificial

**Formato:** Dupla ou Trio

---

## 🎯 Objetivo
Este trabalho tem dois objetivos:
1.  **Técnico:** Implementar algoritmos de busca (BFS e DFS) em um cenário novo.
2.  **Colaborativo:** Simular um fluxo de trabalho real de desenvolvimento de software usando **Git e GitHub**.

---

## 🏗️ O Cenário: "O Entregador de Pizza"
Vocês devem criar um programa onde um entregador precisa levar uma pizza da **Pizzaria** até a **Casa do Cliente**.
O mapa da cidade deve ter pelo menos **10 locais** (nós) conectados.

---

## 📝 Requisitos do Git (Obrigatórios)
A nota do trabalho depende tanto do código quanto do uso correto do Git.

1.  **Repositório:** Criar um repositório público no GitHub.
2.  **Colaboração:** Todos os integrantes devem ser "Collaborators" no repositório.
3.  **Branches:** NINGUÉM commita direto na `main` (exceto o setup inicial). Cada funcionalidade deve ter sua própria branch.
    *   Ex: `feature/mapa`, `feature/bfs`, `feature/dfs`.
4.  **Pull Requests (PR):**
    *   Cada integrante deve abrir pelo menos **1 Pull Request**.
    *   O PR deve ser **revisado e aprovado** por outro integrante antes do merge.
5.  **Commits:**
    *   Cada integrante deve ter pelo menos **5 commits** no histórico final.
    *   Mensagens de commit devem ser claras (Ex: "Adiciona função de busca", "Corrige bug no mapa").

---

## 💻 Divisão de Tarefas Sugerida

### EXEMPLO:
*   **Integrante A (Branch `feature/mapa`):**
    *   Cria o arquivo `sistema.js` (ou `index.js`).
    *   Define o Grafo (Mapa com 10 locais).
    *   Faz o PR para a main.
*   **Integrante B (Branch `feature/bfs`):**
    *   Cria a função BFS no código.
    *   Testa a rota mais curta.
    *   Faz o PR.
*   **Integrante A (Branch `feature/dfs`):**
    *   Cria a função DFS no código.
    *   Testa uma rota alternativa.
    *   Faz o PR.
*   **Integrante B (Branch `feature/menu`):**
    *   Cria um menu simples para escolher qual algoritmo rodar.
    *   Faz o PR final.

---

## 🏆 Critérios de Avaliação
1.  **Código Funcional:** O entregador acha a casa do cliente?
2.  **Fluxo Git:**
    *   Branches separadas? (Sim/Não)
    *   Pelo menos 1 PR por pessoa? (Sim/Não)
    *   Pelo menos 5 commits por pessoa? (Sim/Não)
    *   Histórico organizado?

## 🚀 Como Entregar (Importante!)

1.  **Pull Requests:** Todos os PRs devem ser feitos para a branch `main` (ou `master`) do repositório do grupo.
2.  **Envio Final:** Apenas **UM integrante** do grupo deve enviar o link do repositório para o e-mail:
    *   📧 **Para:** `karan.luciano@afya.com.br`
    *   **CC (Cópia Carbono):** Adicionar os e-mails dos demais integrantes do grupo.
    *   📨 **Assunto:** `[IA] Nome dos Alunos - Atividade Busca`

O professor avaliará o código na branch `main` e a aba "Insights/Contributors" para verificar os commits individuais.
