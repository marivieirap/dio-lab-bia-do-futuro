# 🤖 Dom - Assistente de Pontuação de Cartão

Dom é um agente virtual desenvolvido para ajudar clientes a entenderem como funciona a pontuação e os benefícios dos seus cartões de crédito.

---

## 📌 Sobre o Projeto

Muitos clientes não sabem como seus pontos são acumulados ou quais benefícios possuem.  
O Dom resolve isso explicando de forma clara e acessível:

- Como os pontos são calculados  
- Quantos pontos o cliente acumulou  
- Quais benefícios estão disponíveis  

---

## 🎯 Objetivo

Auxiliar clientes bancários a aproveitarem melhor seus cartões de crédito por meio de um assistente inteligente, seguro e especializado.

---

## 👤 Persona do Agente

- **Nome:** Dom  
- **Personalidade:** Consultivo e educado  
- **Tom:** Formal e acessível  
- **Especialidade:** Pontuação e benefícios de cartões  

---

## 🧠 Funcionalidades

- Consulta de pontos acumulados  
- Explicação de cálculo de pontuação  
- Exibição de benefícios do cartão  
- Respostas baseadas em dados reais  
- Tratamento de perguntas fora do escopo  

---

## 📂 Estrutura do Projeto

```
dom/
├── data/
│   ├── clientes.csv
│   ├── cartoes.json
│   ├── beneficios.json
│   └── transacoes.csv
├── src/
│   ├── app.py
│   ├── agente.py
│   ├── config.py
│   └── requirements.txt
└── README.md
```

## 📊 Base de Conhecimento

O agente utiliza dados estruturados para gerar respostas:

- **clientes.csv:** informações do cliente  
- **cartoes.json:** regras de pontuação  
- **beneficios.json:** benefícios por cartão  
- **transacoes.csv:** histórico de compras  

---

## 🔐 Segurança

- Responde apenas com base nos dados fornecidos  
- Não inventa informações  
- Não acessa dados sensíveis  
- Não responde fora do escopo  

---

## ⚠️ Limitações

- Não responde perguntas fora do contexto de pontuação e benefícios  
- Não realiza operações financeiras  
- Não fornece informações de outros serviços bancários  

---

# 🚀 Como Executar
 
## 1. Clonar o projeto
 
```bash
git clone <seu-repositorio>
cd dom
```
 
## 2. Instalar dependências
 
```bash
pip install -r src/requirements.txt
```
 
## 3. Configurar API Key
 
Crie um arquivo `.env` dentro da pasta `src`:
 
```env
OPENAI_API_KEY=sua_chave_aqui
```
 
## 4. Rodar a aplicação
 
```bash
cd src
streamlit run app.py
```
 
---
 
## 🧪 Testes
 
O agente foi testado com cenários como:
 
- Consulta de pontos
- Consulta de benefícios
- Perguntas fora do escopo
- Solicitação de informação inexistente  

Resultados demonstraram boa assertividade, segurança e coerência.
