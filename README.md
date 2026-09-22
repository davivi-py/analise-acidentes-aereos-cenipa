# Análise de Acidentes Aéreos - CENIPA

Projeto em andamento de análise exploratória de dados sobre ocorrências aeronáuticas no Brasil, registradas pelo CENIPA entre 2007 e 2021.

Dataset: https://www.kaggle.com/datasets/victorhiga/acidentes-areos-fav

## Pergunta central

Quais fatores estão mais associados ao número de fatalidades (`aeronave_fatalidades_total`) em ocorrências aeronáuticas no Brasil?

## Dados

Do conjunto original de 6 tabelas, uso 3:

- `ocorrencia.csv` - dados gerais de cada ocorrência
- `aeronave.csv` - detalhes das aeronaves envolvidas
- `ocorrencia_tipo.csv` - tipo/categoria da ocorrência

## O que já foi feito

Carregamento dos 3 datasets (encoding latin-1, separador ;), primeiro olhar nos dados e checagem de valores faltantes.

## Próximos passos

Tratar dados faltantes, unir as tabelas, fazer análise univariada e bivariada, olhar correlações e chegar em conclusões.

## Stack

Python, Pandas, Seaborn, Matplotlib, rodando no Google Colab.
