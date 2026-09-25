# Análise de Acidentes Aéreos - CENIPA

Projeto em andamento de análise exploratória de dados sobre ocorrências aeronáuticas no Brasil, registradas pelo CENIPA entre 2007 e 2023.

Dataset: https://www.kaggle.com/datasets/victorhiga/acidentes-areos-fav

## Pergunta central

Quais fatores estão mais associados ao número de fatalidades (`aeronave_fatalidades_total`) em ocorrências aeronáuticas no Brasil?

## Dados

Do conjunto original de 5 tabelas, uso 3:

- `ocorrencia.csv` - dados gerais de cada ocorrência
- `aeronave.csv` - detalhes das aeronaves envolvidas
- `ocorrencia_tipo.csv` - tipo/categoria da ocorrência

## O que já foi feito

Carregamento dos 3 datasets (encoding latin-1, separador `;`), primeiro olhar nos dados e checagem de valores faltantes.

Construção de um banco SQLite local com as 3 tabelas, e montagem da query de tendência de fatalidades por ano (join entre `ocorrencia` e `aeronave`, conversão da data do formato brasileiro pro formato esperado pelo SQLite, agrupamento por ano).

Investigação de integridade do join: ao juntar `ocorrencia` e `aeronave`, o resultado tem mais linhas que `ocorrencia` sozinha. Confirmei que isso se explica por ocorrências com múltiplas aeronaves envolvidas (checagem rigorosa: a soma de `total_aeronaves_envolvidas` bate exatamente com o total de linhas do join). Também confirmei, comparando os valores de fatalidade entre aeronaves de uma mesma ocorrência, que `aeronave_fatalidades_total` é por aeronave, não um total duplicado — ou seja, somar essa coluna não gera contagem duplicada de mortes.

## Próximos passos

Fechar a documentação dessa investigação no notebook, trazer a query de tendência por ano pro Colab com visualização, tratar os demais dados faltantes, seguir com as outras sub-perguntas da análise temporal (letalidade por tipo de ocorrência ao longo do tempo), análise univariada e bivariada mais ampla, correlações, e conclusões.

## Stack

Python, Pandas, Seaborn, Matplotlib, SQLite3 rodando no Google Colab.
