# Exercício Prático: Estratégias de Busca (BFS vs DFS)
**Disciplina:** Inteligência Artificial - Resolução de Problemas I
**Professor:** Karan Luciano

---

## 🎯 Objetivo
O objetivo deste exercício é exercitar a capacidade analítica de escolher a melhor estratégia de busca (cega) para diferentes tipos de problemas. Você não precisa programar, apenas **formular cenários**.

---

## 📝 A Atividade

Você deve descrever **dois cenários originais** (problemas do mundo real ou jogos) onde um agente inteligente precisa encontrar um objetivo.
*   Para o **Cenário A**, a Busca em Largura (BFS) deve ser a melhor escolha.
*   Para o **Cenário B**, a Busca em Profundidade (DFS) deve ser a melhor escolha (ou a única viável).

Para cada cenário, você deve preencher a seguinte ficha:

### Estrutura da Resposta

1.  **Descrição do Problema:** (O que o agente deve fazer? Qual o objetivo?)
2.  **Características do Ambiente:**
    *   O mapa/espaço de estados é grande ou pequeno?
    *   A solução (objetivo) está perto do início ou longe (profunda)?
    *   Existem muitos caminhos ou poucos?
    *   A memória disponível é ilimitada ou restrita?
3.  **Algoritmo Escolhido:** (BFS ou DFS)
4.  **Justificativa:** (Por que este algoritmo é melhor que o outro *neste caso específico*?)

---

## 💡 Exemplos para Inspiração (Não copie!)

### Exemplo de Cenário BFS (Foco na Garantia/Otimalidade)
*   **Problema:** Um robô em um labirinto pegando fogo precisa encontrar a saída *mais próxima* para salvar humanos.
*   **Justificativa:** Como o tempo é crítico e queremos a saída *mais perto* (menor número de passos), o BFS é ideal pois ele garante encontrar a solução mais rasa primeiro. O DFS poderia mergulhar num corredor longo e demorar muito para voltar.

### Exemplo de Cenário DFS (Foco na Memória/Profundidade)
*   **Problema:** Um programa que precisa gerar uma frase válida em português com 50 palavras.
*   **Justificativa:** A árvore de possibilidades (palavras do dicionário) é gigantesca. O BFS tentaria guardar todas as frases de 1 palavra, depois todas de 2 palavras... a memória explodiria. O DFS segue uma linha de raciocínio (sujeito -> verbo -> predicado) até o fim, gastando pouca memória.

---

## 🚀 Entrega
Entregue um documento PDF ou Texto com os dois cenários descritos.
> **Enviar para o professor:** `karan.luciano@afya.com.br`
> 
> **Assunto do E-mail:** [IA] Nome do Aluno - Atividade Busca
