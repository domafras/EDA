
# Análise Exploratória de Dados (EDA)

A análise exploratória de dados (EDA, do inglês: Exploratory Data Analysis) é uma importante etapa na ciência de dados. Ela envolve a exploração dos dados para entender melhor as informações contidas neles, identificar padrões e relacionamentos entre variáveis e descobrir insights importantes que podem ser usados para tomar decisões informadas. Neste projeto, utilizando Python tem-se como objetivo demonstrar como utilizar as bibliotecas mais comuns para trabalhar com dados, além de apresentar algumas técnicas básicas para visualização, pré-processamento dos dados, aplicação e validação de modelos de Machine Learning.
 
Consulte o seguinte artigo utilizado como referência para esse estudo: [Análise Exploratória de Dados com Python](https://medium.com/@aasouzaconsult/python-para-an%C3%A1lise-de-dados-24028d7013b3)

## Pré-requisitos

Antes de começar, certifique-se de ter instalado o `Python 3.x`, uma IDE como Jupyter Notebook e algumas bibliotecas que serão utilizadas ao longo do estudo, como `numpy`, `pandas`, `matplotlib`, `seaborn` e `scikitlearn`.

## Base de dados

A base de dados utilizada neste projeto é de uma concessionária de veículos e trata das vendas de veículos usados. As informações que compõem o conjunto de dados são:

- data.set: Dado de treino ou de test
- total.cost: Custo total do veículo
- lot.sale.days: Tempo de venda em dias
- overage: Venda após 90 dias
- mileage: Quilometragem
- vehicle.type: Tipo do veículo (economy, family.medium, family.large...)
- domestic.import: Fabricação, doméstico ou importado
- vehicle.age: Idade do veículo
- vehicle.age.group: Grupo de idade do veículo
- color.set: Cor
- makex: Marca
- state: Estado do Carro (região)
- make.model: Modelo

## Instalação

1. Clone o repositório para sua máquina local.
2. Certifique-se de ter os pré-requisitos instalados (consulte a seção acima).
3. Abra o arquivo `eda.ipynb` no Jupyter Notebook ou outra ferramenta similar.

## Uso

O arquivo `eda.ipynb` contém todo o código utilizado na análise de dados. Ele é dividido em seções que correspondem a diferentes etapas do processo de análise, como leitura, visualização, análise estatística e etapas de Machine Learning.

Ao executar cada célula do notebook, você poderá ver os resultados das operações realizadas em tempo real. Você também pode modificar o código e experimentar com diferentes técnicas.

## Perguntas e hipóteses

Durante a análise exploratória dos dados, várias perguntas e hipóteses podem surgir. Para responder à essas perguntas, utilizaremos gráficos e estatísticas descritivas. Exemplos: gráficos de dispersão, histogramas, boxplots, mapas de calor e outras visualizações para identificar padrões e correlações entre variáveis.

## Modelo de Machine Learning

Após a análise exploratória dos dados, compreendendo correlações, dispersões e outras métricas, segue à criação de um modelo de aprendizagem de máquina:

### Pré-processamento dos dados

Existem diversas etapas de pré-processamento de dados que são importantes para construir um bom modelo de machine learning. Algumas delas incluem:

- **Remover colunas irrelevantes**: remover colunas que não possuem relevância para o problema em questão pode melhorar a qualidade dos resultados do modelo.
- **Tratar valores ausentes**: é comum os dados coletados conterem valores ausentes. Esses valores precisam ser tratados antes do treinamento do modelo, pois eles podem levar a resultados imprecisos.
- **Adaptar colunas de valores categóricos**: muitas vezes, as colunas contêm valores categóricos, como cores ou tipos de produtos. Para transformar esses dados em um formato que possa ser usado pelo modelo, é necessário aplicar técnicas de codificação, como a codificação one-hot ou a codificação ordinal.
- **Normalização e padronização**: muitos modelos de machine learning são sensíveis à escala dos dados. Portanto, é importante normalizar ou padronizar as colunas que têm valores muito diferentes.
- **Remoção de outliers**: outliers são valores atípicos que podem distorcer os resultados do modelo. É importante identificá-los e removê-los antes do treinamento do modelo para evitar resultados imprecisos.

Após o pré-processamento dos dados, é necessário transformá-los em um formato que possa ser usado pelo modelo. Normalmente, isso envolve a separação dos dados em variáveis independentes e dependentes.

### Separação em classes

É necessário separar as classes das variáveis independentes. No nosso caso, queremos prever se um veículo será vendido em menos ou mais de 90 dias após sua inclusão na base de dados. Portanto, essa variável será nossa classe.

### Separação em dados de treino e teste

Para avaliar o desempenho do modelo, é necessário separar os dados em um conjunto de treinamento e um conjunto de teste.

### Aplicação do modelo

Após o treinamento do modelo, é necessário aplicá-lo aos dados de teste para avaliar sua precisão e desempenho. Podemos utilizar diversos modelos de machine learning, como regressão logística, **árvores de decisão**, random forest, entre outros.

Uma árvore de decisão (escolha para este projeto) é um algoritmo de aprendizado de máquina supervisionado que é utilizado para classificação e para regressão. Isto é, pode ser usado para prever categorias discretas (sim ou não, por exemplo) e para prever valores numéricos (o valor do lucro em reais).

Para mais detalhes, visite: ([Decision Tree e Random Forest para Classificação e Regressão](https://blogdozouza.wordpress.com/2019/09/30/decision-trees-e-random-forests-para-classificacao-e-regressao/))

### Validação do modelo

Após a aplicação do modelo aos dados de teste, é importante avaliar sua precisão. Podemos utilizar diversas métricas de avaliação, como matriz de confusão, acurácia, precision, recall e F1-score:

- **Accuracy (acurácia)**: é a proporção das previsões corretas em relação ao total de previsões feitas pelo modelo.
- **Precision (precisão)**: é a proporção das previsões positivas corretas em relação ao total de previsões positivas feitas pelo modelo.
- **Recall (revocação)**: é a proporção das previsões positivas corretas em relação ao total de amostras verdadeiramente positivas no conjunto de dados.
- **F1-score**: é a média harmônica entre precision e recall, que leva em conta tanto falsos positivos quanto falsos negativos.
- **Support (suporte)**: é o número de amostras verdadeiras para cada classe presente no conjunto de dados.

Quando temos mais de uma classe no conjunto de dados, podemos também utilizar as seguintes métricas:

- **Macro avg** é a média aritmética das métricas por classe
- **Weighted avg** é a média ponderada pela proporção de amostras em cada classe

### Feature Engineering

Etapa crucial no desenvolvimento de modelos de machine learning, porque pode ajudar a melhorar o desempenho do modelo e a capacidade de generalização. Em geral, feature engineering envolve a seleção das variáveis mais importantes para um determinado problema, bem como a criação de novas variáveis que possam ajudar a capturar relações mais complexas entre as variáveis.

Nesse caso, descobrimos as variáveis (features) mais importantes para o modelo usando Árvore de Decisão.

## Conclusão

A análise exploratória de dados e a construção de um modelo de machine learning podem ajudar a concessionária de veículos a entender melhor seus clientes e a tomar decisões informadas sobre o gerenciamento de estoque e a adoção de medidas para aumentar as vendas. É importante lembrar que esses processos são iterativos e devem ser continuamente revisados e ajustados à medida que surgem novos insights e informações.

## Contato e licença

Este é um objeto de estudo, que utilizou como referência o artigo mencionado anteriormente.
Sem restrições ao uso, modificações e distribuição do código fonte.

Feito com ❤️ por Leonardo Mafra.