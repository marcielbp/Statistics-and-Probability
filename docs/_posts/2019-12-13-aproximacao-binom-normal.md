---
title: "Aproximação Binomial pela Normal"
date: 2019-12-13T21:20:30-03:00
categories:
  - probabilidade
tags:
  - python
  - funcao-probabilidade
toc: true
toc_sticky: true
---

<script>
  MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
  </script>
  <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js"></script>
  
   <script src="https://cdn.jsdelivr.net/npm/mermaid@8.4.0/dist/mermaid.min.js"></script>
 <script>mermaid.initialize({startOnLoad:true});</script>


# Distribuição Normal e aproximações da Binomial e Poisson
Anteriormente, estabelecemos uma metodologia para determinar a probabilidade de intervalos de uma distribuição normal arbitrária, fazendo sua normalização em torno da média e da variância. A variável aleatória da distribuição normal padrão é definida como:
$$z=\left(\frac{x-\mu}{\sigma}\right)$$ 
O valor de referência é consultado em uma tabela da distribuição cumulativa da normal padrão, como segue abaixo:

|x|0|0,01|0,02|0,03|0,04|0,05|0,06|0,07|0,08|0,09|
|--|--|--|--|--|--|--|--|--|--|--|
|0,0|0,5000|0,5040|0,5080|0,5120|0,5160|0,5199|0,5239|0,5279|0,5319|0,5359|
|0,1|0,5398|0,5438|0,5478|0,5517|0,5557|0,5596|0,5636|0,5675|0,5714|0,5753|
|0,2|0,5793|0,5832|0,5871|0,5910|0,5948|0,5987|0,6026|0,6064|0,6103|0,6141|
|0,3|0,6179|0,6217|0,6255|0,6293|0,6331|0,6368|0,6406|0,6443|0,6480|0,6517|
|0,4|0,6554|0,6591|0,6628|0,6664|0,6700|0,6736|0,6772|0,6808|0,6844|0,6879|
|0,5|0,6915|0,6950|0,6985|0,7019|0,7054|0,7088|0,7123|0,7157|0,7190|0,7224|
|0,6|0,7257|0,7291|0,7324|0,7357|0,7389|0,7422|0,7454|0,7486|0,7517|0,7549|
|0,7|0,7580|0,7611|0,7642|0,7673|0,7704|0,7734|0,7764|0,7794|0,7823|0,7852|
|0,8|0,7881|0,7910|0,7939|0,7967|0,7995|0,8023|0,8051|0,8078|0,8106|0,8133|
|0,9|0,8159|0,8186|0,8212|0,8238|0,8264|0,8289|0,8315|0,8340|0,8365|0,8389|
|1,0|0,8413|0,8438|0,8461|0,8485|0,8508|0,8531|0,8554|0,8577|0,8599|0,8621|
|1,1|0,8643|0,8665|0,8686|0,8708|0,8729|0,8749|0,8770|0,8790|0,8810|0,8830|
|1,2|0,8849|0,8869|0,8888|0,8907|0,8925|0,8944|0,8962|0,8980|0,8997|0,9015|
|1,3|0,9032|0,9049|0,9066|0,9082|0,9099|0,9115|0,9131|0,9147|0,9162|0,9177|
|1,4|0,9192|0,9207|0,9222|0,9236|0,9251|0,9265|0,9279|0,9292|0,9306|0,9319|
|1,5|0,9332|0,9345|0,9357|0,9370|0,9382|0,9394|0,9406|0,9418|0,9429|0,9441|
|1,6|0,9452|0,9463|0,9474|0,9484|0,9495|0,9505|0,9515|0,9525|0,9535|0,9545|
|1,7|0,9554|0,9564|0,9573|0,9582|0,9591|0,9599|0,9608|0,9616|0,9625|0,9633|
|1,8|0,9641|0,9649|0,9656|0,9664|0,9671|0,9678|0,9686|0,9693|0,9699|0,9706|
|1,9|0,9713|0,9719|0,9726|0,9732|0,9738|0,9744|0,9750|0,9756|0,9761|0,9767|
|2,0|0,9772|0,9778|0,9783|0,9788|0,9793|0,9798|0,9803|0,9808|0,9812|0,9817|
|2,1|0,9821|0,9826|0,9830|0,9834|0,9838|0,9842|0,9846|0,9850|0,9854|0,9857|
|2,2|0,9861|0,9864|0,9868|0,9871|0,9875|0,9878|0,9881|0,9884|0,9887|0,9890|
|2,3|0,9893|0,9896|0,9898|0,9901|0,9904|0,9906|0,9909|0,9911|0,9913|0,9916|
|2,4|0,9918|0,9920|0,9922|0,9925|0,9927|0,9929|0,9931|0,9932|0,9934|0,9936|
|2,5|0,9938|0,9940|0,9941|0,9943|0,9945|0,9946|0,9948|0,9949|0,9951|0,9952|
|2,6|0,9953|0,9955|0,9956|0,9957|0,9959|0,9960|0,9961|0,9962|0,9963|0,9964|

