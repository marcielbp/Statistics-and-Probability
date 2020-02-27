---
title: "Grandezas Função de Probabilidade"
date: 2019-12-13T21:10:30-03:00
author_profile: false
categories:
  - probabilidade
tags:
  - python
  - funcao-probabilidade
toc: true
---

<script>
  MathJax = {
    tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]}
  };
  </script>
  <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js"></script>
  
   <script src="https://cdn.jsdelivr.net/npm/mermaid@8.4.0/dist/mermaid.min.js"></script>
 <script>mermaid.initialize({startOnLoad:true});</script>

# Determinação de grandezas para uma função de probabilidade
Funções de probabilidade discretas são representações em tabela da probabilidade de ocorrência das várias saídas em um espaço amostral discreto, não necessariamente finito. Vamos relembrar funções de probabilidade simples:
1. Lançamento de um dado de seis faces: $X = \{1, 2, 3, 4, 5,6\}$ $$f_X (X) = \left\{\dfrac{1}{6},\dfrac{1}{6},\dfrac{1}{6},\dfrac{1}{6},\dfrac{1}{6},\dfrac{1}{6}\right\}$$
2. Determinando média e variância dessa função de probabilidade: $$E(X) = \mu_X =  \sum_{i=1}^{n=6}{X_i \cdot f_X(X_i)} = 1\cdot\dfrac{1}{6} + 2\cdot\dfrac{1}{6} + 3\cdot\dfrac{1}{6} + 4\cdot\dfrac{1}{6} + 5\cdot\dfrac{1}{6} + 6\cdot\dfrac{1}{6}  = 3,\!5$$
$$VAR(X) = E(X^2) -\mu_X^2 = \sum_{i=1}^{n=6}{X_i^2 \cdot f_X(X_i)} - (3,\!5)^2$$
$$\sum_{i=1}^{n=6}{X_i^2 \cdot f_X(X_i)} = 1\cdot\dfrac{1}{6} + 4\cdot\dfrac{1}{6} + 9\cdot\dfrac{1}{6} + 16\cdot\dfrac{1}{6} + 25\cdot\dfrac{1}{6} + 36\cdot\dfrac{1}{6}  = 15,\!166$$
$$VAR(X) = 15,\!166 - 12,\!25 = 2,\!916$$
Em python, devemos implementar as equações acima para determinar as média e variância a priori. Observe o código a seguir e implemente-o como `pratica05_parte01.py`:

````python
import numpy as np
#função de probabilidade a priori
fi = [1.0/6.0, 1.0/6.0, 1.0/6.0, 1.0/6.0, 1.0/6.0, 1.0/6.0] 
xi = [1, 2, 3, 4, 5, 6] # variável aleatória
#fi e xi devem ter dimensões identicas
mean = 0.0
desv = 0.0
for i in range(0, len(xi)):
	mean+= float(xi[i])*fi[i]
	desv+= (float(xi[i])**2)*fi[i]
var = desv - mean**2
print('Média a priori:', mean)
print('Variância a priori:', var)
````
Lembre-se que a soma de todas as probabilidades da função de probabilidade deve ser igual a 1. 
 # Trabalhando com método para geração de experimentos aleatórios

