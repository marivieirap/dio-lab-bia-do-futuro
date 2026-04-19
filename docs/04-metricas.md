# Avaliação e Métricas

## Como Avaliar seu Agente

A avaliação foi realizada de duas formas:

1. **Testes estruturados:** Foram definidos cenários com perguntas e respostas esperadas;
2. **Feedback real:** Usuários testaram o agente e avaliaram sua qualidade.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | O agente respondeu corretamente sobre pontos e benefícios? | Perguntar quantos pontos foram acumulados |
| **Segurança** | O agente evitou inventar informações? | Perguntar algo fora do contexto |
| **Coerência** | A resposta faz sentido com o cartão do cliente? | Benefícios compatíveis com o tipo de cartão |

> [!TIP]
> Os testes foram realizados considerando clientes fictícios com dados simulados de cartão, transações e benefícios.

---

## Exemplos de Cenários de Teste

### Teste 1: Consulta de pontos
- **Pergunta:** "Quantos pontos eu fiz esse mês?"
- **Resposta esperada:** Valor baseado nas transações e na regra do cartão
- **Resultado:** [x] Correto  [ ] Incorreto

---

### Teste 2: Benefícios do cartão
- **Pergunta:** "Quais benefícios meu cartão tem?"
- **Resposta esperada:** Lista de benefícios conforme o cartão do cliente
- **Resultado:** [x] Correto  [ ] Incorreto

---

### Teste 3: Pergunta fora do escopo
- **Pergunta:** "Qual a previsão do tempo?"
- **Resposta esperada:** Agente informa que não trata desse assunto
- **Resultado:** [x] Correto  [ ] Incorreto

---

### Teste 4: Informação inexistente
- **Pergunta:** "Qual a pontuação do cartão Black?"
- **Resposta esperada:** Agente informa que não possui essa informação
- **Resultado:** [x] Correto  [ ] Incorreto

---

## Resultados

**O que funcionou bem:**
- O agente respondeu corretamente sobre cálculo de pontos  
- Manteve o foco apenas em pontuação e benefícios  
- Evitou responder perguntas fora do escopo  
- Linguagem clara e acessível para o usuário  

**O que pode melhorar:**
- Tornar os cálculos mais detalhados na resposta  
- Incluir mais tipos de cartões na base de dados  
- Melhorar a personalização com mais dados do cliente  

---

## Métricas Avançadas (Opcional)

- Tempo médio de resposta baixo (respostas rápidas)  
- Baixo risco de alucinação devido ao uso de dados estruturados  
- Possibilidade futura de monitoramento com ferramentas como LangFuse ou LangWatch  
