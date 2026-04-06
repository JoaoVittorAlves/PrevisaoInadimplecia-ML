# Previsão de Inadimplência

Projeto de Machine Learning desenvolvido para prever a **probabilidade de inadimplência de clientes B2B**, com base em dados cadastrais e comportamentais da startup Praso 

---

## Objetivo

Construir modelos preditivos para:

1. **Avaliação de novos clientes (Application Model)**
   - Prever risco de inadimplência no momento do cadastro

2. **Avaliação de clientes recorrentes (Behavioral Model)**
   - Prever risco com base no histórico de pedidos

---

## Contexto de Negócio

A Praso atua como um marketplace B2B conectando indústrias e varejistas. Um dos principais desafios é:

> **Reduzir o risco de inadimplência ao conceder crédito para pequenos empreendedores**

---

## Dados Utilizados

### Dados de Clientes
- Informações cadastrais
- Dados de crédito (Serasa)
- Presença digital (iFood, Google Maps)

### Dados de Pedidos
- Histórico de compras
- Valores dos pedidos
- Atrasos nos pagamentos

---

## Metodologia

### 1. Análise Exploratória (EDA)
- Identificação de padrões de inadimplência
- Visualização de variáveis relevantes

### 2. Feature Engineering
- Criação de variáveis derivadas
- Agregações comportamentais por cliente
- Tratamento de dados categóricos e nulos

### 3. Modelagem
Modelos testados:
- Regressão Logística
- Random Forest
- XGBoost
- LightGBM

### 4. Avaliação
- Métrica principal: **ROC-AUC**
- Comparação entre modelos

---

## Modelos Desenvolvidos

### Modelo de Aplicação
- Entrada: dados cadastrais
- Saída: score de risco (0 a 1)

### Modelo Comportamental
- Entrada: dados cadastrais + histórico de pedidos
- Saída: score de risco atualizado

---

## Política de Crédito (Proposta)

| Score de Risco | Decisão |
|---------------|--------|
| < 0.2         | Aprovar crédito |
| 0.2 – 0.4     | Aprovar com limite reduzido |
| > 0.4         | Rejeitar |

---

## Estrutura do Projeto

```
PrevisaoInadimplecia-ML/
│
├── dados/                          # Dados brutos e processados
│   ├── Brutos/
│   │   ├── credito_aplicacao_clientes.csv
│   │   └── credito_comportamental_pedidos.csv
│   └── tratados/
│       ├── clientes_preprocessado.csv
│       ├── teste_preprocessado.csv
│       └── treino_preprocessado.csv
│
├── notebooks/                      # Análises e experimentos
│   ├── 01_fase1_EDA.ipynb         # Análise exploratória dos dados
│   ├── 02_fase2_PreProcessamento.ipynb  # Limpeza e transformação
│   └── 03_fase3_Treinamento.ipynb # Treinamento e avaliação dos modelos
│
├── src/                            # Código modularizado
│   ├── preprocessamento.py         # Funções de pré-processamento
│   └── train.py                    # Script de treinamento
│
├── modelos/                        # Modelos treinados salvos
│
├── resultados/                     # Métricas e comparações
│   ├── baseline.json
│   ├── comparacao_geral.csv
│   ├── random_forest_sem_smote.json
│   ├── random_forest_smote.json
│   ├── xgboost_sem_smote.json
│   ├── xgboost_smote.json
│   ├── lightgbm_sem_smote.json
│   ├── lightgbm_smote.json
│   ├── regressao_logistica_sem_smote.json
│   ├── regressao_logistica_smote.json
│   └── modelo_selecionado.json
│
├── requirements.txt                # Dependências do projeto
└── readme.md                       # Este arquivo

```

---

## Tecnologias

- **Python 3.8+**
- **Pandas** — Manipulação e análise de dados
- **NumPy** — Computações numéricas
- **Scikit-learn** — Modelos de machine learning (Regressão Logística, Random Forest)
- **XGBoost** — Gradient boosting otimizado
- **LightGBM** — Gradient boosting leve e rápido
- **Imbalanced-learn** — Técnicas de balanceamento (SMOTE)
- **Category-encoders** — Encodificação de variáveis categóricas
- **SHAP** — Interpretabilidade dos modelos
- **Optuna** — Otimização de hiperparâmetros
- **Matplotlib & Seaborn** — Visualizações
- **Jupyter** — Notebooks interativos

---

## Como Executar

### 1. Configuração do Ambiente

```bash
# Clone ou acesse o repositório
cd PrevisaoInadimplecia-ML

# Crie um ambiente virtual
python -m venv venv

# Ative o ambiente (Windows)
.\venv\Scripts\Activate.ps1

# Ative o ambiente (Linux/Mac)
source venv/bin/activate

# Instale as dependências
pip install -r requirements.txt
```

### 2. Execução dos Notebooks

Os análises devem ser executadas **em sequência**:

```bash
# Terminal dentro do diretório do projeto
jupyter lab
```

Depois abra e execute:
1. `notebooks/01_fase1_EDA.ipynb` — Explore os dados
2. `notebooks/02_fase2_PreProcessamento.ipynb` — Processe e transforme
3. `notebooks/03_fase3_Treinamento.ipynb` — Treine os modelos

```

### 3. Resultados

Após a execução:
- Modelos treinados são salvos em `modelos/`
- Métricas e resultados são salvos em `resultados/`
- O melhor modelo é referenciado em `resultados/modelo_selecionado.json`

---
