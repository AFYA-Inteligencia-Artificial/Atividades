# 📊 Desafio de Lógica: O Sistema de Fretes

**Cenário:** Você trabalha no e-commerce "Amazonia". O sistema precisa tomar decisões automáticas sobre benefícios aos clientes.

---

A regra de negócio explicada pelo gerente foi:

> *"O cliente ganha frete grátis SE for **VIP** .... OU .... SE a compra for **maior que 100** E tiver **Cupom**. Porém, o jurídico avisou que clientes com **Suspeita de Fraude** JAMAIS podem ganhar benefícios, mesmo que sejam VIPs."*

### Desafio de Código
Combine a regra básica com a trava de segurança usando os operadores lógicos `&&` (AND) e `!` (NOT).

```javascript
/**
 * Nível 2: Regra completa com Anti-Fraude
 */
function aprovarPedido(ehVIP, valor, temCupom, ehFraude) {
    
    let aprovado = false; // <--- SUA LÓGICA AQUI
    
    return aprovado ? "APROVADO ✅" : "BLOQUEADO ❌";
}

// Testes Nível 2
console.log("VIP mas Fraude:", aprovarPedido(true, 50, false, true)); // Esperado: BLOQUEADO
console.log("Comum, Rico, Cupom, Limpo:", aprovarPedido(false, 200, true, false)); // Esperado: APROVADO
