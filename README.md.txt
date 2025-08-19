# Telecom X – Parte 2: Prevendo Churn

## 📌 Propósito do Projeto
Este projeto tem como objetivo desenvolver **modelos preditivos capazes de identificar clientes com maior probabilidade de cancelar os serviços da Telecom X (churn)**.  
A análise permite à empresa antecipar a evasão de clientes e tomar decisões estratégicas para retenção, melhorando a experiência do usuário e reduzindo perdas financeiras.

---

## 📂 Estrutura do Projeto
telecomx_parte2/
│
├─ data/ # Contém os dados tratados em CSV
│ └─ data_challenge_alura_telecom.csv
│
├─ notebooks/ # Notebooks Jupyter com análise e modelagem
│ └─ 01_preprocessamento.ipynb
│
├─ visuals/ # Gráficos e visualizações geradas
│
├─ README.md # Documentação do projeto


---

## 🧹 Preparação dos Dados
O pré-processamento dos dados seguiu as etapas abaixo:

### 1️⃣ Classificação das variáveis
- **Numéricas:** `tenure`, `Charges_Monthly`, `Charges_Total`  
- **Categóricas (já codificadas como dummies):** gênero, status de parceria, dependentes, tipo de serviço, métodos de pagamento, contrato e billing.

### 2️⃣ Tratamento das variáveis
- As variáveis numéricas foram **normalizadas** usando `StandardScaler` para melhorar a performance de modelos sensíveis à escala.  
- As variáveis categóricas já estavam convertidas em 0/1 (dummy/one-hot encoding), não sendo necessário novo encoding.

### 3️⃣ Separação dos dados
- Divisão em **treino (70%) e teste (30%)** usando `train_test_split` do scikit-learn.  
- A divisão foi estratificada em relação à variável `Churn` para manter a proporção de clientes que cancelaram e não cancelaram.

---

## 🛠️ Modelagem e Justificativas
- **Modelos utilizados:**
  - **Logistic Regression** → baseline interpretável.
  - **Random Forest** → captura interações entre variáveis e não depende de escalonamento.
  - **XGBoost** → algoritmo robusto e de alta performance para classificação binária.

- **Justificativas:**
  - Seleção de variáveis baseada na disponibilidade e relevância de informações.  
  - Uso de métricas variadas (`accuracy`, `precision`, `recall`, `f1-score` e `ROC-AUC`) para avaliação completa do desempenho.

---

## 📊 Exemplos de Insights e Visualizações
- Gráficos de distribuição de churn por idade e tipo de contrato.  
- Correlações entre serviços contratados e cancelamentos.  
- Matriz de confusão e curva ROC para cada modelo, permitindo análise de falsos positivos/negativos e performance geral.

---

## 🚀 Instruções para Executar
1. Clone este repositório:
```bash
git clone https://github.com/zucajunior/telecomx_parte2.git
