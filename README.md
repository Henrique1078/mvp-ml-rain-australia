# MVP - Machine Learning & Analytics: Previsao de Chuva na Australia

Projeto individual da pos-graduacao em Ciencia de Dados. Modelo de classificacao binaria para prever a ocorrencia de chuva no dia seguinte a partir de observacoes meteorologicas diarias.

## Problema

Classificacao binaria do target RainTomorrow (chovera amanha: sim/nao) a partir de variaveis meteorologicas registradas em 49 estacoes australianas entre 2007 e 2017. O problema apresenta desbalanceamento real de classes (aproximadamente 22% de dias com chuva), o que orienta a escolha de metricas e a estrategia de avaliacao.

## Dataset

Rain in Australia (weatherAUS), originado do Australian Bureau of Meteorology e distribuido pelo pacote R rattle. Sao 142.193 observacoes e 24 atributos.

O dataset e carregado diretamente no notebook pela URL raw deste repositorio, sem necessidade de upload, login ou autenticacao:

https://raw.githubusercontent.com/Henrique1078/mvp-ml-rain-australia/main/data/weatherAUS.csv

## Execucao

O notebook e publico e executavel do inicio ao fim no Google Colab, sem configuracao manual.

## Reprodutibilidade

Seeds fixas em todas as etapas estocasticas. Todo o pre-processamento e encapsulado em pipelines do scikit-learn, ajustados exclusivamente nos dados de treino para prevenir vazamento.
