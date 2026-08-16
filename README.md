# Análise de Regressão Linear Múltipla — USArrests

Projeto desenvolvido para a disciplina de **Estatística Aplicada — UFCG (2026.1)**.

O projeto realiza uma análise estatística do conjunto de dados **USArrests**, buscando modelar a taxa de prisões por assalto (`Assault`) a partir das taxas de prisões por assassinato (`Murder`) e estupro (`Rape`), além do percentual de população urbana (`UrbanPop`).

## Objetivo

Aplicar **Regressão Linear Múltipla** para:

* explorar e descrever os dados;
* avaliar as relações entre as variáveis;
* verificar a presença de multicolinearidade;
* comparar e selecionar modelos através do Critério de Informação de Akaike (AIC);
* avaliar os pressupostos da regressão por meio da análise de resíduos;
* identificar observações atípicas, de alavanca e influentes;
* realizar previsões e calcular intervalos de confiança e de predição.

## Dados

A análise utiliza a base `USArrests`, composta por **50 estados americanos** e quatro variáveis numéricas:

| Variável   | Descrição                                      |
| :--------- | :--------------------------------------------- |
| `Murder`   | Prisões por assassinato por 100 mil habitantes |
| `Assault`  | Prisões por assalto por 100 mil habitantes     |
| `UrbanPop` | Percentual da população urbana                 |
| `Rape`     | Prisões por estupro por 100 mil habitantes     |

A variável `Assault` é utilizada como variável resposta.

## Análise

O modelo inicialmente considera as três variáveis explicativas contínuas. A análise de multicolinearidade é realizada por meio da matriz de correlação e do **VIF**. Em seguida, os modelos candidatos são comparados utilizando o **AIC**.

O modelo final selecionado utiliza:

```text
Assault ~ Murder + Rape

```

A variável `UrbanPop` foi removida por não apresentar significância estatística no modelo inicial. O modelo reduzido apresentou AIC menor, mantendo praticamente o mesmo poder explicativo do modelo completo, o que o torna mais simples e parcimonioso.

Também são realizados:

* análise dos resíduos;
* avaliação da normalidade e homocedasticidade;
* análise de pontos atípicos e influentes;
* comparação do modelo com e sem observações influentes;
* cálculo de intervalos de confiança para o valor médio esperado;
* cálculo de intervalos de predição para novas observações.

## Resultados principais

O modelo final apresentou **R² ajustado = 0,697** e mostrou que as variáveis `Murder` e `Rape` possuem associação positiva e coerente com `Assault`.

O projeto também disponibiliza as análises gráficas e resultados utilizados na elaboração do relatório.

## Relatório

O relatório completo apresenta a metodologia, resultados, diagnóstico do modelo, previsões e conclusões da análise.
