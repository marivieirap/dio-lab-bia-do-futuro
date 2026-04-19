# Código da Aplicação

Esta pasta contém o código do agente Dom, responsável por auxiliar clientes com informações sobre pontuação e benefícios de cartões.

## Estrutura Sugerida

```
src/
├── app.py # Aplicação principal (Streamlit)
├── agente.py # Lógica do agente
├── config.py # Configurações (API keys, etc.)
├── data/ # Base de conhecimento (CSV/JSON)
└── requirements.txt # Dependências
```

## Exemplo de requirements.txt

```
streamlit
openai
python-dotenv
pandas
```
---

## Exemplo de config.py

```python
import os
from dotenv import load_dotenv

load_dotenv()

OPENAI_API_KEY = os.getenv("OPENAI_API_KEY")
```
---
## Exemplo de agente.py

```python
import json
import pandas as pd
from openai import OpenAI
from config import OPENAI_API_KEY

client = OpenAI(api_key=OPENAI_API_KEY)

# Carregar dados
clientes = pd.read_csv("data/clientes.csv")
transacoes = pd.read_csv("data/transacoes.csv")

with open("data/cartoes.json") as f:
    cartoes = json.load(f)

with open("data/beneficios.json") as f:
    beneficios = json.load(f)


def buscar_cliente(nome):
    return clientes[clientes["nome"] == nome].iloc[0]


def calcular_pontos(cliente_id, cartao_nome):
    trans = transacoes[transacoes["id_cliente"] == cliente_id]
    total = trans["valor"].sum()

    regra = next(c for c in cartoes if c["cartao"] == cartao_nome)
    pontos = total * regra["pontos_por_real"]

    return pontos


def gerar_resposta(pergunta, nome_cliente="João Silva"):
    cliente = buscar_cliente(nome_cliente)
    pontos = calcular_pontos(cliente["id_cliente"], cliente["cartao"])

    contexto = f"""
    Cliente: {cliente['nome']}
    Cartão: {cliente['cartao']}
    Pontos acumulados: {pontos}
    """

    prompt = f"""
    Você é Dom, assistente do Bradesco especialista em pontos.

    Contexto:
    {contexto}

    Pergunta do cliente:
    {pergunta}
    """

    response = client.chat.completions.create(
        model="gpt-4.1-mini",
        messages=[{"role": "user", "content": prompt}]
    )

    return response.choices[0].message.content
```
---

## Exemplo de app.py

```python
import streamlit as st
from agente import gerar_resposta

st.title("Dom - Assistente de Pontos do Cartão")

nome = st.text_input("Digite seu nome:")
pergunta = st.text_input("Digite sua pergunta:")

if st.button("Perguntar"):
    resposta = gerar_resposta(pergunta, nome)
    st.write(resposta)
```
---

## Como Rodar

```bash
# Instalar dependências
pip install -r requirements.txt

# Rodar a aplicação
streamlit run app.py
```
