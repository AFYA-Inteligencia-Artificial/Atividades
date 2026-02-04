# 📊 Desafio de Lógica: O Sistema de Fretes

**Cenário:** Você trabalha no e-commerce "Amazonia". O sistema precisa tomar decisões automáticas sobre benefícios aos clientes.

---

## 🟢 Nível 1: A Regra do Frete Grátis (Básico)

A regra de negócio explicada pelo gerente foi:
> *"O cliente ganha frete grátis SE for **VIP** .... OU .... SE a compra for **maior que 100** E tiver **Cupom**."*

### 1. Modelagem Lógica
*   **P (VIP):** Cliente é VIP?
*   **Q (Alta):** Compra > 100?
*   **R (Cupom):** Tem cupom?

**Fórmula:** `P OR (Q AND R)`

### 2. Tabela Verdade
*(Marque V ou F)*

| VIP (P) | Alta (Q) | Cupom (R) | **Resultado** |
| :---: | :---: | :---: | :---: |
| F | F | F | **?** |
| F | V | F | **?** |
| F | V | V | **?** |
| V | F | F | **?** |

### 3. Código (JS)
```javascript
function simularFrete(ehVIP, valor, temCupom) {
    // Implemente a lógica Nível 1
    return ehVIP || (valor > 100 && temCupom);
}
```

---

## 🔴 Nível 2: O Sistema Anti-Fraude (Avançado)

**Novo Cenário:** O jurídico avisou que clientes com **Suspeita de Fraude** JAMAIS podem ganhar benefícios, mesmo que sejam VIPs.

A nova regra é:
> *"A regra do Nível 1 continua valendo... MAS APENAS SE **NÃO** houver suspeita de fraude."*

### 1. Nova Modelagem
*   **S (Fraude):** É suspeita de fraude? (`true`/`false`)
*   **Fórmula:** `( [Regra Antiga] ) AND ( NOT S )`
*   **Expandida:** `( P OR (Q AND R) ) AND NOT S`

### 2. Tabela Verdade Complexa
Aqui a coisa fica séria. O **operador NOT** inverte tudo.

| VIP (P) | Alta (Q) | Cupom (R) | Fraude (S) | Regra Antiga (X) | NÃO Fraude (~S) | **Resultado Final** `X AND ~S` |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| V | V | V | **F** | V | V | **V** (Ganhou!) |
| V | V | V | **V** | V | F | **F** (Barrado!) |
| F | V | V | **F** | V | V | **?** |
| V | F | F | **V** | V | F | **?** |

### 3. Desafio de Código
Use parênteses corretamente!

```javascript
/**
 * Nível 2: Regra completa com Anti-Fraude
 */
function aprovarPedido(ehVIP, valor, temCupom, ehFraude) {
    
    // Passo 1: Calcula a regra básica (Nível 1)
    let regraBasica = ehVIP || (valor > 100 && temCupom);
    
    // Passo 2: Aplica a restrição de fraude (Use o operador ! para NOT)
    // Lembre-se: Só aprova se regraBasica for TRUE -E- ehFraude for FALSE.
    
    let aprovado = false; // <--- SUA LÓGICA AQUI
    
    return aprovado ? "APROVADO ✅" : "BLOQUEADO �";
}

// Testes Nível 2
console.log("VIP mas Fraude:", aprovarPedido(true, 50, false, true)); // Esperado: BLOQUEADO
console.log("Comum, Rico, Cupom, Limpo:", aprovarPedido(false, 200, true, false)); // Esperado: APROVADO
```

---
