# Usando Correspondencia Multipla no dataset do titanic

---
## Project Overview

Fonte: https://www.kaggle.com/datasets/yasserh/titanic-dataset/data
Resultado: https://fernezlian.github.io/titanicmca/grafico_3D.html

Objetivo: Aplicar a Análise de Correspondência Múltipla ao dataset do Titanic para identificar padrões de associação entre sobrevivência e características dos passageiros.

---
## Dataset

O Dataset tem as seguintes colunas:

```
→ PassengerId - ID do passageiro
→ Survived - Se sobreviveu ou não, inicialmente com 0 e 1
→ Pclass - Qual a classe do passageiro, iniciamente com 1, 2 e 3 como as classes
→ Name - Nome dos passageiros
→ Sex - Sexo dos passageiros
→ Age - Idade dos passageiros
→ SibSp - Número de irmãos
→ Parch - Número de pessoas na familia
→ Ticket - Numero do ticket
→ Fare - Tarifa do passageiro
→ Cabin - Número da cabine
→ Embarked - Onde embarcou
```

---
## Pipeline

```
→ Escolha de colunas relevantes
→ Mudança para variáveis qualitativas
→ Tabelas de frequencia
→ Cálculo do p-value para as tabelas de frequencia
→ Cálculo das coordenadas
→ Gráfico plotado
```

---
## Exploração e decisões metodológicas

### Coluna nova de idade

Foi feito inicialmente uma distribuição igualitária das idades em 3 partes, 33% para 'pessoas jovens', 33% para 'pessoas adultas' e o restante para ' pessoas idosas, porem quando foi calculado o p-value observou-se que, com um p-value = 0.8835, não rejeita-se a hipótese nula de independência, ou seja, as categorias de idade que criadas não explicam a sobrevivência.

Para resolver isso foi feito uma divisão entre idades e grupos conhecidos, como:

0-12 anos - Criança
12-18 anos - Adolescente
18-60 anos - Adulto
60-100 anos - Idoso

Com isso o p-value deu 0.0062.

---
## Resultado final

A Análise de Correspondência Múltipla mostrou-se eficaz para identificar associações entre sexo, classe social e sobrevivência, evidenciando padrões consistentes com o contexto histórico do naufrágio do Titanic.

---
## Interpretação crítica

Como é possivel observar no grafico 3D (arquivo em .html), existe uma alta associação entre o sexo e a taxa de sobrevivência, algo particularmente surpreendente, pois imaginava-se que o grupo de idosos ou crianças seriam mais associados com sobreviver ou não.

---
## Dependências

Instalação:
```bash
pip install pandas pathlib sys numpy scipy.stats seaborn matplotlib prince itertools plotly
```

---
## Estrutura do repositório

```
├── data/
│ └── raw/
│ └── customer_data.csv
├── notebook/
│ └── cluster.ipynb
├── src
└── README.md
```