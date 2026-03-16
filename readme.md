# AlzheimerPredict: Predição de Alzheimer e Análise de Fatores de Risco com Machine Learning

## Projeto de Ciência de Dados que utiliza técnicas de Aprendizado de Máquina para prever o diagnóstico de Alzheimer com base em dados clínicos, demográficos, comportamentais e cognitivos. Além da predição, o projeto busca identificar quais fatores possuem maior influência no desenvolvimento da doença, contribuindo para uma análise mais fundamentada.

---

## Objetivos Específicos

- Realizar análise exploratória dos dados

- Construir um pipeline de pré-processamento

- Treinar e comparar diferentes algoritmos de classificação

- Avaliar o desempenho dos modelos

- Identificar as variáveis mais importantes

- Analisar o impacto de diferentes grupos de atributos

---

## Perguntas a serem respondidas

Este projeto busca responder questões como:

- Características demográficas são suficientes para prever Alzheimer?
- Fatores de estilo de vida melhoram a capacidade preditiva?
- Qual o impacto de variáveis clínicas e cognitivas?
- Quais atributos são mais relevantes para o diagnóstico?
- Existe ganho significativo ao combinar diferentes tipos de dados?

---

## Tecnologias Utilizadas

- Python
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## Metodologia

### 1. Pré-processamento
- Tratamento de dados ausentes
- Codificação de variáveis categóricas
- Normalização de dados
- Análise de correlação

### 2. Modelagem

Serão utilizados os seguintes algoritmos:

- Regressão Logística
- Árvore de Decisão
- Random Forest
- KNN

### 3. Experimentos

Serão avaliados três cenários:

1. **Demografia apenas**
2. **Demografia + Estilo de Vida**
3. **Todos os dados (incluindo clínicos e cognitivos)**

### 4. Avaliação

Métricas utilizadas:

- Accuracy
- Precision
- Recall
- F1-score
- Matriz de confusão
