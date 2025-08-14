# 📞 Previsão e Análise de Churn em Telecom

**Ciência de Dados • Machine Learning • Python**

Este projeto foi desenvolvido para **prever a evasão (churn)** de clientes da **Telecom X** e fornecer **insights acionáveis** para retenção.  
O trabalho engloba desde a análise e tratamento dos dados até a construção de modelos preditivos, interpretação de variáveis e definição de estratégias de negócio.

---

## 🎯 Missão e Objetivo
- **Missão**: Desenvolver um pipeline robusto capaz de prever quais clientes têm maior probabilidade de cancelar os serviços.
- **Objetivo**: Antecipar o churn, identificar os principais fatores de evasão e apoiar o time de negócios na criação de estratégias preventivas e reativas.

---

## 🧠 Escopo e Etapas Realizadas

### 1. Carregamento e Análise Inicial dos Dados
- Fonte: `df_limpo.csv` com mais de **7.000 registros**.
- Inspeção inicial: amostra de dados, `info()`, `describe()`, tipos de variáveis, valores ausentes.
- Identificação de colunas irrelevantes (`customerID`) para remoção.

### 2. Análise Exploratória (EDA)
- Distribuição da variável-alvo `Churn`.
- Comparação de churn por tipo de contrato, tempo de relacionamento (`tenure`), gastos mensais/totais e serviços adicionais.
- Análises gráficas (countplots, boxplots, histogramas, matriz de correlação).

### 3. Pré-processamento e Tratamento
- Remoção de colunas irrelevantes.
- Conversão de variáveis categóricas via **One-Hot Encoding**.
- Padronização de colunas numéricas.
- Balanceamento das classes com **SMOTE**.

### 4. Modelagem Preditiva
- Modelos utilizados:
  - **Logistic Regression**
  - **Random Forest**
- Divisão treino/teste estratificada.
- Escalonamento de variáveis numéricas.
- Ajuste e avaliação de modelos com métricas de classificação.

### 5. Avaliação de Modelos
- Métricas: **Acurácia, Precisão, Recall, F1-score**.
- Comparação visual e tabular de desempenho.
- Diagnóstico de overfitting/underfitting.

### 6. Interpretação e Explicabilidade
- **Random Forest**: análise da importância das variáveis.
- **Logistic Regression**: análise de coeficientes para interpretar impacto positivo/negativo no churn.

### 7. Conclusão Estratégica
- Modelo campeão escolhido.
- Drivers de churn destacados.
- Estratégias de retenção sugeridas.
- Plano operacional e indicadores de acompanhamento.

---

## 📈 Desempenho dos Modelos

| Modelo              | Acurácia | Precisão | Recall  | F1-Score |
|---------------------|----------|----------|---------|----------|
| Logistic Regression | 0.7502   | 0.8087   | 0.7502  | 0.7634   |
| Random Forest       | 0.7787   | 0.7809   | 0.7787  | 0.7797   |

🏆 **Modelo Campeão:** **Random Forest** (critério: F1-Score)  
- Acurácia: 77,87%  
- Precisão: 78,09%  
- Recall: 77,87%  
- F1-Score: 77,97%

---

## 🔍 Principais Fatores de Evasão

**Random Forest — Top 5 (importância)**  
1. **Tempo de permanência do cliente (em meses) na empresa** — 14,2%  
2. **Valor total cobrado do cliente** — 12,1%  
3. **Valor mensal cobrado do cliente** — 11,0%  
4. **Cobrança média diária de uso** — 10,7%  
5. **Tipo de contrato: plano de dois anos** — 6,5%  

**Logistic Regression — Top 5 (coeficiente)**  
- **Tempo de permanência do cliente**: **REDUZ o churn** — Quanto maior o tempo de permanência, menor a probabilidade de cancelamento.  
- **Valor total cobrado do cliente**: **AUMENTA o churn** — Valores totais mais altos estão associados a maior probabilidade de cancelamento.  
- **Valor mensal cobrado do cliente**: **REDUZ o churn** — Valores mensais mais baixos estão associados a menor probabilidade de cancelamento.  
- **Serviço de internet: fibra óptica**: **AUMENTA o churn** — Clientes com internet de fibra óptica têm maior probabilidade de cancelar.  
- **Tipo de contrato: plano de dois anos**: **REDUZ o churn** — Clientes com contrato de dois anos têm menor probabilidade de cancelamento.  

---

## 💡 Insights de Negócio
- Contratos mensais apresentam maior risco de churn.
- Clientes com pouco tempo de relacionamento têm alta propensão à evasão.
- Gastos mensais e totais influenciam diretamente a retenção.
- A presença de serviços adicionais (segurança, backup, suporte técnico) está associada a maior fidelização.

---

## 🎯 Estratégias de Retenção

**Preventivas (antes do risco se concretizar)**  
- Incentivar migração para contratos anuais.  
- Oferecer pacotes adicionais com descontos.  
- Contato ativo nos primeiros meses.

**Reativas (após identificação pelo modelo)**  
- Campanhas segmentadas para clientes de alto risco.  
- Descontos temporários e upgrades gratuitos.  
- Atendimento prioritário.

**Longo Prazo**  
- Programa de fidelidade com benefícios crescentes.  
- Monitoramento contínuo de NPS.  
- Inovação em produtos e serviços.

---

## ⚙️ Plano Operacional
- **Threshold inicial de risco**: 0.17 (ajustável via testes A/B).  
- Scoring semanal ou mensal; re-treino trimestral.  
- Integração com CRM para ações automáticas.  
- **KPIs**: taxa de churn, ROI, NPS, uplift de campanhas.

---

## 🚀 Impacto Esperado
- **Precisão**: 78,1% — clientes identificados como risco realmente sairão.  
- **Recall**: 77,9% — clientes que sairiam serão identificados.  
- Redução potencial de 10–20% no churn.  
- ROI estimado positivo (ganho > 3x o investimento).  
- Aumento no tempo médio de permanência.

---

## 📌 Possíveis Extensões
- Testar modelos como **XGBoost** e **LightGBM**.
- Implementar **SHAP** para interpretabilidade global/local.
- Criar dashboard interativo com **Streamlit** ou **Power BI**.
- Implementar alertas preditivos em tempo real integrados ao CRM.
