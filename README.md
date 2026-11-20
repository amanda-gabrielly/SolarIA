# ☀️ SolarIA — Previsão de geração e economia com energia solar em tempo real

> Projeto desenvolvido para a disciplina de **Inteligência Artificial** do curso de **Análise e Desenvolvimento de Sistemas (ADS)** da **FICR – Faculdade Católica Imaculada Conceição do Recife**.

## 📌 O problema

Cada vez mais casas e empresas em Recife instalam energia solar, mas o gestor **não sabe quanto o sistema vai gerar nos próximos dias** nem **quanto vai economizar na conta de luz**. Dias nublados e chuvosos derrubam a geração, e o prejuízo só aparece quando a conta chega.

**Pergunta que o projeto responde:**
*Com base no clima, é possível prever quanta energia um sistema solar vai gerar e transformar isso em economia (R$) em tempo real?*

## 💡 A solução

O SolarIA usa **Machine Learning** para prever a geração de energia solar a partir de dados climáticos e converte essa previsão em **impacto financeiro** para o gestor.

- Prevê a potência gerada com base em radiação solar, temperatura e vento
- Usa a **previsão do tempo dos próximos 7 dias** para Recife
- Calcula a **economia estimada em R$**
- Lê a **conta de luz** da pessoa com o **Google Gemini** para obter o consumo e a tarifa reais

## 🧠 Técnica e algoritmos

| Item | Descrição |
|---|---|
| **Técnica** | Inferência (previsão) da geração de energia a partir do clima |
| **Família** | Regressão (aprendizado supervisionado), porque a resposta é um número: a potência gerada |
| **Modelos comparados** | Regra simples (modelo base), Regressão Linear e Random Forest |

## 📊 Dados utilizados

| Fonte | O que fornece |
|---|---|
| **PVGIS** (Comissão Europeia, JRC) | Histórico hora a hora de radiação solar, temperatura, vento e geração de um sistema solar de 1 kWp em Recife |
| **Open-Meteo** | Clima atual e previsão dos próximos 7 dias para Recife |
| **Conta de luz** (lida pelo Gemini) | Consumo e tarifa reais da pessoa |

## 🛠️ Tecnologias

- Python
- Google Colab
- scikit-learn (Regressão Linear e Random Forest)
- API Open-Meteo e dados do PVGIS
- Google Gemini API (`google-genai`)

## ▶️ Como executar

1. Abra o notebook `.ipynb` deste repositório no **Google Colab**.
2. Crie uma chave gratuita da API do Gemini no [Google AI Studio](https://aistudio.google.com/).
3. No Colab, clique no ícone de chave 🔑 (**Secrets**) na barra lateral e adicione:
   - **Nome:** `GEMINI_API_KEY`
   - **Valor:** sua chave
   - Ative o **acesso ao notebook**.
4. Execute as células em ordem (**Ambiente de execução → Executar tudo**).

> Sem a chave do Gemini, o notebook continua funcionando: apenas a leitura da conta de luz fica desativada.

## 🔒 Segurança

A chave da API **não está no código**. Ela é lida dos *Secrets* do Colab com `userdata.get("GEMINI_API_KEY")`.

## 👩‍💻 Autora

**Amanda Gabrielly da Silva**
Estudante de Análise e Desenvolvimento de Sistemas — FICR

