# Previsão de Demanda com Modelos de Espaço de Estados

## 1. Objetivo

<p align="justify">
Este projeto demonstra como utilizar um modelo de Espaço de Estados (State Space Model) para realizar previsão de demanda em séries temporais. O exemplo simula dois anos de vendas diárias contendo tendência crescente, sazonalidade semanal, um componente cíclico e ruído aleatório. Em seguida, o modelo identifica automaticamente esses padrões e produz previsões para os próximos sessenta dias juntamente com intervalos de confiança.
</p>

---

## 2. Estrutura do Projeto

```text
state-space-demand/
│
├── explicando_series_temporais.ipynb
├── README.md
├── fig1.png
└── fig2.png
```

---

## 3. Tecnologias Utilizadas

- Python
- NumPy
- Pandas
- Matplotlib
- Statsmodels

---

## 4. Geração da Série Temporal

<p align="justify">
A primeira etapa consiste na criação de uma base sintética de demanda diária ao longo de dois anos. A série é construída combinando quatro componentes fundamentais:
</p>

- tendência crescente;
- sazonalidade semanal;
- componente cíclico;
- ruído aleatório.

<p align="justify">
Esse processo gera uma série temporal semelhante ao comportamento encontrado em problemas reais de previsão de vendas, permitindo avaliar a capacidade do modelo em identificar diferentes padrões simultaneamente.
</p>

---

## 5. Construção do Modelo de Espaço de Estados

<p align="justify">
Após a geração dos dados, é ajustado um modelo <em>Unobserved Components</em> da biblioteca Statsmodels. Esse tipo de modelo representa a série temporal como a soma de componentes latentes que não são observados diretamente, mas são estimados pelo algoritmo durante o treinamento.
</p>

<p align="justify">
Neste exemplo são considerados:
</p>

- tendência local linear;
- sazonalidade semanal;
- componente cíclico.

<p align="justify">
O treinamento estima automaticamente cada componente e seus respectivos parâmetros utilizando máxima verossimilhança.
</p>

---

## 6. Decomposição dos Componentes

<p align="justify">
Depois do treinamento, o modelo permite visualizar separadamente cada componente estimado da série temporal. Essa decomposição facilita compreender quanto da demanda é explicado pela tendência de longo prazo, pela sazonalidade recorrente e pelos ciclos identificados durante o ajuste.
</p>

<p align="justify">
A Figura 1 apresenta essa decomposição realizada automaticamente pelo modelo.
</p>

<p align="center">
<img src="fig1.png" width="850">
</p>

---

## 7. Previsão de Demanda

<p align="justify">
Com o modelo treinado, é realizada uma previsão para os sessenta dias seguintes. Além da estimativa da demanda futura, também são calculados intervalos de confiança de 95%, fornecendo uma medida da incerteza associada às previsões.
</p>

<p align="justify">
Essa abordagem permite não apenas estimar o valor esperado da demanda, mas também avaliar o risco associado às decisões de planejamento.
</p>

---

## 8. Visualização do Forecast

<p align="justify">
A Figura 2 compara os dados históricos com a previsão produzida pelo modelo. A linha vermelha representa a demanda prevista enquanto a região sombreada corresponde ao intervalo de confiança de 95%, indicando a faixa na qual a demanda futura provavelmente estará.
</p>

<p align="center">
<img src="fig2.png" width="900">
</p>

---

## 9. Aplicações

<p align="justify">
Modelos de Espaço de Estados são amplamente utilizados em problemas de previsão devido à capacidade de separar diferentes componentes da série temporal e lidar naturalmente com incertezas. Entre suas aplicações destacam-se previsão de vendas, planejamento de estoques, demanda logística, consumo de energia, séries financeiras, indicadores econômicos e monitoramento de processos industriais.
</p>

---

## 10. Conclusão

<p align="justify">
Os modelos de Espaço de Estados constituem uma ferramenta poderosa para apoiar a tomada de decisão em ambientes onde a demanda apresenta tendência, sazonalidade e variações ao longo do tempo. Ao separar esses componentes e produzir previsões acompanhadas de intervalos de confiança, o modelo fornece uma visão mais completa do comportamento esperado da demanda futura.
</p>

<p align="justify">
No contexto comercial, essas previsões permitem direcionar campanhas promocionais para períodos de baixa demanda, reforçar ações de marketing em momentos estratégicos, ajustar níveis de estoque antes de picos sazonais, otimizar compras junto a fornecedores e planejar equipes de vendas e logística com maior eficiência. Além disso, os intervalos de confiança ajudam a quantificar a incerteza das previsões, permitindo decisões mais seguras em relação à alocação de recursos e ao gerenciamento de riscos.
</p>

<p align="justify">
Dessa forma, modelos de Espaço de Estados transformam séries históricas em informações estratégicas capazes de orientar ações comerciais, reduzir custos operacionais, melhorar o nível de serviço ao cliente e aumentar as oportunidades de geração de receita por meio de um planejamento baseado em dados.
</p>
