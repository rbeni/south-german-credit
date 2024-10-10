# South german credit analysis

Este repositório contém os jupyter notebooks resultantes da análise do dataset South German Credit, disponível em no site da [UC Irvine](https://archive.ics.uci.edu/dataset/573/south+german+credit+update)

# Descrição dos arquivos

/data: pasta que contém os arquivos obtidos do site da UC Irvine

/data/codetable.txt: contém descrição das features e significado de cada categoria

/data/SouthGermanCredit.asc: Dataset

eda.ipynb: Notebook que contém a análise exploratória do dataset

xgboost.ipynb: Notebook com o código necessário para treinar um modelo XGBoost neste dataset

lightgbm.ipynb: Notebook com o código necessário para treinar um modelo LightGBM neste dataset

gridsearch.ipynb: Notebook com o código necessário para treinar vários classificadores neste dataset, através de GridSearch

# Resultados obtidos com os modelos treinados

A tabela abaixo apresenta as métricas obtidas dos modelos treinados

| Modelo  | Acc | F1
| ------------- | ------------- | ------------- |
| XGBoost  | 0.73  | 0.81 |
| LightGBM  | 0.77  | 0.839 |
| AdaBoost  | 0.75  | 0.831 |
| GradientBoosting  | 0.73  | 0.816 |
| RandomForest  | 0.76  | 0.839 |
| SVC  | 0.75  | 0.833 |
| Reg. Logistic  | 0.74  | 0.83 |
| GaussianNB  | 0.75  | 0.832 |

Os resultados obtidos apontam o modelo LightGBM como o que obteve o melhor resultado, tanto na acurácia como em F1.

Dentre os motivos que destacam o LightGBM, podemos citar que este modelo têm uma preferencia por árvores mais complexas, lidando melhor com os padrões mais complexos do dataset e possibilidando que a árvore represente bem as características de maior variância.

Outro fator importante é que o LightGBM lida bem com datasets desbalanceados. Neste caso temos um dataset com um split de 30%/70% no target 'kredit'.

Por fim, ele também lida bem com variáveis categoricas sem a necessidade de one-hot encoding, evitando tornar o dataset disperso ('sparse'). Vale lembrar também que a maioria das features são do tipo categórico, que certamente contribui para o desempenho deste modelo frente aos demais

# Pontos pendentes

Com mais tempo seria possível realizar mais atividades, como:
- Uma análise mais profunda dos outliers
- Treinar os modelos sem os outliers 
- Combinação de features
- Undersampling/Resampling
- Retreinar os modelos somente com as features mais importantes
- Ensemble dos melhores modelos
- Melhor fine-tuning, explorando diferentes regularizações, taxas de aprendizagem, dimensões das árvores, etc

# Licença

O dataset possui sua própria licença, conforme disponĩvel no site  da [UC Irvine](https://archive.ics.uci.edu/dataset/573/south+german+credit+update).

Os códigos criados para análise e treinamento são disponibilizados com a licença MIT.
