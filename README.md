# 📦 DataCo Supply Chain Analytics & Prediction

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data_Wrangling-green.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit_Learn-Machine_Learning-orange.svg)
![Status](https://img.shields.io/badge/Status-Concluído-success.svg)

## 📊 Sobre o Projeto
Este projeto tem como objetivo realizar uma análise ponta a ponta de uma base de dados global de cadeia de suprimentos (Supply Chain) e varejo. O foco principal é transformar dados brutos em **Inteligência de Negócios (Business Intelligence)**, avaliando o comportamento de vendas, a eficiência logística, o impacto financeiro de descontos e, por fim, utilizando **Machine Learning** para prever riscos de atrasos nas entregas.

O conjunto de dados contém mais de 180.000 registros de transações, englobando informações de clientes, produtos, localidades geográficas e métricas logísticas.

## 🎯 Objetivos do Projeto
- **Análise Exploratória (EDA):** Identificar os produtos mais/menos vendidos e mapear o volume de vendas por país.
- **Auditoria Logística:** Verificar se o volume de pedidos ou a localidade afetam a velocidade de entrega real da empresa.
- **Análise Financeira:** Descobrir se a política de descontos está canibalizando as margens de lucro.
- **Modelagem Preditiva:** Desenvolver um modelo de classificação capaz de prever pedidos com risco de atraso (`Late_delivery_risk`) e entender as causas raiz desses atrasos.

---

## 💡 Principais Insights de Negócio

### 1. Comportamento de Consumo (O que vende e para onde vai?)
* O portfólio de maior sucesso da empresa é fortemente voltado para artigos esportivos e vestuário leve (ex: *Perfect Fitness Perfect Rip Deck*).
* Equipamentos pesados (como elípticos e halteres) possuem saída irrisória, o que levanta a necessidade de revisão de estoque.
* Os maiores mercados consumidores globais são **Estados Unidos, México e França**.

### 2. A "Máquina" Logística
* Cruzando os países que mais compram com o tempo real de entrega, descobriu-se uma cadeia de suprimentos altamente padronizada.
* Independentemente do país de destino ou do volume de itens comprados, a empresa possui um SLA (Acordo de Nível de Serviço) incrivelmente consistente, realizando entregas em uma média de **3,4 a 3,6 dias** globalmente.

### 3. Estratégia de Pricing (Precificação) Blindada
* Ao rodar uma correlação de Pearson entre a Taxa de Desconto e a Margem de Lucro Líquida, o resultado foi **-0.0041** (estatisticamente nulo).
* **Conclusão:** O time de vendas utiliza os descontos de forma estratégica, sem sacrificar a saúde da empresa. Mesmo com descontos de até 25%, a margem de lucro se mantém cravada em cerca de **17%**.

---

## 🤖 Machine Learning: Previsão de Atrasos

Para passar da análise descritiva para a preditiva, foi construído um modelo de **Inteligência Artificial (Random Forest Classifier)** para prever a probabilidade de um pacote atrasar.

* **Acurácia do Modelo:** Excelente taxa de acerto na base de testes.
* **Feature Importance:** O modelo revelou que a raiz dos atrasos não é geográfica (o país) nem relacionada ao produto, mas sim atrelada ao **Prazo Programado (`Days for shipment scheduled`)** e ao **Modo de Envio (`Shipping Mode`)** escolhidos no momento do checkout. 

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python
* **Manipulação e Limpeza de Dados:** `pandas`, `numpy`
* **Visualização de Dados:** `matplotlib`, `seaborn`
* **Machine Learning:** `scikit-learn` (RandomForestClassifier, train_test_split, classification_report)
* **Ambiente de Desenvolvimento:** Jupyter Notebook / Kaggle Notebooks

---

## 📂 Estrutura do Repositório

```text
├── data/                   # Pasta para os arquivos CSV (DataCoSupplyChainDataset) - não inclusos no git por tamanho
├── notebooks/              # Jupyter Notebooks com as análises passo a passo
│   └── analise_supply_chain.ipynb
├── src/                    # Scripts Python auxiliares (se houver)
├── README.md               # Este documento