## Padronização da normal
Em `python`, encontramos o valor a probabilidade desejada utilizando o método `norm.cdf(z, loc=0, scale=1)`, admitindo uma normal padrão, da classe `stats` da biblioteca `scipy`.

### Exemplo
Encontre os valores das probabilidades a seguir:
- $P(Z \le 1)$
````python
import numpy as np
import scipy.stats as st
#Distribuicao normal
z = 1
prob = st.norm.cdf(z,loc=0, scale=1)
print(prob)
````
- $P(Z \ge 2,2)$
````python
import numpy as np
import scipy.stats as st
#Distribuicao normal
z = 2.2
#p(x<=A) = 1 - P(x>=A)
prob = 1 - st.norm.cdf(z,loc=0, scale=1)
print(prob)
````
- $P(Z \ge -2)$
- $P(Z \le 1,2)$

Compare os valores obtidos com a tabela normal padrão apresentada.
### Exercício
Realize a padronização das variáveis normais a seguir e determine a probabilidade:
- $X_1 \sim N(\mu = 4, \sigma^2 = 4)$
	- Determinar $P(X_1 \le 4)$, $P(X_1 \ge 8)$ e $P(2 < X_1 < 5)$
````python
import numpy as np
import scipy.stats as st
#Distribuicao normal
x = 4 #valor de referencia
media = 4
variancia = 4
desvPadrao = np.sqrt(variancia)
#padronizacao em Z
z = (x - media)/desvPadrao
prob = st.norm.cdf(z,loc=0, scale=1)
print(prob)
````
- $X_2 \sim N(\mu = 250, \sigma^2 = 400)$
- $X_3 \sim N(\mu = 1500, \sigma^2 = 1600)$


## Aproximação da distribuição binomial

Em uma distribuição binomial, existem n ensaios de Bernoulli independentes, com probabilidade de sucesso $p$;
$X$ é o número de sucessos observados nos $n$ ensaios, portanto $X$ obedece a uma distribuição binomial;
Lembrando que, para uma distribuição Binomial: $E\{X\} = np$ e $VAR\{X\} = np(1-p)$  e a probabilidade de $k$ sucessos em $n$ tentativas é dada pela expressão:
$$P(X=k) = \binom{n}{k}p^k(1-p)^{(n-k)}$$

Em `python`, encontramos o valor da probabilidade desejada utilizando o método `binom.cdf(x, n, p)`, da classe `stats` da biblioteca `scipy`. Por exemplo, para calcularmos a probabilidade de 2 sucessos em 10 tentativas, sabendo a probabilidade de sucesso é de $p = 0,25$, utilizamos o código a seguir:
````python
import numpy as np
import matplotlib.pyplot as plt
import scipy.stats as st
#numero de tentativas
n = 10
#probabilidade de sucesso 
p = 0.25
#numero de sucessos
x = 2
prob = st.binom.cdf(x, n, p)
print(prob)
````
Modifique o código acima para mostrar a probabilidade do exemplo a seguir:
### Exemplo
*Uma moeda honesta é lançada n = 10 vezes em idênticas condições. Determinar a  probabilidade de ocorrer cara entre 40% e 70% das vezes, inclusive.*

