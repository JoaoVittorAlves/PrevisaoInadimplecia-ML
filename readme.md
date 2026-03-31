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

---
## Tecnologias

---
## Como Executar

---
