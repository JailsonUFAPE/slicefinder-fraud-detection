# slicefinder-fraud-detection
# Slice Finder para Fairness em Fraudes de Cartão de Crédito

## Descrição

Este projeto implementa uma versão prática inspirada no artigo **Automated Data Slicing for Model Validation: A Big Data – AI Integration Approach** para análise de subconjuntos interpretáveis (slices) em uma base de fraudes de cartão de crédito.

O objetivo é identificar slices dos dados que apresentem comportamento problemático do modelo, combinando desempenho preditivo e fairness.

## Base de dados

A base contém transações financeiras com variável-alvo `is_fraud` e atributos transacionais, demográficos e geográficos.

## Enriquecimento de features

Foram criadas as seguintes novas features:

- after_midnight
- is_weekend
- is_holiday
- n_trans_24h
- first_time_merchant
- num_diff_merchants_7d
- new_zip_code
- dist_km_home
- dist_km_last_transaction
- impossible_travel
- amt_over_usr_avg
- job_type
- idade

## Atributos protegidos

Os atributos protegidos considerados foram:

- gender
- job_type
- idade

## Função objetivo

A análise utilizou uma função objetivo que relaciona:

- F1 Score
- Disparate Impact

## Metodologia

1. Carregamento da base
2. Feature engineering
3. Treinamento de modelo Random Forest
4. Predição em base de teste
5. Cálculo de perda individual
6. Geração automática de slices interpretáveis
7. Avaliação estatística das slices
8. Repetição em N experimentos
9. Análise de recorrência das slices

## Saídas geradas

- `metricas_globais_experimentos.csv`
- `slices_problematicas_todos_experimentos.csv`
- `recorrencia_slices.csv`

## Como executar

Abra o notebook:

`notebooks/slice_finder_fraude_fairness.ipynb`

e execute as células em sequência no Google Colab.

## Referência

Chung, Y., Kraska, T., Polyzotis, N., Tae, K. H., & Whang, S. E.  
**Automated Data Slicing for Model Validation: A Big Data – AI Integration Approach**.