Percebemos nesse exemplo que é possível obter as probabilidades de forma manual. No entanto, quando o número de experimentos de Bernoulli aumenta, o binômio de newton assume um valor numérico muito alto, enquanto que as potências reduzem a valores cada vez menores. Portanto, é difícil ou pouco prático encontrarmos o valor de probabilidade para um número alto de repetições;

O aumento no número de repetições implica em um histograma bastante similar ao da distribuição normal;
````python
import numpy as np
import matplotlib.pyplot as plt
import scipy.stats as st
n=10
p=0.5
x = np.arange(n+1)
plt.vlines(x, 0, st.binom.pmf(x, n, p), colors='b', lw=8, alpha=0.5)
plt.legend(loc='best', frameon=False)
plt.show()
````
Aumente o numero de realizações $n$ para 50, 100, 250 e veja o que acontece quando se muda $p$ para $0,25$ e $0,75$.

### Procedimento para aproximação da binomial

Se $X$ é uma variável aleatória do tipo binomial com parâmetros $n$ e $p$:
$$
Z = \frac{X - np}{\sqrt{np(1-p)}}
$$
A variável Z é aproximadamente uma **distribuição normal;**
Para a aproximação apropriada, é necessário aplicar um fator de correção de  continuidade tal que:
- Quando $P(X \le x)$:
$$
P(X \le x + 0,5) \approx P\left(Z \le \frac{x + 0,5 - np}{\sqrt{np(1-p)}} \right)
$$
- Quando $P(X \ge x)$:
$$
P(X \ge x - 0,5) \approx P\left(Z \ge \frac{x - 0,5 - np}{\sqrt{np(1-p)}} \right)
$$
A aproximação é boa quando $np >5$ e $n(1− p)>5$

Voltando ao exemplo da moeda lançada 10 vezes, vamos fazer a padronização em `python`, um exemplo de código para realizar a aproximação é mostrado a seguir:
````python
import numpy as np
import scipy.stats as st
#Parametros da Binomial
n = 10
p = 0.5
#Limites superior e inferior
x1 = 4
x2 = 7
media = n*p
variancia = n*p*(1-p)
desvPadrao = np.sqrt(variancia)
#Limite superior
z2 = (x2 + 0.5 - media)/desvPadrao
#Limite inferior
z1 = (x1 - 0.5 - media)/desvPadrao
#probabilidade
prob = st.norm.cdf(z2,loc=0, scale=1) - st.norm.cdf(z1,loc=0, scale=1)
print(prob)
````

Compare com a solução teórica a seguir:
$$
P(4 \le X \le 7) = \sum_{k=4}^{7}\binom{10}{k}(0,5)^k(0,5)^{(10-k)} = 
$$
````python
import numpy as np
import scipy.stats as st
#Parametros da Binomial
n = 10
p = 0.5
#Calculo recursivo das probabilidades
probTotal = 0.0
for i in range(4,8):
	probTotal = probTotal + st.binom.pmf(i, n, p)
print(probTotal)
````
### Exemplo 2
Uma prova é constituída de 20 testes com quatro alternativas cada. Um aluno não estudou a matéria e vai respondê-los ao acaso. Qual a probabilidade de acertar 50% ou mais das questões?
Onserve que $X \sim B(N = 20; p = 0,25)$ é binomial
Fazendo pelo método tradicional, temos:
$$
P(X\ge 50\%) = P(X\ge 10) =P(10) + P(11) + \cdots + P(20)
$$
O código a seguir utiliza o método `binom.pmf(x, n, p)` para calcular $x$ sucessos de uma binomial de probabilidade de sucesso $p$ e $n$ tentativas.
````python
import numpy as np
import matplotlib.pyplot as plt
import scipy.stats as st
#numero de tentativas
n = 20
#probabilidade de sucesso 
p = 0.25
#numero de sucessos
x = 10
probAcum = 0
for i in range (10,21):
	prob = st.binom.pmf(i, n, p)
	probAcum = probAcum + prob
	print("Probabilidade de acertar" ,i,  "Questoes: ", prob)
