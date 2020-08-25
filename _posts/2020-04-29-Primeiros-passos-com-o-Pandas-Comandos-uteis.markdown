---
layout: post
title:  Primeiros passos com Pandas - Comandos úteis
date:   2020-04-29 10:18:00
categories: data-science python
image: "/assets/images/pandas.jpg"
---

<p>O <i>Pandas</i> é uma biblioteca Python que fornece estruturas e ferramentas de análise de dados. A ideia deste post não é explorar todas as funções e estruturas de dados do Pandas, mas sim trazer algumas funcionalidades simples, porém importantes para análise, tratamento e manipulação de dados.</p>

><p>Nos exemplos que vou trazer logo abaixo, estou rodando um ambiente virtual com o Anaconda e Jupiter Notebook.</p>

* **Anaconda:**<br>
É uma plataforma que auxilia na preparação do ambiente necessário para o trabalho com análise de dados e ciência de dados que contém a maioria das bibliotecas científicas comumente usadas.
[Saiba mais.](https://www.anaconda.com/){:target="_blank" rel="noopener"}


* **Jupiter Notebook:**<br>
Resumindo, é uma aplicação web que pode ajudar a entender e visualizar dados e resultados de análises.
[Saiba mais.](https://jupyter.org/){:target="_blank" rel="noopener"}

Antes de mais nada vamos precisar importar o *Pandas*, utilizando a regra de convenção. Logo, seguimos com os comandos:

 **Importando *Pandas*:**
~~~python
import panda as pd
~~~

  **Lendo um arquivo .csv e setando em um *dataframe* = df:**
```python
df = pd.read_csv('nome_do_arquivo.csv')
```

 **Visualizando as 5 primeiras linhas do arquivo, caso queira visualizar mais linhas, basta adicionar o número de linhas como parâmetro:**
```python
df.head()
df.head(120)
``` 
<p><img class="image-post" src="/assets/images/pandas-head.png"></p>

 **Descobrindo a quantidade de linhas e colunas do *dataframe*:**
```python
df.shape
```
<p><img class="image-post" src="/assets/images/pandas-shape.png"></p>

 **Descobrindo o nome de cada coluna, o número de linhas por coluna e o tipo de dado de cada uma dessas colunas. Também temos a informação da quantidade de memória utilizada para ler o arquivo.**
```python
df.info()
```
<p><img class="image-post" src="/assets/images/pandas-info.png"></p>

**Para trazer somente o nome das colunas:**
```python
df.columns
```
<p><img class="image-post" src="/assets/images/pandas-columns.png"></p>

 **Geralmente para resumir as estatísticas dos dados se usa o método describe:**
```python
df.describe()
df ['nome_da_coluna'].describe()
```
<p><img class="image-post" src="/assets/images/pandas-describe.png"></p>

 **Somando valores do *dataframe* ou de uma coluna especifica:**
```python
df.sum()
df ['nome_coluna'].sum()
```
<p><img class="image-post" src="/assets/images/pandas-sum.png"></p>


**Encontrando os maiores valores dentro do *dataframe* ou de uma coluna especifica:**
```python
df.max()
df ['nome_coluna'].max()
```
<p><img class="image-post" src="/assets/images/pandas-max.png"></p>

**Encontrando os menores valores dentro do *dataframe* ou de uma coluna especifica:**
```python
df.min()
df ['nome_coluna'].min()
```
<p><img class="image-post" src="/assets/images/pandas-min.png"></p>

**Localizando a média dos valores dentro do *dataframe* ou de uma coluna especifica:**
```python
df.mean()
df ['nome_coluna'].mean ()
```
<p><img class="image-post" src="/assets/images/pandas-mean.png"></p>

**Encontrando a mediana dos valores dentro do *dataframe* ou de uma coluna especifica:**
```python
df.median()
df ['nome_coluna'].median ()
```
<p><img class="image-post" src="/assets/images/pandas-median.png"></p>

**Agrupando e realizando análises aos dados:**
Neste exemplo, estou agrupando o *Dataframe* por estados (coluna de agrupamento) e tirando a média da pontuação de crédito (coluna agregadora + função agregadora):
```python
df.groupby ('coluna_de_agrupamento')['coluna_agredadora'].função_agredadora()
```
<p><img class="image-post" src="/assets/images/pandas-groupby-mean.png"></p>

Caso a coluna de agrupamento seja a mesma, podemos adicionar mais colunas de agregação, logo também podemos adicionar outras funções agredadoras, veja:

```python
df.groupby ('estado_residencia'). agg ({
                                    'saldo_conta': ['min', 'max'], 
                                    'nivel_estabilidade': ['median'],
                                    'numero_produtos': ['mean']})
```
<p><img class="image-post" src="/assets/images/pandas-groupby-agg.png"></p>

Na imagem acima, realizei o agrupamento por estado, trouxe o valor máximo e mínimo referente ao saldo da conta, a mediana da idade e a média da pontuação de crédito.

**Criando variáveis para análises:**
Neste exemplo, criei uma variavál chamada *idade_idoso* e foi setado a seguinta regra:
Para pessoas com idade igual e maior que 60 anos, inclua como *idoso*, para as demais inclua como *nao_idoso*, veja:
```python
df ['idade_idoso'] = ['idoso' if x >= 60 else 'não_idoso' for x in df ['idade']]
```
<p><img class="image-post" src="/assets/images/pandas-variable.png"></p>

Logo, realizei um filtro de agrupamento junto com uma função de agregadora para identificar quantas pessoas da minha base eram considerados idosas. No Brasil, por lei, pessoas com idade igual e maior que 60 anos, são identificadas como idosas.
```python
df.groupby('idade_idoso')['idade'].count()
```
<p><img class="image-post" src="/assets/images/pandas-variable-groupby.png"></p>

**Conclusão:**
Nesta base, temos 360 pessoas com idade maior que 60 anos, logo consideradas como idosas e 6640 menores de 60 anos.

**Contando valores únicos no *Dataframe*:** Nesse caso, vou utilizar dois exemplos. <br>
**Exemplo 1:** Identificando quantos id's únicos existem:
```python
df['id'].nunique()
```
<p><img class="image-post" src="/assets/images/pandas-nunique.png"></p>

**Exemplo 2:** Saber quantas idades diferentes existe dentro do *dataframe*:
```python
df['idade'].nunique()
```
<p><img class="image-post" src="/assets/images/pandas-nunique-idade.png"></p>

A base utilizada para este *Dataframe* foi concedida pela Codenation em um dos desafios realizados.<br>
Me coloco à disposição para qualquer dúvida, na [minha página](https://melzilucas.github.io/about.html){:target="_blank" rel="noopener"} deixei minhas redes sociais e também o meu [GitHub](https://github.com/melzilucas/codenation-studies){:target="_blank" rel="noopener"} com outros exemplos utilizando o Pandas.