Vamos observar o método numpy.random de um objeto numpy. Seja `np` um objeto `numpy`, observe os métodos a seguir (referência: https://docs.scipy.org/doc/numpy/reference/routines.random.html)
````python
np.random.geometric(p[, size])	#Draw samples from the geometric distribution.
np.random.binomial(n, p[, size])	#Draw samples from a binomial distribution.
np.random.normal([loc, scale, size])	#Draw random samples from a normal (Gaussian) distribution.
np.random.poisson([lam, size])	#Draw samples from a Poisson distribution.
np.random.uniform([low, high, size])	#Draw samples from a uniform distribution.
````


Neste momento iremos realizar experimentos utilizando uma distribuição **uniforme**.

No python, utilizar o método `np.random.uniform` significa gerar uma variável aleatória contínua uniforme entre `low` e `high` cuja saída é equiprovável. Porém, a saída não pertence a um espaço amostral contável, sendo necessária uma operação nesta saída para deixá-la em um conjunto contável.

Crie um arquivo chamado `pratica05_parte02.py` contendo o código a    seguir e o execute:           

````python
import numpy as np
n = 10
out = np.random.uniform(0,1,n)
print('Resultados:', out)
````

Observe que as saídas são valores aleatórios entre 0 e 1. Como podemos utilizar para gerar, de maneira equiprovável, os números 0 e 1?

Se o vetor `out` receber o resultado da expressão lógica que verifica em que faixa está o número sorteado, é possível simular uma variável aleatória discreta definindo a probabilidade de cada um dos resultados.
modifique o código para que o vetor out seja definido da seguinte forma:

    out = (np.random.uniform(0,1,n)<0.5)

**verifique a mesma saída**
````python
import numpy as np
n = 10
out = (np.random.uniform(0,1,n)<0.5)
print('Resultados:', out)
````

Observe que, dessa vez, o vetor é composto por saídas lógicas **True** e **False**. Para facilitar nossa contagem, utilizaremos a propriedade de tipagem forte do python para conversão para inteiro.
Faça:

    out = (np.random.uniform(0,1,n)<0.5)*1

**e verifique a saída**

Agora, vamos verificar experimentalmente a probabilidade da saída lógica. Execute o código
````python
import numpy as np
n = 10
p = 0.5
out = (np.random.uniform(0,1,n)<p)*1
print('Proporcao de 1s:', float(sum(out))/float(n))
````

aumente o valor de `n` para `100`, `1000` e `10 000` e verifique para quais valores converge a proporção de UMs

Agora, modifique a proporção `p` para `0.75`, isso significa que a proporção de UMs é de 75% e de 0s será de 25%. Veja para quais valores a proporção converge para `n = 100, 1000, 10 000`.

Dessa vez, iremos gerar um conjunto de valores aleatórios em um espaço amostral discreto finito. 
Observe o método 

    np.random.random_integers(low[, high, size])	Random integers of type np.int between low and high, inclusive

O método irá gerar `size` números inteiros entre "`low`" e "`high`", inclusive.
Execute o código abaixo algumas vezes e observe a saída
````python
import numpy as np
n = 10
out = np.random.random_integers(1,6,n)
print ('Vetor: ', out)
````

Veja que o vetor de saída assume números entre 1 e 6, inclusive. O código simula o lançamento de um dado de seis faces.

Agora verifique experimentalmente a probabilidade de cada face usando o codigo a seguir:
````python
import numpy as np
n = 100
facesDado = sum(np.random.random_integers(1,6,n)) #gera 10 lancamentos
for i in range(1,7): #varredura das saidas 1 a 6, excluindo o 7
	out = (facesDado==i)*1
	print('Probabilidade da face', i, '=', float(out)/float(n))
````

Aumente o n para `1000` e `10 000` e verifique os resultados.
### Exercício 01: 
Crie uma rotina para determinar experimentalmente a probabilidade da soma das faces de um dado 6 após dois lançamentos em sequência para `n = 100, 1000, 10 000`
**Dica:** crie dois dados e faça a soma das faces conforme sugerido abaixo:

    facesDado01 = np.random.random_integers(1,6,n)
    facesDado02 = np.random.random_integers(1,6,n)
    somaFaces = facesDado01 + facesDado02

## Execução de um experimento aleatório

Observe a seguinte pergunta:

**Dado o lançamento de cinco moedas, verificar para quais valores a probabilidade de que saia exatamente quatro caras converge.**

Uma vez que as quatro caras podem sair em qualquer ordem, existem 5 combinações (5!/(4!*1!)) que nos interessam, dentre as 32 possibilidades de sorteio. Portanto, a probabilidade *a priori* que saiam 4 caras vale 5/32, ou 15,63 %
Para verificar experimentalmente, fazemos n repetições, variando `n = 100, 1000, 10 000`. Utilize o código a seguir para executar essas repetições. **OBS**: antes de aumentar o `n` para `100, 1000, 10` comente as linhas com o método `print` dentro do laço `for` e os *prints* que exibem os resultados dos experimentos.
````python
import numpy as np
p = 0.5 #Probabilidade de dar Cara
numDeLanc= 5 #Numero de Lancamentos
n = 10
numCaras = np.int_(np.zeros(n))#vetor que armazenara o numero de caras em cada rodada
experimento = [] #matriz dos resultados dos experimentos
for i in range(0, n): #realização dos experimentos
	experimento.append((np.random.uniform(0,1,numDeLanc)<p)*1) #lancamento de 5 moedas
	print('Resultado do experimento', i+1, ':',experimento[i])
	somaCaras = sum(experimento[i])
	numCaras[i] = (somaCaras)
print('Numero de caras em cada experimento:', numCaras)
vecUns = 4*np.int_(np.ones(n))
vec4Caras = (numCaras == vecUns)*1
print('Experimentos que obtiveram 4 caras: ', vec4Caras)
print('Probabilidade de 4 caras:',float(sum(vec4Caras)/(float(n)))) #exibicao da probabilidade do experimento
````
Agora observe a pergunta: qual o número médio de caras que aparecem no lançamento dessas 5 moedas? 

Podemos usar o vetor `numCaras`, de dimensão `n`, para verificar experimentalmente o número médio de caras, em um lançamento de 5 moedas. Faça:

a) A contabilização *a priori* dessa probabilidade (fazer os cálculos de probabilidade);
b) A verificação experimental, usando o método da biblioteca **numpy** `np.mean(numCaras)`

### Exercício 02
Crie uma rotina para responder às duas perguntas a seguir:

 1. Uma moeda viciada tem 75% de chance de sair cara. Determine a probabilidade *a priori* de saírem 7 caras em um lançamento de 10 moedas e veja para quais valores converge o experimento aleatório para n grande (100 000). Qual o número médio de caras para esses 10 lançamentos? Verifique experimentalmente.
 2. Faça a geração de um experimento aleatório de lançamento de um dado de 6 faces tal que a probabilidade de sair uma face par seja o dobro da probabilidade de sair uma face ímpar. Determine analiticamente e verifique experimentalmente a função de probabilidade da soma das faces no lançamento de três dados.






