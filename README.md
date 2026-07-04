# MVP - Machine Learning & Analytics: Previsão de Chuva na Austrália

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Henrique1078/mvp-ml-rain-australia/blob/main/notebook_mvp.ipynb)

Projeto individual da pós-graduação em Ciência de Dados. Modelo de classificação binária para prever a ocorrência de chuva no dia seguinte a partir de observações meteorológicas diárias.

Clique no badge acima para abrir o notebook diretamente no Google Colab e executá-lo do início ao fim.

## Problema

Classificação binária do target `RainTomorrow` (choverá amanhã: sim ou não) a partir de variáveis meteorológicas registradas em 49 estações australianas entre 2007 e 2017. O problema apresenta desbalanceamento real de classes (aproximadamente 22% de dias com chuva), o que orienta a escolha de métricas e a estratégia de avaliação.

## Dataset

Rain in Australia (weatherAUS), originado do Australian Bureau of Meteorology e distribuído pelo pacote R rattle. São 142.193 observações e 24 atributos.

O dataset é carregado diretamente no notebook pela URL raw deste repositório, sem necessidade de upload, login ou autenticação:

```
https://raw.githubusercontent.com/Henrique1078/mvp-ml-rain-australia/main/data/weatherAUS.csv
```

## Abordagem

O notebook percorre o fluxo completo de um projeto de Machine Learning: definição do problema, análise exploratória conectada à modelagem, preparação dos dados com prevenção de vazamento, divisão temporal treino/teste, modelagem comparativa, otimização de hiperparâmetros e avaliação crítica.

A coluna `RISK_MM` é identificada e removida por constituir vazamento direto do target. A divisão treino/teste é temporal, respeitando a ordem cronológica. Os modelos comparados são um baseline ingênuo (DummyClassifier), uma referência linear (LogisticRegression) e dois candidatos de gradient boosting (XGBoost e LightGBM), avaliados por F1-score e PR-AUC, métricas adequadas ao desbalanceamento.

## Estrutura

```
mvp-ml-rain-australia/
├── data/
│   └── weatherAUS.csv
├── notebook_mvp.ipynb
└── README.md
```

## Execução

O notebook é público e executável do início ao fim no Google Colab, sem configuração manual. Todas as dependências são instaladas na primeira célula.

## Reprodutibilidade

Seeds fixas em todas as etapas estocásticas. Todo o pré-processamento é encapsulado em pipelines do scikit-learn, ajustados exclusivamente nos dados de treino para prevenir vazamento.
