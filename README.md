# Análise de Regressão Linear Múltipla — USArrests

Projeto desenvolvido para a disciplina de **Estatística Aplicada — UFCG (2026.1)**.

O projeto realiza uma análise estatística do conjunto de dados **USArrests**, buscando modelar a taxa de prisões por assalto (`Assault`) a partir das taxas de prisões por assassinato (`Murder`) e estupro (`Rape`), além do percentual de população urbana (`UrbanPop`).

## Objetivo

Aplicar **Regressão Linear Múltipla** para:

* explorar e descrever os dados;
* avaliar as relações entre as variáveis;
* verificar a presença de multicolinearidade;
* comparar e selecionar modelos;
* avaliar os pressupostos da regressão por meio da análise de resíduos;
* identificar observações atípicas, de alavanca e influentes;
* realizar previsões e calcular intervalos de confiança e de predição.

## Dados

A análise utiliza a base `USArrests`, composta por **50 estados americanos** e quatro variáveis numéricas:

| Variável   | Descrição                                      |
| ---------- | ---------------------------------------------- |
| `Murder`   | Prisões por assassinato por 100 mil habitantes |
| `Assault`  | Prisões por assalto por 100 mil habitantes     |
| `UrbanPop` | Percentual da população urbana                 |
| `Rape`     | Prisões por estupro por 100 mil habitantes     |

A variável `Assault` é utilizada como variável resposta.

## Análise

O modelo inicialmente considera as três variáveis explicativas. A análise de multicolinearidade é realizada por meio da matriz de correlação e do **VIF**. Em seguida, os modelos candidatos são comparados utilizando **AIC, BIC e teste F**.

O modelo final selecionado utiliza:

```text
Assault ~ Murder + Rape
```

A variável `UrbanPop` foi removida por não apresentar evidências suficientes de associação com `Assault`. O modelo reduzido apresentou AIC e BIC menores, mantendo praticamente o mesmo poder explicativo do modelo completo.

Também são realizados:

* análise dos resíduos;
* avaliação da normalidade e homocedasticidade;
* análise de pontos atípicos e influentes;
* comparação do modelo com e sem observações influentes;
* análise dos coeficientes padronizados;
* intervalos de confiança;
* intervalos de predição.

## Estrutura

```text
.
├── README.md
├── relatorio/
│   └── relatorio.pdf
├── dados/
├── scripts/
├── figuras/
└── tabelas/
```

A organização dos diretórios pode variar conforme os arquivos utilizados na implementação.

## Resultados principais

O modelo final apresentou **R² ajustado = 0,697** e mostrou que `Murder` e `Rape` possuem associação positiva com `Assault`. O coeficiente padronizado de `Murder` também foi maior que o de `Rape`, indicando maior contribuição relativa dessa variável no modelo.

O projeto também disponibiliza as análises gráficas e resultados utilizados na elaboração do relatório.

## Relatório

O relatório completo apresenta a metodologia, resultados, diagnóstico do modelo, previsões e conclusões da análise.