print("Probabilidade de acertar mais de 10 Questoes:", probAcum)
````
Para fazermos a aproximação, definimos os valores a seguir:
$$Z \ge \frac{x - 0,5 - np}{\sqrt{np(1-p)}}$$
Portanto
$$P(X\ge 10) = P\left(Z \ge \frac{10 - 0,5 - np}{\sqrt{np(1-p)}} \right)$$
Sabemos que $np = 10\cdot 0,25 = 2,5$ e $\sqrt{np(1-p)} = 1,936$
Assim:
$$P(X\ge 10) = P\left(Z \ge \frac{4,5}{1,581} \right) =$$
$$= P\left(Z \ge 3,6157\right) = 1- P\left(Z \le 3,6157\right) = 0,001$$
Ou seja, pela aproximação via distribuição normal, a probabilidade será de aproximadamente 1%. 

## Aproximação da Poisson
A distribuição de Poisson é desenvolvida quando se considera o número de tentativas de uma variável Binomial tendendo ao infinito, então, é de se esperar que a distribuição normal também possa aproximá-la:
$$
P(X) = \frac{e^{-\lambda} \lambda^x}{x!}
$$
Os parâmetros da distribuição de Poisson são: $E\{X\} = VAR\{X\} = \lambda$  

Utiliza-se o mesmo fator de correção de continuidade utilizado na distribuição Binomial deve ser utilizado na aproximação de Poisson. Por sua vez, a aproximação se torna boa quando $\lambda > 5$.
### Exemplo 3
Em 2h, 360 chamadas chegam em uma central telefônica. Qual a chance de que cheguem entre 70 e 100 chamadas num dado intervalo de 30min (dentro das 2h)?
Modelamos a distribuição como uma variável de Poisson cujo parâmetro $\lambda = 90$.

Neste exemplo, podemos visualizar a solução analítica da seguinte forma:
$$P(70 \le x \le 100) = \sum_{x=70}^{100} \frac{e^{-90} \lambda^x}{x!}$$
Observe que é impraticável tentarmos resolver o exemplo manualmente. Assim, escrevemos uma nova variável 
$$
Z = \frac{X - \lambda}{\sqrt{\lambda}}
$$
Com o fator de correção, teremos:
- Quando $P(X \le x)$:
$$
P(X \le x + 0,5) \approx P\left(Z \le \frac{x + 0,5 - \lambda}{\sqrt{\lambda}} \right)
$$
- Quando $P(X \ge x)$:
$$
P(X \ge x - 0,5) \approx P\left(Z \ge \frac{x - 0,5 - \lambda}{\sqrt{\lambda}} \right)
$$
Assim, rescrevemos o exemplo como:
$$P(70 \le x \le 100)  = P(X \le 100,5) - P(X \le 69,5) $$
$$P(X \le 100,5)= P\left(Z \le \frac{100,5- 90}{\sqrt{90}} \right) =  P\left(Z \le  1,11\right) = 0,8665$$
$$P(X \le 69,5)= P\left(Z \le \frac{69,5- 90}{\sqrt{90}} \right)=  P\left(Z \le  -2,16\right) = 0,01538$$
A probabilidade se torna $P(70 \le x \le 100) = 0,8511$
## Exercícios de aplicação

1. A vida de um semicondutor a laser é normalmente distribuída com média 7000 horas e desvio-padrão de 600 horas. Qual a probabilidade do laser falhar antes de 5000 horas?
2. Uma maquina produz 400 parafusos, dos quais 5% apresenta algum defeito. Determine a probabilidade de:
a. No máximo 30 sejam defeituosos;
b. Entre 25 e 45 defeituosos;
c. mais de 50 parafusos defeituosos;

> Written with [StackEdit](https://stackedit.io/).






