# Quality Inspection CNN

Projeto de **Deep Learning com CNN** para **inspeção visual de qualidade** em peças metálicas, com classificação binária entre **OK** e **defeituosa**.

## Objetivo do projeto
O objetivo foi desenvolver uma solução de classificação de imagens alinhada com a lógica trabalhada na unidade curricular de **Deep Learning**, usando **TensorFlow/Keras** e seguindo uma abordagem experimental simples e coerente:

- definição do problema;
- construção de uma **baseline**;
- aumento de complexidade do modelo;
- observação de **tendência a overfitting**;
- aplicação de **regularização**;
- escolha do modelo final com base no desempenho em validação;
- avaliação final no conjunto de teste.

## Problema
O problema consiste em classificar imagens industriais de peças fundidas em duas classes:

- **ok_front** → peça sem defeito visível;
- **def_front** → peça com defeito visível.

Trata-se, portanto, de um problema de **classificação binária de imagens** com aplicação potencial em **inspeção visual automática em contexto industrial**.

## Dataset
O dataset **não está incluído neste repositório** devido ao tamanho dos ficheiros.

Dataset original no Kaggle:
https://www.kaggle.com/datasets/ravirajsinh45/real-life-industrial-dataset-of-casting-product

### Como usar o dataset
1. Fazer download do dataset no link acima.
2. Extrair os ficheiros localmente.
3. Garantir que a estrutura do dataset fica compatível com o notebook.
4. Se necessário, ajustar no notebook o caminho para a pasta local dos dados.

Este projeto foi preparado para ser executado **localmente**.

## Estrutura esperada dos dados
No notebook, o dataset foi considerado numa estrutura semelhante a esta:

```text
archive/
└── casting_data/
    └── casting_data/
        ├── train/
        └── test/
```

Se a tua estrutura local for diferente, basta ajustar o caminho da variável correspondente no notebook.

## Como executar localmente

1. Fazer download do dataset original no Kaggle.
2. Extrair o dataset localmente.
3. Abrir o ficheiro `casting_defects.ipynb` no VS Code ou Jupyter Notebook.
4. Se necessário, ajustar no notebook o caminho para a pasta do dataset.
5. Executar as células pela ordem apresentada.

## Metodologia
O projeto foi organizado em três momentos principais:

### 1. Baseline
Foi construída uma CNN simples, com o objetivo de estabelecer um ponto de partida claro para comparação.

### 2. Modelo com maior capacidade
Foi criado um modelo mais complexo, com mais capacidade de aprendizagem, para analisar a evolução do desempenho e observar tendência a overfitting.

### 3. Modelo regularizado
Foi aplicada regularização para controlar melhor o treino e melhorar a generalização, originando o modelo final selecionado.

## Resultados finais
O modelo final regularizado apresentou resultados muito fortes no conjunto de teste:

- **Accuracy:** 0.9930
- **Precision (def_front):** 0.9978
- **Recall (def_front):** 0.9912
- **F1-score:** 0.9945

## Principais conclusões
- A **baseline** já apresentou desempenho elevado.
- O aumento de capacidade permitiu observar **tendência a overfitting**, embora de forma moderada.
- O **modelo regularizado** foi o mais equilibrado e o que melhor generalizou.
- O problema mostrou-se relativamente aprendível para CNNs, o que ajuda a explicar a dificuldade em provocar um overfitting extremo.

## Desenvolvimentos futuros
Algumas extensões naturais do projeto seriam:

- testar **data augmentation** de forma controlada;
- validar o modelo em **novos lotes de produção**;
- estudar diferentes **limiares de decisão**;
- explorar técnicas de **explicabilidade visual**;
- aproximar a solução de um fluxo real de produção.

