# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `clientes.csv` | CSV | Identificar informações do cliente (nome, tipo de conta, cartão) |
| `cartoes.json` | JSON | Informações sobre tipos de cartões e regras de pontuação |
| `beneficios.json` | JSON | Listar benefícios disponíveis de acordo com o cartão |
| `transacoes.csv` | CSV | Calcular e explicar o acúmulo de pontos com base nas compras |

> [!TIP]
> **Quer um dataset mais robusto?** Você pode utilizar datasets públicos do [Hugging Face](https://huggingface.co/datasets) relacionados a finanças, desde que sejam adequados ao contexto do desafio.

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Os dados foram estruturados para simular um ambiente bancário, com informações simplificadas sobre clientes, cartões e transações.  
Também foram ajustados para facilitar o cálculo de pontos e a explicação dos benefícios de forma clara para o usuário.

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Os arquivos JSON e CSV são carregados no início da execução do sistema e armazenados em memória para consulta durante a conversa.

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

Os dados são consultados dinamicamente conforme a pergunta do usuário.  
As informações relevantes (como tipo de cartão, transações e regras de pontuação) são inseridas no contexto do prompt para gerar respostas mais precisas e personalizadas.


---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:

- Nome: João Silva
- Tipo de cartão: Gold
- Pontuação: 1 ponto a cada R$ 1 gasto

Últimas transações:

- 01/11: Supermercado - R$ 450
- 03/11: Streaming - R$ 55
- 05/11: Posto de gasolina - R$ 200

Benefícios:

- Acúmulo de pontos em todas as compras
- Descontos em parceiros
- Possibilidade de troca por milhas
...
```
