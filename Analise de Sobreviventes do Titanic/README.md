# Análise de Sobreviventes do Titanic

Este projeto realiza uma análise exploratória de dados (EDA) e modelagem preditiva dos passageiros do Titanic. O objetivo principal é identificar fatores que influenciam a sobrevivência no naufrágio e construir um modelo de Deep Learning para prever a sobrevivência de novos passageiros com base nas suas características.

## Estrutura do Projeto

Este projeto está organizado nas seguintes etapas:

1. **Carregamento e Limpeza dos Dados**
2. **Análise Exploratória de Dados (EDA)**
3. **Engenharia de Atributos**
4. **Visualizações**
5. **Modelagem Preditiva com Multi-Layer Perceptron (MLP)**
6. **Análise de Erros e Ajustes no Modelo**

## 1. Carregamento e Limpeza dos Dados

O dataset contém informações sobre passageiros do Titanic, como:

- `PassengerId`: Identificador do passageiro.
- `Pclass`: Classe do passageiro (1, 2, 3).
- `Name`: Nome do passageiro.
- `Sex`: Gênero do passageiro.
- `Age`: Idade do passageiro.
- `SibSp`: Número de irmãos/cônjuges a bordo.
- `Parch`: Número de pais/filhos a bordo.
- `Ticket`: Número do bilhete.
- `Fare`: Tarifa paga pelo passageiro.
- `Cabin`: Número da cabine.
- `Embarked`: Porto de embarque.

Foi feita uma limpeza inicial, onde foram removidas as colunas com muitas ausências de dados (`Cabin`, `Ticket`, `PassengerId`), além de tratar valores ausentes nas colunas `Age` e `Embarked`.

## 2. Análise Exploratória de Dados (EDA)

A análise exploratória envolveu:

- **Identificação de valores nulos e valores únicos** para entender a qualidade dos dados.
- **Distribuição das variáveis** (idade, gênero, classe, tarifa, etc.).
- **Correlação entre variáveis** usando gráficos de dispersão.
- **Visualização da taxa de sobrevivência** para diferentes grupos, como por classe, gênero e idade.

## 3. Engenharia de Atributos

Algumas variáveis foram modificadas ou criadas para melhorar a análise e a modelagem:

- **Idade transformada em meses** para maior precisão.
- **Gênero transformado para uma variável binária** (0: Homem, 1: Mulher).
- **Criação de variável "Adult"** para distinguir entre adultos e crianças.

## 4. Visualizações

Gráficos interativos foram gerados usando **Plotly** para explorar e visualizar as distribuições dos dados, como:

- Taxa de sobrevivência por classe e gênero.
- Distribuições de idade, tarifa e outras variáveis.
- Análise de sobreviventes por número de irmãos/cônjuges a bordo (SibSp) e pais/filhos a bordo (Parch).

## 5. Modelagem Preditiva com Multi-Layer Perceptron (MLP)

A modelagem preditiva foi realizada com um **Multi-Layer Perceptron (MLP)**, um tipo de rede neural, utilizando as seguintes etapas:

- **Pré-processamento dos dados**: Normalização das variáveis com `MinMaxScaler`.
- **Divisão dos dados**: Separação entre treino e validação (80%/20%).
- **Construção do modelo**: MLP com regularização L2 para evitar overfitting.
- **Avaliação do modelo**: Utilização de métricas como `accuracy`, `precision`, `recall` e `f1-score` para avaliar o desempenho do modelo.

## 6. Análise de Erros e Ajustes no Modelo

Foi realizada uma análise detalhada dos erros cometidos pelo modelo:

- **Precision e Recall**: A precisão e recall para cada classe foram analisadas, e ajustes foram feitos no modelo para melhorar a performance, utilizando a técnica de **sample weighting**.
- **Ajustes nos hiperparâmetros**: Diversas tentativas de alteração no número de neurônios e epochs, juntamente com técnicas de regularização, foram realizadas para otimizar o modelo.

## Resultados

O modelo final obteve uma **acurácia de 83%** e apresentou boas métricas para prever a sobrevivência dos passageiros. No entanto, as análises de erro indicaram que melhorias podem ser feitas, como balancear os dados de classes ou usar outros modelos de Machine Learning.

## Como Executar o Projeto

1. **Instalação das Dependências**
   Certifique-se de ter o Python 3.x instalado. Em seguida, instale as dependências necessárias:

   ```bash
   pip install -r requirements.txt

