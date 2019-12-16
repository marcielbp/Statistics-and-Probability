---
title: "Probabilidade Condicionada"
date: 2019-12-16T11:00:00-03:00
author_profile: false
categories:
  - aulas
tags:
  - estatstica
  - probabilidade
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
 
 <link rel="stylesheet" type="text/css" href="http://tikzjax.com/v1/fonts.css">
<script src="http://tikzjax.com/v1/tikzjax.js"></script>


Probabilidade Condicionada
==========================

Probabilidade Condicionada

Assumindo que $P(A),P(B) \neq 0$, tem-se:
$$P (B|A) = \frac{P(A\cap B)}{P(A)}$$
$$P (A|B) = \frac{P(A\cap B)}{P(B)}$$

 <script type="text/tikz">
  \begin{tikzpicture}
    \draw (0,0) circle (1in);
  \end{tikzpicture}
</script>

Probabilidade Conjunta $$P (A \cap B) = P(B|A)P(A) = P(A|B)P(B)$$

Casos Particulares $P(B|A)$

-   $P(B|A)=0$;

-   $P(B|A)=P(A \cap B)/P(A)=1$;

-   $P(B|A)=P(A \cap B)/P(A) = P(B)/P(A) \ge P(B)$;

Forma Generalizada
$$P(A_1 \cap A_2 \cap \cdots \cap A_K) = P(A_1)P(A_2|A_1)P(A_3|A_2,A_1)\cdots P(A_K| A_{K-1},\cdots, A_1)$$

Propriedades

-   $0 \le P (B|A) \le 1$;

-   $P (S|A) = 1$;

-   $P (B_1 \cup B_2 |A) = P (B_1 |A) + P (B+2 |A)$, se
    $B_1 \cap B_2 = \emptyset$;

Generalizando:
$P (B_1 \cup B_2 \cup \cdots |A) = P (B_1 |A) + P (B_2 |A) + \cdots$
$B_i \cap B_j = \emptyset, \forall i \neq j$\
Note ainda que para $A = S,$

Partição Os eventos $B_1 , B_2 ,\cdots, B_K$ representam uma
**partição** do espaço amostral $S$ se:

-   $B_i \cap B_j = \emptyset$

-   $\bigcup _{ k=1 }^{ K }{ B_k }  = S$

-   $P (B_k ) > 0$, para todo $k$

Um dos eventos $B_k$ , e **exatamente um, ocorrerá!**

Teorema da Probabilidade Total
------------------------------

![image](https://github.com/marcielbp/Statistics-and-Probability/blob/master/docs/_posts/fig/probTotal.png)

Teorena da Probabilidade Total

Teorema de Bayes
----------------

Regra de Bayes Note que:
$P (B_k \cap A) = P (A \cap B_k ) = P (A|B_k )P (B_k )$ E ainda:
$$\begin{aligned}
        P (A) &=& P (A \cap _1 ) + P (A \cap B_2 ) + \cdots + P (A \cap B_K )
        &=& P (A|B_1 )P (B_1 ) + P (A|B_2 )P (B_2 ) + \cdots + P (A|B_K )P (B_K )
        \end{aligned}$$ De onde segue que:
$\displaystyle P (B_k |A) = \frac{P(A|B_k)P(B_k)}{\sum_{k=1}^{K}P(A|B_k)P(B_k)}$


