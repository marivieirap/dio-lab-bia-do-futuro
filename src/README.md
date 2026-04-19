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

## Como Rodar

```bash
# Instalar dependências
pip install -r requirements.txt

# Rodar a aplicação
streamlit run app.py
```
