# 🏥 Auditoria Digital de Plano de Saúde

**Cenário:** Vocês foram contratados pela "SaúdeTech", uma operadora de planos de saúde. O sistema legado era lento porque a auditoria era manual. Agora, vocês precisam criar o algoritmo central que autoriza ou bloqueia exames, cirurgias e consultas.

---

### 📋 Regras de Negócio (Atenção à precedência!)

O sistema deve retornar um dos seguintes status: **"BLOQUEADO"**, **"SUSPENSO"**, **"NEGADO"**, **"AUDITORIA"** ou **"AUTORIZADO"**.

1. **Anti-Fraude (Absoluta):** Se houver sinalização de fraude (`fraudeDetectada`), retorne **"BLOQUEADO"** imediatamente.
2. **Inadimplência:** Se o atraso no pagamento (`diasAtraso`) for maior que 60 dias, retorne **"SUSPENSO"**.
3. **Regra de Ouro (Emergência):** Se for uma emergência (`ehEmergencia` = true), o procedimento é **"AUTORIZADO"** ignorando regras de carência e rede (regras 4, 5 e 8). *Nota: Fraude e Inadimplência ainda bloqueiam emergências.*
4. **Carência de Rotina:** Se o cliente tem menos de 30 dias de plano (`diasPlano`) e o procedimento for "ROTINA", retorne **"NEGADO"**.
5. **Carência de Cirurgia:** Se o cliente tem menos de 180 dias de plano e o procedimento for "CIRURGIA", retorne **"NEGADO"**.
6. **Cobertura Estética:** Procedimentos do tipo "ESTETICA" só são cobertos se o plano for "PREMIUM". Se for "BASICO", retorne **"NEGADO"**.
7. **Risco por Idade:** Se o paciente tiver mais de 65 anos e o procedimento for "ALTO_RISCO", retorne **"AUDITORIA"** (avaliação médica manual).
8. **Rede Credenciada:** Se o atendimento for fora da rede (`foraDaRede` = true) e o plano for "BASICO", retorne **"NEGADO"**. (Planos PREMIUM cobrem fora da rede).
9. **Trava Financeira:** Se o valor do procedimento ultrapassar R$ 15.000 e o plano for "BASICO", retorne **"AUDITORIA"**.
10. **Aprovação Padrão:** Se o pedido não esbarrar em nenhuma das restrições acima, retorne **"AUTORIZADO"**.

---

### 💻 Desafio de Código

**Trabalho em Dupla:** A ordem dos fatores altera o resultado! Se vocês testarem a carência antes da emergência, o paciente pode correr risco de vida. Estruturem a lógica com sabedoria.

```javascript
/**
 * Nível Master: Motor de Autorização Médica
 */
function autorizar(
    fraudeDetectada, diasAtraso, ehEmergencia, diasPlano, 
    tipoProcedimento, tipoPlano, idade, foraDaRede, valor
) {
    
    // SUA LÓGICA AQUI
    // Dica: Usem Guard Clauses (if... return) para matar as regras mais fortes primeiro.


}

// 🧪 Bateria de Testes Oficiais (O código deve passar em todos!)

// 1. Fraude sempre bloqueia
console.log(autorizar(true, 0, true, 500, "ROTINA", "PREMIUM", 30, false, 100)); // BLOQUEADO

// 2. Inadimplência suspende
console.log(autorizar(false, 65, false, 500, "ROTINA", "BASICO", 30, false, 100)); // SUSPENSO

// 3. Emergência salva da carência
console.log(autorizar(false, 0, true, 10, "CIRURGIA", "BASICO", 40, true, 5000)); // AUTORIZADO

// 4. Carência Rotina
console.log(autorizar(false, 0, false, 20, "ROTINA", "BASICO", 25, false, 150)); // NEGADO

// 5. Carência Cirurgia
console.log(autorizar(false, 0, false, 100, "CIRURGIA", "PREMIUM", 45, false, 8000)); // NEGADO

// 6. Estética no Básico
console.log(autorizar(false, 0, false, 300, "ESTETICA", "BASICO", 30, false, 2000)); // NEGADO

// 7. Risco por Idade
console.log(autorizar(false, 0, false, 400, "ALTO_RISCO", "PREMIUM", 70, false, 5000)); // AUDITORIA

// 8. Fora da rede no Básico
console.log(autorizar(false, 0, false, 500, "ROTINA", "BASICO", 35, true, 300)); // NEGADO

// 9. Trava Financeira no Básico
console.log(autorizar(false, 0, false, 500, "CIRURGIA", "BASICO", 50, false, 16000)); // AUDITORIA

// 10. Tudo certo - Premium fora da rede
console.log(autorizar(false, 0, false, 300, "ROTINA", "PREMIUM", 30, true, 500)); // AUTORIZADO
