[]{#title_page.xhtml}

[]{#ch001.xhtml}

<div id="ch001.xhtml#prefácio" class="section level1 unnumbered">

Prefácio
========

Esta apostila foi delineada para servir como material de apoio à
disciplina CE083- Estatística Computacional I. Tal disciplina é
ministrada no segundo semestre do curso de bacharelado em Estatística da
UFPR. O principal objetivo do curso é introduzir os aspectos básico do
software estatístico R. O curso é dividido em duas etapas: a primeira
etapa é destinada a aspectos básicos da linguagem R e sua
operacionalização. Esta etapa complempla os Capítulos 1 a 5. A segunda
etapa objetiva exemplificar o uso do software R através de técnicas de
estatística básica. Nesta etapa revisamos as principais técnicas para
resumo e apresentação de dados através de gráficos e tabelas, bem como,
sua implementação computacional através do software R. Os principais
aspectos ligados à distribuições de probabilidades são discutidos no
Capítulo 7, incluindo tópicos em integração numérica. Por fim, no
Capítulo 8 apresentamos um conjunto de técnicas para a construção de
intervalos de confiança e testes de hipóteses e exemplificamos as as
principais técnicas através de sua implementação em R. Alguns tópicos
adicionais como documentos dinâmicos e programação orientada a objetos
são apresentados no Apêndice.

<div id="ch001.xhtml#para-quem-este-material-é-destinado"
class="section level2 unnumbered">

Para quem este material é destinado?
------------------------------------

Este material é destinado prioritariamente aos alunos do curso de
bacharelado em Estatística da UFPR. Porém, o material pode ser usado por
qualquer pessoa que tenha interesse em aprender os aspectos básicos da
linguagem R com aplicações em estatística. É assumido que o estudante
tem um conhecimento minimo de análise exploratória de dados (gráficos e
tabela), distribuições de probabilidade e noções de inferência
estatística, em particular construção de intervalos de confiança e
testes de hipóteses baseados na distribuiçao normal. Tais requisitos são
facilmente obtidos em disciplinas tais como CE081 - Estatística
Descritiva e Inferencial Básica e CE003 - Estatistica Básica. Além
disso, é assumido que o aluno tenha alguma familiaridade com o uso de
computadores.

</div>

<div id="ch001.xhtml#informação-de-sessão"
class="section level2 unnumbered">

Informação de sessão
--------------------

Abaixo seguem as informações do ambiente em que o documento foi gerado
pela última vez.

    Wednesday, 13 November, 2019, 21:07
    ----------------------------------------
    R version 3.6.1 (2017-01-27)
    Platform: x86_64-pc-linux-gnu (64-bit)
    Running under: Ubuntu 16.04.6 LTS

    Matrix products: default
    BLAS:   /home/travis/R-bin/lib/R/lib/libRblas.so
    LAPACK: /home/travis/R-bin/lib/R/lib/libRlapack.so

    locale:
     [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C              
     [3] LC_TIME=en_US.UTF-8        LC_COLLATE=en_US.UTF-8    
     [5] LC_MONETARY=en_US.UTF-8    LC_MESSAGES=en_US.UTF-8   
     [7] LC_PAPER=en_US.UTF-8       LC_NAME=C                 
     [9] LC_ADDRESS=C               LC_TELEPHONE=C            
    [11] LC_MEASUREMENT=en_US.UTF-8 LC_IDENTIFICATION=C       

    attached base packages:
    [1] stats     graphics  grDevices utils     datasets  methods   base     

    other attached packages:
    [1] MASS_7.3-51.4  rmarkdown_1.17 gdata_2.18.0   knitr_1.26    

    loaded via a namespace (and not attached):
     [1] Rcpp_1.0.3       magrittr_1.5     tidyselect_0.2.5 R6_2.4.1        
     [5] rlang_0.4.1      fansi_0.4.0      stringr_1.4.0    highr_0.8       
     [9] dplyr_0.8.3      tools_3.6.1      rootSolve_1.8.1  xfun_0.11       
    [13] tinytex_0.17     utf8_1.1.4       cli_1.1.0        htmltools_0.4.0 
    [17] gtools_3.8.1     yaml_2.2.0       digest_0.6.22    assertthat_0.2.1
    [21] tibble_2.1.3     crayon_1.3.4     bookdown_0.15.1  purrr_0.3.3     
    [25] vctrs_0.2.0      zeallot_0.1.0    glue_1.3.1       evaluate_0.14   
    [29] stringi_1.4.3    compiler_3.6.1   pillar_1.4.2     backports_1.1.5 
    [33] pkgconfig_2.0.3 

<!--chapter:end:index.Rmd-->

</div>

</div>

[]{#ch002.xhtml}

<div id="ch002.xhtml#computação-científica-e-interação-com-o-r"
class="section level1">

[1]{.header-section-number} Computação científica e interação com o R
=====================================================================

<div id="ch002.xhtml#interagindo-com-o-computador"
class="section level2">

[1.1]{.header-section-number} Interagindo com o computador
----------------------------------------------------------

O que significa este ícone?

![](media/file0.png){width="50%"}

-   É um documento do Microsoft Excel?
-   É um arquivo de **texto pleno**, separado por vírgulas (CSV *comma
    separated values*);
-   De fato, o nome do arquivo é `final.csv` e não `final`;
-   O Excel pode sim abrir este arquivo... assim como milhares de outros
    programas!

O que está acontecendo?

-   O computador (leia-se, nesse caso, o sistema operacional Windows)
    "proteje" o usuário dos detalhes sujos.
-   Isso é ruim? **Sim!**
-   O usuário se acostuma com o computador ditando as regras.
-   É importante lembrar que é você quem deve dizer o que o computador
    deve fazer (nesse caso, com qual programa abrir certo arquivo).

O que deve acontecer?

-   Para a maioria dos usuários, a interação com o computador se limita
    a clicar em links, selecionar menus e caixas de diálogo.
-   O problema com essa abordagem é que parece que o usuário é
    controlado pelo computador.
-   A verdade deve ser o oposto!
-   É o usuário que possui o controle e deve dizer para o computador
    exatamente o que fazer.
-   Escrever código ainda tem a vantagem de deixar registrado tudo o que
    foi feito, possibilitando a reprodução e auditoria.

</div>

<div id="ch002.xhtml#editores-de-texto" class="section level2">

[1.2]{.header-section-number} Editores de texto
-----------------------------------------------

Uma característica importante de códigos de programação é que eles são
em **texto puro**, por isso precisamos de um bom **editor de textos**.

Características de um bom editor:

-   **Identação automática**;
-   **Complementação de parênteses**;
-   **Destaque de sintaxe** (*syntax highlighting*);
-   **Numeração de linhas**;
-   **Auto completar comandos**.

<div id="ch002.xhtml#editores-para-r" class="section level3">

### [1.2.1]{.header-section-number} Editores para R

Windows:

-   Interface padrão: pouco recomendado.
-   Tinn-R.

Linux:

-   Vim-R-plugin.
-   Gedit-R-plugin.

Todas as plataformas:

-   Rstudio: recomendado para iniciantes.
-   Emacs + ESS: altamente recomendado.

</div>

</div>

<div id="ch002.xhtml#r" class="section level2">

[1.3]{.header-section-number} R
-------------------------------

> *"The statistical software should help, by supporting each step from
> user to programmer, with as few intrusive barriers as possible."*

> *"... to turn ideas into software, quickly and faithfully."*

--- John M. Chambers

O R é um dialeto do S e:

-   *Ambiente* estatístico para análise de dados e produção de gráficos.
-   Uma linguagem de programação completa:

    -   Interpretada (contrário de compilada).
    -   Orientada a objetos.

    *Tudo no R é um objeto...*

-   Livre distribuição (código-aberto).
-   Mais de 10000 pacotes adicionais.

Pequeno histórico:

-   1980: Linguagem S: desenvolvida por R. Becker, J. Chambers e A.
    Wilks (AT&T Bell Laboratories);
-   1980: Versão comercial: S-Plus (Insightful Corporation);
-   1996: Versão livre: R desenvolvido por R. Ihaka e R. Gentleman
    (Universidade de Auckland);
-   1997: R Development Core Team;
-   Hoje: 20 desenvolvedores principais e muitos outros colaboradores em
    todo o mundo;
-   Estatísticos, matemáticos e programadores.

<div id="ch002.xhtml#configuração-inicial" class="section level3">

### [1.3.1]{.header-section-number} Configuração inicial

-   O **diretório de trabalho** é uma pasta onde o R será direcionado.
    Todos os arquivos que serão importados (base de dados, ...) ou
    exportados (base de dados, gráficos, ...) por ele ficarão nesta
    pasta.
-   Existem duas maneiras de configurar o diretório de trabalho (suponha
    que vamos usar a pasta `~/estatcomp1`):

-   `1)` Utilizando a função `setwd()` dentro do R:

<div class="sourceCode">

``` {.sourceCode .r}
setwd("~/estatcomp1")
```

</div>

-   `2)` Pelo menu do RStudio em
    `Session > Set Working Directory > Choose Directory...` Confira o
    diretório que está trabalhando com a função

<div class="sourceCode">

``` {.sourceCode .r}
getwd()
```

</div>

</div>

<div id="ch002.xhtml#o-r-como-uma-calculadora" class="section level3">

### [1.3.2]{.header-section-number} O R como uma calculadora

O símbolo `>` indica que o R está pronto para receber um comando:

<div class="sourceCode">

``` {.sourceCode .r}
> 2 + 2
[1] 4
```

</div>

O símbolo `>` muda para `+` se o comando estiver incompleto:

<div class="sourceCode">

``` {.sourceCode .r}
> 2 *
+ 2
[1] 4
```

</div>

Espaços entre os números não fazem diferença:

<div class="sourceCode">

``` {.sourceCode .r}
> 2+         2
[1] 4
```

</div>

</div>

<div id="ch002.xhtml#para-onde-vão-os-resultados"
class="section level3">

### [1.3.3]{.header-section-number} Para onde vão os resultados?

<div class="sourceCode">

``` {.sourceCode .r}
> 1 + 3 + 5 + 7
[1] 16
```

</div>

![](media/file1.png){width="50%"}

![](media/file2.png){width="50%"}

-   Note que o resultado é apenas mostrado na tela, nada é salvo na
    memória (por enquanto).

</div>

<div id="ch002.xhtml#o-editor-de-scripts" class="section level3">

### [1.3.4]{.header-section-number} O editor de scripts

-   Para criar rotinas computacionais é necessário utilizar um editor de
    scripts.
-   Clique em `File > New file > R script`. Salve com a extensão `.R`.
-   Para enviar comandos diretamente para o console, selecione-os e
    aperte `Ctrl + <Enter>`.
-   Para adicionar comentários ao script, utiliza-se o símbolo `#` antes
    do texto e/ou comandos. O que estiver depois do símbolo não será
    interpretado pelo R. Portanto:

<div class="sourceCode">

``` {.sourceCode .r}
2 + 2     # esta linha será executada
# 2 + 2     esta linha não será executada
```

</div>

</div>

<div id="ch002.xhtml#operadores-aritméticos" class="section level3">

### [1.3.5]{.header-section-number} Operadores aritméticos

  Operador                       Significado
  ------------------------------ ---------------
  `+`                            adição
  `-`                            subtração
  `*`                            multiplicação
  `/`                            divisão
  `^`                            potência
  `exp()`                        exponencial
  `sqrt()`                       raíz quadrada
  `factorial()`                  fatorial
  `log()`; `log2()`; `log10()`   logaritmos

</div>

<div id="ch002.xhtml#ordens-de-execução" class="section level3">

### [1.3.6]{.header-section-number} Ordens de execução

As operações são realizadas sempre seguindo as prioridades:

1.  De dentro para fora de parênteses `()`.
2.  Multiplicação e divisão.
3.  Adição e subtração.

<div class="sourceCode">

``` {.sourceCode .r}
> 5 * 2 - 10 + 7
[1] 7
> 5 * 2 - (10 + 7)
[1] -7
> 5 * (2 - 10 + 7)
[1] -5
> 5 * (2 - (10 + 7))
[1] -75
```

</div>

</div>

<div id="ch002.xhtml#exercícios" class="section level3 unnumbered">

### Exercícios

1.  Calcule a seguinte equação: $32 + 16^{2} - 25^{3}$
2.  Divida o resultado por $345$
3.  Qual o resultado da expressão $\frac{e^{- 2}2^{4} - 1}{4!}$?
4.  E do logaritmo desta expressão?

</div>

<div id="ch002.xhtml#salvando-resultados" class="section level3">

### [1.3.7]{.header-section-number} "Salvando" resultados

Do exercício anterior

<div class="sourceCode">

``` {.sourceCode .r}
> x <- 32 + 16^2 - 25^3
> x
[1] -15337
> x/345
[1] -44.45507
> (y <- (exp(-2) * 2^4 - 1)/factorial(4))
[1] 0.04855686
> log(y)
[1] -3.02502
```

</div>

Quando criamos uma variável (`x`, `y`), ela fica armazenada
**temporariamente** na memória RAM.

![](media/file3.png){width="50%"}

Para saber quais objetos foram criados, usamos a **função** `ls()`

<div class="sourceCode">

``` {.sourceCode .r}
> ls()
[1] "x" "y"
```

</div>

Estas variáveis ficam armazenadas no chamado *workspace* do R.

-   O *workspace* consiste de tudo que foi criado durante uma sessão do
    R, e fica armazenado na memória RAM.

Para efetivamente salvar essas variáveis, podemos armazenar esse
*workspace* do R em disco, em um arquivo chamado `.Rdata`

![](media/file4.png){width="50%"} ![](media/file5.png){width="50%"}

-   Quando o R é iniciado em um diretório com um arquivo `.Rdata`, as
    variáveis salvas são automaticamente carregadas.
-   No entanto, é sempre melhor salvar os dados e o **script**, assim é
    possível gerar os resultados novamente, sem salvar nada sem
    necessidade.
-   Veremos mais pra frente como salvar variáveis específicas, por
    exemplo, resultados de uma análise que leva muito tempo para ser
    executada.
-   O mais importante é salvar o **código**, assim sabemos **como**
    chegamos a determinado resultado, e podemos recriá-lo.

</div>

<div id="ch002.xhtml#finalizando-o-programa" class="section level3">

### [1.3.8]{.header-section-number} Finalizando o programa

A qualquer momento durante uma sessão você pode usar o comando

<div class="sourceCode">

``` {.sourceCode .r}
> save.image()
```

</div>

No RStudio:

-   `File > Save As...`
-   Na janela que abrir, digite o nome do arquivo (por exemplo
    `script_aula1`) e salve.
-   Automaticamente o script será salvo com a extensão `.R` (nesse caso
    `script_aula1.R`) no diretório de trabalho que você configurou no
    início.

Alternativamente, você pode também salvar toda sua área de trabalho,
clicando em `Workspace > Save As Default Workspace`. Este processo irá
gerar dois arquivos:

-   `.Rdata`: contém todos os objetos criados durante uma sessão. Não é
    necessário (e nem recomendado) dar um nome antes do ponto. Dessa
    forma, a próxima vez que o programa for iniciado neste diretório, a
    área de trabalho será carregada automaticamente.
-   `.Rhistory`: um arquivo texto que contém todos os comandos que foram
    digitados no console.

<!-- ## Layout de código --> <!-- ## Formatos de arquivos -->
<!-- ### Texto pleno --> <!-- ### CSV --> <!-- ### Encoding -->

</div>

</div>

<div id="ch002.xhtml#referências" class="section level2 unnumbered">

Referências
-----------

-   Leek, J. [The Elements of Data Analytic
    Style](https://leanpub.com/datastyle). Leanpub, 2015.
-   Murrell, P. [Introduction to data
    technologies](https://www.stat.auckland.ac.nz/~paul/ItDT/HTML). Boca
    Raton: Chapman & Hall/CRC, 2009.
-   Peng, RD. [R programming for data
    science](https://leanpub.com/rprogramming). Leanpub, 2015.

<!--chapter:end:01-computacao-cientifica.Rmd-->

</div>

</div>

[]{#ch003.xhtml}

<div id="ch003.xhtml#objetos-e-classes" class="section level1">

[2]{.header-section-number} Objetos e classes
=============================================

<div id="ch003.xhtml#funções-e-argumentos" class="section level2">

[2.1]{.header-section-number} Funções e argumentos
--------------------------------------------------

As funções no R são definidas como:

<div class="sourceCode">

``` {.sourceCode .r}
nome(argumento1, argumento2, ...)
```

</div>

Exemplo: função `runif()` (para gerar valores aleatórios de uma
distribuição uniforme):

<div class="sourceCode">

``` {.sourceCode .r}
runif(n, min = 0, max = 1)
```

</div>

<div class="sourceCode">

``` {.sourceCode .r}
runif(10, 1, 100)
 [1] 31.468845 26.509578 55.679921  6.581932 47.386379 48.893303 81.427859
 [8] 37.661733 55.109301 17.855943
```

</div>

Argumentos que já possuem um valor especificado (como `max` e `min`)
podem ser omitidos:

<div class="sourceCode">

``` {.sourceCode .r}
runif(10)
```

</div>

Se os argumentos forem nomeados, a ordem deles dentro da função não tem
mais importância:

<div class="sourceCode">

``` {.sourceCode .r}
runif(min = 1, max = 100, n = 10)
```

</div>

Argumentos nomeados e não nomeados podem ser utilizados, desde que os
não nomeados estejam na posição correta:

<div class="sourceCode">

``` {.sourceCode .r}
runif(10, max = 100, min = 1)
```

</div>

<div id="ch003.xhtml#outros-tipos-de-argumentos" class="section level3">

### [2.1.1]{.header-section-number} Outros tipos de argumentos

Exemplo: função `sample()`:

<div class="sourceCode">

``` {.sourceCode .r}
sample(x, size, replace = FALSE, prob = NULL)
```

</div>

-   `x` e `size` devem ser obrigatoriamente especificados.
-   `replace` é lógico: `TRUE` (`T`) ou `FALSE` (`F`).
-   `prob` é um argumento vazio ou ausente (“opcional”).

Exemplo: função `plot()`:

<div class="sourceCode">

``` {.sourceCode .r}
plot(x, y, ...)
```

</div>

-   "`...`" permite especificar argumentos de outras funções (por
    exemplo `par()`).

Para ver todos os argumentos disponíveis de uma função, podemos usar a
função `args()`.

<div class="sourceCode">

``` {.sourceCode .r}
args(sample)
function (x, size, replace = FALSE, prob = NULL) 
NULL
```

</div>

</div>

</div>

<div id="ch003.xhtml#mecanismos-de-ajuda" class="section level2">

[2.2]{.header-section-number} Mecanismos de ajuda
-------------------------------------------------

Argumentos e detalhes do funcionamento das funções:

<div class="sourceCode">

``` {.sourceCode .r}
?runif
```

</div>

ou

<div class="sourceCode">

``` {.sourceCode .r}
help(runif)
```

</div>

A documentação contém os campos:

-   **Description:** breve descrição.
-   **Usage:** função e todos seus argumentos.
-   **Arguments:** lista descrevendo cada argumento.
-   **Details:** descrição detalhada.
-   **Value:** o que a função retorna.
-   **References:** bibliografia relacionada.
-   **See Also:** funções relacionadas.
-   **Examples:** exemplos práticos.

Procura por nomes de funções que contenham algum termo:

<div class="sourceCode">

``` {.sourceCode .r}
apropos("mod")
apropos("model")
```

</div>

Procura por funções que contenham `palavra` em qualquer parte de sua
documentação:

<div class="sourceCode">

``` {.sourceCode .r}
help.search("palavra")
```

</div>

Ajuda através do navegador (também contém manuais, ...):

<div class="sourceCode">

``` {.sourceCode .r}
help.start()
```

</div>

Sites para busca na documentação dos diversos pacotes:

-   RDocumentation <https://www.rdocumentation.org/>.
-   R Package Documentation <https://rdrr.io/>.
-   R Contributed Documentation (várias línguas).
    <https://cran.r-project.org/other-docs.html>.

Os pacotes do R contêm funções específicas para determinadas tarefas, e
estendem a instalação básica do R. Atualmente existem mais de 10000
pacotes disponíveis no
[CRAN](http://cran-r.c3sl.ufpr.br/web/packages/index.html), além de
diversos outros hospedados em sites como [Github](https://github.com),
por exemplo.

Ao instalar o R, os seguintes pacotes já vêm instalados (fazem parte do
chamado "R core"):

     [1] "base"       "boot"       "class"      "cluster"    "codetools" 
     [6] "compiler"   "datasets"   "foreign"    "graphics"   "grDevices" 
    [11] "grid"       "KernSmooth" "lattice"    "MASS"       "Matrix"    
    [16] "methods"    "mgcv"       "nlme"       "nnet"       "parallel"  
    [21] "rpart"      "spatial"    "splines"    "stats"      "stats4"    
    [26] "survival"   "tcltk"      "tools"      "utils"     

No entanto, nem todos são carregados na inicialização do R. Por padrão,
apenas os seguintes pacotes são carregados automaticamente:

    [1] "gdata"     "knitr"     "stats"     "graphics"  "grDevices" "utils"    
    [7] "datasets"  "methods"   "base"     

Para listar os pacotes carregados, use a função

<div class="sourceCode">

``` {.sourceCode .r}
search()
```

</div>

Note que o primeiro elemento, `.GlobalEnv`, será sempre carregado pois
ele é o *ambiente* que irá armazenar (e deixar disponível) os objetos
criados pelo usuário. Para carregar um pacote instalado, usamos a função
`library()`, por exemplo

<div class="sourceCode">

``` {.sourceCode .r}
library(lattice)
search()
```

</div>

Isso tornará todas as funções do pacote `lattice` disponíveis para uso.

Para instalar um pacote usamos a função `install.packages()`. Sabendo o
nome do pacote, por exemplo, `mvtnorm`, fazemos

<div class="sourceCode">

``` {.sourceCode .r}
install.packages("mvtnorm")
```

</div>

Se o diretório padrão de instalação de um pacote for de acesso restrito
(root por exemplo), o R irá perguntar se você gostaria de instalar o
pacote em uma biblioteca pessoal, e sugerirá um diretório que possui as
permissões necessárias. Você pode se antecipar e já definir e criar um
diretório na sua pasta pessoal, e instalar os pacotes sempre nesse
local. Por exemplo, defina `~/R/library` como sua biblioteca pessoal.
Para instalar os pacotes sempre nesse diretório faça:

<div class="sourceCode">

``` {.sourceCode .r}
install.packages("mvtnorm", lib = "~/R/library")
```

</div>

Para verificar as bibliotecas disponíveis e se existem pacotes para
serem atualizados, use

<div class="sourceCode">

``` {.sourceCode .r}
packageStatus()
```

</div>

Para atualizar automaticamente todos os pacotes faça

<div class="sourceCode">

``` {.sourceCode .r}
update.packages(ask = FALSE)
```

</div>

</div>

<div id="ch003.xhtml#criando-uma-função" class="section level2">

[2.3]{.header-section-number} Criando uma função
------------------------------------------------

A ideia original do R é transformar usuários em programadores

> *"... to turn ideas into software, quickly and faithfully."*
>
> -- John M. Chambers.

Criar funções para realizar trabalhos específicos é um dos grandes
poderes do R.

Por exemplo, podemos criar a famosa função

<div class="sourceCode">

``` {.sourceCode .r}
ola.mundo <- function(){
    writeLines("Olá mundo")
}
```

</div>

E chama-la através de

<div class="sourceCode">

``` {.sourceCode .r}
ola.mundo()
Olá mundo
```

</div>

A função acima não permite alterar o resultado da saída. Podemos fazer
isso incluindo um **argumento**

<div class="sourceCode">

``` {.sourceCode .r}
ola.mundo <- function(texto){
    writeLines(texto)
}
```

</div>

E fazer por exemplo

<div class="sourceCode">

``` {.sourceCode .r}
ola.mundo("Funções são legais")
Funções são legais
```

</div>

(Veremos detalhes de funções mais adiante)

</div>

<div id="ch003.xhtml#exercícios-1" class="section level2 unnumbered">

Exercícios
----------

1.  Usando a função `runif()` gere $30$ números aleatórios entre:
    -   0 e 1
    -   -5 e 5
    -   10 e 500

alternando a posição dos argumentos da função.

2.  Veja o help da função (?) `"+"`
3.  Crie uma função para fazer a soma de dois números: `x` e `y`
4.  Crie uma função para simular a jogada de um dado.
5.  Crie uma função para simular a jogada de dois dados.

</div>

<div id="ch003.xhtml#objetos" class="section level2">

[2.4]{.header-section-number} Objetos
-------------------------------------

O que é um objeto?

-   Um **símbolo** ou uma **variável** capaz de armazenar qualquer valor
    ou estrutura de dados.

Por quê objetos?

-   Uma maneira simples de acessar os dados armazenados na memória (o R
    não permite acesso direto à memória).

Programação:

-   Objetos $\Rightarrow$ Classes $\Rightarrow$ Métodos.

> *“Tudo no R é um objeto.”*

> *“Todo objeto no R tem uma classe.”*

-   **Classe:** é a definição de um objeto. Descreve a forma do objeto e
    como ele será manipulado pelas diferentes funções.
-   **Método:** são **funções genéricas** que executam suas tarefas de
    acordo com cada classe. Duas das funções genéricas mais importantes
    são:
    -   `summary().`
    -   `plot().`

Veja o resultado de

<div class="sourceCode">

``` {.sourceCode .r}
methods(summary)
methods(plot)
```

</div>

(Veremos mais detalhes adiante).

A variável `x` recebe o valor $2$ (tornando-se um objeto dentro do R):

<div class="sourceCode">

``` {.sourceCode .r}
x <- 2
```

</div>

<div class="alert alert-warning">

O símbolo `<-` é chamado de **operador de atribuição**. Ele serve para
atribuir valores a objetos, e é formado pelos símbolos `<` e `-`,
obrigatoriamente **sem espaços**.

</div>

Para ver o conteúdo do objeto:

<div class="sourceCode">

``` {.sourceCode .r}
x
[1] 2
```

</div>

<div class="alert alert-warning">

**Observação**: O símbolo `=` pode ser usado no lugar de `<-` mas não é
recomendado.

</div>

Quando você faz

<div class="sourceCode">

``` {.sourceCode .r}
x <- 2
```

</div>

está fazendo uma **declaração**, ou seja, declarando que a variável `x`
irá agora se tornar um objeto que armazena o número `2`. As declarações
podem ser feitas uma em cada linha

<div class="sourceCode">

``` {.sourceCode .r}
x <- 2
y <- 4
```

</div>

ou separadas por `;`

<div class="sourceCode">

``` {.sourceCode .r}
x <- 2; y <- 4
```

</div>

Operações matemáticas em objetos:

<div class="sourceCode">

``` {.sourceCode .r}
x + x
[1] 4
```

</div>

Objetos podem armazenar diferentes estruturas de dados:

<div class="sourceCode">

``` {.sourceCode .r}
y <- runif(10)
y
 [1] 0.6249965 0.8821655 0.2803538 0.3984879 0.7625511 0.6690217 0.2046122
 [8] 0.3575249 0.3594751 0.6902905
```

</div>

Note que cada objeto só pode armazenar uma estrutura (um número ou uma
sequência de valores) de cada vez! (Aqui, o valor $4$ que estava
armazenado em `y` foi sobrescrito pelos valores acima).

<div id="ch003.xhtml#nomes-de-objetos" class="section level3">

### [2.4.1]{.header-section-number} Nomes de objetos

-   Podem ser formados por letras, números, "`_`", e "`.`".
-   Não podem começar com número e/ou ponto.
-   Não podem conter espaços.
-   Evite usar acentos.
-   Evite usar nomes de funções como:

`c q t C D F I T diff df data var pt`

-   O R é *case-sensitive*, portanto:

`dados` $\neq$ `Dados` $\neq$ `DADOS`.

</div>

<div id="ch003.xhtml#gerenciando-a-área-de-trabalho"
class="section level3">

### [2.4.2]{.header-section-number} Gerenciando a área de trabalho

Liste os objetos criados com a função `ls()`:

<div class="sourceCode">

``` {.sourceCode .r}
ls()
```

</div>

Para remover apenas um objeto:

<div class="sourceCode">

``` {.sourceCode .r}
rm(x)
```

</div>

Para remover outros objetos:

<div class="sourceCode">

``` {.sourceCode .r}
rm(x, y)
```

</div>

Para remover todos os objetos:

<div class="sourceCode">

``` {.sourceCode .r}
rm(list = ls())
```

</div>

<div class="alert alert-danger">

**Cuidado!** O comando acima apaga todos os objetos na sua área de
trabalho sem perguntar. Depois só é possível recuperar os objetos ao
rodar o script novamente.

</div>

</div>

</div>

<div id="ch003.xhtml#exercícios-2" class="section level2 unnumbered">

Exercícios
----------

1.  Armazene o resultado da equação $32 + 16^{2} - 25^{3}$ no objeto
    `x`.
2.  Divida `x` por $345$ e armazene em `y`.
3.  Crie um objeto (com o nome que você quiser) para armazenar $30$
    valores aleatórios de uma distribuição uniforme entre $10$ e $50$.
4.  Remova o objeto `y`.
5.  Remova os demais objetos de uma única vez.
6.  Procure a função utilizada para gerar numeros aleatórios de uma
    distribuição de Poisson, e gere $100$ valores para a VA
    $X \sim \text{Poisson}(5)$.

</div>

<div id="ch003.xhtml#tipos-e-classes-de-objetos" class="section level2">

[2.5]{.header-section-number} Tipos e classes de objetos
--------------------------------------------------------

Para saber como trabalhar com dados no R, é fundamental entender as
possíveis estruturas (ou tipos) de dados possíveis. O formato mais
básico de dados são os vetores, e a partir deles, outras estruturas mais
complexas podem ser construídas. O R possui dois tipos básicos de
vetores:

-   **Vetores atômicos**: existem seis tipos básicos:
-   `double`.
-   `integer`.
-   `character`.
-   `logical`.
-   `complex`.
-   `raw`.

Os tipos `integer` e `double` são chamados conjuntamente de `numeric`.

-   **Listas**: também chamadas de *vetores recursivos* pois listas
    podem conter outras listas.

A principal diferença entre vetores atômicos e listas é que o primeiro é
**homogêneo** (cada vetor só pode conter um tipo), enquanto que o
segundo pode ser **heterogêneo** (cada vetor pode conter mais de um
tipo).

<div class="alert alert-warning">

Um vetor atômico só pode conter elementos de um mesmo tipo.

</div>

Um vetor, como o próprio nome diz, é uma estrutura unidimensional, mas
na maioria das vezes iremos trabalhar com estruturas de dados
bidimensionais (linhas e colunas). Portanto diferentes estruturas (com
diferentes dimensões) podem ser criadas a partir dos vetores atômicos.
Quando isso acontece, temos o que é chamado de **classe** de um objeto.
Embora os vetores atômicos só possuam seis tipos básicos, existe um
número muito grande de classes, e novas são inventadas todos os dias. E
mesmo que um objeto seja de qualquer classe, ele sempre será de um dos
seis tipos básicos (ou uma lista).

Para verificar o tipo de um objeto, usamos a função `typeof()`, enquanto
que a classe é verificada com a função `class()`. Vejamos alguns
exemplos:

<div class="sourceCode">

``` {.sourceCode .r}
## double
x <- c(2, 4, 6)
typeof(x)
[1] "double"
class(x)
[1] "numeric"
## integer
x <- c(2L, 4L, 6L)
typeof(x)
[1] "integer"
class(x)
[1] "integer"
## character
x <- c("a", "b", "c")
typeof(x)
[1] "character"
class(x)
[1] "character"
## logical
x <- c(TRUE, FALSE, TRUE)
typeof(x)
[1] "logical"
class(x)
[1] "logical"
## complex
x <- c(2 + 1i, 4 + 1i, 6 + 1i)
typeof(x)
[1] "complex"
class(x)
[1] "complex"
## raw
x <- raw(3)
typeof(x)
[1] "raw"
class(x)
[1] "raw"
```

</div>

<div id="ch003.xhtml#vetores-numéricos" class="section level3">

### [2.5.1]{.header-section-number} Vetores numéricos

Características:

-   Coleção ordenada de valores.
-   Estrutura unidimensional.

Usando a função `c()` para criar vetores:

<div class="sourceCode">

``` {.sourceCode .r}
num <- c(10, 5, 2, 4, 8, 9)
num
[1] 10  5  2  4  8  9
typeof(num)
[1] "double"
class(num)
[1] "numeric"
```

</div>

Por que `numeric` e não `integer`?

<div class="sourceCode">

``` {.sourceCode .r}
x <- c(10L, 5L, 2L, 4L, 8L, 9L)
x
[1] 10  5  2  4  8  9
typeof(x)
[1] "integer"
class(x)
[1] "integer"
```

</div>

Para forçar a representação de um número para inteiro é necessário usar
o sufixo `L`.

Note que a diferença entre `numeric` e `integer` também possui impacto
computacional, pois o armazenamento de números inteiros ocupa menos
espaço na memória. Dessa forma, esperamos que o vetor `x` acima ocupe
menos espaço na memória do que o vetor `num`, embora sejam aparentemente
idênticos. Veja:

<div class="sourceCode">

``` {.sourceCode .r}
object.size(num)
[1] 96 bytes
object.size(x)
[1] 80 bytes
```

</div>

A diferença pode parecer pequena, mas pode ter um grande impacto
computacional quando os vetores são formados por milhares ou milhões de
números.

<div id="ch003.xhtml#representação-numérica-dentro-do-r"
class="section level4">

#### [2.5.1.1]{.header-section-number} Representação numérica dentro do R

Os números que aparecem na tela do console do R são apenas
representações simplificadas do número real armazenado na memória. Por
exemplo,

<div class="sourceCode">

``` {.sourceCode .r}
x <- runif(10)
x
 [1] 0.2875775 0.7883051 0.4089769 0.8830174 0.9404673 0.0455565 0.5281055
 [8] 0.8924190 0.5514350 0.4566147
```

</div>

O objeto `x` contém números como 0.2875775, 0.7883051, etc, que possuem
7 casas decimais, que é o padrão do R. O número de casas decimais é
controlado pelo argumento `digits` da função `options()`. Para
visualizar essa opção, use

<div class="sourceCode">

``` {.sourceCode .r}
getOption("digits")
[1] 7
```

</div>

Note que esse valor de 7 é o número de **dígitos significativos**, e
pode variar conforme a sequência de números. Por exemplo,

<div class="sourceCode">

``` {.sourceCode .r}
y <- runif(10)
y
 [1] 0.069360916 0.817775199 0.942621732 0.269381876 0.169348123 0.033895622
 [7] 0.178785004 0.641665366 0.022877743 0.008324827
```

</div>

possui valores com 9 casas decimais. Isto é apenas a representação do
número que aparece na tela. Internamente, cada número é armazenado com
uma precisão de 64 bits. Como consequência, cada número possui uma
acurácia de até 16 dígitos significativos. Isso pode introduzir algum
tipo de erro, por exemplo:

<div class="sourceCode">

``` {.sourceCode .r}
sqrt(2)^2 - 2
[1] 4.440892e-16
print(sqrt(2)^2, digits = 22)
[1] 2.000000000000000444089
```

</div>

não é exatamente zero, pois a raíz quadrada de 2 não pode ser armazenada
com toda precisão com "apenas" 16 dígitos significativos. Esse tipo de
erro é chamado de **erro de ponto flutuante**, e as operações nessas
condições são chamadas de **aritmética de ponto flutuante**. Para mais
informações sobre esse assunto veja [What Every Computer Scientist
Should Know About Floating-Point
Arithmetic](http://www.validlab.com/goldberg/paper.pdf) e [Why doesn’t R
think these numbers are
equal?](http://cran-r.c3sl.ufpr.br/doc/FAQ/R-FAQ.html#Why-doesn_0027t-R-think-these-numbers-are-equal_003f).

No R os números podem ser representados com até 22 casas decimais. Você
pode ver o número com toda sua precisão usando a função `print()` e
especificando o número de casas decimais com o argumento `digits` (de 1
a 22).

<div class="sourceCode">

``` {.sourceCode .r}
print(x, digits = 1)
 [1] 0.29 0.79 0.41 0.88 0.94 0.05 0.53 0.89 0.55 0.46
print(x, digits = 7) # padrão
 [1] 0.2875775 0.7883051 0.4089769 0.8830174 0.9404673 0.0455565 0.5281055
 [8] 0.8924190 0.5514350 0.4566147
print(x, digits = 22)
 [1] 0.28757752012461423873901 0.78830513544380664825439
 [3] 0.40897692181169986724854 0.88301740400493144989014
 [5] 0.94046728429384529590607 0.04555649938993155956268
 [7] 0.52810548804700374603271 0.89241904439404606819153
 [9] 0.55143501446582376956940 0.45661473530344665050507
```

</div>

Também é possível alterar a representação na tela para o formato
científico, usando a função `format()`

<div class="sourceCode">

``` {.sourceCode .r}
format(x, scientific = TRUE)
 [1] "2.875775e-01" "7.883051e-01" "4.089769e-01" "8.830174e-01" "9.404673e-01"
 [6] "4.555650e-02" "5.281055e-01" "8.924190e-01" "5.514350e-01" "4.566147e-01"
```

</div>

Nessa representação, o valor 2.875775e-01 = $2.875775 \times 10^{- 01}$
= $0.2875775$.

</div>

<div id="ch003.xhtml#sequências-de-números" class="section level4">

#### [2.5.1.2]{.header-section-number} Sequências de números

Usando a função `seq()`

<div class="sourceCode">

``` {.sourceCode .r}
seq(1, 10)
 [1]  1  2  3  4  5  6  7  8  9 10
```

</div>

Ou `1:10` gera o mesmo resultado. Para a sequência variar em $2$

<div class="sourceCode">

``` {.sourceCode .r}
seq(from = 1, to = 10, by = 2)
[1] 1 3 5 7 9
```

</div>

Para obter $15$ valores entre $1$ e $10$

<div class="sourceCode">

``` {.sourceCode .r}
seq(from = 1, to = 10, length.out = 15)
 [1]  1.000000  1.642857  2.285714  2.928571  3.571429  4.214286  4.857143
 [8]  5.500000  6.142857  6.785714  7.428571  8.071429  8.714286  9.357143
[15] 10.000000
```

</div>

Usando a função `rep()`

<div class="sourceCode">

``` {.sourceCode .r}
rep(1, 10)
 [1] 1 1 1 1 1 1 1 1 1 1
```

</div>

Para gerar um sequência várias vezes

<div class="sourceCode">

``` {.sourceCode .r}
rep(c(1, 2, 3), times = 5)
 [1] 1 2 3 1 2 3 1 2 3 1 2 3 1 2 3
```

</div>

Para repetir um número da sequência várias vezes

<div class="sourceCode">

``` {.sourceCode .r}
rep(c(1, 2, 3), each = 5)
 [1] 1 1 1 1 1 2 2 2 2 2 3 3 3 3 3
```

</div>

</div>

<div id="ch003.xhtml#operações-matemáticas-em-vetores-numéricos"
class="section level4">

#### [2.5.1.3]{.header-section-number} Operações matemáticas em vetores numéricos

Operações podem ser feitas entre um vetor e um número:

<div class="sourceCode">

``` {.sourceCode .r}
num * 2
[1] 20 10  4  8 16 18
```

</div>

E também entre vetores de mesmo comprimento ou com comprimentos
múltiplos:

<div class="sourceCode">

``` {.sourceCode .r}
num * num
[1] 100  25   4  16  64  81
num + c(2, 4, 1)
[1] 12  9  3  6 12 10
```

</div>

</div>

<div id="ch003.xhtml#a-regra-da-reciclagem" class="section level4">

#### [2.5.1.4]{.header-section-number} A Regra da Reciclagem

![](media/file6.png){width="80%"}

Agora tente:

<div class="sourceCode">

``` {.sourceCode .r}
num + c(2, 4, 1, 3)
```

</div>

</div>

</div>

<div id="ch003.xhtml#outros-tipos-de-vetores" class="section level3">

### [2.5.2]{.header-section-number} Outros tipos de vetores

Vetores também podem ter outros tipos:

-   Vetor de caracteres:

<div class="sourceCode">

``` {.sourceCode .r}
caracter <- c("brava", "joaquina", "armação")
caracter
[1] "brava"    "joaquina" "armação" 
typeof(caracter)
[1] "character"
class(caracter)
[1] "character"
```

</div>

-   Vetor lógico:

<div class="sourceCode">

``` {.sourceCode .r}
logico <- caracter == "armação"
logico
[1] FALSE FALSE  TRUE
typeof(logico)
[1] "logical"
class(logico)
[1] "logical"
```

</div>

ou

<div class="sourceCode">

``` {.sourceCode .r}
logico <- num > 4
logico
[1]  TRUE  TRUE FALSE FALSE  TRUE  TRUE
```

</div>

No exemplo anterior, a condição `num > 4` é uma **expressão
condicional**, e o símbolo `>` um **operador lógico**. Os operadores
lógicos utilizados no R são:

  Operador   Sintaxe            Teste
  ---------- ------------------ --------------------------------------
  `<`        `a < b`            `a` é menor que `b`?
  `<=`       `a <= b`           `a` é menor ou igual a `b`?
  `>`        `a > b`            `a` é maior que `b`
  `>=`       `a >= b`           `a` é maior ou igual a `b`?
  `==`       `a == b`           `a` é igual a `b`?
  `!=`       `a != b`           `a` é diferente de `b`?
  `%in%`     `a %in% c(a, b)`   `a` está contido no vetor `c(a, b)`?

</div>

<div id="ch003.xhtml#misturando-classes-de-objetos"
class="section level3">

### [2.5.3]{.header-section-number} Misturando classes de objetos

Algumas vezes isso acontece por acidente, mas também pode acontecer de
propósito.

O que acontece aqui?

<div class="sourceCode">

``` {.sourceCode .r}
w <- c(5L, "a")
x <- c(1.7, "a")
y <- c(TRUE, 2)
z <- c("a", T)
```

</div>

Lembre-se da regra:

<div class="alert alert-warning">

Um vetor só pode conter elementos do mesmo tipo!

</div>

Quando objetos de diferentes tipos são misturados, ocorre a **coerção**,
para que cada elemento possua a mesma classe.

Nos exemplos acima, nós vemos o efeito da **coerção implícita**, quando
o R tenta representar todos os objetos de uma única forma.

Nós podemos forçar um objeto a mudar de classe, através da **coerção
explícita**, realizada pelas funções `as.*`:

<div class="sourceCode">

``` {.sourceCode .r}
x <- 0:6
typeof(x)
[1] "integer"
class(x)
[1] "integer"
as.numeric(x)
[1] 0 1 2 3 4 5 6
as.logical(x)
[1] FALSE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
as.character(x)
[1] "0" "1" "2" "3" "4" "5" "6"
as.factor(x)
[1] 0 1 2 3 4 5 6
Levels: 0 1 2 3 4 5 6
```

</div>

De `?logical`:

     Logical vectors are coerced to integer vectors in contexts where a
     numerical value is required, with ‘TRUE’ being mapped to ‘1L’,
     ‘FALSE’ to ‘0L’ and ‘NA’ to ‘NA_integer_’.

<div class="sourceCode">

``` {.sourceCode .r}
(x <- c(FALSE, TRUE))
[1] FALSE  TRUE
class(x)
[1] "logical"
as.numeric(x)
[1] 0 1
```

</div>

Algumas vezes não é possível fazer a coerção, então:

<div class="sourceCode">

``` {.sourceCode .r}
x <- c("a", "b", "c")
as.numeric(x)
Warning: NAs introduced by coercion
[1] NA NA NA
as.logical(x)
[1] NA NA NA
```

</div>

</div>

<div id="ch003.xhtml#valores-perdidos-e-especiais"
class="section level3">

### [2.5.4]{.header-section-number} Valores perdidos e especiais

Valores perdidos devem ser definidos como `NA` (*not available*):

<div class="sourceCode">

``` {.sourceCode .r}
perd <- c(3, 5, NA, 2)
perd
[1]  3  5 NA  2
class(perd)
[1] "numeric"
```

</div>

Podemos testar a presença de `NA`s com a função `is.na()`:

<div class="sourceCode">

``` {.sourceCode .r}
is.na(perd)
[1] FALSE FALSE  TRUE FALSE
```

</div>

Ou:

<div class="sourceCode">

``` {.sourceCode .r}
any(is.na(perd))
[1] TRUE
```

</div>

Outros valores especiais são:

-   `NaN` (*not a number*) - exemplo: `0/0`
-   `-Inf` e `Inf` - exemplo: `1/0`

A função `is.na()` também testa a presença de `NaN`s:

<div class="sourceCode">

``` {.sourceCode .r}
perd <- c(-1,0,1)/0
perd
[1] -Inf  NaN  Inf
is.na(perd)
[1] FALSE  TRUE FALSE
```

</div>

A função `is.infinite()` testa se há valores infinitos

<div class="sourceCode">

``` {.sourceCode .r}
is.infinite(perd)
[1]  TRUE FALSE  TRUE
```

</div>

</div>

</div>

<div id="ch003.xhtml#exercícios-3" class="section level2 unnumbered">

Exercícios
----------

1.  Crie um objeto com os valores 54, 0, 17, 94, 12.5, 2, 0.9, 15.
    a.  Some o objeto acima com os valores 5, 6, e depois com os valores
        5, 6, 7.
2.  Construa um único objeto com as letras: `A`, `B`, e `C`, repetidas
    cada uma 15, 12, e 8 vezes, respectivamente.
    a.  Mostre na tela, em forma de verdadeiro ou falso, onde estão as
        letras `B` nesse objeto.
    b.  Veja a página de ajuda da função `sum()` e descubra como fazer
        para contar o número de letras `B` neste vetor (usando `sum()`).
3.  Crie um objeto com 100 valores aleatórios de uma distribuição
    uniforme $U(0,1)$. Conte quantas vezes aparecem valores maiores ou
    iguais a 0,5.
4.  Calcule as 50 primeiras potências de 2, ou seja,
    $2,2^{2},2^{3},\ldots,2^{50}$.
    a.  Calcule o quadrado dos números inteiros de 1 a 50, ou seja,
        $1^{2},2^{2},3^{2},\ldots,50^{2}$.
    b.  Quais pares são iguais, ou seja, quais números inteiros dos dois
        exercícios anteriores satisfazem a condição $2^{n} = n^{2}$?
    c.  Quantos pares existem?
5.  Calcule o seno, coseno e a tangente para os números variando de $0$
    a $2\pi$, com distância de $0.1$ entre eles. (Use as funções
    `sin()`, `cos()`, `tan()`).
    a.  Calcule a tangente usando a relação $\tan(x) = \sin(x)/\cos(x)$.
    b.  Calcule as diferenças das tangentes calculadas pela função do R
        e pela razão acima.
    c.  Quais valores são exatamente iguais?
    d.  Qual a diferença máxima (em módulo) entre eles? Qual é a causa
        dessa diferença?

</div>

<div id="ch003.xhtml#outras-classes" class="section level2">

[2.6]{.header-section-number} Outras classes
--------------------------------------------

Como mencionado na seção anterior, o R possui 6 tipos básicos de
estrutura de dados, mas diversas classes podem ser construídas a partir
destes tipos básicos. Abaixo, veremos algumas das mais importantes.

<div id="ch003.xhtml#fator" class="section level3">

### [2.6.1]{.header-section-number} Fator

Os fatores são parecidos com caracteres no R, mas são armazenados e
tratados de maneira diferente.

Características:

-   Coleção de categorias ou **níveis** (*levels*).
-   Estrutura unidimensional.

Utilizando as funções `factor()` e `c()`:

<div class="sourceCode">

``` {.sourceCode .r}
fator <- factor(c("alta","baixa","baixa","media",
                  "alta","media","baixa","media","media"))
fator
[1] alta  baixa baixa media alta  media baixa media media
Levels: alta baixa media
class(fator)
[1] "factor"
typeof(fator)
[1] "integer"
```

</div>

Note que o objeto é da classe `factor`, mas seu tipo básico é `integer`!
Isso significa que cada categoria única é identificada internamente por
um número, e isso faz com que os fatores possuam uma ordenação, de
acordo com as categorias únicas. Por isso existe a identificação dos
`Levels` (níveis) de um fator.

Veja o que acontece quando "remover a classe" desse objeto

<div class="sourceCode">

``` {.sourceCode .r}
unclass(fator)
[1] 1 2 2 3 1 3 2 3 3
attr(,"levels")
[1] "alta"  "baixa" "media"
```

</div>

Fatores podem ser convertidos para caracteres, e **também** para números
inteiros

<div class="sourceCode">

``` {.sourceCode .r}
as.character(fator)
[1] "alta"  "baixa" "baixa" "media" "alta"  "media" "baixa" "media" "media"
as.integer(fator)
[1] 1 2 2 3 1 3 2 3 3
```

</div>

Caso haja uma hierarquia, os níveis dos fatores podem ser ordenados
explicitamente através do argumento `levels`:

<div class="sourceCode">

``` {.sourceCode .r}
fator <- factor(c("alta","baixa","baixa","media",
                  "alta","media","baixa","media","media"),
                levels = c("alta","media","baixa"))
fator
[1] alta  baixa baixa media alta  media baixa media media
Levels: alta media baixa
typeof(fator)
[1] "integer"
class(fator)
[1] "factor"
```

</div>

Além disso, os níveis dos fatores podem também ser explicitamente
ordenados

<div class="sourceCode">

``` {.sourceCode .r}
fator <- factor(c("alta","baixa","baixa","media",
                  "alta","media","baixa","media","media"),
                levels = c("baixa", "media", "alta"),
                ordered = TRUE)
fator
[1] alta  baixa baixa media alta  media baixa media media
Levels: baixa < media < alta
typeof(fator)
[1] "integer"
class(fator)
[1] "ordered" "factor" 
```

</div>

Veja que um objeto pode ter mais de uma classe. Isso geralmente só será
útil em casos especificos.

As seguintes funções são úteis para verificar os níveis e o número de
níveis de um fator:

<div class="sourceCode">

``` {.sourceCode .r}
levels(fator)
[1] "baixa" "media" "alta" 
nlevels(fator)
[1] 3
```

</div>

</div>

<div id="ch003.xhtml#matriz" class="section level3">

### [2.6.2]{.header-section-number} Matriz

Matrizes são vetores que podem ser dispostos em duas dimensões.

Características:

-   Podem conter apenas um tipo de informação (números, caracteres)
-   Estrutura bidimensional

Utilizando a função `matrix()`:

<div class="sourceCode">

``` {.sourceCode .r}
matriz <- matrix(1:12, nrow = 3, ncol = 4)
matriz
     [,1] [,2] [,3] [,4]
[1,]    1    4    7   10
[2,]    2    5    8   11
[3,]    3    6    9   12
class(matriz)
[1] "matrix"
typeof(matriz)
[1] "integer"
```

</div>

Alterando a ordem de preenchimento da matriz (por linhas):

<div class="sourceCode">

``` {.sourceCode .r}
matriz <- matrix(1:12, nrow = 3, ncol = 4, byrow = TRUE)
matriz
     [,1] [,2] [,3] [,4]
[1,]    1    2    3    4
[2,]    5    6    7    8
[3,]    9   10   11   12
```

</div>

Para verificar a dimensão da matriz:

<div class="sourceCode">

``` {.sourceCode .r}
dim(matriz)
[1] 3 4
```

</div>

Adicionando colunas com `cbind()`

<div class="sourceCode">

``` {.sourceCode .r}
cbind(matriz, rep(99, 3))
     [,1] [,2] [,3] [,4] [,5]
[1,]    1    2    3    4   99
[2,]    5    6    7    8   99
[3,]    9   10   11   12   99
```

</div>

Adicionando linhas com `rbind()`

<div class="sourceCode">

``` {.sourceCode .r}
rbind(matriz, rep(99, 4))
     [,1] [,2] [,3] [,4]
[1,]    1    2    3    4
[2,]    5    6    7    8
[3,]    9   10   11   12
[4,]   99   99   99   99
```

</div>

Matrizes também podem ser criadas a partir de vetores adicionando um
**atributo** de dimensão, por exemplo,

<div class="sourceCode">

``` {.sourceCode .r}
m <- 1:10
m
 [1]  1  2  3  4  5  6  7  8  9 10
class(m)
[1] "integer"
dim(m)
NULL
dim(m) <- c(2, 5)
m
     [,1] [,2] [,3] [,4] [,5]
[1,]    1    3    5    7    9
[2,]    2    4    6    8   10
class(m)
[1] "matrix"
typeof(m)
[1] "integer"
```

</div>

<div id="ch003.xhtml#operações-matemáticas-em-matrizes"
class="section level4">

#### [2.6.2.1]{.header-section-number} Operações matemáticas em matrizes

Matriz multiplicada por um escalar

<div class="sourceCode">

``` {.sourceCode .r}
matriz * 2
     [,1] [,2] [,3] [,4]
[1,]    2    4    6    8
[2,]   10   12   14   16
[3,]   18   20   22   24
```

</div>

Multiplicação de matrizes (observe as dimensões!)

<div class="sourceCode">

``` {.sourceCode .r}
matriz2 <- matrix(1, nrow = 4, ncol = 3)
matriz %*% matriz2
     [,1] [,2] [,3]
[1,]   10   10   10
[2,]   26   26   26
[3,]   42   42   42
```

</div>

</div>

</div>

<div id="ch003.xhtml#array" class="section level3">

### [2.6.3]{.header-section-number} Array

Um array é a forma mais geral de uma matriz, pois pode ter $n$
dimensões.

Características:

-   Estrutura $n$-dimensional.
-   Assim como as matrizes, podem conter apenas um tipo de informação
    (números, caracteres).

Para criar um array, usamos a função `array()`, passando como primeiro
argumento um vetor atômico, e especificamos a dimensão com o argumento
`dim`. Por exemplo, para criar um objeto com 3 dimensões
$2 \times 2 \times 3$, fazemos

<div class="sourceCode">

``` {.sourceCode .r}
ar <- array(1:12, dim = c(2, 2, 3))
ar
, , 1

     [,1] [,2]
[1,]    1    3
[2,]    2    4

, , 2

     [,1] [,2]
[1,]    5    7
[2,]    6    8

, , 3

     [,1] [,2]
[1,]    9   11
[2,]   10   12
```

</div>

Similarmente, um array de 2 dimensões $3 \times 2 \times 2$ é obtido com

<div class="sourceCode">

``` {.sourceCode .r}
ar <- array(1:12, dim = c(3, 2, 2))
ar
, , 1

     [,1] [,2]
[1,]    1    4
[2,]    2    5
[3,]    3    6

, , 2

     [,1] [,2]
[1,]    7   10
[2,]    8   11
[3,]    9   12
```

</div>

</div>

<div id="ch003.xhtml#lista" class="section level3">

### [2.6.4]{.header-section-number} Lista

Como já vimos, uma lista não é uma "classe" propriamente dita, mas sim
um tipo de estrutura de dados básico, ao lado dos vetores atômicos. E,
assim como os vetores atômicos, listas são estruturas unidimensionais. A
grande diferença é que listas agrupam objetos de diferentes tipos,
inclusive outras listas.

Características:

-   Pode combinar uma coleção de objetos de diferentes tipos ou classes
    (é um tipo básico de vetor, assim como os vetores atômicos).
-   Estrutura “unidimensional”: apenas o número de elementos na lista é
    contado.

Por exemplo, podemos criar uma lista com uma sequência de números, um
caracter e outra lista.

<div class="sourceCode">

``` {.sourceCode .r}
lista <- list(1:30, "R", list(TRUE, FALSE))
lista
[[1]]
 [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
[26] 26 27 28 29 30

[[2]]
[1] "R"

[[3]]
[[3]][[1]]
[1] TRUE

[[3]][[2]]
[1] FALSE
class(lista)
[1] "list"
typeof(lista)
[1] "list"
```

</div>

Para melhor visualizar a estrutura dessa lista (ou de qualquer outro
objeto) podemos usar a função `str()`

<div class="sourceCode">

``` {.sourceCode .r}
str(lista)
List of 3
 $ : int [1:30] 1 2 3 4 5 6 7 8 9 10 ...
 $ : chr "R"
 $ :List of 2
  ..$ : logi TRUE
  ..$ : logi FALSE
```

</div>

Note que de fato é uma estrutura unidimensional

<div class="sourceCode">

``` {.sourceCode .r}
dim(lista)
NULL
length(lista)
[1] 3
```

</div>

Listas podem armazenar objetos de diferentes classes e dimensões, por
exemplo, usando objetos criados anteriormente

<div class="sourceCode">

``` {.sourceCode .r}
lista <- list(fator, matriz)
lista
[[1]]
[1] alta  baixa baixa media alta  media baixa media media
Levels: baixa < media < alta

[[2]]
     [,1] [,2] [,3] [,4]
[1,]    1    2    3    4
[2,]    5    6    7    8
[3,]    9   10   11   12
length(lista)
[1] 2
```

</div>

</div>

<div id="ch003.xhtml#data-frame" class="section level3">

### [2.6.5]{.header-section-number} Data frame

Data frame é a versão bidimensional de uma lista. Data frames **são**
listas, mas onde cada componente deve ter obrigatoriamente o mesmo
comprimento. Cada vetor da lista vira uma coluna em um data frame,
permitindo então que as "colunas" sejam de diferentes tipos.

Os data frames são as estruturas mais comuns para se trabalhar com dados
no R.

Características:

-   Uma lista de vetores e/ou fatores, de **mesmo comprimento**.
-   Pode conter diferentes tipos de dados (numérico, fator, ...).
-   Estrutura bidimensional.

Utilizando a função `data.frame()`:

<div class="sourceCode">

``` {.sourceCode .r}
da <- data.frame(nome = c("João", "José", "Maria"),
                 sexo = c("M", "M", "F"),
                 idade = c(32, 34, 30))
da
   nome sexo idade
1  João    M    32
2  José    M    34
3 Maria    F    30
class(da)
[1] "data.frame"
typeof(da)
[1] "list"
dim(da)
[1] 3 3
```

</div>

Veja os detalhes com `str()`

<div class="sourceCode">

``` {.sourceCode .r}
str(da)
'data.frame':   3 obs. of  3 variables:
 $ nome : Factor w/ 3 levels "João","José",..: 1 2 3
 $ sexo : Factor w/ 2 levels "F","M": 2 2 1
 $ idade: num  32 34 30
```

</div>

Note que a função `data.frame()` converte caracteres para fator
automaticamente. Para que isso não aconteça, use o argumento
`stringsAsFactors = FALSE`

<div class="sourceCode">

``` {.sourceCode .r}
da <- data.frame(nome = c("João", "José", "Maria"),
                 sexo = c("M", "M", "F"),
                 idade = c(32, 34, 30),
                 stringsAsFactors = FALSE)
da
   nome sexo idade
1  João    M    32
2  José    M    34
3 Maria    F    30
str(da)
'data.frame':   3 obs. of  3 variables:
 $ nome : chr  "João" "José" "Maria"
 $ sexo : chr  "M" "M" "F"
 $ idade: num  32 34 30
```

</div>

Data frames podem ser formados com objetos criados anteriormente, desde
que tenham o mesmo comprimento:

<div class="sourceCode">

``` {.sourceCode .r}
length(num)
[1] 6
length(fator)
[1] 9
db <- data.frame(numerico = c(num, NA, NA, NA),
                 fator = fator)
db
  numerico fator
1       10  alta
2        5 baixa
3        2 baixa
4        4 media
5        8  alta
6        9 media
7       NA baixa
8       NA media
9       NA media
str(db)
'data.frame':   9 obs. of  2 variables:
 $ numerico: num  10 5 2 4 8 9 NA NA NA
 $ fator   : Ord.factor w/ 3 levels "baixa"<"media"<..: 3 1 1 2 3 2 1 2 2
```

</div>

Algumas vezes pode ser necessário converter um data frame para uma
matriz. Existem duas opções:

<div class="sourceCode">

``` {.sourceCode .r}
as.matrix(db)
      numerico fator  
 [1,] "10"     "alta" 
 [2,] " 5"     "baixa"
 [3,] " 2"     "baixa"
 [4,] " 4"     "media"
 [5,] " 8"     "alta" 
 [6,] " 9"     "media"
 [7,] NA       "baixa"
 [8,] NA       "media"
 [9,] NA       "media"
data.matrix(db)
      numerico fator
 [1,]       10     3
 [2,]        5     1
 [3,]        2     1
 [4,]        4     2
 [5,]        8     3
 [6,]        9     2
 [7,]       NA     1
 [8,]       NA     2
 [9,]       NA     2
```

</div>

Geralmente é o resultado de `data.matrix()` o que você está procurando.

<div class="alert alert-warning">

Lembre que os níveis de um fator são armazenados internamente como
números: $1^{\circ}$ nível = 1, $2^{\circ}$ nível = 2, $\ldots$.

<div class="sourceCode">

``` {.sourceCode .r}
fator
[1] alta  baixa baixa media alta  media baixa media media
Levels: baixa < media < alta
str(fator)
 Ord.factor w/ 3 levels "baixa"<"media"<..: 3 1 1 2 3 2 1 2 2
as.numeric(fator)
[1] 3 1 1 2 3 2 1 2 2
```

</div>

</div>

</div>

</div>

<div id="ch003.xhtml#atributos-de-objetos" class="section level2">

[2.7]{.header-section-number} Atributos de objetos
--------------------------------------------------

Um atributo é um pedaço de informação que pode ser "anexado" à qualquer
objeto, e não irá interferir nos valores daquele objeto. Os atributos
podem ser vistos como "metadados", alguma descrição associada à um
objeto. Os principais atributos são:

-   `names`
-   `dimnames`
-   `dim`
-   `class`

Alguns atributos também podem ser visualizados de uma só vez através da
função `attributes()`.

Por exemplo, considere o seguinte vetor

<div class="sourceCode">

``` {.sourceCode .r}
x <- 1:6
attributes(x)
NULL
```

</div>

Mostra que o objeto `x` não possui nenhum atributo. Mas podemos definir
nomes, por exemplo, para cada componente desse vetor

<div class="sourceCode">

``` {.sourceCode .r}
names(x)
NULL
names(x) <- c("um", "dois", "tres", "quatro", "cinco", "seis")
names(x)
[1] "um"     "dois"   "tres"   "quatro" "cinco"  "seis"  
attributes(x)
$names
[1] "um"     "dois"   "tres"   "quatro" "cinco"  "seis"  
```

</div>

Nesse caso específico, o R irá mostrar os nomes acima dos componentes,
mas isso não altera como as operaçõs serão realizadas.

<div class="sourceCode">

``` {.sourceCode .r}
x
    um   dois   tres quatro  cinco   seis 
     1      2      3      4      5      6 
x + 2
    um   dois   tres quatro  cinco   seis 
     3      4      5      6      7      8 
```

</div>

Os nomes então podem ser definidos através da função *auxiliar*
`names()`, sendo assim, também podemos remover esse atributo declarando
ele como nulo.

<div class="sourceCode">

``` {.sourceCode .r}
names(x) <- NULL
attributes(x)
NULL
x
[1] 1 2 3 4 5 6
```

</div>

Outros atributos também podem ser definidos de maneira similar. Veja os
exemplos abaixo:

<div class="sourceCode">

``` {.sourceCode .r}
length(x)
[1] 6
## Altera o comprimento (preenche com NA)
length(x) <- 10
x
 [1]  1  2  3  4  5  6 NA NA NA NA
## Altera a dimensão
length(x) <- 6
dim(x)
NULL
dim(x) <- c(3, 2)
x
     [,1] [,2]
[1,]    1    4
[2,]    2    5
[3,]    3    6
attributes(x)
$dim
[1] 3 2
## Remove dimensão
dim(x) <- NULL
x
[1] 1 2 3 4 5 6
```

</div>

Assim como vimos em data frames, listas também podem ter nomes

<div class="sourceCode">

``` {.sourceCode .r}
x <- list(Curitiba = 1, Paraná = 2, Brasil = 3)
x
$Curitiba
[1] 1

$Paraná
[1] 2

$Brasil
[1] 3
names(x)
[1] "Curitiba" "Paraná"   "Brasil"  
```

</div>

Podemos também associar nomes às *linhas* e *colunas* de uma matriz:

<div class="sourceCode">

``` {.sourceCode .r}
matriz
     [,1] [,2] [,3] [,4]
[1,]    1    2    3    4
[2,]    5    6    7    8
[3,]    9   10   11   12
attributes(matriz)
$dim
[1] 3 4
rownames(matriz) <- c("A","B","C")
colnames(matriz) <- c("T1","T2","T3","T4")
matriz
  T1 T2 T3 T4
A  1  2  3  4
B  5  6  7  8
C  9 10 11 12
attributes(matriz)
$dim
[1] 3 4

$dimnames
$dimnames[[1]]
[1] "A" "B" "C"

$dimnames[[2]]
[1] "T1" "T2" "T3" "T4"
```

</div>

Para data frames existe uma função especial para os nomes de linhas,
`row.names()`. Data frames também não possuem nomes de colunas, apenas
nomes, já que é um caso particular de lista. Então para
verificar/alterar nomes de colunas de um data frame também use
`names()`.

<div class="sourceCode">

``` {.sourceCode .r}
da
   nome sexo idade
1  João    M    32
2  José    M    34
3 Maria    F    30
attributes(da)
$names
[1] "nome"  "sexo"  "idade"

$class
[1] "data.frame"

$row.names
[1] 1 2 3
names(da)
[1] "nome"  "sexo"  "idade"
row.names(da)
[1] "1" "2" "3"
```

</div>

Um resumo das funções para alterar/acessar nomes de linhas e colunas em
matrizes e data frames.

  Classe         Nomes de colunas   Nomes de linhas
  -------------- ------------------ -----------------
  `data.frame`   `names()`          `row.names()`
  `matrix`       `colnames()`       `rownames()`

</div>

<div id="ch003.xhtml#exercícios-4" class="section level2 unnumbered">

Exercícios
----------

1.  Crie um objeto para armazenar a seguinte matriz $$\begin{bmatrix}
    2 & 8 & 4 \\
    0 & 4 & 1 \\
    9 & 7 & 5 \\
    \end{bmatrix}$$
2.  Atribua nomes para as linhas e colunas dessa matriz.
3.  Crie uma lista (**não nomeada**) com dois componentes: (1) um vetor
    com as letras `A`, `B`, e `C`, repetidas 2, 5, e 4 vezes
    respectivamente; e (2) a matriz do exemplo anterior.
4.  Atribua nomes para estes dois componentes da lista.
5.  Inclua mais um componente nesta lista, com o nome de `fator`, e que
    seja um vetor da classe `factor`, idêntico ao objeto `caracter`
    criado acima (que possui apenas os nomes `brava`, `joaquina`,
    `armação`).
6.  Crie um data frame para armazenar duas variáveis: local (`A`, `B`,
    `C`, `D`), e contagem (42, 34, 59 e 18).
7.  Crie um data frame com as seguintes colunas:

-   Nome
-   Sobrenome
-   Se possui animal de estimação
-   Caso possua, dizer o número de animais (caso contrário, colocar 0)

Para criar o data frame, a primeira linha deve ser preenchida com as
suas próprias informação (use a função `data.frame()`). Depois, pergunte
essas mesmas informações para dois colegas ao seu lado, e adicione as
informações deles à esse data frame (use `rbind()`). Acresente mais uma
coluna com o nome do time de futebol de cada um.

</div>

<div id="ch003.xhtml#referências-1" class="section level2 unnumbered">

Referências
-----------

Para mais detalhes e exemplos dos assuntos abordados aqui, veja
[Grolemund ([2014](#ch003.xhtml#ref-Grolemund2014))]{.citation
data-cites="Grolemund2014"}. Uma abordagem mais avançada e detalhada
sobre programação orientada a objetos no R pode ser consultada em
[Wickham ([2015](#ch003.xhtml#ref-Wickham2015))]{.citation
data-cites="Wickham2015"}.

<!-- Isso faz com que as referências se mantenham noo final do capítulo -->
<div id="ch003.xhtml#refs">

<div id="ch003.xhtml#ref-Grolemund2014">

Grolemund, Garrett. 2014. *Hands-On Programming with R - Write Your Own
Functions and Simulations*. O’Reily Media.
<http://shop.oreilly.com/product/0636920028574.do>.

</div>

<div id="ch003.xhtml#ref-Wickham2015">

Wickham, Hadley. 2015. *Advanced R*. CRC Press.

</div>

</div>

<!--chapter:end:02-objetos-classes.Rmd-->

</div>

</div>

[]{#ch004.xhtml}

<div id="ch004.xhtml#indexação-e-seleção-condicional"
class="section level1">

[3]{.header-section-number} Indexação e seleção condicional
===========================================================

<div id="ch004.xhtml#indexação" class="section level2">

[3.1]{.header-section-number} Indexação
---------------------------------------

Existem 6 maneiras diferentes de indexar valores no R. Podemos indexar
usando:

-   Inteiros positivos.
-   Inteiros negativos.
-   Zero.
-   Espaço em branco.
-   Nomes.
-   Valores lógicos.

Existem três tipos de operadores que podem ser usados para indexar (e
selecionar) **sub-conjuntos** (*subsets*) de objetos no R:

-   O operador `[ ]` sempre retorna um objeto da mesma classe que o
    original. Pode ser usado para selecionar múltiplos elementos de um
    objeto.
-   O operador`[[ ]]` é usado para extrair elementos de uma **lista** ou
    **data frame**. Pode ser usado para extrair um único elemento, e a
    classe do objeto retornado não precisa necessariamente ser uma lista
    ou data frame.
-   O operador `$` é usado para extrair elementos **nomeados** de uma
    lista ou data frame. É similar ao operador `[[ ]]`.

<div id="ch004.xhtml#indexação-de-vetores" class="section level3">

### [3.1.1]{.header-section-number} Indexação de vetores

Observe o seguinte vetor de contagens

<div class="sourceCode">

``` {.sourceCode .r}
cont <- c(8, 4, NA, 9, 6, 1, 7, 9)
cont
[1]  8  4 NA  9  6  1  7  9
```

</div>

Para acessar o valor que está na posição 4, faça:

<div class="sourceCode">

``` {.sourceCode .r}
cont[4]
[1] 9
```

</div>

<div class="alert alert-warning">

Os colchetes `[ ]` são utilizados para **extração** (seleção de um
intervalo de dados) ou **substituição** de elementos. O valor dentro dos
colchetes é chamado de **índice**.

</div>

Para acessar os valores nas posições 1, 4 e 8 é necessário o uso da
função `c()`:

<div class="sourceCode">

``` {.sourceCode .r}
cont[c(1, 4, 8)]
[1] 8 9 9
```

</div>

Ou:

<div class="sourceCode">

``` {.sourceCode .r}
ind <- c(1, 4, 8)
cont[ind]
[1] 8 9 9
```

</div>

<div class="alert alert-warning">

Note que os índices no R começam em 1, e não em 0, como em algumas
outras linguagens.

</div>

Para selecionar todos os valores, **excluindo** aquele da posição 4,
usamos um índice negativo

<div class="sourceCode">

``` {.sourceCode .r}
cont[-4]
[1]  8  4 NA  6  1  7  9
```

</div>

Da mesma forma se quiséssemos todos os valores, menos aqueles das
posições 1, 4 e 8:

<div class="sourceCode">

``` {.sourceCode .r}
cont[-c(1, 4, 8)]
[1]  4 NA  6  1  7
```

</div>

Também é possível selecionar uma sequência de elementos (com qualquer
uma das funções de gerar sequências que já vimos antes):

<div class="sourceCode">

``` {.sourceCode .r}
## Seleciona os elementos de 1 a 5
cont[1:5]
[1]  8  4 NA  9  6
## Seleciona os elementos nas posições ímpar
cont[seq(1, 8, by = 2)]
[1]  8 NA  6  7
```

</div>

Mas note que para selecionar todos menos aqueles de uma sequência,
precisamos colocá-la entre parênteses

<div class="sourceCode">

``` {.sourceCode .r}
cont[-1:5]
Error in cont[-1:5]: only 0's may be mixed with negative subscripts
cont[-(1:5)]
[1] 1 7 9
```

</div>

Para selecionar todos os elementos que sejam `NA`, ou todos menos os
`NA`s, precisamos usar a função `is.na()`

<div class="sourceCode">

``` {.sourceCode .r}
## Para selecionar os NAs
cont[is.na(cont)]
[1] NA
## Para selecionar todos menos os NAs
cont[!is.na(cont)]
[1] 8 4 9 6 1 7 9
```

</div>

Para substituir os `NA`s por algum valor (*e.g.* 0):

<div class="sourceCode">

``` {.sourceCode .r}
cont[is.na(cont)] <- 0
cont
[1] 8 4 0 9 6 1 7 9
```

</div>

E para especificar `NA` para algum valor

<div class="sourceCode">

``` {.sourceCode .r}
is.na(cont) <- 3
cont
[1]  8  4 NA  9  6  1  7  9
## Mais seguro do que
# cont[3] <- NA
```

</div>

<div class="alert alert-warning">

Note que se utilizarmos o operador de atribuição `<-` em conjunto com
uma indexação, estaremos **substituindo** os valores selecionados pelos
valores do lado direito do operador de atribuição.

</div>

Podemos também utilizar mais duas formas de indexação no R: espaços em
branco e zero:

<div class="sourceCode">

``` {.sourceCode .r}
cont[0]
numeric(0)
cont[]
[1]  8  4 NA  9  6  1  7  9
```

</div>

Note que o índice zero não existe no R, mas ao utilizá-lo é retornado um
vetor "vazio", ou um vetor de comprimento zero. Essa forma de indexação
é raramente utilizada no R.

Ao deixar um espaço em branco, estamos simplesmente informando que
queremos todos os valores daquele vetor. Essa forma de indexação será
particularmente útil para objetos que possuem duas ou mais dimensões,
como matrizes e data frames.

</div>

<div id="ch004.xhtml#exercícios-5" class="section level3 unnumbered">

### Exercícios

1.  Crie um vetor com os valores: `88, 5, 12, 13`.
2.  Selecione o elemento na posição 3.
3.  Selecione o valor 88.
4.  Selecione os valores 13 e 5.
5.  Selecione todos os valores, menos o 88 e o 13.
6.  Insira o valor 168 **entre** os valores 12 e 13, criando um novo
    objeto.

<div id="ch004.xhtml#vetores-nomeados" class="section level4">

#### [3.1.1.1]{.header-section-number} Vetores nomeados

Quando vetores possuem seus componentes **nomeados**, a indexação pode
ser realizada pelos nomes destes componentes.

<div class="sourceCode">

``` {.sourceCode .r}
## Atribui as letras "a", "b", ..., "h" para os componentes de cont
names(cont) <- letters[1:length(cont)]
## Acessando o quarto elemento
cont["d"]
d 
9 
## Acessando o sexto e o primeiro elemento
cont[c("f", "a")]
f a 
1 8 
```

</div>

Dica: veja `?letters`

</div>

</div>

<div id="ch004.xhtml#indexação-de-matrizes" class="section level3">

### [3.1.2]{.header-section-number} Indexação de matrizes

Considere a seguinte matriz

<div class="sourceCode">

``` {.sourceCode .r}
mat <- matrix(1:9, nrow = 3)
mat
     [,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9
```

</div>

Acesse o valor que está na linha 2 da coluna 3:

<div class="sourceCode">

``` {.sourceCode .r}
mat[2, 3]
[1] 8
```

</div>

<div class="alert alert-warning">

A indexação de matrizes sempre segue a ordem `[linha, coluna]`

</div>

Para acessar todas as linhas da coluna 1, deixamos o espaço em branco
(que também é uma forma de seleção, como vimos) na posição das linhas e
especificamos a coluna desejada

<div class="sourceCode">

``` {.sourceCode .r}
mat[, 1]
[1] 1 2 3
```

</div>

Para acessar todas as colunas da linha 1, usamos a mesma lógica

<div class="sourceCode">

``` {.sourceCode .r}
mat[1, ]
[1] 1 4 7
```

</div>

Note que o resultado destas extrações trazem os valores internos das
matrizes, mas com a dimensão reduzida (nestes casos para uma dimensão).
Se o objetivo for, por exemplo, extrair uma parte da matriz, mas
mantendo as duas dimensões, então precisamos usar o argumento `drop` da
"função" `[` (sim, também é uma função; veja `"?["`). Veja as
diferenças:

<div class="sourceCode">

``` {.sourceCode .r}
mat[3, 2]
[1] 6
mat[3, 2, drop = FALSE]
     [,1]
[1,]    6
mat[1, ]
[1] 1 4 7
mat[1, , drop = FALSE]
     [,1] [,2] [,3]
[1,]    1    4    7
```

</div>

Para acessar as linhas 1 e 3 das colunas 2 e 3:

<div class="sourceCode">

``` {.sourceCode .r}
mat[c(1, 3), c(2, 3)]
     [,1] [,2]
[1,]    4    7
[2,]    6    9
```

</div>

E note que aqui a dimensão já é 2 pois naturalmente o resultado precisa
ser representado em duas dimensões.

<div id="ch004.xhtml#matrizes-nomeadas" class="section level4">

#### [3.1.2.1]{.header-section-number} Matrizes nomeadas

Se as matrizes tiverem linhas e/ou colunas nomeadas, a indexação também
pode ser feita com os nomes.

<div class="sourceCode">

``` {.sourceCode .r}
##----------------------------------------------------------------------
## Nomes das colunas
colnames(mat) <- LETTERS[1:3]
## Todas as linhas da coluna B
mat[, "B"]
[1] 4 5 6
## Elemento da linha 1 e coluna C
mat[1, "C"]
C 
7 
##----------------------------------------------------------------------
## Nomes das linhas
rownames(mat) <- LETTERS[24:26]
## Todas as colunas da linha X
mat["X", ]
A B C 
1 4 7 
## Elemento da linha Y e coluna A
mat["Y", "A"]
[1] 2
```

</div>

</div>

</div>

<div id="ch004.xhtml#indexação-de-listas" class="section level3">

### [3.1.3]{.header-section-number} Indexação de listas

Considere a seguinte lista:

<div class="sourceCode">

``` {.sourceCode .r}
lis <- list(c(3, 8, 7, 4), mat, 5:0)
lis
[[1]]
[1] 3 8 7 4

[[2]]
  A B C
X 1 4 7
Y 2 5 8
Z 3 6 9

[[3]]
[1] 5 4 3 2 1 0
```

</div>

Podemos acessar um componente da lista da maneira usual

<div class="sourceCode">

``` {.sourceCode .r}
lis[1]
[[1]]
[1] 3 8 7 4
```

</div>

Mas note que esse objeto continua sendo uma lista

<div class="sourceCode">

``` {.sourceCode .r}
class(lis[1])
[1] "list"
```

</div>

Geralmente o que queremos é acessar os elementos que estão **contidos**
nos componentes da lista, e para isso precisamos usar `[[` no lugar de
`[`:

<div class="sourceCode">

``` {.sourceCode .r}
lis[[1]]
[1] 3 8 7 4
class(lis[[1]])
[1] "numeric"
```

</div>

Isso é importante, por exemplo, se quisessemos aplicar uma função
qualquer a um componente da lista. No primeiro caso isso não é possível
pois o conteúdo continua dentro de uma lista, enquanto que no segundo
caso os valores retornados são os próprios números:

<div class="sourceCode">

``` {.sourceCode .r}
mean(lis[1])
Warning in mean.default(lis[1]): argument is not numeric or logical: returning
NA
[1] NA
mean(lis[[1]])
[1] 5.5
```

</div>

Para acessar o segundo **componente** da lista:

<div class="sourceCode">

``` {.sourceCode .r}
lis[[2]]
  A B C
X 1 4 7
Y 2 5 8
Z 3 6 9
```

</div>

Para acessar o terceiro valor do primeiro componente:

<div class="sourceCode">

``` {.sourceCode .r}
lis[[1]][3]
[1] 7
```

</div>

Note que o segundo elemento da lista é uma matriz, portanto a indexação
da matriz *dentro da lista* também segue o mesmo padrão

<div class="sourceCode">

``` {.sourceCode .r}
lis[[2]][2, 3]
[1] 8
```

</div>

Se a lista tiver componentes **nomeados**, eles podem ser acessados com
o operador `$`:

<div class="sourceCode">

``` {.sourceCode .r}
lis <- list(vetor1 = c(3, 8, 7, 4), mat = mat, vetor2 = 5:0)
## Ou
## names(lis) <- c("vetor1", "mat", "vetor2")
lis
$vetor1
[1] 3 8 7 4

$mat
  A B C
X 1 4 7
Y 2 5 8
Z 3 6 9

$vetor2
[1] 5 4 3 2 1 0
```

</div>

<div class="sourceCode">

``` {.sourceCode .r}
## Acesando o segundo componente
lis$mat
  A B C
X 1 4 7
Y 2 5 8
Z 3 6 9
## Linha 2 e coluna 3
lis$mat[2, 3]
[1] 8
## Terceiro elemento do primeiro componente
lis$vetor1[3]
[1] 7
```

</div>

Ou então

<div class="sourceCode">

``` {.sourceCode .r}
lis[["mat"]]
  A B C
X 1 4 7
Y 2 5 8
Z 3 6 9
lis[["vetor1"]][3]
[1] 7
```

</div>

<div class="alert alert-warning">

O símbolo `$` é utilizado para acessar componentes **nomeados** de
listas ou data frames.

</div>

</div>

<div id="ch004.xhtml#indexação-de-data-frames" class="section level3">

### [3.1.4]{.header-section-number} Indexação de data frames

Considere o seguinte data frame

<div class="sourceCode">

``` {.sourceCode .r}
da <- data.frame(A = 4:1, B = c(2, NA, 5, 8))
da
  A  B
1 4  2
2 3 NA
3 2  5
4 1  8
```

</div>

Para acessar o segundo elemento da primeira coluna (segue a mesma lógica
da indexação de matrizes pois também possui duas dimensões):

<div class="sourceCode">

``` {.sourceCode .r}
da[2, 1]
[1] 3
```

</div>

Acesse todas as linhas da coluna B:

<div class="sourceCode">

``` {.sourceCode .r}
da[, 2]
[1]  2 NA  5  8
```

</div>

Ou usando o nome da coluna:

<div class="sourceCode">

``` {.sourceCode .r}
da[,"B"]
[1]  2 NA  5  8
```

</div>

Todas as colunas da linha 1:

<div class="sourceCode">

``` {.sourceCode .r}
da[1, ]
  A B
1 4 2
```

</div>

Ou usando o "nome" da linha:

<div class="sourceCode">

``` {.sourceCode .r}
da["1", ]
  A B
1 4 2
```

</div>

Note que o argumento `drop=` também é válido se quiser manter a dimensão
do objeto

<div class="sourceCode">

``` {.sourceCode .r}
da[, "B"]
[1]  2 NA  5  8
da[, "B", drop = FALSE]
   B
1  2
2 NA
3  5
4  8
```

</div>

Como o data frame é um caso particular de uma lista (onde todos os
componentes tem o mesmo comprimento), as colunas de um data frame também
podem ser acessadas com `$`:

<div class="sourceCode">

``` {.sourceCode .r}
da$A
[1] 4 3 2 1
```

</div>

Para acessar o terceiro elemento da coluna B:

<div class="sourceCode">

``` {.sourceCode .r}
da$B[3]
[1] 5
```

</div>

Para acessar os elementos nas posições 2 e 4 da coluna B:

<div class="sourceCode">

``` {.sourceCode .r}
da$B[c(2, 4)]
[1] NA  8
```

</div>

Assim como nas listas, podemos indexar um data frame usando apenas um
índice, que nesse caso retorna a coluna (componente) do data frame:

<div class="sourceCode">

``` {.sourceCode .r}
da[1]
  A
1 4
2 3
3 2
4 1
class(da[1])
[1] "data.frame"
```

</div>

Note que dessa forma a classe é mantida. Também podemos indexar os data
frames usando `[[` da mesma forma como em listas

<div class="sourceCode">

``` {.sourceCode .r}
da[[1]]
[1] 4 3 2 1
da[["A"]]
[1] 4 3 2 1
da[["A"]][2:3]
[1] 3 2
```

</div>

Para lidar com `NA`s em data frames, podemos também usar a função
`is.na()`

<div class="sourceCode">

``` {.sourceCode .r}
da[is.na(da), ] # nao retorna o resultado esperado
    A  B
NA NA NA
## Deve ser feito por coluna
da[is.na(da$A), ]
[1] A B
<0 rows> (or 0-length row.names)
da[is.na(da$B), ]
  A  B
2 3 NA
## De maneira geral
is.na(da)
         A     B
[1,] FALSE FALSE
[2,] FALSE  TRUE
[3,] FALSE FALSE
[4,] FALSE FALSE
is.na(da$A)
[1] FALSE FALSE FALSE FALSE
is.na(da$B)
[1] FALSE  TRUE FALSE FALSE
```

</div>

Para remover as linhas que possuem `NA`, note que será necessário
remover todas as colunas daquela linha, pois data frames não podem ter
colunas de comprimentos diferentes

<div class="sourceCode">

``` {.sourceCode .r}
da[!is.na(da$B), ]
  A B
1 4 2
3 2 5
4 1 8
```

</div>

A função `complete.cases()` facilita esse processo. Veja o resultado

<div class="sourceCode">

``` {.sourceCode .r}
complete.cases(da)
[1]  TRUE FALSE  TRUE  TRUE
da[complete.cases(da), ]
  A B
1 4 2
3 2 5
4 1 8
```

</div>

<div id="ch004.xhtml#a-função-with" class="section level4">

#### [3.1.4.1]{.header-section-number} A função `with()`

Para evitar fazer muitas indexações de um mesmo data frame, por exemplo,
podemos utilizar a função `with()`

<div class="sourceCode">

``` {.sourceCode .r}
with(da, A)
[1] 4 3 2 1
```

</div>

é o mesmo que

<div class="sourceCode">

``` {.sourceCode .r}
da$A
[1] 4 3 2 1
```

</div>

Também é útil para acessar elementos específicos dentro de data frames.
Por exemplo, o terceiro elemento da coluna B

<div class="sourceCode">

``` {.sourceCode .r}
with(da, B[3])
[1] 5
```

</div>

E também para aplicar funções nas colunas do data frame

<div class="sourceCode">

``` {.sourceCode .r}
with(da, mean(A))
[1] 2.5
```

</div>

</div>

</div>

</div>

<div id="ch004.xhtml#exercícios-6" class="section level2 unnumbered">

Exercícios
----------

1.  Crie a seguinte matriz $$\begin{bmatrix}
    4 & 16 & 2 \\
    10 & 5 & 11 \\
    9 & 9 & 5 \\
    2 & 0 & {NA} \\
    \end{bmatrix}.$$
2.  Acesse o elemento na quarta linha e na segunda coluna.
3.  Acesse todos os elementos, com exceção da segunda coluna e da
    terceira linha.
4.  Crie uma lista (nomeada) com 3 componentes: um vetor numérico de
    comprimento 10, um vetor de caracteres de comprimento 7 e a matriz
    do exercício anterior.
5.  Acesse os elementos nas posições de 5 a 3 do primeiro componente da
    lista.
6.  Acesse os caracteres de todas as posições, menos da 2 e 6.
7.  Acesse todas as linhas da coluna 3 da matriz dentro desta lista.
8.  "Crie" um novo componente nessa lista (usando `$`), contendo 30
    valores aleatórios de uma distribuição normal $\text{N}(12,4)$ (veja
    `?rnorm`).
9.  Crie um data frame que contenha duas colunas: a primeira com as
    letras de "A" até "J", e outra com o resultado de uma chamada da
    função `runif(7, 1, 5)`.
10. Extraia as duas primeiras linhas desse data frame.
11. Extraia as duas últimas linhas desse data frame.
12. Qual é o valor que está na linha 6 e coluna 1?
13. Qual é o valor que está na linha 4 da coluna 2?
14. Como você faria para contar quantos valores perdidos (`NA`s) existem
    nesse data frame?
15. Elimine os `NA`s deste data frame.
16. Crie uma nova coluna neste data frame, com valores numéricos
    (quaisquer).
17. Crie mais um componente na lista anterior, que será também uma lista
    com dois componentes: `A` com os valores `1:5`, e `B` com as letras
    de "a" a "f".
18. Acesse o número 4 de `A`.
19. Acesse a letra "c" de `B`.

</div>

<div id="ch004.xhtml#seleção-condicional" class="section level2">

[3.2]{.header-section-number} Seleção condicional
-------------------------------------------------

<div id="ch004.xhtml#seleção-condicional-em-vetores"
class="section level3">

### [3.2.1]{.header-section-number} Seleção condicional em vetores

<div class="alert alert-warning">

A **seleção condicional** serve para extrair dados que satisfaçam algum
critério, usando **expressões condicionais** e **operadores lógicos**.

</div>

Considere o seguinte vetor

<div class="sourceCode">

``` {.sourceCode .r}
dados <- c(5, 15, 42, 28, 79, 4, 7, 14)
```

</div>

Selecione apenas os valores maiores do que 15:

<div class="sourceCode">

``` {.sourceCode .r}
dados[dados > 15]
[1] 42 28 79
```

</div>

Selecione os valores maiores que 15 E menores ou iguais a 35:

<div class="sourceCode">

``` {.sourceCode .r}
dados[dados > 15 & dados <= 35]
[1] 28
```

</div>

Para entender como funciona a seleção condicional, observe apenas o
resultado da condição dentro do colchetes:

<div class="sourceCode">

``` {.sourceCode .r}
## Usando & (e)
dados > 15 & dados <= 35
[1] FALSE FALSE FALSE  TRUE FALSE FALSE FALSE FALSE
## Usando | (ou)
dados > 15 | dados <= 35
[1] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
```

</div>

Os valores selecionados serão aqueles em que a condição for `TRUE`, no
primeiro caso apenas o quarto elemento do vetor `dados`.

A seleção condicional também é muito útil para selecionar elementos de
um vetor, baseado em uma condição de outro vetor.

Considere o seguinte vetor de caracteres

<div class="sourceCode">

``` {.sourceCode .r}
cara <- letters[1:length(dados)]
```

</div>

Considere que de alguma forma, os objetos `dados` e `cara` possuem
alguma relação. Sendo assim, podemos selecionar elementos de `dados`,
baseados em alguma condição de `cara`

<div class="sourceCode">

``` {.sourceCode .r}
## Elemento de dados onde cara é igual a "c"
dados[cara == "c"]
[1] 42
```

</div>

Se quisermos selecionar mais de um elemento de `dados`, baseado em uma
condição de `cara`?

<div class="sourceCode">

``` {.sourceCode .r}
## Elementos de dados onde cara é igual a "a" e "c"
cara == "a" & cara == "c" # porque não funciona?
[1] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
cara == "a" | cara == "c"
[1]  TRUE FALSE  TRUE FALSE FALSE FALSE FALSE FALSE
dados[cara == "a" | cara == "c"]
[1]  5 42
```

</div>

Uma solução melhor seria se pudessemos usar

<div class="sourceCode">

``` {.sourceCode .r}
dados[cara == c("a", "c")]
[1] 5
```

</div>

mas nesse caso só temos o primeiro elemento. Um operador muito útil
nestes casos é o `%in%`

<div class="sourceCode">

``` {.sourceCode .r}
dados[cara %in% c("a", "c")]
[1]  5 42
cara %in% c("a", "c")
[1]  TRUE FALSE  TRUE FALSE FALSE FALSE FALSE FALSE
```

</div>

Veja a diferença

<div class="sourceCode">

``` {.sourceCode .r}
cara == c("a", "c")
[1]  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
cara %in% c("a", "c")
[1]  TRUE FALSE  TRUE FALSE FALSE FALSE FALSE FALSE
```

</div>

Também é possível fazer a seleção de `cara`, baseado em uma condição em
`dados`

<div class="sourceCode">

``` {.sourceCode .r}
## Elemento de cara onde dados é igual a 15
cara[dados == 15]
[1] "b"
## Elemento de cara onde dados for maior do que 30
cara[dados > 30]
[1] "c" "e"
## Elemento de cara onde dados for igual a 4 ou 14
cara[dados %in% c(4, 14)]
[1] "f" "h"
```

</div>

</div>

<div id="ch004.xhtml#a-função-which" class="section level3">

### [3.2.2]{.header-section-number} A função `which()`

Até agora vimos seleções condicionais que nos retornavam o resultado de
uma expressão condicional em vetores. No entanto, muitas vezes estamos
interessados em saber a **posição** do resultado de uma expressão
condicional, ao invés do resultado em si.

A fução `which()` retorna as posições dos elementos que retornarem
`TRUE` em uma expressão condicional.

<div class="sourceCode">

``` {.sourceCode .r}
## Elementos maiores de 15
dados[dados > 15]
[1] 42 28 79
which(dados > 15)
[1] 3 4 5
## Elementos maiores de 15 e menores ou iguais a 35
dados[dados > 15 & dados <= 35]
[1] 28
which(dados > 15 & dados <= 35)
[1] 4
## Elementos de dados onde cara igual a "c"
dados[cara == "c"]
[1] 42
which(cara == "c")
[1] 3
## Elementos de dados onde cara é igual a "a" ou "c"
dados[cara %in% c("a", "c")]
[1]  5 42
which(cara %in% c("a", "c"))
[1] 1 3
```

</div>

</div>

<div id="ch004.xhtml#exercícios-7" class="section level3 unnumbered">

### Exercícios

1.  Crie um vetor (`x`) com os valores 3, 8, 10, 4, 9, 7, 1, 9, 2, 4.
2.  Selecione os elementos maiores ou iguais a 5.
3.  Selecione todos os elementos menos o 4.
4.  Selecione os elementos maiores que 4 e menores que 8.
5.  Crie um vetor (`a`) com as letras de A até J.
6.  Selecione os elementos de x onde a for igual a "F".
7.  Selecione os elementos de x onde a for igual a "B", "D", e "H".
8.  Qual a posição do número 10 em x?
9.  Quais as posições dos valores maiores ou iguais a 8 e menores ou
    iguais a 10 em x?
10. Quais as posições das letras "A", "B", "D" em a?

</div>

<div id="ch004.xhtml#seleção-condicional-em-data-frames"
class="section level3">

### [3.2.3]{.header-section-number} Seleção condicional em data frames

Considere o seguinte data frame

<div class="sourceCode">

``` {.sourceCode .r}
dados <- data.frame(ano = c(2001, 2002, 2003, 2004, 2005),
                    captura = c(26, 18, 25, 32, NA),
                    porto = c("SP", "RS", "SC", "SC", "RN"))
```

</div>

Extraia deste objeto apenas a linha correspondente ao ano 2004:

<div class="sourceCode">

``` {.sourceCode .r}
dados[dados$ano == 2004, ]
   ano captura porto
4 2004      32    SC
```

</div>

Mostre as linhas apenas do porto "SC":

<div class="sourceCode">

``` {.sourceCode .r}
dados[dados$porto == "SC", ]
   ano captura porto
3 2003      25    SC
4 2004      32    SC
```

</div>

Observe as linhas onde a captura seja maior que 20, selecionando apenas
a coluna `captura`:

<div class="sourceCode">

``` {.sourceCode .r}
dados[dados$captura > 20, "captura"]
[1] 26 25 32 NA
```

</div>

Também exclua as linhas com `NA`s (agora com todas as colunas):

<div class="sourceCode">

``` {.sourceCode .r}
dados[dados$captura > 20 & !is.na(dados$captura), ]
   ano captura porto
1 2001      26    SP
3 2003      25    SC
4 2004      32    SC
dados[dados$captura > 20 & complete.cases(dados), ]
   ano captura porto
1 2001      26    SP
3 2003      25    SC
4 2004      32    SC
```

</div>

A condição pode ser feita com diferentes colunas:

<div class="sourceCode">

``` {.sourceCode .r}
dados[dados$captura > 25 & dados$porto == "SP", ]
   ano captura porto
1 2001      26    SP
```

</div>

A função `subset()` serve para os mesmos propósitos, e facilita todo o
processo de seleção condicional:

<div class="sourceCode">

``` {.sourceCode .r}
dados[dados$porto == "SC", ]
   ano captura porto
3 2003      25    SC
4 2004      32    SC
subset(dados, porto == "SC")
   ano captura porto
3 2003      25    SC
4 2004      32    SC
dados[dados$captura > 20, ]
    ano captura porto
1  2001      26    SP
3  2003      25    SC
4  2004      32    SC
NA   NA      NA  <NA>
subset(dados, captura > 20)
   ano captura porto
1 2001      26    SP
3 2003      25    SC
4 2004      32    SC
dados[dados$captura > 20 & !is.na(dados$captura), ]
   ano captura porto
1 2001      26    SP
3 2003      25    SC
4 2004      32    SC
dados[dados$captura > 20, "captura"]
[1] 26 25 32 NA
subset(dados, captura > 20, select = captura)
  captura
1      26
3      25
4      32
```

</div>

A grande vantagem é que a função `subset()` já lida com os `NA`s (se
isso for o que você precisa).

</div>

<div id="ch004.xhtml#exercícios-8" class="section level3 unnumbered">

### Exercícios

1.  Você contou 42 caranguejos na Joaquina, 34 no Campeche, 59 na
    Armação e 18 na Praia Mole. Crie um data frame para armazenar estas
    informações (número de caranguejos observados e local).
2.  Com o data frame criado no exercício anterior, mostre qual a praia
    onde foram coletadas menos de 30 caranguejos (usando seleção
    condicional!).
3.  Crie uma nova coluna (região) neste data frame indicando que
    Joaquina e Praia Mole estão localizadas no leste da ilha (leste) e
    Campeche e Armação estão no sul (sul).
4.  Selecione as praias de região leste que possuem menos de 20
    caranguejos contados.
5.  Você está interessado em saber em qual das duas praias do sul, o
    número de caranguejos contados foi maior do que 40. Usando a seleção
    condicional, mostre essa informação na tela.
6.  Qual região possui praias com mais de 50 caranguejos contados?

<!--chapter:end:03-indexacao-selecao.Rmd-->

</div>

</div>

</div>

[]{#ch005.xhtml}

<div id="ch005.xhtml#entrada-e-saída-de-dados-no-r"
class="section level1">

[4]{.header-section-number} Entrada e saída de dados no R
=========================================================

A entrada de dados no R pode ser realizada de diferentes formas. O
formato mais adequado vai depender do tamanho do conjunto de dados, e se
os dados já existem em outro formato para serem importados ou se serão
digitados diretamente no R.

A seguir são descritas as formas de entrada de dados com indicação de
quando cada uma das formas deve ser usada. Os três primeiros casos são
adequados para entrada de dados diretamente no R, os seguintes descrevem
como importar dados já disponíveis eletronicamente de um arquivo texto,
em outro sistema ou no próprio R.

Posteriormente também será mostrado como fazer para exportar bases de
dados geradas e/ou alteradas dentro do R.

<div id="ch005.xhtml#entrada-de-dados" class="section level2">

[4.1]{.header-section-number} Entrada de dados
----------------------------------------------

<div id="ch005.xhtml#entrada-de-dados-diretamente-no-r"
class="section level3">

### [4.1.1]{.header-section-number} Entrada de dados diretamente no R

<div id="ch005.xhtml#vetores" class="section level4">

#### [4.1.1.1]{.header-section-number} Vetores

A forma mais básica de entrada de dados no R é através da função `c()`
(como já vimos). A partir dela pode se criar os outros tipos de objetos
como listas e data frames.

As funções básicas de entrada de dados são:

-   `c()`
-   `rep()`
-   `seq()` ou `:`

A partir destas funções básicas podemos criar objetos de classes mais
específicas como

-   `matrix()`
-   `list()`
-   `data.frame()`

</div>

</div>

<div id="ch005.xhtml#entrada-via-teclado" class="section level3">

### [4.1.2]{.header-section-number} Entrada via teclado

<div id="ch005.xhtml#usando-a-função-scan" class="section level4">

#### [4.1.2.1]{.header-section-number} Usando a função `scan()`

Esta função lê dados diretamento do console, isto é, coloca o R em modo
*prompt* onde o usuário deve digitar cada dado seguido da tecla
<kbd>Enter</kbd>. Para encerrar a entrada de dados basta digitar
<kbd>Enter</kbd> duas vezes consecutivas.

Veja o seguinte resultado:

<div class="sourceCode">

``` {.sourceCode .r}
y <- scan()

1: 11
2: 24
3: 35
4: 29
5: 39
6: 47
7:
Read 6 items
```

</div>

<div class="sourceCode">

``` {.sourceCode .r}
y
[1] 11 24 35 29 39 47
```

</div>

Os dados também podem ser digitados em sequência, desde que separados
por um espaço,

<div class="sourceCode">

``` {.sourceCode .r}
y <- scan()

1: 11 24
3: 35 29
5: 39 47
7:
Read 6 items
```

</div>

<div class="sourceCode">

``` {.sourceCode .r}
y
[1] 11 24 35 29 39 47
```

</div>

Este formato é mais ágil que o anterior (com `c()`, por exemplo) e é
conveniente para digitar vetores longos. Esta função pode também ser
usada para ler dados de um arquivo ou conexão, aceitando inclusive
endereços de URLs (endereços da *web*) o que iremos mencionar em
detalhes mais adiante.

Por padrão, a função `scan()` aceita apenas valores numéricos como
entrada (lembre-se que vetores só podem ter elementos da mesma classe).
Para alterar a classe de objeto de entrada, precisamos especificar o
argumento `what` de `scan()`. Por exemplo, para entrar com um vetor de
caracteres, fazemos

<div class="sourceCode">

``` {.sourceCode .r}
x <- scan(what = "character")

1: a
2: b
3: c
4:
Read 3 items
```

</div>

<div class="sourceCode">

``` {.sourceCode .r}
x
[1] "a" "b" "c"
```

</div>

Outras classe possíveis para o argumento `what` são: `logical`,
`integer`, `numeric`, `complex`, `character`, `raw` e `list`.

</div>

</div>

<div id="ch005.xhtml#exercícios-9" class="section level3 unnumbered">

### Exercícios

1.  Usando a função `scan()` crie objetos para armazenar os seguintes
    valores:
    a.  19, 13, 19, 23, 18, 20, 25, 14, 20, 18, 22, 18, 23, 14, 19
    b.  `joaquina`, `armação`, `praia brava`, `praia mole`,
        `morro das pedras`
    c.  `TRUE`, `TRUE`, `FALSE`, `FALSE`, `TRUE`

<div id="ch005.xhtml#usando-a-função-readlines" class="section level4">

#### [4.1.2.2]{.header-section-number} Usando a função `readLines()`

Esta função é particularmente útil para ler entradas na forma de texto
(*strings*). Por exemplo, para ler uma linha a ser digitada na tela do
R, siga o comando abaixo e digite o texto indicado. Ao terminar
pressione a tecla <kbd>Enter</kbd> e o texto será armazenado no objeto
texto.

<div class="sourceCode">

``` {.sourceCode .r}
texto <- readLines(n = 1)
```

</div>

<div class="sourceCode">

``` {.sourceCode .r}
Estou digitando no console
```

</div>

<div class="sourceCode">

``` {.sourceCode .r}
texto
[1] "Estou digitando no console"
```

</div>

Um possível uso é dentro que funções que solicitem que o usuário
responda e/ou entre com informações na medida que são solicitadas.
Experimente definir e rodar a função a seguir.

<div class="sourceCode">

``` {.sourceCode .r}
fn.ex <- function() {
    cat("Digite o nome do time de futebol de sua preferência (em letras minúsculas)\n")
    time <- readLines(n = 1)
    if (time == "atletico-pr")
        cat("BOA ESCOLHA!!!\n")
    else cat("Ihh, tá mal de escolha...\n")
    return(invisible())
}
```

</div>

<div class="sourceCode">

``` {.sourceCode .r}
fn.ex()
```

</div>

Nesse exemplo, `readLines()` foi utilizada para efetuar a leitura via
teclado, mas a função permite ainda entrada de dados por conexões com
outros dispositivos de *input*. Por exemplo, pode ser utilizada para ler
texto de um arquivo. Consulte a documentação da função para maiores
detalhes e exemplos.

<!-- #### Usando `textConnection()` -->
<!-- Esta função generaliza a anterior permitindo que se entre com mais de um -->
<!-- campo por linha, gravando o resultado em um data frame. Por exemplo, -->
<!-- ```{r, eval=FALSE} -->
<!-- teste <- textConnection("trat resposta  --> <!--    a 10  -->
<!--    a 12  --> <!--    b 15  --> <!--    b 20  --> <!--    c 12  -->
<!--    c 5  --> <!--    d 8  --> <!--    d 10") --> <!-- ``` -->
<!-- ```{r, eval=FALSE} -->
<!-- # capture R output: use part of example from help(lm) -->
<!-- zz <- textConnection(object = "foo", open = "w") -->
<!-- ctl <- c(4.17, 5.58, 5.18, 6.11, 4.5, 4.61, 5.17, 4.53, 5.33, 5.14) -->
<!-- trt <- c(4.81, 4.17, 4.41, 3.59, 5.87, 3.83, 6.03, 4.89, 4.32, 4.69) -->
<!-- group <- gl(2, 10, 20, labels = c("Ctl", "Trt")) -->
<!-- weight <- c(ctl, trt) --> <!-- sink(zz) -->
<!-- anova(lm.D9 <- lm(weight ~ group)) -->
<!-- cat("\nSummary of Residuals:\n\n") -->
<!-- summary(resid(lm.D9)) --> <!-- sink() --> <!-- close(zz) -->
<!-- cat(foo, sep = "\n") --> <!-- ``` -->

</div>

</div>

<div id="ch005.xhtml#entrada-de-dados-em-arquivos-texto"
class="section level3">

### [4.1.3]{.header-section-number} Entrada de dados em arquivos texto

Se os dados já estão disponíveis em formato eletrônico, isto é, já foram
digitados em outro programa, você pode importar os dados para o R sem a
necessidade de digitá-los novamente.

A forma mais fácil de fazer isto é usar dados em formato texto (arquivo
do tipo ASCII). Por exemplo, se seus dados estão disponíveis em uma
planilha eletrônica como LibreOffice Calc, MS Excel ou similar, você
pode escolher a opção <kbd>Salvar como...</kbd> e gravar os dados em um
arquivo em formato texto. Os dois principais formatos de texto são:

-   `txt`: arquivo de texto puro, onde as colunas são separadas
    geralmente por uma tabulação (<kbd>Tab</kbd>) ou espaço
    (<kbd>Spc</kbd>)
-   `csv`: arquivo de texto, onde as colunas são geralmente separadas
    por vírgula (*comma separated value*), ou ponto-e-vírgula.

No R usa-se `scan()` mencionada anteriormente, ou então a função mais
flexível `read.table()` para ler os dados de um arquivo texto e
armazenar no formato de um data frame.

Antes de importar para o R:

-   Se houverem valores perdidos, preencha com `NA`
-   A matriz de dados deve formar um bloco só. Se houverem colunas de
    diferentes comprimentos, preencha com `NA`
-   Salve o arquivo como "valores separados por vírgula" (`.csv`), mas
    atenção:
    -   Se o separador de decimal for `,`, o separador de campos será
        `;` automaticamente (o que é mais comum nos sistemas em
        português).

<div id="ch005.xhtml#a-função-read.table" class="section level4">

#### [4.1.3.1]{.header-section-number} A função `read.table()`

O método mais comum de importação de dados para o R, é utilizando a
função `read.table()`. Como exemplo, baixe o arquivo `crabs.csv`
disponível [aqui](http://leg.ufpr.br/~fernandomayer/data/crabs.csv), e
salve em um diretório chamado `dados` no seu diretório de trabalho.

Para importar um arquivo `.csv` faça:

<div class="sourceCode">

``` {.sourceCode .r}
dados <- read.table("dados/crabs.csv", header = TRUE,
                    sep = ";", dec = ",")
```

</div>

Argumentos:

-   `"crabs.csv"`: nome do arquivo. (Considerando que o arquivo
    `crabs.csv` está dentro do diretório `dados`).
-   `header = TRUE`: significa que a primeira linha do arquivo deve ser
    interpretada como os nomes das colunas.
-   `sep = ";"`: o separador de colunas (também pode ser `","`, `"\t"`
    para tabulação e `""` para espaços).
-   `dec = ","`: o separador de decimais (também pode ser `"."`).

As funções `read.csv()` e `read.csv2()` são chamadas de *wrappers*
(envelopes) que tornam o uso da função `read.table()` um pouco mais
direta, alterando alguns argumentos. Por exemplo, o comando acima
poderia ser substituído por

<div class="sourceCode">

``` {.sourceCode .r}
dados <- read.csv2("dados/crabs.csv")
```

</div>

O objeto criado com as funções `read.*()` sempre serão da classe
`data.frame`, e quando houverem colunas com caracteres, estas colunas
sempre serão da classe `factor`. Você pode alterar esse padrão usando o
argumento `stringAsFactors = FALSE`

<div class="sourceCode">

``` {.sourceCode .r}
dados2 <- read.csv2("dados/crabs.csv", stringsAsFactors = FALSE)
```

</div>

Para conferir a estrutura dos dados importados, usamos a função `str()`
que serve para demonstrar a estrutura de um objeto, como o nome das
colunas e suas classes:

<div class="sourceCode">

``` {.sourceCode .r}
str(dados)
'data.frame':   156 obs. of  7 variables:
 $ especie: Factor w/ 2 levels "azul","laranja": 1 1 1 1 1 1 1 1 1 1 ...
 $ sexo   : Factor w/ 2 levels "F","M": 2 2 2 2 2 2 2 2 2 2 ...
 $ FL     : num  8.1 8.8 9.2 9.6 10.8 11.6 11.8 12.3 12.6 12.8 ...
 $ RW     : num  6.7 7.7 7.8 7.9 9 9.1 10.5 11 10 10.9 ...
 $ CL     : num  16.1 18.1 19 20.1 23 24.5 25.2 26.8 27.7 27.4 ...
 $ CW     : num  19 20.8 22.4 23.1 26.5 28.4 29.3 31.5 31.7 31.5 ...
 $ BD     : num  7 7.4 7.7 8.2 9.8 10.4 10.3 11.4 11.4 11 ...
str(dados2)
'data.frame':   156 obs. of  7 variables:
 $ especie: chr  "azul" "azul" "azul" "azul" ...
 $ sexo   : chr  "M" "M" "M" "M" ...
 $ FL     : num  8.1 8.8 9.2 9.6 10.8 11.6 11.8 12.3 12.6 12.8 ...
 $ RW     : num  6.7 7.7 7.8 7.9 9 9.1 10.5 11 10 10.9 ...
 $ CL     : num  16.1 18.1 19 20.1 23 24.5 25.2 26.8 27.7 27.4 ...
 $ CW     : num  19 20.8 22.4 23.1 26.5 28.4 29.3 31.5 31.7 31.5 ...
 $ BD     : num  7 7.4 7.7 8.2 9.8 10.4 10.3 11.4 11.4 11 ...
```

</div>

Podemos também visualizar algumas linhas iniciais e finais do objeto
importado através de duas funções auxiliares:

<div class="sourceCode">

``` {.sourceCode .r}
head(dados)
  especie sexo   FL  RW   CL   CW   BD
1    azul    M  8.1 6.7 16.1 19.0  7.0
2    azul    M  8.8 7.7 18.1 20.8  7.4
3    azul    M  9.2 7.8 19.0 22.4  7.7
4    azul    M  9.6 7.9 20.1 23.1  8.2
5    azul    M 10.8 9.0 23.0 26.5  9.8
6    azul    M 11.6 9.1 24.5 28.4 10.4
tail(dados)
    especie sexo   FL   RW   CL   CW   BD
151 laranja    F 21.3 18.4 43.8 48.4 20.0
152 laranja    F 21.4 18.0 41.2 46.2 18.7
153 laranja    F 21.7 17.1 41.7 47.2 19.6
154 laranja    F 21.9 17.2 42.6 47.4 19.5
155 laranja    F 22.5 17.2 43.0 48.7 19.8
156 laranja    F 23.1 20.2 46.2 52.5 21.1
```

</div>

As funções permitem ainda ler dados diretamente disponíveis na *web*.
Por exemplo, os dados do exemplo poderiam ser lidos diretamente com o
comando a seguir, sem a necessidade de copiar primeiro os dados para
algum local no computador do usuário:

<div class="sourceCode">

``` {.sourceCode .r}
dados <- read.csv2("http://www.leg.ufpr.br/~fernandomayer/data/crabs.csv")
```

</div>

Para maiores informações consulte a documentação desta função com
`?read.table()`. Embora `read.table()` seja provavelmente a função mais
utilizada existem outras que podem ser úteis em determinadas situações:

-   `read.fwf()` é conveniente para ler *fixed width formats*.
-   `read.fortran()` é semelhante à anterior porém usando o estilo
    Fortran de especificação das colunas.
-   `read.csv()`, `read.csv2()`, `read.delim()` e `read.delim2()`: estas
    funções são praticamente iguais a `read.table()` porém com
    diferentes opções padrão. Em geral (mas não sempre) dados em formato
    `csv` usado no Brasil são lidos diretamente com `read.csv2()`.

</div>

</div>

<div id="ch005.xhtml#exercícios-10" class="section level3 unnumbered">

### Exercícios

1.  Baixe os arquivos a seguir e coloque os arquivos em um local
    apropriado (de preferência no mesmo diretório de trabalho que voce
    definiu no início da sessão), faça a importação usando a função
    `read.table()`, e confira a estrutura dos dados com `str()`.
    a.  [prb0519.dat](http://leg.ufpr.br/~fernandomayer/data/BHH2/prb0519.dat)
    b.  [tab0303.dat](http://leg.ufpr.br/~fernandomayer/data/BHH2/tab0303.dat)
    c.  [tab1208.dat](http://leg.ufpr.br/~fernandomayer/data/BHH2/tab1208.dat)
    d.  [ReadMe.txt](http://leg.ufpr.br/~fernandomayer/data/BHH2/ReadMe.txt)
    e.  [montgomery\_6-26.csv](http://leg.ufpr.br/~fernandomayer/data/montgomery_6-26.csv)
    f.  [montgomery\_14-12.txt](http://leg.ufpr.br/~fernandomayer/data/montgomery_14-12.txt)
    g.  [montgomery\_ex6-2.csv](http://leg.ufpr.br/~fernandomayer/data/montgomery_ex6-2.csv)
    h.  [ipea\_habitacao.csv](http://www.leg.ufpr.br/~fernandomayer/data/ipea_habitacao.csv)
    i.  [stratford.csv](http://www.leg.ufpr.br/~fernandomayer/data/stratford.csv)
2.  Faça a leitura dos dados do exercício anterior, mas agora utilize o
    endereço *web* dos arquivos.

</div>

<div id="ch005.xhtml#entrada-de-dados-através-da-área-de-transferência"
class="section level3">

### [4.1.4]{.header-section-number} Entrada de dados através da área de transferência

Um mecanismos comum para copiar dados de um programa para o outro é
usando a **área de transferência** (ou *clipboard*). Tipicamente isto é
feito com o mecanismo de copia-e-cola, ou seja-se, marca-se os dados
desejados em algum aplicativo (editor, planilha, página web, etc),
usa-se o mecanismo de COPIAR (opção no menu do programa que muitas vezes
corresponde o teclar <kbd>Ctrl</kbd> + <kbd>c</kbd>), o que transfere os
dados para a área de transferência. Funções como `scan()`,
`read.table()` e outras podem ser usadas para ler os dados diretamente
da área de transferência passando-se a opção `"clipboard"` ao primeiro
argumento. Por exemplo, os seguintes dados:

    ID  Grupo  Gasto  Ano
    23      A  25,4   11
    12      B  12,3   09
    23      A  19,8   07

podem ser marcados e copiados para área de transferência e lidos
diretamente com

<div class="sourceCode">

``` {.sourceCode .r}
dados.clip <- read.table("clipboard", header = TRUE, dec = ",")
```

</div>

<div class="sourceCode">

``` {.sourceCode .r}
str(dados.clip)
'data.frame':   3 obs. of  4 variables:
 $ ID   : int  23 12 23
 $ Grupo: Factor w/ 2 levels "A","B": 1 2 1
 $ Gasto: num  25.4 12.3 19.8
 $ Ano  : int  11 9 7
```

</div>

</div>

<div id="ch005.xhtml#importando-dados-diretamente-de-planilhas"
class="section level3">

### [4.1.5]{.header-section-number} Importando dados diretamente de planilhas

Existem alguns pacotes disponíveis que podem ler dados diretamente de
planilhas do MS Excel. No entanto, estes pacotes geralmente possuem
particularidades quanto ao sistema operacional e demais dependências
para funcionar corretamente.

Um destes pacotes, é o **gdata**, que funciona em diversos sistemas
operacionais mas depende da linguagem Perl estar instalada. Por exemplo,
para ler o conjuto de dados `crabs` armazenado em uma planilha do Excel
(disponível [aqui](http://leg.ufpr.br/~fernandomayer/data/crabs.xls)),
podemos usar

<div class="sourceCode">

``` {.sourceCode .r}
## Carrega o pacote
library(gdata)
## Leitura diretamente do Excel
dados.xls <- read.xls("dados/crabs.xls", sheet = "Plan1",
                      header = TRUE, dec = ",")
## Estrutura
str(dados.xls)
'data.frame':   156 obs. of  7 variables:
 $ especie: Factor w/ 2 levels "azul","laranja": 1 1 1 1 1 1 1 1 1 1 ...
 $ sexo   : Factor w/ 2 levels "F","M": 2 2 2 2 2 2 2 2 2 2 ...
 $ FL     : num  8.1 8.8 9.2 9.6 10.8 11.6 11.8 12.3 12.6 12.8 ...
 $ RW     : num  6.7 7.7 7.8 7.9 9 9.1 10.5 11 10 10.9 ...
 $ CL     : num  16.1 18.1 19 20.1 23 24.5 25.2 26.8 27.7 27.4 ...
 $ CW     : num  19 20.8 22.4 23.1 26.5 28.4 29.3 31.5 31.7 31.5 ...
 $ BD     : num  7 7.4 7.7 8.2 9.8 10.4 10.3 11.4 11.4 11 ...
```

</div>

Outros pacotes que possuem funções similares são: **openxlsx**,
**xlsx**, e **XLConnect**.

Estruturas de dados mais complexas são tipicamente armazenadas nos
chamados DBMS (*database management system*) ou RDBMS (*relational
database management system*). Alguns exemplos são Oracle, Microsoft SQL
server, MySQL, PostgreSQL, Microsoft Access, dentre outros. O R possui
ferramentas implementadas em pacotes para acesso a estes sistemas
gerenciadores.

Para mais detalhes consulte o manual [R Data
Import/Export](http://cran-r.c3sl.ufpr.br/doc/manuals/r-release/R-data.html)
e a documentação dos pacotes que implementam tal funcionalidade. Alguns
destes pacotes disponíveis são: **RODBC**, **DBI**, **RMySQL**,
**RPostgreSQL**, **ROracle**, **RNetCDF**, **RSQLite**, dentre outros.

</div>

<div id="ch005.xhtml#carregando-dados-já-disponíveis-no-r"
class="section level3">

### [4.1.6]{.header-section-number} Carregando dados já disponíveis no R

O R já possui alguns conjuntos de dados que estão disponíveis logo após
a instalação. Estes dados são também objetos que precisam ser carregados
para ficarem disponíveis para o usuário. Normalmente, estes conjuntos de
dados são para uso de exemplo de funções.

Para carregar conjuntos de dados que são disponibilizados com o R, use o
comando `data()`. Por exemplo, abaixo mostramos como carregar o conjunto
`mtcars` que está no pacote **datasets**.

<div class="sourceCode">

``` {.sourceCode .r}
## Objetos criados até o momento nesta seção
ls()
[1] "dados"      "dados.clip" "dados.xls"  "dados2"     "fn.ex"     
[6] "texto"      "x"          "y"         
## Carrega a base de dados mtcars
data(mtcars)
## Note como agora o objeto mtcars fica disponível na sua área de
## trabalho
ls()
[1] "dados"      "dados.clip" "dados.xls"  "dados2"     "fn.ex"     
[6] "mtcars"     "texto"      "x"          "y"         
## Estrutura e visualização do objeto
str(mtcars)
'data.frame':   32 obs. of  11 variables:
 $ mpg : num  21 21 22.8 21.4 18.7 18.1 14.3 24.4 22.8 19.2 ...
 $ cyl : num  6 6 4 6 8 6 8 4 4 6 ...
 $ disp: num  160 160 108 258 360 ...
 $ hp  : num  110 110 93 110 175 105 245 62 95 123 ...
 $ drat: num  3.9 3.9 3.85 3.08 3.15 2.76 3.21 3.69 3.92 3.92 ...
 $ wt  : num  2.62 2.88 2.32 3.21 3.44 ...
 $ qsec: num  16.5 17 18.6 19.4 17 ...
 $ vs  : num  0 0 1 1 0 1 0 1 1 1 ...
 $ am  : num  1 1 1 0 0 0 0 0 0 0 ...
 $ gear: num  4 4 4 3 3 3 3 4 4 4 ...
 $ carb: num  4 4 1 1 2 1 4 2 2 4 ...
head(mtcars)
                   mpg cyl disp  hp drat    wt  qsec vs am gear carb
Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1
```

</div>

As bases de dados também possuem páginas de documentação para explicar o
que são os dados e as colunas correspondentes. Para ver o que são os
dados do `mtcars` por exemplo, veja `?mtcars`.

O conjunto `mtcars` é disponibilizado prontamente pois faz parte do
pacote **datasets**, que por padrão é sempre carregado na inicialização
do R. No entanto, existem outros conjuntos de dados, disponibilizados
por outros pacotes, que precisam ser carregados para que os dados possam
ser disponibilizados. Por exemplo, os dados do objeto `topo` são do
pacote **MASS**. Se tentarmos fazer

<div class="sourceCode">

``` {.sourceCode .r}
data(topo)
Warning in data(topo): data set 'topo' not found
```

</div>

Portanto, precisamos primeiro carregar o pacote **MASS** com

<div class="sourceCode">

``` {.sourceCode .r}
library(MASS)
```

</div>

e agora podemos carregar o objeto `topo` com

<div class="sourceCode">

``` {.sourceCode .r}
data(topo)
## O objeto fica disponível na sua área de trabalho
ls()
 [1] "dados"      "dados.clip" "dados.xls"  "dados2"     "fn.ex"     
 [6] "mtcars"     "texto"      "topo"       "x"          "y"         
## Confere a estrutura
str(topo)
'data.frame':   52 obs. of  3 variables:
 $ x: num  0.3 1.4 2.4 3.6 5.7 1.6 2.9 3.4 3.4 4.8 ...
 $ y: num  6.1 6.2 6.1 6.2 6.2 5.2 5.1 5.3 5.7 5.6 ...
 $ z: int  870 793 755 690 800 800 730 728 710 780 ...
```

</div>

A função `data()` pode ainda ser usada para listar os conjutos de dados
disponíveis,

<div class="sourceCode">

``` {.sourceCode .r}
data()
```

</div>

e também pode ser útil para listar os conjuntos de dados disponíveis
para um pacote específico, por exemplo

<div class="sourceCode">

``` {.sourceCode .r}
data(package = "nlme")
```

</div>

</div>

<div id="ch005.xhtml#importando-dados-de-outros-programas"
class="section level3">

### [4.1.7]{.header-section-number} Importando dados de outros programas

É possível ler dados diretamente de outros formatos que não seja texto
(ASCII). Isto em geral é mais eficiente e requer menos memória do que
converter para formato texto. Há funções para importar dados diretamente
de EpiInfo, Minitab, S-PLUS, SAS, SPSS, Stata, Systat e Octave. Além
disto é comum surgir a necessidade de importar dados de planilhas
eletrônicas. Muitas funções que permitem a importação de dados de outros
programas são implementadas no pacote **foreign**.

A seguir listamos algumas (não todas!) destas funções:

-   `read.dbf()` para arquivos DBASE.
-   `read.epiinfo()` para arquivos .REC do Epi-Info.
-   `read.mtp()` para arquivos "Minitab Portable Worksheet".
-   `read.S()` para arquivos do S-PLUS, e `restore.data()` para "dumps"
    do S-PLUS.
-   `read.spss()` para dados do SPSS.
-   `read.systat()` para dados do SYSTAT.
-   `read.dta()` para dados do STATA.
-   `read.octave()` para dados do OCTAVE (um clone do MATLAB).
-   Para dados do SAS há ao menos duas alternativas:
    -   O pacote **foreign** disponibiliza `read.xport()` para ler do
        formato TRANSPORT do SAS e `read.ssd()` pode escrever dados
        permanentes do SAS (`.ssd` ou `.sas7bdat`) no formato TRANSPORT,
        se o SAS estiver disponível no seu sistema e depois usa
        internamente `read.xport()` para ler os dados no R.
    -   O pacote **Hmisc** disponibiliza `sas.get()` que também requer o
        SAS no sistema.

Para mais detalhes consulte a documentação de cada função e/ou o manual
[R Data
Import/Export](http://cran-r.c3sl.ufpr.br/doc/manuals/r-release/R-data.html).

</div>

</div>

<div id="ch005.xhtml#saída-de-dados-do-r" class="section level2">

[4.2]{.header-section-number} Saída de dados do R
-------------------------------------------------

<div id="ch005.xhtml#usando-a-função-write.table"
class="section level3">

### [4.2.1]{.header-section-number} Usando a função `write.table()`

Para exportar objetos do R, usamos a função `write.table()`, que possui
argumentos parecidos com aqueles da função `read.table()`.

A função `write.table()` é capaz de criar um arquivo de texto no formato
`txt` ou `csv`, com as especificações definidas pelos argumentos.

Para ilustrar o uso desta função, considere o conjunto de dados `iris`

<div class="sourceCode">

``` {.sourceCode .r}
data(iris)
str(iris)
'data.frame':   150 obs. of  5 variables:
 $ Sepal.Length: num  5.1 4.9 4.7 4.6 5 5.4 4.6 5 4.4 4.9 ...
 $ Sepal.Width : num  3.5 3 3.2 3.1 3.6 3.9 3.4 3.4 2.9 3.1 ...
 $ Petal.Length: num  1.4 1.4 1.3 1.5 1.4 1.7 1.4 1.5 1.4 1.5 ...
 $ Petal.Width : num  0.2 0.2 0.2 0.2 0.2 0.4 0.3 0.2 0.2 0.1 ...
 $ Species     : Factor w/ 3 levels "setosa","versicolor",..: 1 1 1 1 1 1 1 1 1 1 ...
```

</div>

Podemos exportar esse data frame com

<div class="sourceCode">

``` {.sourceCode .r}
write.table(iris, file = "dados/iris.csv")
```

</div>

Por padrão, o arquivo resultante tem colunas separadas por espaço, o
separador de decimal é ponto, e os nomes das linhas são também incluídos
(o que geralmente é desnecessário). Para alterar essa configuração
podemos fazer

<div class="sourceCode">

``` {.sourceCode .r}
write.table(iris, file = "dados/iris.csv", row.names = FALSE,
            sep = ";", dec = ",")
```

</div>

Os argumentos são

-   `iris`: o nome do objeto a ser exportado (matriz ou data frame).
-   `"iris.csv"`: nome do arquivo a ser gerado. (Considerando que o
    arquivo `iris.csv` será criado dentro do diretório `dados`).
-   `row.names = FALSE`: para eliminar o nome das linhas do objeto
    (geralmente desnecessário), como retornado por `row.names()`.
-   `sep = ";"`: o separador de colunas (também pode ser `","`, `"\t"`
    para tabulação e `""` para espaços).
-   `dec = ","`: o separador de decimais (também pode ser `"."`).

Note que o objeto a ser exportado (nesse caso `iris`) deve ser em
formato tabular, ou seja, uma matriz ou data frame. Outras classes de
objetos podem ser exportadas, mas haverá uma coerção para data frame, o
que pode fazer com que o resultado final não seja o esperado.

Assim como `read.table()` possui as funções `read.csv()` e
`read.csv2()`, a função `write.table()` possui as funções
`write.table()` e `write.table2()` como *wrappers*. O comando acima
também poderia ser executado como

<div class="sourceCode">

``` {.sourceCode .r}
write.csv2(iris, file = "dados/iris.csv", row.names = FALSE)
```

</div>

Note que `row.names = FALSE` ainda é necessário para eliminar os nomes
das linhas.

O pacote **foreign** também possui funções para exportar para uma
variedade de formatos. Veja a documentação em
`help(package = "foreign")`. Os pacotes para ler dados diretamente de
arquivos do MS Excel mencionados acima também possuem funções para
exportar diretamente para esse formato.

</div>

<div id="ch005.xhtml#exercícios-11" class="section level3 unnumbered">

### Exercícios

1.  Considere a tabela abaixo com o resultado de uma pesquisa que
    avaliou o número de fumates e não fumantes por sexo.
    <!-- Gerado em http://www.tablesgenerator.com/html_tables -->
    <style type="text/css">
    .tg  {border-collapse:collapse;border-spacing:0;}
    .tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
    .tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
    .tg .tg-s6z2{text-align:center}
    .tg .tg-baqh{text-align:center;vertical-align:top}
    .tg .tg-e3zv{font-weight:bold}
    .tg .tg-hgcj{font-weight:bold;text-align:center}
    .tg .tg-yw4l{vertical-align:top}
    .tg .tg-9hbo{font-weight:bold;vertical-align:top}
    </style>
    <table class="tg">
    <tr>
    <th class="tg-031e">
    </th>
    <th class="tg-hgcj" colspan="2">
    Sexo
    </th>
    </tr>
    <tr>
    <td class="tg-e3zv">
    Condição
    </td>
    <td class="tg-hgcj">
    Masculino
    </td>
    <td class="tg-hgcj">
    Feminino
    </td>
    </tr>
    <tr>
    <td class="tg-e3zv">
    Fumante
    </td>
    <td class="tg-s6z2">
    49
    </td>
    <td class="tg-s6z2">
    54
    </td>
    </tr>
    <tr>
    <td class="tg-031e">
    </td>
    <td class="tg-s6z2">
    64
    </td>
    <td class="tg-s6z2">
    61
    </td>
    </tr>
    <tr>
    <td class="tg-yw4l">
    </td>
    <td class="tg-baqh">
    37
    </td>
    <td class="tg-baqh">
    79
    </td>
    </tr>
    <tr>
    <td class="tg-yw4l">
    </td>
    <td class="tg-baqh">
    52
    </td>
    <td class="tg-baqh">
    64
    </td>
    </tr>
    <tr>
    <td class="tg-yw4l">
    </td>
    <td class="tg-baqh">
    68
    </td>
    <td class="tg-baqh">
    29
    </td>
    </tr>
    <tr>
    <td class="tg-9hbo">
    Não fumante
    </td>
    <td class="tg-baqh">
    27
    </td>
    <td class="tg-baqh">
    40
    </td>
    </tr>
    <tr>
    <td class="tg-yw4l">
    </td>
    <td class="tg-baqh">
    58
    </td>
    <td class="tg-baqh">
    39
    </td>
    </tr>
    <tr>
    <td class="tg-yw4l">
    </td>
    <td class="tg-baqh">
    52
    </td>
    <td class="tg-baqh">
    44
    </td>
    </tr>
    <tr>
    <td class="tg-yw4l">
    </td>
    <td class="tg-baqh">
    41
    </td>
    <td class="tg-baqh">
    34
    </td>
    </tr>
    <tr>
    <td class="tg-yw4l">
    </td>
    <td class="tg-baqh">
    30
    </td>
    <td class="tg-baqh">
    44
    </td>
    </tr>
    </table>
    <!-- |             |    Sexo   |          | -->
    <!-- |-------------|:---------:|:--------:| -->
    <!-- | Condição    | Masculino | Feminino | -->
    <!-- | Fumante     |     49    |    54    | -->
    <!-- |             |     64    |    61    | -->
    <!-- |             |     37    |    79    | -->
    <!-- |             |     52    |    64    | -->
    <!-- |             |     68    |    29    | -->
    <!-- | Não fumante |     27    |    40    | -->
    <!-- |             |     58    |    39    | -->
    <!-- |             |     52    |    44    | -->
    <!-- |             |     41    |    34    | -->
    <!-- |             |     30    |    44    | -->
2.  Digite estes dados em uma planilha eletrônica em um formato
    apropriado para um data frame do R, e salve em um arquivo `csv`.
3.  Importe esse arquivo para o R com `read.table()`.
4.  Crie uma nova coluna no objeto que contém estes dados, sendo a
    coluna com o número de pessoas multiplicada por 2.
5.  Exporte esse novo objeto usando a função `write.table()`.
6.  Tente criar esse mesmo conjunto de dados usando comandos do R (ex.:
    `c()`, `rep()`, `data.frame()`, etc.)

</div>

<div
id="ch005.xhtml#usando-os-formatos-textual-e-binário-para-lerescrever-dados"
class="section level3">

### [4.2.2]{.header-section-number} Usando os formatos textual e binário para ler/escrever dados

As formas mais comuns de entrada de dados no R são através da entrada
direta pelo teclado (e.g. `c()` ou `scan()`), ou pela importação de
arquivos de texto (e.g. `read.table()`). No etanto, ainda existem mais
dois formatos para armazenar dados para leitura no R: o textual e o
binário.

O **formato binário** é aquele armazenado em um arquivo binário, ou
seja, um arquivo que contém apenas 0s e 1s, e possui um formato
específico que só pode ser lido por determinado *software* ou função. É
o oposto de um arquivo de texto, por exemplo, que podemos abrir e editar
em qualquer prorama que edite texto puro.

O **formato textual** é o intermediário entre o texto puro e o binário.
Os dados em formato textual são apresentados como texto puro, mas contém
informações adicionais, chamados de **metadados**, que preservam toda a
estrutura dos dados, como as classes de cada coluna de um data frame.

<div id="ch005.xhtml#formato-textual" class="section level4">

#### [4.2.2.1]{.header-section-number} Formato textual

O formato textual é muito útil para compartilhar conjuntos de dados que
não são muito grandes, e onde a formatação (leia-se: classes de objetos)
precisa ser mantida.

Para criar um conjunto de dados no formato textual, usamos a função
`dput()`. Vamos criar um data frame de exemplo e ver o resultado da
chamada dessa função:

<div class="sourceCode">

``` {.sourceCode .r}
da <- data.frame(A = c(1, 2), B = c("a", "b"))
dput(da)
structure(list(A = c(1, 2), B = structure(1:2, .Label = c("a", 
"b"), class = "factor")), class = "data.frame", row.names = c(NA, 
-2L))
```

</div>

Note que o resultado de `dput()` é no formato do R, e preserva metadados
como as classes do objeto e de cada coluna, e os nomes das linhas e
colunas.

Outas classes de objetos são facilmente preservadas quando armazenadas
com o resultado de `dput()`. Por exemplo, uma matriz:

<div class="sourceCode">

``` {.sourceCode .r}
ma <- matrix(1:9, ncol = 3)
dput(ma)
structure(1:9, .Dim = c(3L, 3L))
```

</div>

E uma lista:

<div class="sourceCode">

``` {.sourceCode .r}
la <- list(da, ma)
dput(la)
list(structure(list(A = c(1, 2), B = structure(1:2, .Label = c("a", 
"b"), class = "factor")), class = "data.frame", row.names = c(NA, 
-2L)), structure(1:9, .Dim = c(3L, 3L)))
```

</div>

A saída da função `dput()` pode ser copiada para um script do R, para
garantir que qualquer pessoa que venha usar o código (incluindo você no
futuro), usará os dados no formato correto (esperado). Isso é muito
importante para a **pesquisa reproduzível**!

A saída de `dput()` também pode ser salva diretamente em um arquivo de
script do R, por exemplo,

<div class="sourceCode">

``` {.sourceCode .r}
dput(da, file = "da.R")
```

</div>

irá criar o arquivo `da.R` com o resultado da função. Para importar os
dados salvos dessa forma, usamos a função `dget()`,

<div class="sourceCode">

``` {.sourceCode .r}
da2 <- dget(file = "da.R")
da2
  A B
1 1 a
2 2 b
```

</div>

Múltiplos objetos podem ser armazenados em formato textual usando a
função `dump()`.

<div class="sourceCode">

``` {.sourceCode .r}
dump(c("da", "ma", "la"), file = "dados.R")
```

</div>

Note que os objetos são passados como um vetor de caracteres, e um
arquivo chamado `dados.R` é criado com todos os objetos no formato
textual. Para importar estes objetos para uma sessão do R, usamos a
função `source()`,

<div class="sourceCode">

``` {.sourceCode .r}
source("dados.R")
```

</div>

que já cria os objetos na sua área de trabalho com os mesmos nomes e
atributos como foram armazenados.

</div>

<div id="ch005.xhtml#formato-binário" class="section level4">

#### [4.2.2.2]{.header-section-number} Formato binário

Armazenar dados em formato binário é vantajoso quando não há uma forma
"fácil" de armazenar os dados em formato de texto puro ou textual. Além
disso, algumas vezes o formato binário possui maior eficiência em termos
de velocidade de leitura/escrita, dependendo dos dados. Outra vantagem é
que valores numéricos geralmente perdem precisão quando armazenados em
texto ou textual, enquanto que o formato binário preserva toda a
precisão (embora essa perda de precisão seja desprezível na maioria dos
casos).

Para salvar um objeto contendo dados no R, usamos a função `save()`. Por
exemplo, para armazenar o objeto `da` criado acima, fazemos

<div class="sourceCode">

``` {.sourceCode .r}
save(da, file = "dados.rda")
```

</div>

Esse comando irá criar o arquivo (binário) `dados.rda`. Note que a
extensão `.rda` é comumente utilizada para dados binários do R, mas não
é única.

Paa salvar mais de um objeto no mesmo arquivo, basta passar os nomes na
mesma função

<div class="sourceCode">

``` {.sourceCode .r}
save(da, ma, file = "dados.rda")
```

</div>

A função `save.image()` pode ser utilizada se a intenção é salvar
**todos** os objetos criados na sua área de trabalho (isso inclui
qualquer objeto, não só os conjuntos de dados). Nesse caso, podemos
fazer

<div class="sourceCode">

``` {.sourceCode .r}
save.image(file = "workspace.RData")
```

</div>

Note que quando foi utilizada a função `save()`, a extensão do arquivo
foi `rda`, e com `save.image()` foi `RData`. Isso é uma convenção comum
de arquivos binários do R, mas não é obrigatório. Qualquer uma das
extensões funciona em ambas as funções.

Para carregar os conjuntos de dados (ou de forma mais geral, os objetos)
armazenados em formato binário, usamos a função `load()`

<div class="sourceCode">

``` {.sourceCode .r}
load("dados.rda")
load("workspace.RData")
```

</div>

Dessa forma, os objetos já estarão disponíveis na sua área de trabalho.

</div>

</div>

</div>

<div id="ch005.xhtml#informações-sobre-diretórios-e-arquivos"
class="section level2">

[4.3]{.header-section-number} Informações sobre diretórios e arquivos
---------------------------------------------------------------------

O R possui uma variedade de funções para mostrar informações sobre
arquivos e diretórios. Alguns exemplos são:

-   `file.info()` mostra o tamanho do arquivo, data de criação, ...
-   `dir()` mostra todos os arquivos presentes em um diretório (tente
    com `recursive = TRUE`)
-   `file.exists()` retorna `TRUE` ou `FALSE` para a presença de um
    arquivo
-   `getwd()` e `setwd()` para verificar e altear o diretório de
    trabalho

Veja `?files` para uma lista copleta de funções úteis para manipular
arquivos de dentro do R.

<!-- Referencias --> <!--chapter:end:04-entrada-dados.Rmd-->

</div>

</div>

[]{#ch006.xhtml}

<div id="ch006.xhtml#programando-com-dados" class="section level1">

[5]{.header-section-number} Programando com dados
=================================================

Por quê programar?

-   Evitar repetições desnecessárias de análises ou cálculos que são
    repetidos com frequência.
-   Documentar as etapas que você realizou para chegar a um resultado.
-   Fácil recuperação e modificação de programas.

Como programar?

-   Criando programas! (Scripts, rotinas, **algoritmos**).
-   Crie uma sequência lógica de comandos que devem ser executados em
    ordem.
-   Utilize as ferramentas básicas da programação: **estruturas de
    repetição** (`for()`) e **estruturas de seleção** (`if()`).

<div id="ch006.xhtml#estrutura-de-repetição-for" class="section level2">

[5.1]{.header-section-number} Estrutura de repetição `for()`
------------------------------------------------------------

Serve para repetir um ou mais comandos diversas vezes. Para ver como
funciona, considere o seguinte exemplo:

<div class="sourceCode">

``` {.sourceCode .r}
for(i in 1:10){
    print(i)
}
[1] 1
[1] 2
[1] 3
[1] 4
[1] 5
[1] 6
[1] 7
[1] 8
[1] 9
[1] 10
```

</div>

O resultado é a chamada do comando `print()` para cada valor que o
índice `i` recebe (nesse caso `i` recebe os valores de 1 a 10).

A sintaxe será sempre nesse formato:

<div class="sourceCode">

``` {.sourceCode .r}
for(<índice> in <valores>){
    <comandos>
}
```

</div>

Veja outro exemplo em como podemos aplicar o índice:

<div class="sourceCode">

``` {.sourceCode .r}
x <- 100:200
for(j in 1:10){
    print(x[j])
}
[1] 100
[1] 101
[1] 102
[1] 103
[1] 104
[1] 105
[1] 106
[1] 107
[1] 108
[1] 109
```

</div>

Veja que o índice não precisa ser `i`, na verdade pode ser qualquer
letra ou palavra. Nesse caso, utilizamos os valores como índice para
selecionar elementos de `x` nas posições específicadas.

Um outro exemplo seria se quisessemos imprimir o quadrado de alguns
números (não necessariamente em sequência):

<div class="sourceCode">

``` {.sourceCode .r}
for(i in c(2, 9, 4, 6)){
    print(i^2)
}
[1] 4
[1] 81
[1] 16
[1] 36
```

</div>

Ou mesmo imprimir caracteres a partir de um vetor de caracteres:

<div class="sourceCode">

``` {.sourceCode .r}
for(veiculos in c("carro", "ônibus", "trem", "bicicleta")){
    print(veiculos)
}
[1] "carro"
[1] "ônibus"
[1] "trem"
[1] "bicicleta"
```

</div>

**Exemplo**: cálculo de notas de uma disciplina.

<div class="sourceCode">

``` {.sourceCode .r}
## Importa os dados
url <- "http://leg.ufpr.br/~fernandomayer/data/notas.csv"
notas <- read.table(url, header = TRUE, sep = ";", dec = ",")
## Analisa a estrutura dos dados
str(notas)
head(notas)
summary(notas)
```

</div>

Antes de seguir adiante, veja o resultado de

<div class="sourceCode">

``` {.sourceCode .r}
for(i in 1:30){
    print(notas[i, c("prova1", "prova2", "prova3")])
}
```

</div>

Para calcular as médias das 3 provas, precisamos inicialmente de um
vetor para armazenar os resultados. Esse vetor pode ser um novo objeto
ou uma nova coluna no dataframe

<div class="sourceCode">

``` {.sourceCode .r}
## Aqui vamos criar uma nova coluna no dataframe, contendo apenas o
## valor 0
notas$media <- 0 # note que aqui será usada a regra da reciclagem, ou
                 # seja, o valor zero será repetido até completar todas
                 # as linhas do dataframe
## Estrutura de repetição para calcular a média
for(i in 1:30){
    ## Aqui, cada linha i da coluna media sera substituida pelo
    ## respectivo valor da media caculada
    notas$media[i] <- sum(notas[i, c("prova1", "prova2", "prova3")])/3
}

## Confere os resultados
head(notas)
     nome prova1 prova2 prova3    media
1 Aluno_1      8      4      1 4.333333
2 Aluno_2      2      7      6 5.000000
3 Aluno_3      9      2      4 5.000000
4 Aluno_4      1     10      9 6.666667
5 Aluno_5      7      6      8 7.000000
6 Aluno_6     10      0      3 4.333333
```

</div>

Agora podemos melhorar o código, tornando-o mais **genérico**. Dessa
forma fica mais fácil fazer alterações e procurar erros. Uma forma de
melhorar o código acima é generalizando alguns passos.

<div class="sourceCode">

``` {.sourceCode .r}
## Armazenamos o número de linhas no dataframe
nlinhas <- nrow(notas)
## Identificamos as colunas de interesse no cálculo da média, e
## armazenamos em um objeto separado
provas <- c("prova1", "prova2", "prova3")
## Sabendo o número de provas, fica mais fácil dividir pelo total no
## cálculo da média
nprovas <- length(provas)
## Cria uma nova coluna apenas para comparar o cálculo com o anterior
notas$media2 <- 0
## A estrutura de repetição fica
for(i in 1:nlinhas){
    notas$media2[i] <- sum(notas[i, provas])/nprovas
}

## Confere
head(notas)
     nome prova1 prova2 prova3    media   media2
1 Aluno_1      8      4      1 4.333333 4.333333
2 Aluno_2      2      7      6 5.000000 5.000000
3 Aluno_3      9      2      4 5.000000 5.000000
4 Aluno_4      1     10      9 6.666667 6.666667
5 Aluno_5      7      6      8 7.000000 7.000000
6 Aluno_6     10      0      3 4.333333 4.333333
identical(notas$media, notas$media2)
[1] TRUE
```

</div>

Ainda podemos melhorar (leia-se: **otimizar**) o código, se utilizarmos
funções prontas do R. No caso da média isso é possível pois a função
`mean()` já existe. Em seguida veremos como fazer quando o cálculo que
estamos utilizando não está implementado em nenhuma função pronta do R.

<div class="sourceCode">

``` {.sourceCode .r}
## Cria uma nova coluna apenas para comparação
notas$media3 <- 0
## A estrutura de repetição fica
for(i in 1:nlinhas){
    notas$media3[i] <- mean(as.numeric(notas[i, provas]))
}

## Confere
head(notas)
     nome prova1 prova2 prova3    media   media2   media3
1 Aluno_1      8      4      1 4.333333 4.333333 4.333333
2 Aluno_2      2      7      6 5.000000 5.000000 5.000000
3 Aluno_3      9      2      4 5.000000 5.000000 5.000000
4 Aluno_4      1     10      9 6.666667 6.666667 6.666667
5 Aluno_5      7      6      8 7.000000 7.000000 7.000000
6 Aluno_6     10      0      3 4.333333 4.333333 4.333333

## A única diferença é que aqui precisamos transformar cada linha em um
## vetor de números com as.numeric(), pois
notas[1, provas]
  prova1 prova2 prova3
1      8      4      1
## é um data.frame:
class(notas[1, provas])
[1] "data.frame"
```

</div>

No caso acima vimos que não era necessário calcular a média através de
`soma/total` porque existe uma função pronta no R para fazer esse
cálculo. Mas, e se quisessemos, por exemplo, calcular a Coeficiente de
Variação (CV) entre as notas das três provas de cada aluno? Uma busca
por

<div class="sourceCode">

``` {.sourceCode .r}
help.search("coefficient of variation")
```

</div>

não retorna nenhuma função (dos pacotes básicos) para fazer esse
cálculo. O motivo é simples: como é uma conta simples de fazer não há
necessidade de se criar uma função extra dentro dos pacotes. No entanto,
nós podemos criar uma função que calcule o CV, e usá-la para o nosso
propósito

<div class="sourceCode">

``` {.sourceCode .r}
cv <- function(x){
    desv.pad <- sd(x)
    med <- mean(x)
    cv <- desv.pad/med
    return(cv)
}
```

</div>

<div class="alert alert-warning">

NOTA: na função criada acima o único argumento que usamos foi `x`, que
neste caso deve ser um vetor de números para o cálculo do CV. Os
argumentos colocados dentro de `function()` devem ser apropriados para o
propósito de cada função.

</div>

Antes de aplicar a função dentro de um `for()` devemos testá-la para ver
se ela está funcionando de maneira correta. Por exemplo, o CV para as
notas do primeiro aluno pode ser calculado "manualmente" por

<div class="sourceCode">

``` {.sourceCode .r}
sd(as.numeric(notas[1, provas]))/mean(as.numeric(notas[1, provas]))
[1] 0.8104349
```

</div>

E através da função, o resultado é

<div class="sourceCode">

``` {.sourceCode .r}
cv(as.numeric(notas[1, provas]))
[1] 0.8104349
```

</div>

o que mostra que a função está funcionando corretamente, e podemos
aplicá-la em todas as linhas usando a repetição

<div class="sourceCode">

``` {.sourceCode .r}
## Cria uma nova coluna para o CV
notas$CV <- 0
## A estrutura de repetição fica
for(i in 1:nlinhas){
    notas$CV[i] <- cv(as.numeric(notas[i, provas]))
}

## Confere
head(notas)
     nome prova1 prova2 prova3    media   media2   media3        CV
1 Aluno_1      8      4      1 4.333333 4.333333 4.333333 0.8104349
2 Aluno_2      2      7      6 5.000000 5.000000 5.000000 0.5291503
3 Aluno_3      9      2      4 5.000000 5.000000 5.000000 0.7211103
4 Aluno_4      1     10      9 6.666667 6.666667 6.666667 0.7399324
5 Aluno_5      7      6      8 7.000000 7.000000 7.000000 0.1428571
6 Aluno_6     10      0      3 4.333333 4.333333 4.333333 1.1842157
```

</div>

Podemos agora querer calcular as médias ponderadas para as provas. Por
exemplo:

-   Prova 1: peso 3
-   Prova 2: peso 3
-   Prova 3: peso 4

Usando a fórmula:

$$\bar{x} = \frac{1}{N}\sum\limits_{i = 1}^{n}x_{i} \cdot w_{i}$$

onde $w_{i}$ são os pesos, e $N = \sum_{i = 1}^{n}w_{i}$ é a soma dos
pesos. Como já vimos, criar uma função é uma forma mais prática (e
elegante) de executar determinada tarefa, vamos criar uma função que
calcule as médias ponderadas.

<div class="sourceCode">

``` {.sourceCode .r}
med.pond <- function(notas, pesos){
    ## Multiplica o valor de cada prova pelo seu peso
    pond <- notas * pesos
    ## Calcula o valor total dos pesos
    peso.total <- sum(pesos)
    ## Calcula a soma da ponderação
    sum.pond <- sum(pond)
    ## Finalmente calcula a média ponderada
    saida <- sum.pond/peso.total
    return(saida)
}
```

</div>

Antes de aplicar a função para o caso geral, sempre é importante testar
e conferir o resultado em um caso menor. Podemos verificar o resultado
da média ponderada para o primeiro aluno

<div class="sourceCode">

``` {.sourceCode .r}
sum(notas[1, provas] * c(3, 3, 4))/10
[1] 4
```

</div>

e testar a função para o mesmo caso

<div class="sourceCode">

``` {.sourceCode .r}
med.pond(notas = notas[1, provas], pesos = c(3, 3, 4))
[1] 4
```

</div>

Como o resultado é o mesmo podemos aplicar a função para todas as linhas
através do `for()`

<div class="sourceCode">

``` {.sourceCode .r}
## Cria uma nova coluna para a média ponderada
notas$MP <- 0
## A estrutura de repetição fica
for(i in 1:nlinhas){
    notas$MP[i] <- med.pond(notas = notas[i, provas], pesos = c(3, 3, 4))
}

## Confere
head(notas)
     nome prova1 prova2 prova3    media   media2   media3        CV  MP
1 Aluno_1      8      4      1 4.333333 4.333333 4.333333 0.8104349 4.0
2 Aluno_2      2      7      6 5.000000 5.000000 5.000000 0.5291503 5.1
3 Aluno_3      9      2      4 5.000000 5.000000 5.000000 0.7211103 4.9
4 Aluno_4      1     10      9 6.666667 6.666667 6.666667 0.7399324 6.9
5 Aluno_5      7      6      8 7.000000 7.000000 7.000000 0.1428571 7.1
6 Aluno_6     10      0      3 4.333333 4.333333 4.333333 1.1842157 4.2
```

</div>

<div class="alert alert-warning">

NOTA: uma função para calcular a média ponderada já existe implementada
no R. Veja `?weighted.mean()` e confira os resultados obtidos aqui.

</div>

Repare na construção da função acima: agora usamos dois argumentos,
`notas` e `pesos`, pois precisamos dos dois vetores para calcular a
média ponderada. Repare também que ambos argumentos não possuem um valor
padrão. Poderíamos, por exemplo, assumir valores padrão para os pesos, e
deixar para que o usuário mude apenas se achar necessário.

<div class="sourceCode">

``` {.sourceCode .r}
## Atribuindo pesos iguais para as provas como padrão
med.pond <- function(notas, pesos = rep(1, length(notas))){
    ## Multiplica o valor de cada prova pelo seu peso
    pond <- notas * pesos
    ## Calcula o valor total dos pesos
    peso.total <- sum(pesos)
    ## Calcula a soma da ponderação
    sum.pond <- sum(pond)
    ## Finalmente calcula a média ponderada
    saida <- sum.pond/peso.total
    return(saida)
}
```

</div>

Repare que neste caso, como os pesos são iguais, a chamada da função sem
alterar o argumento `pesos` gera o mesmo resultado do cálculo da média
comum.

<div class="sourceCode">

``` {.sourceCode .r}
## Cria uma nova coluna para a média ponderada para comparação
notas$MP2 <- 0
## A estrutura de repetição fica
for(i in 1:nlinhas){
    notas$MP2[i] <- med.pond(notas = notas[i, provas])
}

## Confere
head(notas)
     nome prova1 prova2 prova3    media   media2   media3        CV  MP
1 Aluno_1      8      4      1 4.333333 4.333333 4.333333 0.8104349 4.0
2 Aluno_2      2      7      6 5.000000 5.000000 5.000000 0.5291503 5.1
3 Aluno_3      9      2      4 5.000000 5.000000 5.000000 0.7211103 4.9
4 Aluno_4      1     10      9 6.666667 6.666667 6.666667 0.7399324 6.9
5 Aluno_5      7      6      8 7.000000 7.000000 7.000000 0.1428571 7.1
6 Aluno_6     10      0      3 4.333333 4.333333 4.333333 1.1842157 4.2
       MP2
1 4.333333
2 5.000000
3 5.000000
4 6.666667
5 7.000000
6 4.333333
```

</div>

<div id="ch006.xhtml#exercícios-12" class="section level3 unnumbered">

### Exercícios

1.  Escreva um loop for que percorre os números de 1 a 700 e imprime o
    cubo de cada número.
2.  Escreva um loop for que percorre os nomes das colunas do conjunto de
    dados iris e imprime cada um junto com o número de caracteres na
    coluna nomes entre parênteses. Example de output Sepal.Length (12).
    Dica: Use as seguintes funções print(), paste0() e nchar().
3.  Escreva um loop while que imprime o erro padrão de amostras da
    distribuição normal padrão (use rnorm()) e para (break) se o erro
    padrão obtido for maior que 1.
4.  Usando o comando next adapte o loop do exercício (3) para que
    números menores que 0.75 não sejam mostrados.
5.  Use um loop for para simular o lançamento de uma moeda (1 - cara,
    0 - coroa) e armazene os resultados em um vetor pré-especificado.

</div>

</div>

<div id="ch006.xhtml#estrutura-de-seleção-if" class="section level2">

[5.2]{.header-section-number} Estrutura de seleção `if()`
---------------------------------------------------------

Uma estrutura de seleção serve para executar algum comando apenas se
alguma condição (em forma de **expressão condicional**) seja satisfeita.
Geralmente é utilizada dentro de um `for()`.

No exemplo inicial poderíamos querer imprimir um resultado caso
satisfaça determinada condição. Por exemplo, se o valor de `x` for menor
ou igual a 105, então imprima um texto informando isso.

<div class="sourceCode">

``` {.sourceCode .r}
x <- 100:200
for(j in 1:10){
    if(x[j] <= 105){
        print("Menor ou igual a 105")
    }
}
[1] "Menor ou igual a 105"
[1] "Menor ou igual a 105"
[1] "Menor ou igual a 105"
[1] "Menor ou igual a 105"
[1] "Menor ou igual a 105"
[1] "Menor ou igual a 105"
```

</div>

Mas também podemos considerar o que aconteceria caso contrário. Por
exemplo, se o valor de `x`for maior do que 105, então imprima outro
texto.

<div class="sourceCode">

``` {.sourceCode .r}
x <- 100:200
for(j in 1:10){
    if(x[j] <= 105){
        print("Menor ou igual a 105")
    } else{
        print("Maior do que 105")
    }
}
[1] "Menor ou igual a 105"
[1] "Menor ou igual a 105"
[1] "Menor ou igual a 105"
[1] "Menor ou igual a 105"
[1] "Menor ou igual a 105"
[1] "Menor ou igual a 105"
[1] "Maior do que 105"
[1] "Maior do que 105"
[1] "Maior do que 105"
[1] "Maior do que 105"
```

</div>

A sintaxe será sempre no formato:

<div class="sourceCode">

``` {.sourceCode .r}
if(<condição>){
    <comandos que satisfazem a condição>
} else{
   <comandos que não satisfazem a condição>
}
```

</div>

Como vimos acima, a especificação do `else{}` não é obrigatória.

Voltando ao exemplo das notas, podemos adicionar uma coluna com a
condição do aluno: `aprovado` ou `reprovado` de acordo com a sua nota.
Para isso precisamos criar uma condição (nesse caso se a nota é maior do
que 7), e verificar se ela é verdadeira.

<div class="sourceCode">

``` {.sourceCode .r}
## Nova coluna para armazenar a situacao
notas$situacao <- NA # aqui usamos NA porque o resultado será um
                     # caracter
## Estrutura de repetição
for(i in 1:nlinhas){
    ## Estrutura de seleção (usando a média ponderada)
    if(notas$MP[i] >= 7){
        notas$situacao[i] <- "aprovado"
    } else{
        notas$situacao[i] <- "reprovado"
    }
}

## Confere
head(notas)
     nome prova1 prova2 prova3    media   media2   media3        CV  MP
1 Aluno_1      8      4      1 4.333333 4.333333 4.333333 0.8104349 4.0
2 Aluno_2      2      7      6 5.000000 5.000000 5.000000 0.5291503 5.1
3 Aluno_3      9      2      4 5.000000 5.000000 5.000000 0.7211103 4.9
4 Aluno_4      1     10      9 6.666667 6.666667 6.666667 0.7399324 6.9
5 Aluno_5      7      6      8 7.000000 7.000000 7.000000 0.1428571 7.1
6 Aluno_6     10      0      3 4.333333 4.333333 4.333333 1.1842157 4.2
       MP2  situacao
1 4.333333 reprovado
2 5.000000 reprovado
3 5.000000 reprovado
4 6.666667 reprovado
5 7.000000  aprovado
6 4.333333 reprovado
```

</div>

</div>

<div id="ch006.xhtml#o-modo-r-vetorização" class="section level2">

[5.3]{.header-section-number} O modo R: vetorização
---------------------------------------------------

As funções vetorizadas do R, além de facilitar e resumir a execução de
tarefas repetitivas, também são computacionalmente mais eficientes,
*i.e.* o tempo de execução das rotinas é menor.

Já vimos que a **regra da reciclagem** é uma forma de vetorizar cálculos
no R. Os cálculos feitos com funções vetorizadas (ou usando a regra de
reciclagem) são muito mais eficientes (e preferíveis) no R. Por exemplo,
podemos criar um vetor muito grande de números e querer calcular o
quadrado de cada número. Se pensássemos em usar uma estrutura de
repetição, o cálculo seria o seguinte:

<div class="sourceCode">

``` {.sourceCode .r}
## Vetor com uma sequência de 1 a 1.000.000
x <- 1:1000000
## Calcula o quadrado de cada número da sequência em x usando for()
y1 <- numeric(length(x)) # vetor de mesmo comprimento de x que vai
                         # receber os resultados
for(i in 1:length(x)){
    y1[i] <- x[i]^2
}
```

</div>

Mas, da forma vetorial e usando a regra da reciclagem, a mesma operação
pode ser feita apenas com

<div class="sourceCode">

``` {.sourceCode .r}
## Calcula o quadrado de cada número da sequência em x usando a regra da
## reciclagem
y2 <- x^2
## Confere os resultados
identical(y1, y2)
[1] TRUE
```

</div>

Note que os resultados são exatamente iguais, mas então porque se
prefere o formato vetorial? Primeiro porque é muito mais simples de
escrever, e segundo (e principalmente) porque a forma vetorizada é muito
mais **eficiente computacionalmente**. A eficiência computacional pode
ser medida de várias formas (alocação de memória, tempo de execução,
etc), mas apenas para comparação, vamos medir o tempo de execução destas
mesmas operações usando o `for()` e usando a regra da reciclagem.

<div class="sourceCode">

``` {.sourceCode .r}
## Tempo de execução usando for()
y1 <- numeric(length(x))
st1 <- system.time(
    for(i in 1:length(x)){
        y1[i] <- x[i]^2
    }
)
st1
   user  system elapsed 
  0.078   0.000   0.078 

## Tempo de execução usando a regra da reciclagem
st2 <- system.time(
    y2 <- x^2
)
st2
   user  system elapsed 
  0.002   0.000   0.003 
```

</div>

Olhando o resultado de `elapsed`, que é o tempo total de execução de uma
função medido por `system.time()`, notamos que usando a regra da
reciclagem, o cálculo é aproximadamente $0.078/0.003 = 26$ vezes mais
rápido. Claramente esse é só um exemplo de um cálculo muito simples. Mas
em situações mais complexas, a diferença entre o tempo de execução das
duas formas pode ser muito maior.

<div class="panel panel-primary">

<div class="panel-heading">

Uma nota de precaução

</div>

<div class="panel-body">

Existem duas formas básicas de tornar um loop `for` no R mais rápido:

1.  Faça o máximo possível fora do loop.
2.  Crie um objeto com tamanho suficiente para armazenar *todos* os
    resultados do loop **antes** de executá-lo.

Veja este exemplo:

<div class="sourceCode">

``` {.sourceCode .r}
## Vetor com uma sequência de 1 a 1.000.000
x <- 1:1000000

## Cria um objeto de armazenamento com o mesmo tamanho do resultado
st1 <- system.time({
    out <- numeric(length(x))
    for(i in 1:length(x)){
        out[i] <- x[i]^2
    }
})
st1
   user  system elapsed 
  0.080   0.000   0.079 

## Cria um objeto de tamanho "zero" e vai "crescendo" esse vetor
st2 <- system.time({
    out <- numeric(0)
    for(i in 1:length(x)){
        out[i] <- x[i]^2
    }
})
st2
   user  system elapsed 
  0.326   0.016   0.342 
```

</div>

Essa simples diferença gera um aumento de tempo de execução da segunda
forma em aproximadamente 0.342/0.079 = 4.33 vezes. Isso acontece porque,
da segunda forma, o vetor `out` precisa ter seu tamanho aumentado com um
elemento a cada iteração. Para fazer isso, o R precisa encontrar um
espaço na memória que possa armazenar o objeto maior. É necessário então
copiar o vetor de saída e apagar sua versão anterior antes de seguir
para o próximo loop. Ao final, foi necessário escrever um milhão de
vezes na memória do computador.

Já no primeiro caso, o tamanho do vetor de armazenamento nunca muda, e a
memória para esse vetor já foi alocada previamente, de uma única vez.

![](media/file7.jpg){width="90%"}

</div>

</div>

Voltando ao exemplo das notas, por exemplo, o cálculo da média simples
poderia ser feito diretamente com a função `apply()`

<div class="sourceCode">

``` {.sourceCode .r}
notas$media.apply <- apply(X = notas[, provas], MARGIN = 1, FUN = mean)
head(notas)
     nome prova1 prova2 prova3    media   media2   media3        CV  MP
1 Aluno_1      8      4      1 4.333333 4.333333 4.333333 0.8104349 4.0
2 Aluno_2      2      7      6 5.000000 5.000000 5.000000 0.5291503 5.1
3 Aluno_3      9      2      4 5.000000 5.000000 5.000000 0.7211103 4.9
4 Aluno_4      1     10      9 6.666667 6.666667 6.666667 0.7399324 6.9
5 Aluno_5      7      6      8 7.000000 7.000000 7.000000 0.1428571 7.1
6 Aluno_6     10      0      3 4.333333 4.333333 4.333333 1.1842157 4.2
       MP2  situacao media.apply
1 4.333333 reprovado    4.333333
2 5.000000 reprovado    5.000000
3 5.000000 reprovado    5.000000
4 6.666667 reprovado    6.666667
5 7.000000  aprovado    7.000000
6 4.333333 reprovado    4.333333
```

</div>

As médias ponderadas poderiam ser calculadas da mesma forma, e usando a
função que criamos anteriormente

<div class="sourceCode">

``` {.sourceCode .r}
notas$MP.apply <- apply(X = notas[, provas], MARGIN = 1, FUN = med.pond)
head(notas)
     nome prova1 prova2 prova3    media   media2   media3        CV  MP
1 Aluno_1      8      4      1 4.333333 4.333333 4.333333 0.8104349 4.0
2 Aluno_2      2      7      6 5.000000 5.000000 5.000000 0.5291503 5.1
3 Aluno_3      9      2      4 5.000000 5.000000 5.000000 0.7211103 4.9
4 Aluno_4      1     10      9 6.666667 6.666667 6.666667 0.7399324 6.9
5 Aluno_5      7      6      8 7.000000 7.000000 7.000000 0.1428571 7.1
6 Aluno_6     10      0      3 4.333333 4.333333 4.333333 1.1842157 4.2
       MP2  situacao media.apply MP.apply
1 4.333333 reprovado    4.333333 4.333333
2 5.000000 reprovado    5.000000 5.000000
3 5.000000 reprovado    5.000000 5.000000
4 6.666667 reprovado    6.666667 6.666667
5 7.000000  aprovado    7.000000 7.000000
6 4.333333 reprovado    4.333333 4.333333
```

</div>

Mas note que como temos o argumento `pesos` especificado com um padrão,
devemos alterar na própria função `apply()`

<div class="sourceCode">

``` {.sourceCode .r}
notas$MP.apply <- apply(X = notas[, provas], MARGIN = 1,
                        FUN = med.pond, pesos = c(3, 3, 4))
head(notas)
     nome prova1 prova2 prova3    media   media2   media3        CV  MP
1 Aluno_1      8      4      1 4.333333 4.333333 4.333333 0.8104349 4.0
2 Aluno_2      2      7      6 5.000000 5.000000 5.000000 0.5291503 5.1
3 Aluno_3      9      2      4 5.000000 5.000000 5.000000 0.7211103 4.9
4 Aluno_4      1     10      9 6.666667 6.666667 6.666667 0.7399324 6.9
5 Aluno_5      7      6      8 7.000000 7.000000 7.000000 0.1428571 7.1
6 Aluno_6     10      0      3 4.333333 4.333333 4.333333 1.1842157 4.2
       MP2  situacao media.apply MP.apply
1 4.333333 reprovado    4.333333      4.0
2 5.000000 reprovado    5.000000      5.1
3 5.000000 reprovado    5.000000      4.9
4 6.666667 reprovado    6.666667      6.9
5 7.000000  aprovado    7.000000      7.1
6 4.333333 reprovado    4.333333      4.2
```

</div>

<div class="alert alert-warning">

NOTA: veja que isso é possível devido à presença do argumento `...` na
função `apply()`, que permite passar argumentos de outras funções dentro
dela.

</div>

Também poderíamos usar a função `weighted.mean()` implementada no R

<div class="sourceCode">

``` {.sourceCode .r}
notas$MP2.apply <- apply(X = notas[, provas], MARGIN = 1,
                         FUN = weighted.mean, w = c(3, 3, 4))
head(notas)
     nome prova1 prova2 prova3    media   media2   media3        CV  MP
1 Aluno_1      8      4      1 4.333333 4.333333 4.333333 0.8104349 4.0
2 Aluno_2      2      7      6 5.000000 5.000000 5.000000 0.5291503 5.1
3 Aluno_3      9      2      4 5.000000 5.000000 5.000000 0.7211103 4.9
4 Aluno_4      1     10      9 6.666667 6.666667 6.666667 0.7399324 6.9
5 Aluno_5      7      6      8 7.000000 7.000000 7.000000 0.1428571 7.1
6 Aluno_6     10      0      3 4.333333 4.333333 4.333333 1.1842157 4.2
       MP2  situacao media.apply MP.apply MP2.apply
1 4.333333 reprovado    4.333333      4.0       4.0
2 5.000000 reprovado    5.000000      5.1       5.1
3 5.000000 reprovado    5.000000      4.9       4.9
4 6.666667 reprovado    6.666667      6.9       6.9
5 7.000000  aprovado    7.000000      7.1       7.1
6 4.333333 reprovado    4.333333      4.2       4.2
```

</div>

O Coeficiente de Variação poderia ser calculado usando nossa função
`cv()`

<div class="sourceCode">

``` {.sourceCode .r}
notas$CV.apply <- apply(X = notas[, provas], MARGIN = 1, FUN = cv)
head(notas)
     nome prova1 prova2 prova3    media   media2   media3        CV  MP
1 Aluno_1      8      4      1 4.333333 4.333333 4.333333 0.8104349 4.0
2 Aluno_2      2      7      6 5.000000 5.000000 5.000000 0.5291503 5.1
3 Aluno_3      9      2      4 5.000000 5.000000 5.000000 0.7211103 4.9
4 Aluno_4      1     10      9 6.666667 6.666667 6.666667 0.7399324 6.9
5 Aluno_5      7      6      8 7.000000 7.000000 7.000000 0.1428571 7.1
6 Aluno_6     10      0      3 4.333333 4.333333 4.333333 1.1842157 4.2
       MP2  situacao media.apply MP.apply MP2.apply  CV.apply
1 4.333333 reprovado    4.333333      4.0       4.0 0.8104349
2 5.000000 reprovado    5.000000      5.1       5.1 0.5291503
3 5.000000 reprovado    5.000000      4.9       4.9 0.7211103
4 6.666667 reprovado    6.666667      6.9       6.9 0.7399324
5 7.000000  aprovado    7.000000      7.1       7.1 0.1428571
6 4.333333 reprovado    4.333333      4.2       4.2 1.1842157
```

</div>

Finalmente, a estrutura de repetição `if()` também possui uma forma
vetorizada através da função `ifelse()`. Essa função funciona da
seguinte forma:

<div class="sourceCode">

``` {.sourceCode .r}
ifelse(<condição>, <valor se verdadeiro>, <valor se falso>)
```

</div>

Dessa forma, a atribuição da situação dos alunos poderia ser feita da
seguinte forma:

<div class="sourceCode">

``` {.sourceCode .r}
notas$situacao2 <- ifelse(notas$MP >= 7, "aprovado", "reprovado")
head(notas)
     nome prova1 prova2 prova3    media   media2   media3        CV  MP
1 Aluno_1      8      4      1 4.333333 4.333333 4.333333 0.8104349 4.0
2 Aluno_2      2      7      6 5.000000 5.000000 5.000000 0.5291503 5.1
3 Aluno_3      9      2      4 5.000000 5.000000 5.000000 0.7211103 4.9
4 Aluno_4      1     10      9 6.666667 6.666667 6.666667 0.7399324 6.9
5 Aluno_5      7      6      8 7.000000 7.000000 7.000000 0.1428571 7.1
6 Aluno_6     10      0      3 4.333333 4.333333 4.333333 1.1842157 4.2
       MP2  situacao media.apply MP.apply MP2.apply  CV.apply situacao2
1 4.333333 reprovado    4.333333      4.0       4.0 0.8104349 reprovado
2 5.000000 reprovado    5.000000      5.1       5.1 0.5291503 reprovado
3 5.000000 reprovado    5.000000      4.9       4.9 0.7211103 reprovado
4 6.666667 reprovado    6.666667      6.9       6.9 0.7399324 reprovado
5 7.000000  aprovado    7.000000      7.1       7.1 0.1428571  aprovado
6 4.333333 reprovado    4.333333      4.2       4.2 1.1842157 reprovado
```

</div>

<div id="ch006.xhtml#exercícios-13" class="section level3 unnumbered">

### Exercícios

1.  Faça uma função usando loop for que recebe duas matrizes de mesma
    dimensão e retorna a soma das matrizes. Note que é necessário
    verificar se as matrizes fornecidas pelo usuário podem ser somadas,
    caso contrário retorne uma mensagem de erro dizendo que as matrizes
    não podem ser somadas.
2.  Faça uma função usando loop for para multiplicar duas matrizes
    compatíveis. Note que é necessário verificar se as matrizes
    fornecidas pelo usuário podem ser multiplicadas, caso contrário
    retorne uma mensagem de erro dizendo que as matrizes não podem ser
    multiplicadas.
3.  Faça uma função para resolver sistemas lineares 2 x 2 usando o
    método de decomposição de Gauss. Veja esta página se você não
    conhece o método <https://matrixcalc.org/pt/slu.html>.
4.  Faça uma função que encontra o máximo de uma função fornecida pelo
    usuário em um intervalo e precisão pré-determinado pelo usuário.
5.  Faça uma função que resolve uma equação não-linear de um único
    parâmetro em um intervalo e precisão pré-determinado pelo usuário.

</div>

</div>

<div id="ch006.xhtml#outras-estruturas-while-e-repeat"
class="section level2">

[5.4]{.header-section-number} Outras estruturas: while e repeat
---------------------------------------------------------------

O `while` executa comandos enquanto uma determinada condição permanece
verdadeira.

<div class="sourceCode">

``` {.sourceCode .r}
## Calcule a soma em 1,2,3... até que o soma seja maior do que 1000
n <- 0
soma <- 0
while(soma <= 1000){
    n <- n + 1
    soma <- soma + n
}
soma
[1] 1035
```

</div>

O `repeat` é ainda mais básico, e irá executar comandos até que você
explicitamente pare a execução com o comando `break`.

<div class="sourceCode">

``` {.sourceCode .r}
## Mesmo exemplo
n <- 0
soma <- 0
repeat{
    n <- n + 1
    soma <- soma + n
    if(soma > 1000) break
}
soma
[1] 1035
```

</div>

<div id="ch006.xhtml#exercícios-14" class="section level3 unnumbered">

### Exercícios

1.  Crie uma função que retorna o absoluto de um vetor de inteiros.
2.  Crie uma função em R que retorna o maior valor em um vetor de
    elementos númericos.
3.  Crie uma função que retorna o número de valores maiores que a média
    de um vetor. Você pode usar a função mean().
4.  Crie uma função que dado um vetor de tamanho 3 retorna os seus
    valores em ordem crescente e decrescente.
5.  Crie uma função que calcula o fatorial de um número.

<!--chapter:end:05-programacao.Rmd-->

</div>

</div>

</div>

[]{#ch007.xhtml}

<div id="ch007.xhtml#análise-exploratória-de-dados"
class="section level1">

[6]{.header-section-number} Análise exploratória de dados
=========================================================

Nesta sessão vamos ver alguns (mas não todos!) comandos do R para fazer
uma análise descritiva de um conjunto de dados.

Uma boa forma de iniciar uma análise descritiva adequada é verificar os
tipos de variáveis disponíveis. Variáveis podem ser classificadas da
seguinte forma:

-   Qualitativas
    -   Nominais
    -   Ordinais
-   Quantitativas
    -   Discretas
    -   Contínuas

e podem ser resumidas por tabelas, gráficos e/ou medidas de tendência
central e dispersão.

<div id="ch007.xhtml#o-conjunto-de-dados-milsa" class="section level2">

[6.1]{.header-section-number} O conjunto de dados `milsa`
---------------------------------------------------------

O livro "Estatística Básica" de W. O. Bussab e P. A. Morettin traz no
segundo capítulo um conjunto de dados hipotético de atributos de 36
funcionários da companhia "Milsa". Os dados estão reproduzidos na tabela
abaixo. Consulte o livro para mais detalhes sobre este dados.

  Funcionario   Est.civil   Inst       Filhos   Salario   Anos   Meses   Regiao
  ------------- ----------- ---------- -------- --------- ------ ------- ----------
  1             solteiro    1o Grau    NA       4.00      26     3       interior
  2             casado      1o Grau    1        4.56      32     10      capital
  3             casado      1o Grau    2        5.25      36     5       capital
  4             solteiro    2o Grau    NA       5.73      20     10      outro
  5             solteiro    1o Grau    NA       6.26      40     7       outro
  6             casado      1o Grau    0        6.66      28     0       interior
  7             solteiro    1o Grau    NA       6.86      41     0       interior
  8             solteiro    1o Grau    NA       7.39      43     4       capital
  9             casado      2o Grau    1        7.59      34     10      capital
  10            solteiro    2o Grau    NA       7.44      23     6       outro
  11            casado      2o Grau    2        8.12      33     6       interior
  12            solteiro    1o Grau    NA       8.46      27     11      capital
  13            solteiro    2o Grau    NA       8.74      37     5       outro
  14            casado      1o Grau    3        8.95      44     2       outro
  15            casado      2o Grau    0        9.13      30     5       interior
  16            solteiro    2o Grau    NA       9.35      38     8       outro
  17            casado      2o Grau    1        9.77      31     7       capital
  18            casado      1o Grau    2        9.80      39     7       outro
  19            solteiro    Superior   NA       10.53     25     8       interior
  20            solteiro    2o Grau    NA       10.76     37     4       interior
  21            casado      2o Grau    1        11.06     30     9       outro
  22            solteiro    2o Grau    NA       11.59     34     2       capital
  23            solteiro    1o Grau    NA       12.00     41     0       outro
  24            casado      Superior   0        12.79     26     1       outro
  25            casado      2o Grau    2        13.23     32     5       interior
  26            casado      2o Grau    2        13.60     35     0       outro
  27            solteiro    1o Grau    NA       13.85     46     7       outro
  28            casado      2o Grau    0        14.69     29     8       interior
  29            casado      2o Grau    5        14.71     40     6       interior
  30            casado      2o Grau    2        15.99     35     10      capital
  31            solteiro    Superior   NA       16.22     31     5       outro
  32            casado      2o Grau    1        16.61     36     4       interior
  33            casado      Superior   3        17.26     43     7       capital
  34            solteiro    Superior   NA       18.75     33     7       capital
  35            casado      2o Grau    2        19.40     48     11      capital
  36            casado      Superior   3        23.30     42     2       interior

Estes dados estão disponíveis em um arquivo `csv` no endereço
<http://www.leg.ufpr.br/~fernandomayer/data/milsa.csv>.

O nosso objetivo é, através do R,

-   Entrar com os dados;
-   Fazer uma análise descritiva.

Estes são dados no "estilo planilha", com variáveis de diferentes tipos:
categóricas e numéricas (qualitativas e quantitativas). Portanto o
formato ideal de armazenamento destes dados no R é o `data.frame`.

Para importar os dados do endereço acima diretamente para o R, usamos

<div class="sourceCode">

``` {.sourceCode .r}
url <- "http://www.leg.ufpr.br/~fernandomayer/data/milsa.csv"
milsa <- read.csv(url)
```

</div>

E para conferir a estrutura dos dados podemos usar algumas funções como:

<div class="sourceCode">

``` {.sourceCode .r}
str(milsa)
'data.frame':   36 obs. of  8 variables:
 $ Funcionario: int  1 2 3 4 5 6 7 8 9 10 ...
 $ Est.civil  : Factor w/ 2 levels "casado","solteiro": 2 1 1 2 2 1 2 2 1 2 ...
 $ Inst       : Factor w/ 3 levels "1o Grau","2o Grau",..: 1 1 1 2 1 1 1 1 2 2 ...
 $ Filhos     : int  NA 1 2 NA NA 0 NA NA 1 NA ...
 $ Salario    : num  4 4.56 5.25 5.73 6.26 6.66 6.86 7.39 7.59 7.44 ...
 $ Anos       : int  26 32 36 20 40 28 41 43 34 23 ...
 $ Meses      : int  3 10 5 10 7 0 0 4 10 6 ...
 $ Regiao     : Factor w/ 3 levels "capital","interior",..: 2 1 1 3 3 2 2 1 1 3 ...
head(milsa)
  Funcionario Est.civil    Inst Filhos Salario Anos Meses   Regiao
1           1  solteiro 1o Grau     NA    4.00   26     3 interior
2           2    casado 1o Grau      1    4.56   32    10  capital
3           3    casado 1o Grau      2    5.25   36     5  capital
4           4  solteiro 2o Grau     NA    5.73   20    10    outro
5           5  solteiro 1o Grau     NA    6.26   40     7    outro
6           6    casado 1o Grau      0    6.66   28     0 interior
tail(milsa)
   Funcionario Est.civil     Inst Filhos Salario Anos Meses   Regiao
31          31  solteiro Superior     NA   16.22   31     5    outro
32          32    casado  2o Grau      1   16.61   36     4 interior
33          33    casado Superior      3   17.26   43     7  capital
34          34  solteiro Superior     NA   18.75   33     7  capital
35          35    casado  2o Grau      2   19.40   48    11  capital
36          36    casado Superior      3   23.30   42     2 interior
```

</div>

Podemos classificar todas as variáveis desse conjunto de dados como:

  Variável        Classificação
  --------------- -----------------------
  `Funcionario`   Quantitativa discreta
  `Est.civil`     Qualitativa nominal
  `Inst`          Qualitativa ordinal
  `Filhos`        Quantitativa discreta
  `Salario`       Quantitativa contínua
  `Anos`          Quantitativa contínua
  `Meses`         Quantitativa contínua
  `Regiao`        Qualitativa nominal

Como a variável `Inst` é qualitativa ordinal, podemos indicar para o R
que ela deve ser tratada como ordinal. Se observarmos os níveis desse
fator:

<div class="sourceCode">

``` {.sourceCode .r}
levels(milsa$Inst)
[1] "1o Grau"  "2o Grau"  "Superior"
```

</div>

já notamos que a ordenação está correta (da esquerda para a direita),
pois sabemos que a classificação interna dos níveis é por ordem
alfabética, e nesse caso, por coincidência, a ordem já está na sequência
correta. Mesmo assim, podemos indicar que este fator é ordinal, usando o
argumento `ordered` da função `factor()`

<div class="sourceCode">

``` {.sourceCode .r}
milsa$Inst <- factor(milsa$Inst, ordered = TRUE)
```

</div>

Note agora a modificação na classe dessa coluna, e a representação dos
níveis:

<div class="sourceCode">

``` {.sourceCode .r}
class(milsa$Inst)
[1] "ordered" "factor" 
milsa$Inst
 [1] 1o Grau  1o Grau  1o Grau  2o Grau  1o Grau  1o Grau  1o Grau  1o Grau 
 [9] 2o Grau  2o Grau  2o Grau  1o Grau  2o Grau  1o Grau  2o Grau  2o Grau 
[17] 2o Grau  1o Grau  Superior 2o Grau  2o Grau  2o Grau  1o Grau  Superior
[25] 2o Grau  2o Grau  1o Grau  2o Grau  2o Grau  2o Grau  Superior 2o Grau 
[33] Superior Superior 2o Grau  Superior
Levels: 1o Grau < 2o Grau < Superior
```

</div>

A coluna continua sendo um `factor`, mas agora também é `ordered` (sim,
um objeto pode ter mais de uma classe, se elas foram compatíveis e/ou
complementares). Os níveis agora são representados por

    1o Grau < 2o Grau < Superior

para indicar explicitamente que existe uma ordem nos níveis desse fator.

Podemos ainda definir uma nova variável, chamada `Idade`, a partir das
variáveis `Anos` e `Meses`:

<div class="sourceCode">

``` {.sourceCode .r}
milsa$Idade <- milsa$Anos + milsa$Meses/12
```

</div>

Os dois comandos acima (de modificação da classe de uma variável, e a
criação de uma nova variável) poderiam ser facilmente executadas de uma
única vez através do comando `transform()`

<div class="sourceCode">

``` {.sourceCode .r}
milsa <- transform(milsa,
                   Inst = factor(Inst, ordered = TRUE),
                   Idade = Anos + Meses/12)
```

</div>

Agora que os dados estão prontos podemos começar a análise descritiva. A
seguir mostramos como fazer análises descritivas uni e bivariadas.
Inspecione os comandos mostrados a seguir e os resultados por eles
produzidos. Sugerimos ainda que o leitor use o R para reproduzir os
resultados mostrados no texto dos capítulos 1 a 3 do livro de Bussab &
Morettin, relacionados com este exemplo. Veja os scripts do livro
[aqui](https://rpubs.com/EstatBasica/Introd).

</div>

<div id="ch007.xhtml#análise-univariada" class="section level2">

[6.2]{.header-section-number} Análise univariada
------------------------------------------------

A análise univariada consiste basicamente em, para cada uma das
variáveis individualmente:

-   Classificar a variável quanto a seu tipo: qualitativa (nominal ou
    ordinal) ou quantitativa (discreta ou contínua).
-   Obter tabelas, gráficos e/ou medidas que resumam a variável.

A partir destes resultados pode-se montar um resumo geral dos dados.

A seguir vamos mostrar como obter tabelas, gráficos e medidas com o R.
Para isto vamos selecionar uma variável de cada tipo para que o leitor
possa, por analogia, obter resultados para as demais.

<div id="ch007.xhtml#variável-qualitativa-nominal"
class="section level3">

### [6.2.1]{.header-section-number} Variável Qualitativa Nominal

A variável `Est.civil` é uma qualitativa nominal. Desta forma podemos
obter: (i) uma tabela de frequências (absolutas e/ou relativas), (ii) um
gráfico de setores, (iii) a "moda", *i.e.* o valor que ocorre com maior
frequência.

Já vimos, através do resultado da função `str()` acima, que esta
variável é um fator. A seguir obtemos frequências absolutas e relativas
(note duas formas diferentes de obter as frequências relativas).

<div class="sourceCode">

``` {.sourceCode .r}
## Frequência absoluta
civil.tb <- table(milsa$Est.civil)
civil.tb

  casado solteiro 
      20       16 
## Frequência relativa, calculando manualmente
civil.tb/length(milsa$Est.civil)

   casado  solteiro 
0.5555556 0.4444444 
## Frequência relativa, com a função prop.table()
prop.table(civil.tb)

   casado  solteiro 
0.5555556 0.4444444 
```

</div>

Os gráficos de barras e de setores são adequados para representar esta
variável. Os comandos `barplot()` e `pie()` usam o resultado da função
`table()` para gerar os gráficos:

<div class="sourceCode">

``` {.sourceCode .r}
par(mfrow = c(1,2))
barplot(civil.tb)
pie(civil.tb)
par(mfrow = c(1,1))
```

</div>

![](media/file8.png)

A *moda* de qualquer variável aleatória é definida como o valor mais
frequente encontrado na amostra. No R não há uma função pronta para
"calcular" a moda, pois ela pode ser obtida facilmente através do uso de
funções básicas. Uma opção seria usar os comandos abaixo:

<div class="sourceCode">

``` {.sourceCode .r}
names(civil.tb)[which.max(civil.tb)]
[1] "casado"
```

</div>

Deixamos a cargo do leitor entender e interpretar esse comando.

</div>

<div id="ch007.xhtml#variável-qualitativa-ordinal"
class="section level3">

### [6.2.2]{.header-section-number} Variável Qualitativa Ordinal

Para exemplificar como obter análises para uma variável qualitativa
ordinal vamos selecionar a variável `Inst`.

As tabelas de frequências são obtidas de forma semelhante à mostrada
anteriormente.

<div class="sourceCode">

``` {.sourceCode .r}
## Frequência absoluta
inst.tb <- table(milsa$Inst)
inst.tb

 1o Grau  2o Grau Superior 
      12       18        6 
## Frequência relativa
prop.table(inst.tb)

  1o Grau   2o Grau  Superior 
0.3333333 0.5000000 0.1666667 
```

</div>

O gráfico de setores não é adequado para este tipo de variável por não
expressar a ordem dos possíveis valores. Usamos então apenas um gráfico
de barras conforme mostrado abaixo

<div class="sourceCode">

``` {.sourceCode .r}
barplot(inst.tb)
```

</div>

![](media/file9.png)

Em alguns casos podemos querer mostrar o gráfico de barras com as barras
classificadas da menor para a maior, ou vice-versa, independente da
ordem dos níveis. Para isso podemos usar a função `sort()` para ordenar
os valores da tabela e fazer o gráfico

<div class="sourceCode">

``` {.sourceCode .r}
par(mfrow = c(1,2))
## Menor para maior
barplot(sort(inst.tb))
## Maior para menor
barplot(sort(inst.tb, decreasing = TRUE))
par(mfrow = c(1,1))
```

</div>

![](media/file10.png)

Para uma variável ordinal, além da moda podemos também calcular outras
medidas, tais como a mediana conforme exemplificado a seguir. Note que o
comando `median()` não funciona com variáveis não numéricas, e por isso
usamos o comando seguinte.

<div class="sourceCode">

``` {.sourceCode .r}
## Moda
names(inst.tb)[which.max(inst.tb)]
[1] "2o Grau"
## Mediana
median(milsa$Inst) # só funciona para variáveis numéricas
Error in median.default(milsa$Inst): need numeric data
median(as.numeric(milsa$Inst)) # traz a mediana da codificação do nível
[1] 2
levels(milsa$Inst)[median(as.numeric(milsa$Inst))] # valor correto
[1] "2o Grau"
```

</div>

</div>

<div id="ch007.xhtml#variável-quantitativa-discreta"
class="section level3">

### [6.2.3]{.header-section-number} Variável quantitativa discreta

Vamos agora usar a variável `Filhos` (número de filhos) para ilustrar
algumas análises que podem ser feitas com uma quantitativa discreta.

Frequências absolutas e relativas são obtidas como anteriormente. Também
vamos calcular a frequência acumulada, onde a frequência em uma classe é
a soma das frequências das classes anteriores. Para isso usamos a função
`cumsum()`, que já faz a soma acumulada.

<div class="sourceCode">

``` {.sourceCode .r}
## Frequência absoluta
filhos.tb <- table(milsa$Filhos)
filhos.tb

0 1 2 3 5 
4 5 7 3 1 
## Frequência relativa
filhos.tbr <- prop.table(filhos.tb)
filhos.tbr

   0    1    2    3    5 
0.20 0.25 0.35 0.15 0.05 
## Frequência acumulada
filhos.tba <- cumsum(filhos.tbr)
filhos.tba
   0    1    2    3    5 
0.20 0.45 0.80 0.95 1.00 
```

</div>

O gráfico adequado para frequências absolutas de uma variável discreta é
parecido com um gráfico de barras, mas nesse caso, as frequências são
indicadas por linhas. Usando a função `plot()` em um objeto resultado da
função `table()`, o gráfico adequado já é selecionado:

<div class="sourceCode">

``` {.sourceCode .r}
plot(filhos.tb)
```

</div>

![](media/file11.png)

Outra possibilidade seria fazer gráficos de frequências relativas e de
frequências acumuladas conforme mostrado na

<div class="sourceCode">

``` {.sourceCode .r}
par(mfrow = c(1,2))
## Frequência relativa
plot(filhos.tbr)
## Frequência relativa acumulada
plot(filhos.tba, type = "S") # tipo step (escada)
par(mfrow = c(1,1))
```

</div>

![](media/file12.png)

Sendo a variável numérica há uma maior diversidade de medidas
estatísticas que podem ser calculadas.

A seguir mostramos como obter algumas medidas de posição: moda, mediana,
média e média aparada. Note que o argumento `na.rm = TRUE` é necessário
porque não há informação sobre número de filhos para alguns indivíduos
(`NA`). Para calcular a média aparada, usamos o argumento `trim = 0.1`
que indica que a média deve ser calculada excluindo-se 10% dos menores e
10% dos maiores valores do vetor de dados. Ao final mostramos como obter
os quartis, incluido o mínimo e o máximo.

<div class="sourceCode">

``` {.sourceCode .r}
## Moda
names(filhos.tb)[which.max(filhos.tb)]
[1] "2"
## Mediana
median(milsa$Filhos, na.rm = TRUE)
[1] 2
## Média
mean(milsa$Filhos, na.rm = TRUE)
[1] 1.65
## Média aparada
mean(milsa$Filhos, trim = 0.1, na.rm = TRUE)
[1] 1.5625
## Quartis
quantile(milsa$Filhos, na.rm = TRUE)
  0%  25%  50%  75% 100% 
   0    1    2    2    5 
```

</div>

Passando agora para medidas de dispersão, vejamos como obter o máximo e
mínimo, e com isso a amplitude, além da variância, desvio padrão, e
coeficiente de variação. Também obtemos os quartis para calcular a
amplitude interquartílica.

<div class="sourceCode">

``` {.sourceCode .r}
## Máximo e mínimo
max(milsa$Filhos, na.rm = TRUE)
[1] 5
min(milsa$Filhos, na.rm = TRUE)
[1] 0
## As duas informações juntas
range(milsa$Filhos, na.rm = TRUE)
[1] 0 5
## Amplitude é a diferença entre máximo e mínimo
diff(range(milsa$Filhos, na.rm = TRUE))
[1] 5
## Variância
var(milsa$Filhos, na.rm = TRUE)
[1] 1.607895
## Desvio-padrão
sd(milsa$Filhos, na.rm = TRUE)
[1] 1.268028
## Coeficiente de variação
sd(milsa$Filhos, na.rm = TRUE)/mean(milsa$Filhos, na.rm = TRUE)
[1] 0.7685018
## Quartis
(filhos.qt <- quantile(milsa$Filhos, na.rm = TRUE))
  0%  25%  50%  75% 100% 
   0    1    2    2    5 
## Amplitude interquartílica
filhos.qt[4] - filhos.qt[2]
75% 
  1 
```

</div>

Finalmente, podemos usar a função **genérica** `summary()` para resumir
os dados de uma só vez

<div class="sourceCode">

``` {.sourceCode .r}
summary(milsa$Filhos)
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max.    NA's 
   0.00    1.00    2.00    1.65    2.00    5.00      16 
```

</div>

</div>

<div id="ch007.xhtml#variável-quantitativa-contínua"
class="section level3">

### [6.2.4]{.header-section-number} Variável quantitativa contínua

Para concluir os exemplos para análise univariada vamos considerar a
variável quantitativa contínua `Salario`.

Para se fazer uma tabela de frequências de uma variável contínua, é
preciso primeiro agrupar os dados em classes. Nos comandos mostrados a
seguir verificamos inicialmente os valores máximo e mínimo dos dados,
depois usamos o critério de Sturges para definir o número de classes.
Usamos a função `cut()` para agrupar os dados em classes e finalmente
obtemos as frequências absolutas e relativas.

<div class="sourceCode">

``` {.sourceCode .r}
## Máximo e mínimo
range(milsa$Salario)
[1]  4.0 23.3
## Número de classes estimado, com base no critério de Sturges. Veja
## outras opções em ?nclass
nclass.Sturges(milsa$Salario)
[1] 7
## Criando as classes com a função cut(), usando os valores mínimos e
## máximos dados em range()
cut(milsa$Salario, breaks = seq(4, 23.3, length.out = 8))
 [1] <NA>        (4,6.76]    (4,6.76]    (4,6.76]    (4,6.76]    (4,6.76]   
 [7] (6.76,9.51] (6.76,9.51] (6.76,9.51] (6.76,9.51] (6.76,9.51] (6.76,9.51]
[13] (6.76,9.51] (6.76,9.51] (6.76,9.51] (6.76,9.51] (9.51,12.3] (9.51,12.3]
[19] (9.51,12.3] (9.51,12.3] (9.51,12.3] (9.51,12.3] (9.51,12.3] (12.3,15]  
[25] (12.3,15]   (12.3,15]   (12.3,15]   (12.3,15]   (12.3,15]   (15,17.8]  
[31] (15,17.8]   (15,17.8]   (15,17.8]   (17.8,20.5] (17.8,20.5] (20.5,23.3]
7 Levels: (4,6.76] (6.76,9.51] (9.51,12.3] (12.3,15] (15,17.8] ... (20.5,23.3]
```

</div>

Note que uma das classes é `NA`. Isso ocorre pela definição das classes,
que por padrão é no formato `(a,b]`, ou seja, o intervalo é aberto em
`a` (não inclui `a`) e fechado em `b` (inclui `b`). Podemos alterar esse
padrão usando o argumento `include.lowest = TRUE`,

<div class="sourceCode">

``` {.sourceCode .r}
cut(milsa$Salario, breaks = seq(4, 23.3, length.out = 8),
    include.lowest = TRUE)
 [1] [4,6.76]    [4,6.76]    [4,6.76]    [4,6.76]    [4,6.76]    [4,6.76]   
 [7] (6.76,9.51] (6.76,9.51] (6.76,9.51] (6.76,9.51] (6.76,9.51] (6.76,9.51]
[13] (6.76,9.51] (6.76,9.51] (6.76,9.51] (6.76,9.51] (9.51,12.3] (9.51,12.3]
[19] (9.51,12.3] (9.51,12.3] (9.51,12.3] (9.51,12.3] (9.51,12.3] (12.3,15]  
[25] (12.3,15]   (12.3,15]   (12.3,15]   (12.3,15]   (12.3,15]   (15,17.8]  
[31] (15,17.8]   (15,17.8]   (15,17.8]   (17.8,20.5] (17.8,20.5] (20.5,23.3]
7 Levels: [4,6.76] (6.76,9.51] (9.51,12.3] (12.3,15] (15,17.8] ... (20.5,23.3]
```

</div>

E note que agora a primeira classe fica `[a,b]`, ou seja, fechada
(incluindo) os dois lados. Para que o intervalo seja fechado à esquerda,
usamos o argumento `right = FALSE`. As combinações possíveis para esses
dois argumentos, e as classes resultantes são apresentadas na tabela
abaixo:

  Argumentos                        Resultado
  --------------------------------- ---------------------
  `include.lowest = T, right = T`   `[a,b], ..., (y,z]`
  `include.lowest = F, right = T`   `(a,b], ..., (y,z]`
  `include.lowest = F, right = F`   `[a,b), ..., [y,z)`
  `include.lowest = T, right = F`   `[a,b), ..., [y,z]`

Outra opção para "acomodar" todos os extremos dentro das classes, seria
naturalmente atribuir valores um pouco menores que o mínimo, e um pouco
maiores que o máximo. Abaixo, usamos essa abordagem e fazemos uma tabela
com as frequências absolutas e relativas.

<div class="sourceCode">

``` {.sourceCode .r}
salario.cut <- cut(milsa$Salario,
                   breaks = seq(3.5, 23.5, length.out = 8))
salario.cut
 [1] (3.5,6.36]  (3.5,6.36]  (3.5,6.36]  (3.5,6.36]  (3.5,6.36]  (6.36,9.21]
 [7] (6.36,9.21] (6.36,9.21] (6.36,9.21] (6.36,9.21] (6.36,9.21] (6.36,9.21]
[13] (6.36,9.21] (6.36,9.21] (6.36,9.21] (9.21,12.1] (9.21,12.1] (9.21,12.1]
[19] (9.21,12.1] (9.21,12.1] (9.21,12.1] (9.21,12.1] (9.21,12.1] (12.1,14.9]
[25] (12.1,14.9] (12.1,14.9] (12.1,14.9] (12.1,14.9] (12.1,14.9] (14.9,17.8]
[31] (14.9,17.8] (14.9,17.8] (14.9,17.8] (17.8,20.6] (17.8,20.6] (20.6,23.5]
7 Levels: (3.5,6.36] (6.36,9.21] (9.21,12.1] (12.1,14.9] ... (20.6,23.5]
## Tabela com as frequencias absolutas por classe
salario.tb <- table(salario.cut)
salario.tb
salario.cut
 (3.5,6.36] (6.36,9.21] (9.21,12.1] (12.1,14.9] (14.9,17.8] (17.8,20.6] 
          5          10           8           6           4           2 
(20.6,23.5] 
          1 
## Tabela com as frequências relativas
prop.table(salario.tb)
salario.cut
 (3.5,6.36] (6.36,9.21] (9.21,12.1] (12.1,14.9] (14.9,17.8] (17.8,20.6] 
 0.13888889  0.27777778  0.22222222  0.16666667  0.11111111  0.05555556 
(20.6,23.5] 
 0.02777778 
```

</div>

Na sequência vamos mostrar dois possíveis gráficos para variáveis
contínuas: o histograma e o *box-plot*.

Para fazer um histograma usamos a função `hist()`, por exemplo,

<div class="sourceCode">

``` {.sourceCode .r}
hist(milsa$Salario)
```

</div>

![](media/file13.png)

A função `hist()` possui vários argumentos para alterar o comportamento
da saída do gráfico. Por exemplo, com `labels = TRUE` as frequências são
mostradas acima de cada barra. Com `freq = FALSE`, o gráfico é feito com
as frequências relativas.

<div class="sourceCode">

``` {.sourceCode .r}
hist(milsa$Salario, freq = FALSE, labels = TRUE)
```

</div>

![](media/file14.png)

Por padrão, a função `hist()` calcula automaticamente o número de
classes e os valores limites de cada classe. No entanto, isto pode ser
alterado com o argumento `breaks`, que pode receber um vetor definindo
os limites das classes, uma função para definir as quebras, um nome de
critério (por exemplo, `"Sturges"`), ou um único escalar definido o
número de classes. As últimas três opções são apenas sugestões
utilizadas pela função. O argumento `nclass` também funciona dessa
forma, recebendo apenas um valor com o número de classes (como
sugestão).

<div class="sourceCode">

``` {.sourceCode .r}
hist(milsa$Salario, nclass = 15)
```

</div>

![](media/file15.png)

Assim como na função `cut()`, os argumentos `include.lowest` e `right`
são utilizados para controlar a borda das classes.

Uma característica importante da função `hist()` é que ela retorna não
apenas o gráfico, mas também uma lista com as informações utilizadas
para construir o gráfico. Associando um histograma a um objeto, podemos
ver o seu conteúdo:

<div class="sourceCode">

``` {.sourceCode .r}
salario.hist <- hist(milsa$Salario)
```

</div>

![](media/file16.png)

<div class="sourceCode">

``` {.sourceCode .r}
salario.hist
$breaks
 [1]  4  6  8 10 12 14 16 18 20 22 24

$counts
 [1] 4 6 8 5 4 3 3 2 0 1

$density
 [1] 0.05555556 0.08333333 0.11111111 0.06944444 0.05555556 0.04166667
 [7] 0.04166667 0.02777778 0.00000000 0.01388889

$mids
 [1]  5  7  9 11 13 15 17 19 21 23

$xname
[1] "milsa$Salario"

$equidist
[1] TRUE

attr(,"class")
[1] "histogram"
```

</div>

Estas informações podem então ser utilizadas para outros propósitos
dentro do R.

Os **boxplots** são úteis para revelar o centro, a dispersão e a
distribuição dos dados, além de **outliers**. São construídos da
seguinte forma:

-   A linha central mais escura representa a mediana. Os extremos da
    caixa são o $1^{o}$ ($q1$) e o $3^{o}$ ($q3$) quartis.
-   As linhas que se extendem das caixas são definidas como:
    $$q1 - 1,5 \cdot IQR\ \qquad e\ \qquad q3 + 1,5 \cdot IQR$$ onde
    $IQR$ é o intervalo inter-quartil. As linhas vão até os valores
    máximo e mínimo que ainda se encontram dentro deste intervalo.

<div class="sourceCode">

``` {.sourceCode .r}
boxplot(milsa$Salario)
```

</div>

![](media/file17.png)

Existem também vários argumentos que permitem variações do *boxplot*,
tais como caixas com tamanho proporcional aos tamanhos dos grupos
(`varwidth = TRUE`), e caixas "acinturadas" (*notched boxplot*)
(`notch = TRUE`).

<div class="sourceCode">

``` {.sourceCode .r}
boxplot(milsa$Salario, varwidth = TRUE, notch = TRUE)
```

</div>

![](media/file18.png)

Ambas opções são úteis quando há mais de um grupo e a comparação entre
os boxplots é facilitada.

Finalmente, podemos obter as medidas de posição e dispersão da mesma
forma que para variáveis discretas. Veja alguns exemplos a seguir. Note
que aqui não é necessário o uso do argumento `na.rm = TRUE`, pois não
existem `NA`s nesta variável.

<div class="sourceCode">

``` {.sourceCode .r}
## Mediana
median(milsa$Salario)
[1] 10.165
## Média
mean(milsa$Salario)
[1] 11.12222
## Média aparada
mean(milsa$Salario, trim = 0.1)
[1] 10.838
## Quartis
quantile(milsa$Salario)
     0%     25%     50%     75%    100% 
 4.0000  7.5525 10.1650 14.0600 23.3000 
## Máximo e mínimo
max(milsa$Salario)
[1] 23.3
min(milsa$Salario)
[1] 4
## As duas informações juntas
range(milsa$Salario)
[1]  4.0 23.3
## Amplitude é a diferença entre máximo e mínimo
diff(range(milsa$Salario))
[1] 19.3
## Variância
var(milsa$Salario)
[1] 21.04477
## Desvio-padrão
sd(milsa$Salario)
[1] 4.587458
## Coeficiente de variação
sd(milsa$Salario)/mean(milsa$Salario)
[1] 0.4124587
## Quartis
salario.qt <- quantile(milsa$Salario)
## Amplitude interquartílica
salario.qt[4] - salario.qt[2]
   75% 
6.5075 
```

</div>

</div>

</div>

<div id="ch007.xhtml#análise-bivariada" class="section level2">

[6.3]{.header-section-number} Análise Bivariada
-----------------------------------------------

Na análise bivariada procuramos identificar relações entre duas
variáveis. Assim como na análise univariada, estas relações podem ser
resumidas por gráficos, tabelas e/ou medidas estatísticas. O tipo de
resumo vai depender dos tipos das variáveis envolvidas. Vamos considerar
três possibilidades:

-   Qualitativa *vs* qualitativa
-   Qualitativa *vs* quantitativa
-   Quantitativa *vs* quantitativa

Salienta-se ainda que:

-   As análise mostradas a seguir não esgotam as possibilidades de
    análises envolvendo duas variáveis e devem ser vistas apenas como
    uma sugestão inicial.
-   Relações entre duas variáveis devem ser examinadas com cautela pois
    podem ser mascaradas por uma ou mais variáveis adicionais não
    considerada na análise. Estas são chamadas **variáveis de
    confundimento**. Análises com variáveis de confundimento não serão
    discutidas neste ponto.

> **Observação**: de agora em diante, como serão consideradas mais de
> uma variável, usaremos a função `with()` para chamar a maioria das
> funções.

<div id="ch007.xhtml#qualitativa-vs-qualitativa" class="section level3">

### [6.3.1]{.header-section-number} Qualitativa *vs* qualitativa

Vamos considerar as variáveis `Est.civil` (estado civil), e `Inst` (grau
de instrução). A tabela envolvendo duas variáveis é chamada **tabela de
cruzamento** ou **tabela de contingência**, e pode ser apresentada de
várias formas, conforme discutido a seguir.

A forma adequada de apresentação vai depender dos objetivos da análise e
da interpretação desejada para os dados. Inicialmente obtemos a tabela
de frequências absolutas para o cruzamento das duas variáveis, usando a
função `table()`. A tabela extendida incluindo os totais marginais pode
ser obtida com a função `addmargins()`.

<div class="sourceCode">

``` {.sourceCode .r}
## Tabela de frequências absolutas
civ.inst.tb <- with(milsa, table(Est.civil, Inst))
civ.inst.tb
          Inst
Est.civil  1o Grau 2o Grau Superior
  casado         5      12        3
  solteiro       7       6        3
addmargins(civ.inst.tb)
          Inst
Est.civil  1o Grau 2o Grau Superior Sum
  casado         5      12        3  20
  solteiro       7       6        3  16
  Sum           12      18        6  36
```

</div>

<!-- Ver tambem margin.table() -->
Tabelas de frequências relativas são obtidas com `prop.table()`, mas
aqui existem três possibilidades para as proporções em cada casela:

-   Em relação ao total geral.
-   Em relação aos totais por linha (`margin = 1`).
-   Em relação aos totais por coluna (`margin = 2`).

<div class="sourceCode">

``` {.sourceCode .r}
## Frequência relativa global
prop.table(civ.inst.tb)
          Inst
Est.civil     1o Grau    2o Grau   Superior
  casado   0.13888889 0.33333333 0.08333333
  solteiro 0.19444444 0.16666667 0.08333333
## Frequência relativa por linha
prop.table(civ.inst.tb, margin = 1)
          Inst
Est.civil  1o Grau 2o Grau Superior
  casado    0.2500  0.6000   0.1500
  solteiro  0.4375  0.3750   0.1875
## Frequência relativa por coluna
prop.table(civ.inst.tb, margin = 2)
          Inst
Est.civil    1o Grau   2o Grau  Superior
  casado   0.4166667 0.6666667 0.5000000
  solteiro 0.5833333 0.3333333 0.5000000
```

</div>

Abaixo são representados quatro tipos de gráficos de barras que podem
ser usados para representar o cruzamento das variáveis. A transposição
da tabela com `t()` permite alterar a variável que define os grupos no
eixo horizontal. O uso de `prop.table()` permite o obtenção de gráficos
com frequências relativas.

<div class="sourceCode">

``` {.sourceCode .r}
par(mfrow = c(2,2))
barplot(civ.inst.tb, legend = TRUE)
barplot(t(civ.inst.tb), legend = TRUE)
barplot(civ.inst.tb, beside = TRUE, legend = TRUE)
barplot(t(prop.table(civ.inst.tb)), beside = TRUE, legend = TRUE)
par(mfrow = c(1,1))
```

</div>

![](media/file19.png)

<!-- Incluir aqui a medida de associacao chi-quadrado -->
<!-- Incluir reagrupamento -->

</div>

<div id="ch007.xhtml#qualitativa-vs-quantitativa"
class="section level3">

### [6.3.2]{.header-section-number} Qualitativa *vs* quantitativa

Para exemplificar este caso vamos considerar as variáveis `Inst` e
`Salario`.

Para se obter uma tabela de frequências é necessário agrupar a variável
quantitativa em classes. No exemplo a seguir vamos agrupar a variável
salário em 4 classes definidas pelos quartis usando a função `cut()`.
Lembre-se que as classes são definidas por intervalos abertos à
esquerda, então usamos o argumento `include.lowest = TRUE` para garantir
que todos os dados, inclusive o menor (mínimo) seja incluído na primeira
classe. Após agrupar esta variável, obtemos a(s) tabela(s) de cruzamento
como mostrado no caso anterior.

<div class="sourceCode">

``` {.sourceCode .r}
## Quartis de salario
quantile(milsa$Salario)
     0%     25%     50%     75%    100% 
 4.0000  7.5525 10.1650 14.0600 23.3000 
## Classificação de acordo com os quartis
salario.cut <- cut(milsa$Salario, breaks =  quantile(milsa$Salario),
                   include.lowest = TRUE)
## Tabela de frequências absolutas
inst.sal.tb <- table(milsa$Inst, salario.cut)
inst.sal.tb
          salario.cut
           [4,7.55] (7.55,10.2] (10.2,14.1] (14.1,23.3]
  1o Grau         7           3           2           0
  2o Grau         2           6           5           5
  Superior        0           0           2           4
prop.table(inst.sal.tb, margin = 1)
          salario.cut
            [4,7.55] (7.55,10.2] (10.2,14.1] (14.1,23.3]
  1o Grau  0.5833333   0.2500000   0.1666667   0.0000000
  2o Grau  0.1111111   0.3333333   0.2777778   0.2777778
  Superior 0.0000000   0.0000000   0.3333333   0.6666667
```

</div>

No gráfico vamos considerar que neste exemplo a instrução deve ser a
variável explicativa e portanto colocada no eixo X, e o salário é a
variável resposta, e portanto deve ser colocada no eixo Y. Isto é,
consideramos que a instrução deve explicar, ainda que parcialmente, o
salário (e não o contrário!).

Vamos então obter um *boxplot* dos salários para cada nível de
instrução. Note que na função abaixo, usamos a notação de **fórmula** do
R, com `Salario ~ Inst` indicando que a variável `Salario` é explicada,
ou descrita, ($\sim$) pela variável `Inst`.

<div class="sourceCode">

``` {.sourceCode .r}
boxplot(Salario ~ Inst, data = milsa)
```

</div>

![](media/file20.png)

Poderíamos ainda fazer gráficos com a variável `Salario` agrupada em
classes, e neste caso os gráficos seriam como no caso anterior com duas
variáveis qualitativas.

Para as medidas descritivas, o usual é obter um resumo da variável
quantitativa como mostrado na análise univariada, porém agora informando
este resumo para cada nível do fator qualitativo de interesse.

A seguir mostramos alguns exemplos de como obter a média, desvio padrão
e o resumo de cinco números do salário para cada nível de instrução.

<div class="sourceCode">

``` {.sourceCode .r}
with(milsa, tapply(Salario, Inst, mean))
  1o Grau   2o Grau  Superior 
 7.836667 11.528333 16.475000 
with(milsa, tapply(Salario, Inst, sd))
 1o Grau  2o Grau Superior 
2.956464 3.715144 4.502438 
with(milsa, tapply(Salario, Inst, quantile))
$`1o Grau`
     0%     25%     50%     75%    100% 
 4.0000  6.0075  7.1250  9.1625 13.8500 

$`2o Grau`
     0%     25%     50%     75%    100% 
 5.7300  8.8375 10.9100 14.4175 19.4000 

$Superior
     0%     25%     50%     75%    100% 
10.5300 13.6475 16.7400 18.3775 23.3000 
```

</div>

> NOTE que aqui usamos a função `tapply()`. Para saber mais sobre os
> recursos dessa função e de outras da família `*apply`, veja o
> [script\_gapminder.R](scripts/script_gapminder.R).

</div>

<div id="ch007.xhtml#quantitativa-vs-quantitativa"
class="section level3">

### [6.3.3]{.header-section-number} Quantitativa *vs* Quantitativa

Para ilustrar este caso vamos considerar as variáveis `Salario` e
`Idade`. Para se obter uma tabela é necessário agrupar as variáveis em
classes conforme fizemos no caso anterior.

Nos comandos abaixo, agrupamos as duas variáveis em classes definidas
pelos respectivos quartis, gerando portanto uma tabela de cruzamento
$4\  \times \ 4$.

<div class="sourceCode">

``` {.sourceCode .r}
## Classes de Idade
idade.cut <- with(milsa, cut(Idade, breaks = quantile(Idade),
                             include.lowest = TRUE))
table(idade.cut)
idade.cut
[20.8,30.7] (30.7,34.9] (34.9,40.5] (40.5,48.9] 
          9           9           9           9 
## Classes de salario
salario.cut <- with(milsa, cut(Salario, breaks = quantile(Salario),
                               include.lowest = TRUE))
table(salario.cut)
salario.cut
   [4,7.55] (7.55,10.2] (10.2,14.1] (14.1,23.3] 
          9           9           9           9 
## Tabela cruzada
table(idade.cut, salario.cut)
             salario.cut
idade.cut     [4,7.55] (7.55,10.2] (10.2,14.1] (14.1,23.3]
  [20.8,30.7]        4           2           2           1
  (30.7,34.9]        1           3           3           2
  (34.9,40.5]        1           3           2           3
  (40.5,48.9]        3           1           2           3
prop.table(table(idade.cut, salario.cut), margin = 1)
             salario.cut
idade.cut      [4,7.55] (7.55,10.2] (10.2,14.1] (14.1,23.3]
  [20.8,30.7] 0.4444444   0.2222222   0.2222222   0.1111111
  (30.7,34.9] 0.1111111   0.3333333   0.3333333   0.2222222
  (34.9,40.5] 0.1111111   0.3333333   0.2222222   0.3333333
  (40.5,48.9] 0.3333333   0.1111111   0.2222222   0.3333333
```

</div>

Caso queiramos definir um número menor de classes podemos fazer como no
exemplo a seguir onde cada variável é dividida em 3 classes e gerando um
tabela de cruzamento $3\  \times \ 3$.

<div class="sourceCode">

``` {.sourceCode .r}
idade.cut2 <- with(milsa, cut(Idade,
                              breaks = quantile(Idade, seq(0, 1, length = 4)),
                              include.lowest = TRUE))
salario.cut2 <- with(milsa, cut(Salario,
                                breaks = quantile(Salario, seq(0, 1, length = 4)),
                                include.lowest = TRUE))
table(idade.cut2, salario.cut2)
             salario.cut2
idade.cut2    [4,8.65] (8.65,12.9] (12.9,23.3]
  [20.8,32.1]        5           5           2
  (32.1,37.8]        4           3           5
  (37.8,48.9]        3           4           5
prop.table(table(idade.cut2, salario.cut2), margin = 1)
             salario.cut2
idade.cut2     [4,8.65] (8.65,12.9] (12.9,23.3]
  [20.8,32.1] 0.4166667   0.4166667   0.1666667
  (32.1,37.8] 0.3333333   0.2500000   0.4166667
  (37.8,48.9] 0.2500000   0.3333333   0.4166667
```

</div>

O gráfico adequado para representar duas variáveis quantitativas é um
diagrama de dispersão. Note que se as variáveis envolvidas puderem ser
classificadas como "explicativa" e "resposta" devemos colocar a primeira
no eixo X e a segunda no eixo Y. Neste exemplo é razoável admitir que a
idade deve explicar, ao menos parcialmente, o salário e portanto fazemos
o gráfico com idade no eixo X. Note que na função `plot()`, podemos usar
tanto os argumentos `x` e `y`, quanto o formato de fórmula (como visto
anteriormente).

<div class="sourceCode">

``` {.sourceCode .r}
plot(x = milsa$Idade, y = milsa$Salario)
plot(Salario ~ Idade, data = milsa)
```

</div>

![](media/file21.png)

Para quantificar a associação entre variáveis deste tipo, usamos o
coeficiente de correlação. A função `cor()` possui opção para três
coeficientes de correlação, tendo como *default* o coeficiente de
correlação linear de Pearson.

<div class="sourceCode">

``` {.sourceCode .r}
with(milsa, cor(Idade, Salario))
[1] 0.3651397
with(milsa, cor(Idade, Salario, method = "kendall"))
[1] 0.214456
with(milsa, cor(Idade, Salario, method = "spearman"))
[1] 0.2895939
```

</div>

</div>

</div>

<div id="ch007.xhtml#exercícios-15" class="section level2 unnumbered">

Exercícios
----------

1.  Experimente as funções `mean()`, `var()`, `sd()`, `median()`,
    `quantile()` nos dados mostrados anteriormente (`milsa`). Veja a
    documentação das funções e as opções de uso.
2.  Carregue o conjunto de dados `women` com `data(women)`. Veja o que
    são os dados com `help(women)`, e faça uma análise descritiva
    adequada.

3.  Carregue o conjunto de dados `USArrests` com `data(USArrests)`.
    Examine a sua documentação com `help(USArrests)` e responda as
    perguntas a seguir:
    1.  Qual o número médio e mediano de cada um dos crimes?
    2.  Encontre a mediana e quartis para cada crime.
    3.  Encontre o número máximo e mínimo para cada crime.
    4.  Faça um gráfico adequado para o número de assassinatos
        (`Murder`).
    5.  Faça um *boxplot* para o número de estupros (`Rape`).
    6.  Verifique se há correlação entre os diferentes tipos de crime.
    7.  Verifique se há correlação entre os crimes e a proporção de
        população urbana.
    8.  Encontre os estados com maior e menor ocorrência de cada tipo de
        crime.
    9.  Encontre os estados com maior e menor ocorrência per capta de
        cada tipo de crime.
    10. Encontre os estados com maior e menor ocorrência do total de
        crimes.
    11. Calcule a média de crimes (entre `Murder`, `Assault` e `Rape`)
        para cada estado.

A resolução de todos os exercícios desta página está disponível neste
[script](scripts/analise-exploratoria-exercicios.R).

<!--chapter:end:06-analise-exploratoria.Rmd-->

</div>

</div>

[]{#ch008.xhtml}

<div id="ch008.xhtml#probabilidade-e-variáveis-aleatórias"
class="section level1">

[7]{.header-section-number} Probabilidade e variáveis aleatórias
================================================================

<div
id="ch008.xhtml#conceitos-básicos-sobre-distribuições-de-probabilidade"
class="section level2">

[7.1]{.header-section-number} Conceitos básicos sobre distribuições de probabilidade
------------------------------------------------------------------------------------

O objetivo desta sessão é mostrar o uso de funções do R em problemas de
probabilidade. Exercícios que podem (e devem!) ser resolvidos
analiticamente, serão utilizados para ilustrar o uso do programa e
alguns de seus recursos para análises numéricas.

Os problemas desta sessão foram retirados do livro de [Bussab e Morettin
(2017)](https://www.ime.usp.br/~pam/EstBas.html). Veja também os códigos
do R dos exemplos do livro para os capítulos 6 e 7, disponíveis
[aqui](https://rpubs.com/EstatBasica/Introd).

**Exemplo 1**: (Adaptado de Bussab e Morettin, cap. 7 ex. 1)

Dada a função

[\$\$ \\ f(x) = \\left\\{ \\begin{array}{ll} 2 e\^{-2x} & \\mbox{ , se
\$ \\; x \\geq 0\$} \\cr 0 & \\mbox{ , se \$ \\; x &lt; 0\$}
\\end{array} \\right. \\ \$\$]{.math .display}

a.  Mostre que está função é uma f.d.p.
b.  Calcule a probabilidade de que $X > 1$.
c.  calcule a probabilidade de que $0.2 < X < 0.8$.

Para ser f.d.p. a função não deve ter valores negativos e deve integrar
1 em seu domínio. Vamos começar definindo esta função como uma *função*
no R para qual daremos o nome de `f1`.

<div class="sourceCode">

``` {.sourceCode .r}
f1 <- function(x){
    fx <- ifelse(x < 0, 0, 2 * exp(-2 * x))
    return(fx)
}
```

</div>

A seguir fazemos o gráfico da função. Como a função tem valores
positivos para $x$ no intervalo de zero a infinito, temos que definir um
limite em $x$ até onde vai o gráfico da função. Vamos achar este limite
tentando vários valores, conforme mostrado nos comandos abaixo.

<div class="sourceCode">

``` {.sourceCode .r}
par(mfrow = c(2, 2))
plot(f1)
plot(f1, from = 0, to = 5)
plot(f1, from = 0, to = 7)
plot(f1, from = 0, to = 10)
par(mfrow = c(1, 1))
```

</div>

![](media/file22.png)

Para verificar que a integral da função é igual a 1 podemos usar a
função `integrate()`, que efetua integração numérica. A função recebe
como argumentos o objeto com a função a ser integrada e os limites de
integração. Neste exemplo o objeto é `f1` definido acima, e o domínio da
função é $\lbrack 0,\infty)$. A saída da função mostra o valor da
integral acima, e o erro máximo da aproximação numérica.

<div class="sourceCode">

``` {.sourceCode .r}
integrate(f1, lower = 0, upper = Inf)
1 with absolute error < 5e-07
```

</div>

Para fazer os cálculos pedidos nos itens (b) e (c) lembramos que a
probabilidade é dada pela área sob a curva da função no intervalo
pedido. Desta forma as soluções seriam dadas pelas expressões

$$\begin{array}{rcl}
p_{b} & = & {P(X > 1) = \int_{1}^{\infty}f(x)dx = \int_{1}^{\infty}2\, e^{- 2x}dx} \\
p_{c} & = & {P(0,2 < X < 0,8) = \int_{0,2}^{0,8}f(x)dx = \int_{0.2}^{0.8}2\, e^{- 2x}dx\,} \\
\end{array}$$

cuja representação gráfica é mostrada na abaixo.

Os comandos a seguir mostram como fazer o gráfico dessas funções. O
comando `plot()` desenha o gráfico principal, e para destacar as áreas
que correspondem às probabilidades pedidas vamos usar a função
`polygon()`. Esta função adiciona a um gráfico um polígono que é
definido pelas coordenadas de seus vértices. Para sombrear a área usa-se
o argumento `density`. Finalmente, para escrever um texto no gráfico
usamos a função `text()` com as coordenadas de posição do texto.

<div class="sourceCode">

``` {.sourceCode .r}
plot(f1, from = 0, to = 5)
polygon(x = c(1, seq(1, 5, length.out = 20)),
        y = c(0, f1(seq(1, 5,length.out = 20))),
        density = 10)
polygon(x = c(0.2, seq(0.2, 0.8, length.out = 20), 0.8),
        y = c(0, f1(seq(0.2, 0.8, length.out = 20)), 0),
        col = "gray")
text(x = c(1.2, 0.5), y = c(0.1, 0.2),
     c(expression(p[b], p[c])))
```

</div>

![](media/file23.png)

Oara obter as probabilidades pedidas usamos a função `integrate()`.

<div class="sourceCode">

``` {.sourceCode .r}
integrate(f1, lower = 1, upper = Inf)
0.1353353 with absolute error < 2.1e-05
integrate(f1, lower = 0.2, upper = 0.8)
0.4684235 with absolute error < 5.2e-15
```

</div>

**Exemplo 2**: (Adaptado de Bussab e Morettin, cap. 7 ex. 10)

A demanda diária de arroz em um supermercado, em centenas de quilos, é
uma v.a $X$ com f.d.p. dada por

[\$\$\\begin{eqnarray} f(x) = \\left\\{ \\begin{array}{ll} \\frac{2}{3}x
\\mbox{ , se \$0 \\leq x &lt; 1\$} \\cr -\\frac{x}{3} + 1 \\mbox{ , se
\$ 1 \\leq x &lt; 3\$} \\cr 0 \\mbox{ , se \$x &lt; 0\$ ou \$x \\geq
3\$} \\end{array} \\right. \\end{eqnarray}\$\$]{.math .display}

a.  Calcular a probabilidade de que sejam vendidos mais que 150 kg.
b.  Calcular a venda esperada em 30 dias.

Novamente começamos definindo um objeto do R que contém a função dada
acima. Neste caso definimos um vetor do mesmo tamanho do argumento `x`
para armazenar os valores de $f(x)$ e a seguir preenchemos os valores
deste vetor para cada faixa de valor de $x$:

<div class="sourceCode">

``` {.sourceCode .r}
f2 <- function(x){
  fx <- numeric(length(x))
  fx[x < 0] <- 0
  fx[x >= 0 & x < 1] <- (2/3) * x[x >= 0 & x < 1]
  fx[x >= 1 & x < 3] <- (-1/3) * x[x >= 1 & x < 3] + 1
  fx[x >= 3] <- 0
  return(fx)
}
```

</div>

A seguir verificamos que a integral da função é 1 e fazemos o seu
gráfico conforme mostrado abaixo:

<div class="sourceCode">

``` {.sourceCode .r}
integrate(f2, 0, 3) ## verificando que a integral vale 1
1 with absolute error < 1.1e-15
plot(f2, -1, 4)     ## fazendo o gráfico da função
```

</div>

![](media/file24.png)

Agora vamos responder às questões levantadas. Na questão (a) pede-se a
probabilidade de que sejam vendidos mais que 150 kg (1,5 centenas de
quilos), portanto a probabilidade $P\lbrack X > 1,5\rbrack$. A
probabilidade corresponde à área sob a função no intervalo pedido, ou
seja, $P\lbrack X > 1,5\rbrack = \int_{1,5}^{\infty}f(x)dx$, que pode
ser vista na figura abaixo.

<div class="sourceCode">

``` {.sourceCode .r}
plot(f2, -1, 4)
polygon(x = c(1.5, 1.5, 3), y = c(0, f2(1.5), 0), dens = 10)
```

</div>

![](media/file25.png)

A integral pode então ser resolvida numericamente com o comando:

<div class="sourceCode">

``` {.sourceCode .r}
integrate(f2, 1.5, 3)
0.375 with absolute error < 4.2e-15
```

</div>

A venda esperada em trinta dias é 30 vezes o valor esperado de venda em
um dia. Para calcular a esperança $E\lbrack X\rbrack = \int xf(x)dx$
definimos uma nova função e resolvemos a integral. A função
`integrate()` retorna uma lista onde um dos elementos (`value`) é o
valor da integral.

<div class="sourceCode">

``` {.sourceCode .r}
ef2 <- function(x) { x * f2(x) }
integrate(ef2, 0, 3)
1.333333 with absolute error < 7.3e-05
30 * integrate(ef2, 0, 3)$value
[1] 40
```

</div>

Finalmente lembramos que os exemplos discutidos aqui são simples e não
requerem soluções numéricas, devendo ser resolvidos analiticamente.
Utilizamos estes exemplos somente para ilustrar a obtenção de soluções
numéricas com o uso do R, que na prática deve ser utilizado em problemas
mais complexos onde soluções analíticas não são triviais ou mesmo
impossíveis.

</div>

<div id="ch008.xhtml#exercícios-16" class="section level2 unnumbered">

Exercícios
----------

1.  (Adaptado de Bussab e Morettin, cap. 7, ex. 28). Em uma determinada
    localidade a distribuição de renda, em u.m. (unidade monetária) é
    uma variável aleatória $X$ com função de distribuição de
    probabilidade: [\$\$ f(x) = \\left\\{ \\begin{array}{ll}
    \\frac{1}{10}x + \\frac{1}{10} & \\mbox{ se \$0 \\leq x \\leq 2\$}
    \\cr -\\frac{3}{40}x + \\frac{9}{20} & \\mbox{ se \$ 2 &lt; x \\leq
    6\$} \\cr 0 & \\mbox{ se \$x &lt; 0\$ ou \$x &gt; 6\$} \\end{array}
    \\right. \$\$]{.math .display}
    a.  Mostre que $f(x)$ é uma f.d.p.
    b.  Qual a renda média nesta localidade?
    c.  Calcule a probabilidade de encontrar uma pessoa com renda acima
        de 4,5 u.m. e indique o resultado no gráfico da distribuição.
2.  Sabe-se que uma variável aleatória contínua $X$ é equiprovável no
    intervalo 10 e 20.
    a.  Apresente o gráfico da função densidade de probabilidade.
    b.  Calcule $P(X < 15)$.
    c.  Calcule $P(12 \leq X \leq 18)$.
    d.  Calcule $E(X)$ e $V(X)$.
3.  Dois jogadores se alternam lançando dois dados equilibrados. O
    jogador A vence o jogo se ocorrer soma 6, enquanto B vencerá se
    ocorrer 7. Faça um estudo de simulação para responder as seguintes
    questões:
    a.  Se A começa jogando, qual é a sua probabilidade de vitória?
    b.  Qual é a probabilidade do iniciante, escolhido ao acaso, vencer
        o jogo?
4.  A duração, em anos, de uma certa lâmpada especial é uma variável
    aleatória contínua com densidade dada por: [\$\$ f(x) = \\left\\{
    \\begin{array}{ll} 2 \\exp\^{-2x} & x \\geq 0 \\cr 0 & x &lt; 0
    \\end{array} \\right. \$\$]{.math .display}
    a.  Crie uma função para calcular a função de distribuição acumulado
        de $X$.
    b.  Calcule $P(X > 2)$.
    c.  Calcule $P(0.5 < X < 1.2)$.
    d.  Calcule $P(X > 3)$.
    e.  Calcule $P(X < 3|X > 1)$.
5.  (Desafio - Problema da ruína do jogador) Dois jogadores participam
    de um jogo com uma moeda que tem probabilidade de cara igual a $p$ e
    de coroa igual a $q$, sujeito a $p + q = 1$. O jogador A inicia o
    jogo com $i$ fichas e ganha mais uma de B, cada vez que der cara. O
    jogador B começa com $N - i$ fichas e, em cada lançamento que
    resultar coroa, ganha uma ficha de A. Para enfatizar a dependência
    do número inicial de fichas $i$, denomine por $p_{(i)}$ a
    probabilidade do jogador A ficar com todas as fichas, o que implica
    na ruína de B. Condicione no resultado do primeiro lançamento da
    moeda, para estabelecer uma relação de recorrência entre os
    $p_{(i)\prime s}$. Usando $p_{(0)} = 0$ e $p_{N} = 1$, mostre via
    simulação que $p_{(i)} = \frac{1 - (q/p)^{i}}{1 - (q/p)^{N}}$ para
    $p \neq \frac{1}{2}$ e $p_{(i)} = \frac{i}{N}$ para
    $p = \frac{1}{2}$.

</div>

<div id="ch008.xhtml#distribuições-de-probabilidade"
class="section level2">

[7.2]{.header-section-number} Distribuições de Probabilidade
------------------------------------------------------------

O R inclui funcionalidade para operações com distribuições de
probabilidades. Para cada distribuição há 4 operações básicas indicadas
pelas letras:

-   `d` calcula a densidade de probabilidade $f(x)$ no ponto $x$.
-   `p` calcula a função de probabilidade acumulada $F(x)$ no ponto $x$.
-   `q` calcula o quantil correspondente a uma dada probabilidade.
-   `r` retorna uma amostra aleatória da distribuição.

Para usar as funções deve-se combinar uma das letras acima com uma
abreviatura do nome da distribuição. Por exemplo, para calcular
probabilidades usamos: `pnorm()` para normal, `pexp()` para exponencial,
`pbinom()` para binomial, `ppois()` para Poisson e assim por diante.

Vamos ver com mais detalhes algumas distribuições de probabilidades.

<div id="ch008.xhtml#distribuição-normal" class="section level3">

### [7.2.1]{.header-section-number} Distribuição Normal

A funcionalidade para distribuição normal é implementada por argumentos
que combinam as letras acima com o termo `norm`. Vamos ver alguns
exemplos com a distribuição normal padrão. Por `default` as funções
assumem a distribuição normal padrão $N(\mu = 0,\sigma^{2} = 1)$.

<div class="sourceCode">

``` {.sourceCode .r}
dnorm(-1)
[1] 0.2419707
pnorm(-1)
[1] 0.1586553
qnorm(0.975)
[1] 1.959964
rnorm(10)
 [1] -0.50219235  0.13153117 -0.07891709  0.88678481  0.11697127  0.31863009
 [7] -0.58179068  0.71453271 -0.82525943 -0.35986213
```

</div>

O primeiro valor acima, de `dnorm(-1)`, corresponde ao valor da
densidade da normal

$$f(x) = \frac{1}{\sigma\sqrt{2\pi}}\exp\left\lbrack - \frac{1}{2}\left( \frac{x - \mu}{\sigma} \right)^{2} \right\rbrack$$

com parâmetros $(\mu = 0,\sigma^{2} = 1)$ no ponto $x = - 1$. Portanto,
o mesmo valor seria obtido substituindo $x$ por $- 1$ na expressão da
normal:

<div class="sourceCode">

``` {.sourceCode .r}
mu <- 0
sigma <- 1
x <- -1
(1/(sigma * sqrt(2*pi))) * exp((-1/2) * ((x - mu)/sigma)^2)
[1] 0.2419707
```

</div>

A função `pnorm(-1)` calcula a probabilidade $P(X \leq - 1)$. O comando
`qnorm(0.975)` calcula o valor de $a$ tal que $P(X \leq a) = 0.975$.
Finalmente, o comando `rnorm(10)` gera uma amostra aleatória de 10
elementos da normal padrão. Note que os valores que você obtêm rodando
este comando podem ser diferentes dos mostrados acima.

As funções acima possuem argumentos adicionais, para os quais valores
padrão (*default*) foram assumidos, e que podem ser modificados. Usamos
`args()` para ver os argumentos de uma função e `help()` para visualizar
a documentação detalhada:

<div class="sourceCode">

``` {.sourceCode .r}
args(rnorm)
function (n, mean = 0, sd = 1) 
NULL
```

</div>

As funções relacionadas à distribuição normal possuem os argumentos
`mean` e `sd` para definir a média e o desvio padrão da distribuição que
podem ser modificados como nos exemplos a seguir. Note nestes exemplos
que os argumentos podem ser passados de diferentes formas.

<div class="sourceCode">

``` {.sourceCode .r}
qnorm(0.975, mean = 100, sd = 8)
[1] 115.6797
qnorm(0.975, m = 100, s = 8)
[1] 115.6797
qnorm(0.975, 100, 8)
[1] 115.6797
```

</div>

> **Observação**: na segunda linha de comando acima, foi utilizado um
> recurso do R chamado *partial matching*. Isso significa que nomes de
> argumentos de funções podem ser especificados pelo seu nome parcial,
> ou seja, com apenas o início do nome, desde que não haja ambiguação
> com outros argumentos.

Para informações mais detalhadas pode-se usar `help()`. O comando

<div class="sourceCode">

``` {.sourceCode .r}
help(rnorm)
```

</div>

irá exibir em uma janela a documentação da função que pode também ser
chamada com `?rnorm`. Note que ao final da documentação são apresentados
exemplos que podem ser rodados pelo usuário e que auxiliam na
compreensão da funcionalidade. Note também que as 4 funções relacionadas
à distribuição normal são documentadas conjuntamente, portanto
`help(rnorm)`, `help(qnorm)`, `help(dnorm)` e `help(pnorm)` irão exibir
a mesma documentação.

Cálculos de probabilidades usuais, para os quais utilizavamos tabelas
estatísticas podem ser facilmente obtidos como no exemplo a seguir.

Seja $X$ uma v.a com distribuição $N(100,100)$. Calcular as
probabilidades:

-   $P\lbrack X < 95\rbrack$
-   $P\lbrack 90 < X < 110\rbrack$
-   $P\lbrack X > 95\rbrack$

Calcule estas probabilidades de forma usual, usando a tabela da normal.
Depois compare com os resultados fornecidos pelo R. Os comandos do R
para obter as probabilidades pedidas são:

<div class="sourceCode">

``` {.sourceCode .r}
## P[X < 95]
pnorm(95, 100, 10)
[1] 0.3085375
## P[90 < X < 110]
pnorm(110, 100, 10) - pnorm(90, 100, 10)
[1] 0.6826895
## P[X > 95] = 1 - P[X < 95]
1 - pnorm(95, 100, 10)
[1] 0.6914625
pnorm(95, 100, 10, lower.tail = FALSE) # melhor
[1] 0.6914625
```

</div>

Note que a última probabilidade foi calculada de duas formas diferentes,
a segunda usando o argumento `lower.tail` que implementa um algorítmo de
cálculo de probabilidades mais estável numericamente, e essa forma é
preferida no lugar de usar o complementar.

A seguir vamos ver comandos para fazer gráficos de distribuições de
probabilidade. Vamos fazer gráficos de funções de densidade e de
probabilidade acumulada. Estude cuidadosamente os comandos abaixo e
verifique os gráficos por eles produzidos.

A figura abaixo mostra gráficos da densidade (esquerda) e probabilidade
acumulada (direita) da normal padrão, produzidos com os comandos a
seguir. Para fazer o gráfico consideramos valores de $X$ entre -3 e 3
que correspondem a +/- três desvios padrões da média, faixa que
concentra 99,73% da massa de probabilidade da distribuição normal.

<div class="sourceCode">

``` {.sourceCode .r}
par(mfrow = c(1, 2))
plot(dnorm, from = -3, to = 3)
plot(pnorm, from = -3, to = 3)
par(mfrow = c(1, 1))
```

</div>

![](media/file26.png)

> VEJA a página de ajuda da função `plot.function()` para entender os
> argumentos e demais funcionalidades desta função gráfica para plotar
> gráficos de funções

A seguinte figura mostra gráficos da densidade (esquerda) e
probabilidade acumulada (direita) da $N(100,64)$. Para fazer estes
gráficos tomamos uma sequência de valores de $X$ entre 70 e 130 e para
cada um deles calculamos o valor das funções $f(x)$ e $F(x)$. Depois
unimos os pontos $(x,f(x))$ em um gráfico e $(x,F(x))$ no outro.

<div class="sourceCode">

``` {.sourceCode .r}
par(mfrow = c(1, 2))
x <- seq(70, 130, length.out = 100)
fx <- dnorm(x, 100, 8)
plot(x, fx, type = "l")
Fx <- pnorm(x, 100, 8)
plot(x, Fx, type = "l")
par(mfrow = c(1, 1))
```

</div>

![](media/file27.png)

Note que, alternativamente, os mesmos gráficos poderiam ser produzidos
com os comandos a seguir, onde fazemos usa da função `plot.function()`.

<div class="sourceCode">

``` {.sourceCode .r}
par(mfrow = c(1, 2))
plot(function(x) dnorm(x, 100, 8), from = 70, to = 130)
plot(function(x) pnorm(x, 100, 8), from = 70, to = 130)
par(mfrow = c(1, 1))
```

</div>

![](media/file28.png)

Comandos usuais do R podem ser usados para modificar a aparência dos
gráficos. Por exemplo, podemos incluir títulos e mudar texto dos eixos
conforme mostrado abaixo.

<div class="sourceCode">

``` {.sourceCode .r}
plot(dnorm, from = -3, to = 3,
     xlab = "Valores de X",
     ylab = "Densidade de probabilidade")
title("Distribuicão Normal\nX ~ N(0, 1)")
```

</div>

![](media/file29.png)

Os demais comandos abaixo mostram como colocar diferentes densidades em
um mesmo gráfico, usando o argumento `add = TRUE`.

<div class="sourceCode">

``` {.sourceCode .r}
plot(function(x) dnorm(x, 100, 8), 60, 140, ylab = 'f(x)')
plot(function(x) dnorm(x, 90, 8), 60, 140, add = TRUE, col = 2)
plot(function(x) dnorm(x, 100, 15), 60, 140, add = TRUE, col = 3)
legend(120, 0.05, fill = 1:3,
       legend = c("N(100,64)", "N(90,64)", "N(100,225)"))
```

</div>

![](media/file30.png)

</div>

<div id="ch008.xhtml#distribuição-binomial" class="section level3">

### [7.2.2]{.header-section-number} Distribuição Binomial

Cálculos para a distribuição binomial são implementados combinando as
letras básicas vistas acima com o termo `binom`. Vamos primeiro
investigar os argumentos e a documentação com `args()` e `help()`.

<div class="sourceCode">

``` {.sourceCode .r}
args(dbinom)
function (x, size, prob, log = FALSE) 
NULL
```

</div>

<div class="sourceCode">

``` {.sourceCode .r}
help(dbinom)
```

</div>

Seja $X$ uma v.a com distribuição binomial, com $n = 10$ e $p = 0.35$.
Vamos ver os comandos do R para:

-   Fazer o gráfico da função de probabilidade.
-   Idem para a função de distribuição acumulada.
-   Calcular $P(X = 7)$.
-   Calcular $P(X \leq 7)$.
-   Calcular $P(X > 7)$.
-   Calcular $P(3 < X \leq 6)$.

Note que sendo uma distribuição discreta de probabilidades os gráficos
são diferentes dos obtidos para a distribuição normal e os cálculos de
probabilidades devem considerar as probabilidades nos pontos
específicos. Os gráficos das funções de probabilidade e distribuição são
mostrados abaixo.

<div class="sourceCode">

``` {.sourceCode .r}
par(mfrow = c(1, 2))
x <- 0:10
fx <- dbinom(x, size = 10, prob = 0.35)
plot(x, fx, type = "h")
Fx <- pbinom(x, size = 10, prob = 0.35)
plot(x, Fx, type = "s")
par(mfrow = c(1, 1))
```

</div>

![](media/file31.png)

As probabilidades pedidas são obtidas com os comandos a seguir.

<div class="sourceCode">

``` {.sourceCode .r}
## P[X = 7]
dbinom(7, size = 10, prob = 0.35)
[1] 0.02120302
## P[X <= 7]
pbinom(7, size = 10, prob = 0.35)
[1] 0.9951787
# OU
sum(dbinom(0:7, size = 10, prob = 0.35))
[1] 0.9951787
## P[X > 7]
1 - pbinom(7, size = 10, prob = 0.35)
[1] 0.004821265
pbinom(7, size = 10, prob = 0.35, lower.tail = FALSE) # melhor
[1] 0.004821265
## P[3 < X <= 6]
pbinom(6, 10, 0.35) - pbinom(3, 10, 0.35)
[1] 0.4601487
# OU
sum(dbinom(4:6, 10, 0.35))
[1] 0.4601487
```

</div>

</div>

<div id="ch008.xhtml#distribuição-de-poisson" class="section level3">

### [7.2.3]{.header-section-number} Distribuição de Poisson

**Definição:** Seja um experimento realizado nas seguintes condições: i.
As ocorrências são independentes; ii. As ocorrências são aleatórias;
iii. A variável aleatória $X$ é o número de ocorrências de um evento
**ao longo de algum intervalo** (de tempo ou espaço);

Denominamos esse experimento de **processo de Poisson**. Vamos associar
a v.a $X$ como sendo o número de ocorrências em um intervalo. Portanto
$X$ poderá assumir os valores $0,1,\ldots,$ (sem limite superior).

A distribuição de Poisson é utilizada para descrever a probabilidade do
**número de ocorrências** em um **intervalo contínuo** (de tempo ou
espaço). No caso da distribuição binomial, a variável de interesse era o
número de sucessos em um **intervalo discreto** ($n$ ensaios de
Bernoulli). A unidade de medida (tempo ou espaço) é uma variável
contínua, mas a *variável aleatória*, **número de ocorrências**, é
discreta.

Uma v.a $X$ segue o modelo de Poisson se surge a partir de um processo
de Poisson, e sua **função de probabilidade** for dada por

$$P(X = x) = \frac{e^{- \mu}\mu^{x}}{x!},\quad\quad x = 0,1,\ldots$$

onde

$$\mu = \lambda \cdot t$$

O parâmetro $\mu$ indica a taxa de ocorrência ($\lambda$) por unidade de
medida ($t$), ou seja,

$$\lambda = \text{taxa\ de\ ocorrência}\quad\text{e}\quad t = \text{intervalo\ de\ tempo\ ou\ espaço}$$

-   Notação: $X \sim \text{Pois}(\mu)$
-   Esperança e variância: $\text{E}(X) = \mu = \text{Var}(X)$

Alguns exemplos de gráficos da distribuição de Poisson com diferentes
valores do parâmetro $\mu$.

<div class="sourceCode">

``` {.sourceCode .r}
par(mfrow=c(2,2))
plot(0:30, dpois(x = 0:30, lambda = 1), type = "h",
     xlab = "X", ylab = "P[X = x]", main = expression(mu == 1),
     ylim = c(0,.4))
plot(0:30, dpois(x = 0:30, lambda = 5), type = "h",
     xlab = "X", ylab = "P[X = x]", main = expression(mu == 5),
     ylim = c(0,.4))
plot(0:30, dpois(x = 0:30, lambda = 10), type = "h",
     xlab = "X", ylab = "P[X = x]", main = expression(mu == 10),
     ylim = c(0,.4))
plot(0:30, dpois(x = 0:30, lambda = 15), type = "h",
     xlab = "X", ylab = "P[X = x]", main = expression(mu == 15),
     ylim = c(0,.4))
```

</div>

![](media/file32.png)

-   **Exemplo**: As chamadas telefônicas chegam a uma delegacia de
    polícia à uma taxa de 8 chamadas por hora, em dias úteis.
    a.  Quantas chamadas de emergência são esperadas em um período de 15
        minutos?
    b.  Qual a probabilidade de nenhuma chamada em um período de 15
        minutos?
    c.  Qual a probabilidade de ocorrer pelo menos duas chamadas no
        período de 15 minutos?
    d.  Qual a probabilidade de ocorrer exatamente duas chamadas em 20
        minutos?

<div class="sourceCode">

``` {.sourceCode .r}
## a) E(X) = mu = lambda . t
lambda <- 8/60 # 8 chamadas/60 minutos
t <- 15 # 15 minutos
(mu <- lambda * t)
[1] 2
## b) P[x = 0]
ppois(0, mu)
[1] 0.1353353
dpois(0, mu)
[1] 0.1353353
## c) P[X >= 2] = 1 - P[X < 2]
1 - ppois(1, mu)
[1] 0.5939942
ppois(1, mu, lower.tail = FALSE)
[1] 0.5939942
## d) P[X = 2]
t <- 20
(mu <- lambda * t)
[1] 2.666667
dpois(2, mu)
[1] 0.2470523
```

</div>

-   **Exemplo:** Suponha que 150 erros de impressão são distribuídos
    aleatoriamente em um livro de 200 páginas. Encontre a probabilidade
    de que em 2 páginas contenham:
    a.  nenhum erro de impressão
    b.  três erros de impressão
    c.  um ou mais erros de impressão

<div class="sourceCode">

``` {.sourceCode .r}
## lambda = taxa de ocorrência por página
lambda <- 150/200
## intervalo de interesse
t <- 2
## Parâmetro mu = lambda . t
(mu <- lambda * t)
[1] 1.5
## a) P[X = 0]
dpois(0, mu)
[1] 0.2231302
## b) P[X = 3]
dpois(3, mu)
[1] 0.1255107
## c) P[X >= 1] = 1 - P[X < 1]
1 - ppois(0, mu)
[1] 0.7768698
ppois(0, mu, lower.tail = FALSE)
[1] 0.7768698
```

</div>

</div>

<div id="ch008.xhtml#distribuição-uniforme" class="section level3">

### [7.2.4]{.header-section-number} Distribuição Uniforme

<div id="ch008.xhtml#uniforme-contínua" class="section level4">

#### [7.2.4.1]{.header-section-number} Uniforme Contínua

Para a distribuição uniforme *contínua* usa-se as funções `*unif()` onde
`*` deve ser $p$, $q$, $d$ ou $r$ como mencionado anteriormente. Nos
comandos a seguir inspecionamos os argumentos, sorteamos 5 valores da
$U(0,1)$ e calculamos a probabilidade acumulada até 0,75.

<div class="sourceCode">

``` {.sourceCode .r}
args(runif)
function (n, min = 0, max = 1) 
NULL
runif(5)
[1] 0.5358112 0.7108038 0.5383487 0.7489722 0.4201015
punif(0.75)
[1] 0.75
```

</div>

Portanto, o *default* é uma distribuição uniforme no intervalo
$\lbrack 0,1\rbrack$ e os argumentos opcionais são `min` e `max`. Por
exemplo, para simular 5 valores de $X \sim U(5,20)$ usamos:

<div class="sourceCode">

``` {.sourceCode .r}
runif(5, min = 5, max = 20)
[1]  7.571303 16.554524 18.229304 13.236451  9.165856
```

</div>

</div>

<div id="ch008.xhtml#uniforme-discreta" class="section level4">

#### [7.2.4.2]{.header-section-number} Uniforme Discreta

Não há entre as funções básicas do R uma função específica para a
distribuição uniforme discreta com opções de prefixos $r,d,p$ e $d$,
provavelmente devido a sua simplicidade, embora algumas outras funções
possam ser usadas. Por exemplo para sortear números pode-se usar
`sample()`, como no exemplo a seguir onde são sorteados 15 valores de
uma uniforme discreta com valores (inteiros) entre 1 e 10
($X \sim U_{d}(1,10)$).

<div class="sourceCode">

``` {.sourceCode .r}
sample(1:10, size = 15, replace = TRUE)
 [1] 2 3 4 4 4 5 7 9 4 2 6 7 1 6 9
```

</div>

</div>

</div>

<div id="ch008.xhtml#a-função-sample" class="section level3">

### [7.2.5]{.header-section-number} A função `sample()`

A função `sample()` **não** é restrita à distribuição uniforme discreta,
podendo ser usada para sorteios, com ou sem reposição (argumento
`replace`, que por padrão é `FALSE`, ou seja, sem reposição), com a
possibilidade de associar diferentes probabilidades a cada elemento
(argumento `prob`, que por padrão associa probabilidades iguais para
todos os elementos).

<div class="sourceCode">

``` {.sourceCode .r}
args(sample)
function (x, size, replace = FALSE, prob = NULL) 
NULL
```

</div>

Vejamos alguns exemplos:

-   Sorteio de 3 números entre inteiros de 0 a 20.

<div class="sourceCode">

``` {.sourceCode .r}
sample(0:20, size = 3)
[1]  8 20 10
```

</div>

-   Sorteio de 5 números entre os elementos de um certo vetor `x`.

<div class="sourceCode">

``` {.sourceCode .r}
x <- c(23, 34, 12, 22, 17, 28, 18, 19, 20, 13, 18)
sample(x, size = 5)
[1] 18 23 20 28 22
```

</div>

-   Sorteio de 10 números entre os possíveis resultados do lançamento de
    um dado, com reposição.

<div class="sourceCode">

``` {.sourceCode .r}
sample(1:6, size = 10, replace = TRUE)
 [1] 6 3 5 6 3 6 4 3 3 3
```

</div>

-   Idem ao anterior, porém agora com a probabilidade de cada face
    proporcional ao valor da face.

<div class="sourceCode">

``` {.sourceCode .r}
sample(1:6, size = 10, replace = TRUE,  prob = 1:6)
 [1] 6 4 3 6 5 3 2 6 5 5
```

</div>

Este último exemplo ilustra ainda que os valores passados para o
argumento `prob` não precisam ser probabilidades, são apenas entendidos
como **pesos**. A própria função trata isto internamente fazendo a
ponderação adequada.

</div>

</div>

<div id="ch008.xhtml#complementos-sobre-distribuições-de-probabilidade"
class="section level2">

[7.3]{.header-section-number} Complementos sobre distribuições de probabilidade
-------------------------------------------------------------------------------

Agora que já nos familiarizamos com o uso das distribuições de
probabilidade vamos ver alguns detalhes adicionais sobre seu
funcionamento.

<div id="ch008.xhtml#probabilidades-e-integrais" class="section level3">

### [7.3.1]{.header-section-number} Probabilidades e integrais

A probabilidade de um evento em uma distribuição contínua é a área sob a
curva da distribuição. Vamos reforçar esta idéia revisitando um exemplo
visto na distribuição normal.

Seja $X$ uma v.a com distribuição $N(100,100)$. Para calcular a
probabilidade $P(X < 95)$ usamos o comando:

<div class="sourceCode">

``` {.sourceCode .r}
pnorm(95, mean = 100, sd = 10)
[1] 0.3085375
```

</div>

Vamos agora "esquecer" o comando `pnorm()` e ver uma outra forma de
resolver usando integração numérica. Lembrando que a normal tem a função
de densidade dada por

$$f(x) = \frac{1}{\sigma\sqrt{2\pi}}\exp\left\lbrack - \frac{1}{2}\left( \frac{x - \mu}{\sigma} \right)^{2} \right\rbrack.$$

Podemos então definir uma função no R para calcular qualquer densidade
em $x$

<div class="sourceCode">

``` {.sourceCode .r}
fn <- function(x, mu, sigma){
    (1/(sigma * sqrt(2*pi))) * exp((-1/2) * ((x - mu)/sigma)^2)
}
```

</div>

Para obter o gráfico desta distribuição, usamos o fato que a maior parte
da massa da função está no intervalo entre a média +/- três desvios
padrões, portanto entre 70 e 130. Podemos então fazer como nos comandos
que se seguem. Para marcar no gráfico a área que corresponde a
probabilidade pedida criamos um polígono com coordenadas `ax` e `ay`
definindo o perímetro desta área.

<div class="sourceCode">

``` {.sourceCode .r}
x <- seq(70, 130, length.out = 200)
fx <- fn(x, mu = 100, sigma = 10)
plot(x, fx, type = "l")
ax <- c(70, 70, x[x < 95], 95, 95)
ay <- c(0, fn(70, 100, 10), fx[x < 95], fn(95, 100, 10),0)
polygon(ax, ay, density = 10)
```

</div>

![](media/file33.png)

Para calcular a área pedida sem usar a função `pnorm()` podemos usar a
função de integração numérica. Note que esta função, diferentemente da
`pnorm()` reporta ainda o erro de aproximação numérica.

<div class="sourceCode">

``` {.sourceCode .r}
integrate(fn, mu = 100, sigma = 10, lower = -Inf, upper = 95)
0.3085375 with absolute error < 2.1e-06
```

</div>

Portanto para os demais ítens do problema, $P(90 < X < 110)$, e
$P(X > 95)$ fazemos:

<div class="sourceCode">

``` {.sourceCode .r}
integrate(fn, mu = 100, sigma = 10, lower = 90, upper = 110)
0.6826895 with absolute error < 7.6e-15
integrate(fn, mu = 100, sigma = 10, lower = 95, upper = +Inf)
0.6914625 with absolute error < 8.1e-05
```

</div>

e os resultados acima evidentemente coincidem com os obtidos
anterioriormente usando `pnorm()`,

<div class="sourceCode">

``` {.sourceCode .r}
pnorm(110, 100, 10) - pnorm(90, 100, 10)
[1] 0.6826895
pnorm(95, 100, 10, lower.tail = FALSE)
[1] 0.6914625
```

</div>

Note ainda que na prática não precisamos definir e usar a função `fn()`,
pois ela fornece o mesmo resultado que a função `dnorm()`.

</div>

</div>

<div id="ch008.xhtml#exercícios-17" class="section level2 unnumbered">

Exercícios
----------

Nos exercícios abaixo iremos também usar o R como uma calculadora
estatística para resolver alguns exemplos/exercícios de probabilidade
tipicamente apresentados em um curso de estatística básica.

1.  Para $X \sim N(90,100)$, obtenha:
    a.  $P(X \leq 115)$.
    b.  $P(X \geq 80)$.
    c.  $P(X \leq 75)$.
    d.  $P(85 \leq X \leq 110)$.
    e.  $P(|X - 90| \leq 10)$.
    f.  O valor de $a$ tal que $P(90 - a \leq X \leq 90 + a) = 0.95$.
2.  Sendo $X$ uma variável seguindo o modelo Binomial com parâmetros
    $n = 15$ e $p = 0.4$, pergunta-se:
    a.  $P(X \geq 14)$.
    b.  $P(8 < X \leq 10)$.
    c.  $P(X < 2\;{\mspace{6mu}\text{ou}\mspace{6mu}}\;\; X \geq 11)$.
    d.  $P(X \geq 11\;{\mspace{6mu}\text{ou}\mspace{6mu}}\;\; X > 13)$.
    e.  $P(X > 3\;{\mspace{6mu}\text{e}\mspace{6mu}}\;\; X < 6)$.
    f.  $P(X \leq 13\;|\; X \geq 11)$.
3.  Uma empresa informa que 30% de suas contas a receber de outras
    empresas encontram-se vencidas. Se o contador da empresa seleciona
    aleatoriamente 5 contas, determine a probabilidade de:
    a.  Nenhuma conta estar vencida
    b.  Exatamente duas contas estarem vencidas
    c.  Três ou mais contas estarem vencidas
4.  Uma empresa recebe 720 emails em um intervalo de 8 horas. Qual a
    probabilidade de que:
    a.  Em 6 minutos receba pelo menos 3 emails?
    b.  Em 4 minutos não receba nenhum email?
5.  O processo de empacotamento de uma fábrica de cereais foi ajustado
    de maneira que uma média de $\mu = 13,0$ kg de cereal seja colocado
    em cada caixa. Sabe-se que existe uma pequena variabilidade no
    enchimento dos pacotes devido à fatores aleatórios, e que o
    desvio-padrão do peso de enchimento é de $\sigma = 0,1$ kg.
    Assume-se que a distribuição dos pesos tem distribuição normal. Com
    isso, determine as probabilidades de que uma caixa escolhida ao
    acaso:
    a.  Pese entre 13,0 e 13,2 kg.
    b.  Tenha um peso maior do que 13,25 kg.
    c.  Pese entre 12,8 e 13,1 kg.
    d.  Pese entre 13,1 e 13,2 kg.
6.  Faça os seguintes gráficos:
    a.  da função de densidade de uma variável com distribuição de
        Poisson com parâmetro $\lambda = 5$.
    b.  da densidade de uma variável $X \sim N(90,100)$.
    c.  sobreponha ao gráfico anterior a densidade de uma variável
        $Y \sim N(90,80)$ e outra $Z \sim N(85,100)$.
    d.  densidades de distribuições $\chi^{2}$ com 1, 2 e 5 graus de
        liberdade.

<!-- Referencias --> <!--chapter:end:07-probabilidade.Rmd-->

</div>

</div>

[]{#ch009.xhtml}

<div id="ch009.xhtml#inferência-estatística" class="section level1">

[8]{.header-section-number} Inferência estatística
==================================================

<div id="ch009.xhtml#introdução-ao-pensamento-estatístico"
class="section level2">

[8.1]{.header-section-number} Introdução ao pensamento estatístico
------------------------------------------------------------------

No contexto de análise e modelagem estatística o analista assume que
todos os fenômenos aleatórios podem ser representados por distribuições
de probabilidades, ou seja, um modelo estatístico. Tais distribuições
são representações de como a variável aleatória deve se comportar na
população. Em cursos de inferência estatística é usual a frase ''seja X
uma variável aleatória de uma população normal com média $\mu$ e
variância $\sigma^{2}$''. Essa frase exemplifica a forma como o
estatístico supõe que um certo fenômeno aleatório se comporta na
população.

Considere o caso de uma pesquisa eleitoral onde potenciais eleitores são
entrevistados sobre a sua intenção em votar (SUCESSO) ou não votar
(FRACASSO) em um determinado candidato X. Note que pela estrutura do
fenômeno aleatório o modelo Bernoulli é um candidato natural para
modelar o comportamento da variável aleatória ''intenção de voto''.
Suponha ainda que um conjunto de $n$ eleitores vão ser entrevistados e
que a probabilidade de sucesso, ou seja, votar no candidato X seja
constante para todos os entrevistados e denotada por $p.$ Nestas
condições podemos estar interessados na variável aleatória Y que conta o
número de sucessos (eleitores que vão votar em X) entre $n$ eleitores.
Sendo assim, a distribuição de probabilidade de $Y$ é binomial com
parâmetros $n$ e $p$ e sua função de probabilidade é dada por

$$P(Y = y) = P(Y = y) = \left( \frac{n}{y} \right)p^{y}(1 - p)^{n - y}.$$
Note que esta distribuição é completamente governada pelos valores de
seus parâmetros, ou seja, $n$ e $p$. Em geral $n$ é fixado e conhecido,
por outro lado $p$ é desconhecido. Em termos práticos, o valor de $p$ é
o que estamos interessados, uma vez que ele representa a proporção
populacional de eleitores do candidato $X$.

Se fossemos capazes de entrevistar todos os elementos da população de
interesse, poderíamos facilmente calcular a proporção de eleitores de
$X$ e plugar no modelo para calcular quaisquer tipos de probabilidades
de interesse. No entanto na prática, muitas vezes entrevistar todos os
elementos da população de interesse é impossível ou extremamente
custoso. Nestas situações o problema que surge é como que baseado apenas
em uma amostra da população de interesse podemos falar algo sobre toda a
população. Este é o problema de uma das áreas da estatística chamada de
inferência estatística.

O objetivo deste texto não é discutir inferência estatística em
detalhes, mas apenas apresentar as principais ideias e ilustrar a sua
implementação computacional utilizando o software R. Além disso, uma
série de procedimentos pré-prontos estão disponíveis em R e devem ser
apresentados de forma breve, uma vez que as ideias são similares apenas
adaptadas à situações específicas.

O processo de inferência estatística começa com a especificação de uma
distribuição de probabilidade para a variável aleatória de interesse.
Neste caso, vamos definir a variável de interesse como sendo $Y$ - votar
no candidato X. Note que esta é uma v.a binária, ou seja, apresenta
apenas os valores $0$-não vai votar no candidato X ou $1$ vai votar no
candidato X. Neste caso, podemos especificar que $Y \sim B(p)$, ou seja,
$Y$ segue o modelo de Bernoulli com parâmetro $p$. Importante lembrar
que o espaço paramétrico de $p$ neste caso é o intervalo unitário, ou
seja, $p \in (0,1)$.

Uma vez com o modelo especificado precisamos de informações sobre o
parâmetro populacional de interesse, neste caso $p$ que representa a
proporção de eleitores do candidato X. Para obter informações sobre $p$
vamos coletar uma amostra da população de interesse e medir a variável
de interesse. Neste caso, isso significa simplesmente perguntar se o
eleitor vai ou não votar no candidato X. Em R podemos facilmente simular
esta situação prática usando a função $rbinom()$, conforme ilustra o
código abaixo

<div class="sourceCode">

``` {.sourceCode .r}
set.seed(123)
y <- rbinom(n = 10, size = 1, prob = 0.5)
y
 [1] 0 1 0 1 1 0 1 1 1 0
```

</div>

Note que para simular uma amostra nós precisamos especificar o tamanho
da amostra, neste caso $n = 10$ o número de ensaios Bernoulli neste caso
apenas $1$ e a probabilidade de sucesso (proporção populacional). É
claro que na prática a proporção populacional é desconhecida, mas neste
caso fixamos um valor para simular observações e o objetivo é apenas
baseado nas realizações da variável aleatória **descobrir** ou
**inferir** qual é o verdadeiro valor de $p$. De forma mais geral os
objetivos da inferência estatística são:

-   Estimar $p$ baseado apenas na amostra (valor pontual)! Pense que
    deseja-se responder a pergunta: Quanto você acha que é a proporção
    de eleitores do candidato X na população?
-   Informar o quanto você acredita no valor estimado (intervalo de
    confiança).
-   Decidir sobre possíveis valores de p baseado apenas na amostra. Por
    exemplo, O candidato X vai ganhar (p &gt; 0,50)?

Interessante notar que até este momento não fizemos nenhuma suposição em
como as observações foram obtidas. No entanto, se supomos que as
observações são independentes podemos facilmente obter a distribuição
conjunta de todas as variáveis aleatórias envolvidas no modelo como o
produto da distribuição de cada uma. Neste caso, todas as observações
vêm de uma população Bernoulli com parâmetro $p$. Assim, a distribuição
conjunta é dada pelo seguinte produtório

$$P(Y = y) = \prod\limits_{i = 1}^{n}p^{y_{i}}(1 - p)^{1 - y_{i}} = p^{\sum\limits_{i = 1}^{n}y_{i}}(1 - p)^{n - \sum\limits_{i = 1}^{n}y_{i}}.$$
Uma forma alternativa é escrever a distribuição do número de sucessos em
$n$ ensaios Bernoulli que é simplesmente uma distribuição binomial com
parâmetros $n$ e $p$, ou seja,

$$P(Y = y) = P(Y = y) = \left( \frac{n}{y} \right)p^{y}(1 - p)^{n - y}.$$
É importante enfatizar que após a amostra ser coletada o número $y$ de
sucesso é fixo. Para a nossa amostra, temos $y = 6$. Lembre-se que o $n$
foi fixado, assim para avaliar a equação acima em algum ponto, só
precisamos fixar o valor de $p$.

Agora vamos refletir sobre o que a equação acima está nos fornecendo.
Suponha que em um primeiro momento você apenas precise decidir se
$p = 0.5$ ou $p = 0.8$. Como poderíamos usar o nosso modelo para tomar
esta decisão?

Note que podemos calcular qual é a probabilidade de obter $6$ sucessos
em $n$ ensaios supondo que $p = 0.5$ e também supondo que $p = 0.8$.
Vamos fazer estas contas

$$P(Y = 6|p = 0.5) = \left( \frac{10}{6} \right)0.5^{6}(1 - 0.5)^{10 - 6} = 0.205.$$
$$P(Y = 6|p = 0.8) = \left( \frac{10}{6} \right)0.8^{6}(1 - 0.8)^{10 - 6} = 0.088.$$
Em R temos,

<div class="sourceCode">

``` {.sourceCode .r}
dbinom(6, size = 10, prob = 0.5)
[1] 0.2050781
dbinom(6, size = 10, prob = 0.8)
[1] 0.08808038
```

</div>

Baseado apenas nestas probabilidades, é possível observar que a
probabilidade de observarmos $6$ sucessos em $10$ ensaios é mais
provável quando $p = 0.5$ do que quando $p = 0.8$. Neste caso podemos
concluir que existe mais evidências em favor de $p = 0.5$ do que em
favor de $p = 0.8$. Veja que fizemos uma espécie de pensamento inverso,
observamos $6$ sucessos e agora estamos pensando, qual é o valor de $p$
mais compatível com esse valor. Além disso, a função de probabilidade
conjunta vista como uma função do parâmetro ao invés da variável
aleatória nos fornece exatamente essa noção de compatibilidade, ou seja,
qual é o valor de $p$ mais compatível com as minhas observações.

Para enfatizar esta idéia vamos rescrever a função acima para enfatizar
que a quantidade desconhecida agora é $p$ e não mais $y$.

$$L(p|y) = \left( \frac{n}{y} \right)p^{y}(1 - p)^{n - y}.$$ A função
acima é chamada de **verossimilhança** e é fundamental em todo o
processo de inferência estatística. No caso de variáveis aleatórias
discretas ela nos fornece a probabilidade de observar o que realmente
foi observado dado um particular valor para o parâmetro de interesse.
Particularizando para o nosso exemplo temos

$$L(p|y) = \left( \frac{10}{6} \right)p^{6}(1 - p)^{10 - 6}.$$ Como dito
a função de verossimilhança nos fornece uma medida de compatibilidade de
um particular valor de $p$ com a amostra observada. Assim, é natural
tomarmos como o nosso melhor ''chute'' o valor mais compatível com a
amostra observada, ou seja, o ponto de máximo da função de
verossimilhança. Vamos fazer um gráfico para ilustrar esta ideia.

<div class="sourceCode">

``` {.sourceCode .r}
L <- function(p, n, y) {
  out <- dbinom(y, size = n, prob = p)
  return(out)
}
curve(L(x, n = 10, y = 6), 0, 1)
```

</div>

![](media/file34.png) Na prática é mais comum trabalhar com o log da
verossimilhança por conveniência computacional. Isso leva a chamada
função de log-verossimilhança, cujo gráfico é apresentado abaixo para o
nosso exemplo

<div class="sourceCode">

``` {.sourceCode .r}
ll <- function(p, n, y) {
  out <- dbinom(y, size = n, prob = p, log = TRUE)
  return(out)
}
curve(ll(x, n = 10, y = 6), 0.4, 0.8)
abline(v = mean(y))
```

</div>

![](media/file35.png) Não é dificil mostrar usando ferramentas padrões
de cálculo diferencial que o ponto de máximo ocorre em $\hat{p} = y/n$,
ou seja, na proporção amostral de eleitores do candidato X.

Com essa ideia simples resolvemos o primeiro objetivo da inferência
estatística que consiste em dizer qual valor achamos razoável para $p$
dado a amostra que coletamos. O próximo objetivo é dizer o quanto
acreditamos neste valor. Note que uma vez que temos a função de
verossimilhança ou log-verossmilhança basta olhar para a função para
responder a tal pergunta. O ponto de máximo é o mais compatível, porém
valores ao redor do máximo também apresentam uma boa compatibilidade com
a amostra e portanto são bons candidatos a valor de $p$. Essa ideia pode
ser resumida por fazer um corte horizontal na função de
log-verossimilhança. Assim, todos os pontos acima do corte são bons
candidatos a verdadeiro valor de $p$.

<div class="sourceCode">

``` {.sourceCode .r}
curve(ll(x, n = 10, y = 6), 0.4, 0.8)
abline(h = -2)
```

</div>

![](media/file36.png) Entretanto, onde fazer tal corte não é uma tarefa
simples e explicar como e por que fazer isso em detalhes está fora do
escopo deste material. Esta é a ideia por traz da definição do que se
chama popularmente de intervalo de confiança. Uma forma alternativa é
fazer um gráfico da função de verossimilhança relativa, definida como a
verossimilhança divida pela verossimilhança no ponto de máximo,
$$LR(p) = L(p)/L(\hat{p}).$$

Neste caso um intervalo pode ser obtido por definir algum valor entre
$0$ e $1$ para obter intervalos não vazios. Por exemplo, podemos definir
que uma compatibilidade de pelo menos 0.4 com a amostra é necessário
para que um valor seja parte do intervalo. Ilustrando graficamente
temos,

<div class="sourceCode">

``` {.sourceCode .r}
LR <- function(p, p_hat, n, y) {
  out <- L(p = p, n = n, y = y)/L(p = p_hat, n = n, y = y)
  return(out)
}
curve(LR(x, p_hat = 0.6, n = 10, y = 6), 0, 1)
abline(h = 0.4)
```

</div>

![](media/file37.png)

Por fim, o último objetivo da inferência consiste em decidir se um
determinado valor hipotético para $p$ é ou não compatível com a amostra
observada. Note que o valor mais compatível é o máximo da
verossimilhança, assim para decidir se um valor é ou não compatível com
a amostra, basta verificar se ele está perto ou longe do valor que tem
maior compatibilidade. Esta ideia é o que esta por traz do que se chama
de teste de hipóteses e é ilustrada abaixo.

![](media/file38.png)

</div>

<div id="ch009.xhtml#estimação-pontual-e-intervalos-de-confiança"
class="section level2">

[8.2]{.header-section-number} Estimação pontual e intervalos de confiança
-------------------------------------------------------------------------

O processo de estimação pontual consiste em encontrar um valor ao qual
chamamos de estimativa do verdadeiro valor do parâmetro, em nosso
exemplo o parâmetro $p$ da distribuição Bernoulli. Como discutido
anteriormente a função de verossimilhança nos fornece uma forma
intuitiva de obter tal valor que no caso da distribuição de Bernoulli é
simplesmente a proporção amostral, $\hat{p} = y/n$.

O próximo passo é encontrar um intervalo de confiança para o parâmetro
$p$. Neste texto vamos enfatizar o pensamento frequentista de
probabilidade para motivar a construção do intervalo de confiança.

Importante salientar que $Y$ é uma variável aleatória cuja observações
são denotadas por $y$. Nossa estimativa de $p$ é o valor $\hat{p} = y/n$
que é uma função dos valores observados. Agora suponha que o experimento
seja refeito um número grande vezes. O que vai acontecer com $\hat{p}$?
Vamos fazer um experimento computacional para ilustrar esta situação.

<div class="sourceCode">

``` {.sourceCode .r}
set.seed(1234)
p.hat <- c()
for(i in 1:1000) {
  y <- rbinom(10, prob = 0.5, size = 1)
  p.hat[i] <- mean(y)
}
```

</div>

<div class="sourceCode">

``` {.sourceCode .r}
par(mfrow = c(1,1), mar=c(2.6, 2.8, 1.2, 0.5), mgp = c(1.6, 0.6, 0))
plot(prop.table(table(p.hat)), main = "", 
     ylab = "Proporção observada",
     xlab = expression(hat(p)), xlim = c(0,1))
```

</div>

![](media/file39.png)

A Figura acima mostra que mesmo o verdadeiro valor de $p$ sendo 0.5
existe uma probabilidade razoável de observarmos $\hat{p} = 0.4$ e
$\hat{p} = 0.6$ em uma amostra de tamanho 10. Porém, quando nos
distanciamos de $0.5$ a probabilidade de observar $\hat{p}$ mais
extremos como 0.1 ou 0.9 é pequena. No geral, a incerteza com relação ao
valor de $p$ é grande. Para diminuir tal incerteza precisamos ganhar
mais informações sobre o valor de $p$ e para isso precisamos de mais
amostras.

Note que para cada possível amostra coletada o valor de $\hat{p}$ é
alterado. Isso é decorrente de $\hat{p}$ ser também uma função da
variável aleatória $Y$. Para enfatizar isso usamos a notação
$\hat{p} = Y/n$ e neste caso chamamos $\hat{p}$ de estimador do valor de
$p$. Pensando desta forma $\hat{p}$ é também uma variável aleatória e
consequentemente ele deve ter uma distribuição de probabilidade que pode
ser resumida, por exemplo, usando esperança e variância.

A Figura abaixo mostra o efeito do tamanho da amostra sobre a
distribuição amostral do estimador $\hat{p}$.

<div class="sourceCode">

``` {.sourceCode .r}
set.seed(1234)
p.hat.list <- list()
amostra <- c(10, 50, 100, 250,500, 1000)
par(mfrow = c(2,3), mar=c(2.6, 2.8, 1.2, 0.5), mgp = c(1.6, 0.6, 0))
for(j in 1:6) {
  p.hat.list[[j]] <- matrix(NA, ncol = 1, nrow = 1000)
  for(i in 1:1000) {
  y <- rbinom(amostra[j], prob = 0.5, size = 1)
  p.hat.list[[j]][i,] <- mean(y)
  }
hist(p.hat.list[[j]], prob = TRUE, main = paste("Amostra", amostra[j]), 
     ylab = "Proporção observada",
     xlab = expression(hat(p)), xlim = c(0,1))
}
```

</div>

![](media/file40.png){width="99%"}

Note que quanto maior a amostra a distribuição amostral fica mais
concentrada ao redor do verdadeiro valor de $p$. Isso é decorrente da
Lei dos grandes números. Além disso, note que a distribuição é muito
parecida com a distribuição normal, um resultado conhecido como Teorema
Central do Limite.

A idéia de intervalo de confiança é simplesmente olhar para a
distribuição amostral e responder a pergunta: Qual o intervalo em que
$\hat{p}$ tem uma probabilidade, digamos $(1 - \alpha)$ de pertencer?

O valor de $\alpha$ deve ser especificado e alguns valores populares são
$0.05$ e $0.01$. A Figura abaixo ilustra esta ideia.

<div class="sourceCode">

``` {.sourceCode .r}
set.seed(1234)
p.hat.list <- list()
amostra <- c(10, 50, 100)
par(mfrow = c(1,3), mar=c(2.6, 2.8, 1.2, 0.5), mgp = c(1.6, 0.6, 0))
for(j in 1:3) {
  p.hat.list[[j]] <- matrix(NA, ncol = 1, nrow = 1000)
  for(i in 1:1000) {
  y <- rbinom(amostra[j], prob = 0.5, size = 1)
  p.hat.list[[j]][i,] <- mean(y)
  }
hist(p.hat.list[[j]], prob = TRUE, main = paste("Amostra", amostra[j]), 
     ylab = "Densidade",
     xlab = expression(hat(p)), xlim = c(0,1))
abline(v= c(quantile(p.hat.list[[j]], probs = c(0.025, 0.975))), col = "red")
}
```

</div>

![](media/file41.png){width="99%"}

Temos um procedimento bastante simples para obter os limites do
intervalo de confiança, porém tal procedimento depende de sermos capazes
de realizar o experimento um número grande de vezes. Na prática só temos
uma amostra coletada e baseado apenas nesta amostra precisamos inferir
sobre $p$. É neste ponto que entra o fato de $\hat{p}$ ser uma variável
aleatória. Este fato permite que exploremos sua distribuição mesmo sem
realizar um grande número de experimentos.

De forma geral obter a distribuição de probabilidade de um estimador não
é uma tarefa trivial, porém o Teorema Central do Limite nos fornece uma
boa aproximação, ao menos para grandes amostras. O Teorema Central do
limite em sua versão mais simples é como segue:

-   Teorema Lindeberg-Levy: Seja $Y_{1},\ldots,Y_{n}$ uma amostra iid
    com $E(Y_{i}) = \mu$ e $V(Y_{i}) = \sigma^{2} < \infty$. Então,
    $$\left. \sqrt{n}\left( \frac{\bar{Y} - \mu}{\sigma} \right)\overset{D}{\rightarrow}Z \sim N(0,1),\quad\text{para}\quad n\rightarrow\infty. \right.$$
-   Isso significa que, para todo $y \in \Re$,
    $$\left. P(Y_{n} \leq y)\rightarrow\Phi(y)\quad\text{quando}\quad n\rightarrow\infty, \right.$$
    onde
    $$\Phi(y) = \int_{- \infty}^{y}\phi(z)dz\quad\text{e}\quad\phi(z) = \frac{1}{\sqrt{2\pi}}\exp\left( - \frac{1}{2}z^{2} \right).$$
-   Forma alternativa: $\bar{Y} \sim N(\mu,\sigma^{2}/n).$

Particularizando para o nosso exemplo temos que:

-   Estimador de máxima verossimilhança $\hat{p} = \frac{Y}{n}.$
-   Usando as propriedades da distribuição binomial, temos
    $$E(\hat{p}) = E(Y/n) = \frac{1}{n}E(Y) = \frac{np}{n} = p.$$
    $$Var(\hat{p}) = Var(Y/n) = \frac{1}{n^{2}}Var(Y) = \frac{np(1 - p)}{n^{2}} = \frac{p(1 - p)}{n}.$$
-   Usando o TLC, temos $$\hat{p} \sim N(p,\frac{p(1 - p)}{n}).$$

Vamos fazer uma ilustração computacional deste importante resultado.

<div class="sourceCode">

``` {.sourceCode .r}
set.seed(1234)
p.hat.list <- list()
amostra <- c(10, 50, 100, 250, 500, 1000)
par(mfrow = c(2,3), mar=c(2.6, 2.8, 1.2, 0.5), mgp = c(1.6, 0.6, 0))
for(j in 1:6) {
  p.hat.list[[j]] <- matrix(NA, ncol = 1, nrow = 1000)
  for(i in 1:1000) {
  y <- rbinom(amostra[j], prob = 0.5, size = 1)
  p.hat.list[[j]][i,] <- mean(y)
  }
  hist(p.hat.list[[j]], prob = TRUE, main = paste("Amostra", amostra[j]), 
       ylab = "Densidade", xlab = expression(hat(p)), xlim = c(0,1))
  curve(dnorm(x, mean = 0.5, sd = sqrt(0.5*(1-0.5)/amostra[j])), 0.1, 0.9, add = TRUE)
}
```

</div>

![](media/file42.png){width="99%"}

Agora usando resultados convencionais da distribuição normal podemos
encontrar os limites do intervalo de confiança. Para o caso binomial o
intervalo é dado por
$$\hat{p} \pm Z_{\alpha/2}\sqrt{\frac{\hat{p}(1 - \hat{p})}{n}},$$ onde
$Z_{\alpha/2}$ é o quantil da distribuição normal padrão com $\alpha/2$
probabilidade.

Cálculos similares mostram que para os casos da média de uma
distribuição normal e Poisson os intervalos ficam dados por:

-   Intervalo de confiança: Caso Normal
    $$\hat{\mu} \pm Z_{\alpha/2}\sqrt{\frac{{\hat{\sigma}}^{2}}{n}},$$
    onde
    ${\hat{\sigma}}^{2} = \sum_{i = 1}^{n}\frac{(y_{i} - \hat{\mu})^{2}}{n - 1}$.

-   Intervalo de confiança: Caso Poisson
    $$\hat{\lambda} \pm Z_{\alpha/2}\sqrt{\frac{\hat{\lambda}}{n}},$$
    onde $\hat{\lambda} = \sum_{i = 1}^{n}\frac{y_{i}}{n}.$

O intervalo de confiança deve ser interpretado sempre com muito cuidado.
A interpretação frequentista é a seguinte: Se o experimento for repetido
um número $n$ de vezes e para cada realização obtermos o intervalo de
confiança, esperamos que $(1 - \alpha)\%$ dos intervalos contenham o
verdadeiro valor do parâmetro. Note que a variável aleatória é o próprio
intervalo de confiança.

O código abaixo ilustra computacionalmente tal interpretação.

<div class="sourceCode">

``` {.sourceCode .r}
set.seed(12)
results_wald <- matrix(NA, ncol = 2, nrow = 100)
for(i in 1:100) {
  y <- rbinom(100, size = 1, prob = 0.5)
  p_hat <- mean(y)
  v_hat <- (p_hat*(1-p_hat))/100
  temp_wald <- c(p_hat -  qnorm(0.975)*sqrt(v_hat), p_hat + qnorm(0.975)*sqrt(v_hat))
  results_wald[i,] <- temp_wald
}

## Intervalo Wald
plot(c(0.30,0.72) ~ c(1,100), type = "n", ylab = expression(p), xlab = "Ensaio")
abline(h=0.50)
for(i in 1:100) {
  arrows(c(i),results_wald[i,1],c(i),results_wald[i,2],code=3,angle=90,length=0.03,
         col=ifelse(results_wald[i,1] > 0.5 | results_wald[i,2] < 0.5, "darkred","lightgray"))
}
```

</div>

![](media/file43.png)

**Exemplo 1** No caso do candidato X suponha que é de interesse
apresentar uma estimativa intervalar para a proporção de eleitores de X
na população. Assumindo que a estimativa amostral foi de $0,60$ (seis
sucessos em dez ensaios) o intervalo com $95\%$ de confiança é dado por
$${\hat{p}}_{I} = 0,6 - 1.96\sqrt{0,6(1 - 0,6)/10} = 0.296\quad\text{e}\quad{\hat{p}}_{S} = 0,6 - 1.96\sqrt{0,6(1 - 0,6)/10} = 0.904.$$

**Exemplo 2** Num grupo de pacientes, o nível de colesterol é uma
variável aleatória com distribuição Normal, de média desconhecida e
variância $64(mg/ml)^{2}$. - Para uma amostra de 46 indivíduos que
forneceu nível médio de colesterol de 120 $mg/ml$, construa o intervalo
de confiança de $88\%$.

<div class="sourceCode">

``` {.sourceCode .r}
media <- 120
sd <- sqrt(64)
n <- 46
alpha = 0.12
mu_I <- media - qnorm((1 - alpha/2))*sd/sqrt(46)
mu_S <- media + qnorm((1 - alpha/2))*sd/sqrt(46)
c(mu_I, mu_S)
[1] 118.1661 121.8339
```

</div>

</div>

<div id="ch009.xhtml#exercícios-18" class="section level2 unnumbered">

Exercícios
----------

1.  Por analogia a produtos similares, o tempo de reação de um novo
    medicamento pode ser considerado como tendo distribuição Normal com
    desvio padrão igual a 2 minutos (a média desconhecida). Vinte
    pacientes foram sorteados, receberam o medicamento e tiveram seu
    tempo de reação anotado. Os dados foram os seguintes (em minutos):
    $2,9;3,4;3,5;4,1;4,6;4,7;4,5;3,8;5,3;4,9;4,8;5,7;5,8;5,0;3,4;5,9;6,3;4,6;5,5$
    e $6,2$. Obtenha um intervalo de confiança para o tempo médio de
    reação. Use $96\%$ de confiança.

2.  Uma amostra de 25 observações de uma Normal $(\mu,16)$ foi coletada
    e forneceu uma média amostral de 8. Construa intervalos de confiança
    com $80\%$, $85\%$, $90\%$ e $95\%$ de confiança. Comente as
    diferenças encontradas.

3.  Numa pesquisa com 50 eleitores, o candidato José João obteve $0,34$
    da preferência dos eleitores. Construa, para a confiança de $94\%$ o
    intervalo de confiança para a proporção de votos a serem recebidos
    pelo candidato mencionado.

4.  Considere a seguinte amostra da distribuição de Poisson de parâmetro
    $\lambda$. Proponha um estimador pontual e intervalar para $\lambda$
    usando o método de máxima verossimilhança. Implemente seu método
    em R. Faça um estudo de simulação para ilustrar a distribuição
    aproximada deste estimador.

5.  O número de atendimentos em um pronto-socorro pode ser modelado por
    uma distribuição de Poisson de parâmetro $\lambda$. Suponha que o
    interesse seja modelar o número de atendimentos por hora e que para
    um conjunto de $30$ horas o número de atendimentos por hora foi
    contado e as observações são mostradas abaixo.

<!-- -->

    # A tibble: 3 x 1
      `matrix(y, 3, 10)`[,1]  [,2]  [,3]  [,4]  [,5]  [,6]  [,7]  [,8]  [,9] [,10]
                       <int> <int> <int> <int> <int> <int> <int> <int> <int> <int>
    1                      6    11     8     8     9    12     7     9     9     9
    2                     10    13    12    13     8     6    13     9     9     6
    3                      7     4     8     8     5     3    12    16     8     5

O seu interesse é dimensionar o número de médicos para este pronto
socorro. Suponha que um médico consegue atender até quatro pessoas em um
período de uma hora. A politica do hospital especifica que se deve
manter um contigente de médicos necessários para atender a demanda em
$95\%$ dos dias. Especifique quantos médicos devem estar de plantão para
que a politica do hospital seja respeitada.

</div>

<div id="ch009.xhtml#teste-de-hipótese" class="section level2">

[8.3]{.header-section-number} Teste de hipótese
-----------------------------------------------

O último objetivo da inferência estatística é a construção de testes de
hipóteses. Uma hipótese é qualquer afirmativa sobre uma propriedade da
população. Um teste de hipótese é um procedimento para avaliar uma
afirmativa sobre uma propriedade da população. Em termos estatísticos
uma hipótese estatística é qualquer afirmativa sobre um parâmetro da
distribuição de probabilidade.

Voltando ao nosso exemplo do candidato X, podemos estar interessados por
exemplo em saber se a proporção de votos no candidato X é maior que 0.5,
o que implicaria que ele ganharia a eleição. Em termos de distribuição
de probabilidade essa é uma afirmativa acerca do valor do parâmetro $p$.
Sendo assim, enunciamos as hipóteses da seguinte forma:

$$H_{0}:p = \frac{1}{2}\quad vs\quad H_{1}:p \neq \frac{1}{2}.$$ Nesta
notação $H_{0}$ é chamada de hipótese nula. Por outro lado, $H_{1}$ é
chamada de hipótese alternativa.

Para construir um teste de hipótese usamos novamente o pensamento
frequentista de probabilidade, ou seja, considere que é possível
realizar o experimento um número indefinido de vezes. Para cada uma
destas realizações obtemos uma estimativa para o valor de $p$ digamos
$\hat{p}$. Verique quais valores realizados de $\hat{p}$ são
**razoáveis** de ocorrer sob a hipótese nula. No caso da hipótese nula
ser verdadeira podemos facilmente gerar dados do fenômeno de interesse.
Neste caso, vamos realizar o experimento $1000$ vezes e ver como se
comporta nosso estimador.

<div class="sourceCode">

``` {.sourceCode .r}
set.seed(1234)
p.hat <- c()
for(i in 1:1000) {
  y <- rbinom(10, prob = 0.5, size = 1)
  p.hat[i] <- mean(y)
}
par(mfrow = c(1,1), mar=c(2.6, 2.8, 1.2, 0.5), mgp = c(1.6, 0.6, 0))
plot(prop.table(table(p.hat)), main = "", 
     ylab = "Proporção observada",
     xlab = expression(hat(p)), xlim = c(0,1))
```

</div>

![](media/file44.png)

Veja que mesmo a hipótese nula sendo verdadeira existe uma probabilidade
não desprezível de observarmos $8$ eleitores de X em $10$ eleitores. A
incerteza associada a decisão no caso de apenas $10$ observações é
grande. Para diminuir a incerteza precisamos de mais informação o que
conseguimos aumentanto a amostra. A Figura abaixo ilustra esta situação

<div class="sourceCode">

``` {.sourceCode .r}
set.seed(1234)
p.hat.list <- list()
amostra <- c(10, 50, 100, 250,500)
par(mfrow = c(1,5), mar=c(2.6, 2.8, 1.2, 0.5), mgp = c(1.6, 0.6, 0))
for(j in 1:5) {
  p.hat.list[[j]] <- matrix(NA, ncol = 1, nrow = 1000)
  for(i in 1:1000) {
  y <- rbinom(amostra[j], prob = 0.5, size = 1)
  p.hat.list[[j]][i,] <- mean(y)
  }
hist(p.hat.list[[j]], prob = TRUE, main = paste("Amostra", amostra[j]), 
     ylab = "Proporção observada",
     xlab = expression(hat(p)), xlim = c(0,1))
}
```

</div>

![](media/file45.png){width="99%"}

O procedimento é bastante intuivo e parecido com a construção de
intervalos de confiança. No entanto, no caso de teste de hipóteses
precisamos tomar uma decisão. Sendo assim, a ideia é construir uma
região de valores para os quais você aceitará (ou não rejeitará) a
hipótese nula esta região é chamada de região de aceitação ou não
rejeição de $H_{0}$. A Figura abaixo ilustra a construção da região de
rejeição

<div class="sourceCode">

``` {.sourceCode .r}
set.seed(1234)
p.hat.list <- list()
amostra <- c(10, 50, 100, 250,500)
par(mfrow = c(1,5), mar=c(2.6, 2.8, 1.2, 0.5), mgp = c(1.6, 0.6, 0))
for(j in 1:5) {
  p.hat.list[[j]] <- matrix(NA, ncol = 1, nrow = 1000)
  for(i in 1:1000) {
  y <- rbinom(amostra[j], prob = 0.5, size = 1)
  p.hat.list[[j]][i,] <- mean(y)
  }
hist(p.hat.list[[j]], prob = TRUE, main = paste("Amostra", amostra[j]), 
     ylab = "Proporção observada",
     xlab = expression(hat(p)), xlim = c(0,1))
abline(v= c(quantile(p.hat.list[[j]], probs = c(0.025, 0.975))), col = "red")
}
```

</div>

![](media/file46.png){width="99%"}

Novamente em termos práticos não temos como repetir o experimento um
número grande vezes. Assim, recorremos novamente ao Teorema Central do
Limite e estabelecemos a região critica de forma aproximada usando a
aproximação Gaussiana. No caso Bernoulli, este procedimento resulta na
seguinte estatística de teste

-   Estatística do teste caso Bernoulli

$$Z = \frac{\hat{p} - p_{0}}{\sqrt{\frac{p_{0}(1 - p_{0})}{n}}} \sim N(0,1).$$

O procedimento aqui descrito em linhas gerais é bastante genérico e
perfaz toda a estatística. No entanto está fora do escopo deste material
discutir tais procedimentos em detalhes. Na sequência apresentamos o
resumo de alguns casos notáveis de testes de hipóteses que aparecem com
frequência em cursos de estatística básica.

**Exemplo 1** Considere que seja de interesse verificar se existe
evidências que o candidato $X$ vai ganhar as eleições. Em termos
estatístico isso significa que

-   $H_{0}:p = 0.5$ contra $H_{1}:p > 0.5.$

Suponha que adotamos $5\%$ de significância. Neste caso a região crítica
é unilateral, e tem a seguinte forma
$$p_{c} = 0.5 + 1.64\sqrt{0.25/10} = 0.76.$$ Vamos fazer um gráfico da
região de aceitação e rejeição e verificar onde a proporção amostral
está localizada para concluir o teste.

<div class="sourceCode">

``` {.sourceCode .r}
curve(dnorm(x, mean = 0.5, sd = sqrt(0.25/10)), 0.1, 0.9, 
      ylab = "Densidade", xlab = expression(hat(p)))
abline(v = 0.5+qnorm(0.95)*sqrt(0.25/10))
abline(v = 6/10, col = "red", lty = 2, lwd = 2)
```

</div>

![](media/file47.png)

Lembre-se que a proporção amostral foi de $0.6$ em $10$ entrevistas.
Assim, vemos claramente que não temos evidências para rejeitar $H_{0}$.
Neste caso não temos evidências para dizer que o candidato X irá ganhar
a eleição.

-   Estatística do teste caso Normal

No caso de população Normal, a estatística de teste para testar
$H_{0}:\mu = \mu_{0}$ contra $H_{1}:\mu \neq \mu_{0}$ com variância
conhecida $\sigma^{2}$ é dada por

$$\frac{\hat{y} - \mu_{0}}{\sigma/\sqrt{n}} \sim N(0,1)$$ onde $\mu_{0}$
é o valor especificado sob a hipótese nula. Neste caso a região crítica
para testes bilaterais toma a seguinte forma:

$$y_{I} = \mu_{0} - Z_{\alpha/2}\sqrt{\sigma^{2}/n}\quad\text{e}\quad y_{S} = \mu_{0} + Z_{\alpha/2}\sqrt{\sigma^{2}/n}.$$

**Exemplo 2** (Magalhães e Lima, pg. 252). Um pesquisador deseja estudar
o efeito de certa substância no tempo de reação de seres vivos a um
certo tipo de estímulo. Um experimento é desenvolvido com cobaias que
são inoculadas com a substância e submetidas a um estimulo elétrico, com
seus tempos de reação (em segundos) anotados. Os seguintes valores foram
obtidos:
$9,1;\quad 9,3;\quad 7,2;\quad 7,5;\quad 13,3;\quad 10,9;\quad 7,2;\quad 9,9;\quad 8,0;\quad 8,6$.
Admite-se que o tempo de reação segue, em geral o modelo Normal com
média 8 e desvio padrão $\sigma = 2$ segundos. O pesquisador desconfia,
entretanto, que o tempo médio sofre alteração por influência da
substância. Neste caso as hipóteses de interesse são:

-   $H_{0}:$ as cobais apresentam tempo de reação padrão;
-   $H_{1}:$ as cobais tem o tempo de reação alterado.

Em termos de modelo estatístico, tais hipóteses são traduzidas para
afirmações acerca do parâmetro $\mu$.

-   $H_{0}:\mu = 8$ contra $H_{1}:\mu \neq 8$.

Neste caso a região crítica para $\alpha = 0,05$ fica dada por
$$y_{I} = 8 - 1,96\sqrt{4/10} = 6,76\quad\text{e}\quad y_{S} = 8 + 1,96\sqrt{4/10} = 9,24.$$
Vamos agora obter a média amostral e concluir o teste.

<div class="sourceCode">

``` {.sourceCode .r}
x <- c(9.1,9.3,7.2,7.5,13.3,10.9,7.2,9.9,8.0,8.6)
mean(x)
[1] 9.1
```

</div>

Ilustrando a região crítica

<div class="sourceCode">

``` {.sourceCode .r}
curve(dnorm(x, mean = 8, sd = sqrt(4/10)), 6, 10, 
      ylab = "Densidade", xlab = expression(hat(y)))
abline(v = c(8-qnorm(0.975)*sqrt(4/10), 8+qnorm(0.975)*sqrt(4/10) ))
abline(v = mean(x), col = "red", lwd = 2, lty = 2)
```

</div>

![](media/file48.png)

Como o valor observado da média amostral pertence a região de aceitação
de $H_{0}$, aceitamos a hipóteses $H_{0}$ ao nível de significância de
$5\%$. Em outras palavras, concluímos que o tempo de reação das cobais
submetidas à substância não é alterado.

<div id="ch009.xhtml#teste-t-one-sample-t-test" class="section level3">

### [8.3.1]{.header-section-number} Teste t (one sample t-test)

-   Teste t (one sample t-test)
    -   Hipóteses:
        $H_{0}:\mu = \mu_{0}\quad \times \quad H_{1}:\mu \neq \mu_{0}.$
    -   Estatística de teste:
        $\frac{\bar{y} - \mu_{0}}{\hat{\sigma}/\sqrt{n}} \sim t_{n - 1}.$
-   Suposições: Para o teste ser exato, precisamos
    -   $Y \sim N(\mu,\sigma^{2})$ iid.
    -   ${\hat{\sigma}}^{2} = \sum_{i = 1}^{n}(y_{i} - \bar{y})^{2}/n - 1$.
-   Podem ser razoavelmente relaxadas para grandes amostras.
-   Neste caso a distribuição t não é mais necessária.
-   Assintóticamente a estatística tem distribuição Normal padrão.

**Exemplo 3**: (Magalhães e Lima, pg. 259). Deseja-se investigar se uma
certa moléstia que ataca o rim altera o consumo de oxigênio desse orgão.
Para indivíduos sadios, admite-se que esse consumo tem distribuição
Normal com média 12 $cm^{3}/min$. Os valores medidos em cinco pacientes
com a moléstia foram: $14,4;12,9;15,0;13,7;$ e $13,5$. Qual seria a
conclusão, ao nível de 1$\%$ de significância?

O teste de interesse é

-   $H_{0}:$ A moléstia não altera a média de consumo renal de oxigênio;
-   $H_{1}:$ Indivíduos portadores da moléstia têm média alterada.

Passando as hipóteses em termos do nosso modelo

-   $H_{0}:\mu = 12$ contra $H_{1}:\mu \neq 12$.

O R conta com uma função especifica para este teste, conforme mostra o
código abaixo.

<div class="sourceCode">

``` {.sourceCode .r}
y <- c(14.4,12.9,15,13.7,13.5)
t.test(x = y, mu = 12)

    One Sample t-test

data:  y
t = 5.2099, df = 4, p-value = 0.006472
alternative hypothesis: true mean is not equal to 12
95 percent confidence interval:
 12.88745 14.91255
sample estimates:
mean of x 
     13.9 
```

</div>

Neste caso rejeitamos $H_{0}$ em favor de $H_{1}$. Note que a função
retorna uma série de informações úteis. Temos o tipo de teste realizado,
o valor da estatística $t$ e os graus de liberdade do teste ao lado do
$p - valor$. A função já apresenta a conclusão do teste e por reporta o
intervalo de confiança para a média amostral e a média amostral.

</div>

<div id="ch009.xhtml#teste-t-independent-two-sample-t-test"
class="section level3">

### [8.3.2]{.header-section-number} Teste t (independent two sample t-test)

-   Teste t duas populações independentes variâncias iguais (independent
    two sample t-test)
    -   Hipóteses:
        $H_{0}:\mu_{1} = \mu_{2}\quad \times \quad H_{1}:\mu_{1} \neq \mu_{2}.$
    -   Estatística de teste:
        $\frac{{\bar{y}}_{1} - {\bar{y}}_{2}}{s_{p}\sqrt{\frac{1}{n_{1}} + \frac{1}{n_{2}}}} \sim t_{n_{1} + n_{2} - 2}.$
    -   $s_{p} = \sqrt{\frac{(n_{1} - 1)s_{1}^{2} + (n_{2} - 1)s_{2}^{2}}{n_{1} + n_{2} - 2}}$
        se variâncias assumidas iguais e tamanhos de amostras
        diferentes.

**Exemplo 4** Digitadores são treinados em uma empresa em duas turmas
distintas. Na primeira, denominada Turma J, utiliza-se um métodos
japonês de ensino, ao passo que na segunda turma, denominada Turma A,
utiliza-se um método alemão. Deseja-se comparar os dois métodos e para
tanto, 16 alunos de cada turma foram escolhidos aleatoriamente e uma
mesma tarefa foi atribuída a cada um. Ao final do experimento, o tempo
gasto na realização da tarefa, para cada aluno, foi anotado. No
processo, dois computadores utilizados pelos alunos selecionados da
turma J e três da turma A apresentaram problemas que impediram a
realização da tarefa; o tamanho da amostra foi assim reduzido para 14 e
13 respectivamente, para as turmas J e A. Os dados são os seguintes:

<div class="sourceCode">

``` {.sourceCode .r}
J <- c(10,13,9,10,14,13,10,15,12,10,9,10,13,14)
A <- c(15,12,18,16,15,17,17,15,16,17,11,17,14,NA)
dplyr::tibble(J,A)
# A tibble: 14 x 2
       J     A
   <dbl> <dbl>
 1    10    15
 2    13    12
 3     9    18
 4    10    16
 5    14    15
 6    13    17
 7    10    17
 8    15    15
 9    12    16
10    10    17
11     9    11
12    10    17
13    13    14
14    14    NA
```

</div>

Apesar de não conhecidas, as variâncias populacionais são assumidas
iguais com base em estudos anteriores. Suponha que o interesse é testar

-   $H_{0}:\mu_{J} = \mu_{A}$ contra $H_{1}:\mu_{J} \neq \mu_{A}$.

<div class="sourceCode">

``` {.sourceCode .r}
t.test(x = J, y = A, paired = FALSE, var.equal = TRUE)

    Two Sample t-test

data:  J and A
t = -4.7965, df = 25, p-value = 6.313e-05
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -5.450501 -2.175872
sample estimates:
mean of x mean of y 
 11.57143  15.38462 
```

</div>

</div>

<div id="ch009.xhtml#teste-t-variância-diferentes"
class="section level3">

### [8.3.3]{.header-section-number} Teste t variância diferentes

-   Teste t duas populações independentes variâncias diferentes
    (independent two sample t-test)
    -   Hipóteses:
        $H_{0}:\mu_{1} = \mu_{2}\quad \times \quad H_{1}:\mu_{1} \neq \mu_{2}.$
    -   Estatística de teste:
        $\frac{{\bar{y}}_{1} - {\bar{y}}_{2}}{s_{\delta}} \sim t_{df}.$
    -   $s_{\delta} = \sqrt{\frac{s^{1}}{n_{1}} + \frac{s^{2}}{n_{2}}}$
        se variâncias diferentes e tamanhos de amostras diferentes.
    -   Graus de liberdade
        $df = \frac{\left( \frac{s_{1}^{2}}{n_{1}} + \frac{s_{2}^{2}}{n_{2}} \right)}{\frac{(s_{1}^{2}/n_{1})^{2}}{n_{1} - 1} + \frac{(s_{2}^{2}/n_{2})^{2}}{n_{2} - 1}}.$

**Exemplo 5** Considere o exemplo dos digitadores, porém agora sem
assumir que as variâncias populacionais são iguais. O teste t neste caso
pode ser realizado da seguinte forma:

<div class="sourceCode">

``` {.sourceCode .r}
t.test(x = J, y = A, paired = FALSE, var.equal = FALSE)

    Welch Two Sample t-test

data:  J and A
t = -4.7967, df = 24.856, p-value = 6.399e-05
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -5.450930 -2.175444
sample estimates:
mean of x mean of y 
 11.57143  15.38462 
```

</div>

</div>

<div id="ch009.xhtml#teste-t-pareado" class="section level3">

### [8.3.4]{.header-section-number} Teste t pareado

-   Teste t duas populações dependentes (paired two sample t-test)
    -   Hipóteses:
        $H_{0}:\mu_{D} = 0\quad \times \quad H_{1}:\mu_{D} \neq 0.$
    -   Estatística de teste:
        $\frac{{\bar{y}}_{D} - 0}{{\hat{\sigma}}_{D}/\sqrt{n}} \sim t_{n - 1}.$
    -   Neste caso, $\mu_{D}$ e ${\hat{\sigma}}_{D}$ são a média e o
        desvio-padrão da diferença entre $y_{1}$ e $y_{2}$.

**Exemplo 6** Uma distribuidora de combustíveis deseja verificar se um
novo tipo de gasolina é eficaz na revitalização de moteores velhos. Com
esse objetivo, seleciona 12 automóveis de um mesmo modelo com mais de 8
anos de uso e, após regulagem de seus motores, verifica o consumo de
combustível. Em seguida, o carro é abastecido com o novo tipo de
combustível durante 15 semanas, e uma nova aferição do consumo é feita.
Defina as variáveis aleatórias $X_{i}$ e $Y_{i}$ como o rendimento do
automóvel $i$ respectivamente antes e após as 15 semanas. Vemos que
$X_{i}$ e $Y_{i}$ foram medidas em uma mesma unidade amostral e, assim,
é razoável assumir que exista alguma dependência entre elas. Os valores
observados, em $km/l$, junto com as diferenças $D_{i} = Y_{i} - X_{i}$,
para os 12 automóveis são apresentados na tabela a seguir.

<div class="sourceCode">

``` {.sourceCode .r}
Apos <- c(11.6,8.8,9.9,9.5,11.6,9.1,10.6,10.8,13.4,10.6,10.5,11.4)
Antes <- c(8.1,7.9,6.8,7.8,7.6,7.9,5.7,8.4,8,9.5,8,6.8)
D <- Apos - Antes
dplyr::tibble(Apos, Antes, D)
# A tibble: 12 x 3
    Apos Antes     D
   <dbl> <dbl> <dbl>
 1  11.6   8.1  3.5 
 2   8.8   7.9  0.9 
 3   9.9   6.8  3.1 
 4   9.5   7.8  1.7 
 5  11.6   7.6  4   
 6   9.1   7.9  1.20
 7  10.6   5.7  4.90
 8  10.8   8.4  2.4 
 9  13.4   8    5.4 
10  10.6   9.5  1.10
11  10.5   8    2.5 
12  11.4   6.8  4.6 
```

</div>

Queremos testar as hipóteses - $H_{0}:$ $\mu_{D} = 0$ (a intervenção não
produz efeito) - $H_{1}:$ $\mu_{D} \neq 0$ (a intervenção produz algum
efeito)

<div class="sourceCode">

``` {.sourceCode .r}
t.test(x = Apos, y = Antes, paired = TRUE)

    Paired t-test

data:  Apos and Antes
t = 6.5396, df = 11, p-value = 4.195e-05
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 1.951609 3.931724
sample estimates:
mean of the differences 
               2.941667 
```

</div>

</div>

<div id="ch009.xhtml#teste-f" class="section level3">

### [8.3.5]{.header-section-number} Teste F

-   Teste F para igualdade de variâncias.
    -   Hipóteses:
        $H_{0}:\sigma_{1}^{2} = \sigma_{2}^{2}\quad \times H_{1}:\sigma_{1}^{2} \neq \sigma_{2}^{2}$.
    -   Estatística de teste:
        $F = \frac{s_{1}^{2}}{s_{2}^{2}} \sim F_{(n_{1} - 1)(n_{2} - 1)}$.
    -   Suposições $Y_{1} \sim N(\mu_{1},\sigma_{1}^{2})$ e
        $Y_{2} \sim N(\mu_{2},\sigma_{2}^{2})$.
    -   Em geral, este teste é conhecido por ser sensível a suposição de
        normalidade.
-   Se normalidade é duvidosa, use o teste para variâncias diferentes.
-   Poder e tamanho do teste podem ser altamente sensíveis a suposições.
-   Para grandes amostras o TCL fornece uma opção robusta a
    não-normalidade.
-   **Regra do dedão** Amostra maior que $30$ TCL funciona bem!
-   Mas cuidado!! depende da situação!!

**Exemplo 7** Sabe-se que em uma região do país a altura média é de
$1,68$m, com variância de $0,30m^{2}$. Um pesquisador acredita que a
alimentação rotineira em uma cidade litorânea, sendo diferente da região
como um todo, contribui para que as pessoas apresentem alturas mais
homogêneas, apesar de não alterar a altura média da população da cidade.
Para verificar sua suspeita, ele coletou um amostra de 31 pessoas e
obteve a seguinte amostra:

<div class="sourceCode">

``` {.sourceCode .r}
y <- c(1.77, 1.72, 2.39, 1.95, 1.69, 1.84, 1.86, 1.57, 1.38, 1.47, 1.94, 
       1.15, 1.93, 2.18, 1.37, 1.56, 1.28, 1.81, 1.66, 1.99, 2.07, 1.67, 
       1.40, 1.03, 1.58, 1.99, 1.48, 1.73, 1.44, 1.35, 1.54)
```

</div>

Além disso, coletou um conjunto de 20 observações da população geral.

<div class="sourceCode">

``` {.sourceCode .r}
set.seed(123)
x <- rnorm(20, mean = 1.68, sd = 0.30)
```

</div>

Realize um teste de hipótese para verificar - $H_{0}:\sigma^{2} = 0,30$
contra $H_{1}:\sigma^{2} < 0,30$.

<div class="sourceCode">

``` {.sourceCode .r}
var.test(y, x, alternative = "less")

    F test to compare two variances

data:  y and x
F = 1.1044, num df = 30, denom df = 19, p-value = 0.5811
alternative hypothesis: true ratio of variances is less than 1
95 percent confidence interval:
 0.000000 2.148239
sample estimates:
ratio of variances 
           1.10436 
```

</div>

</div>

</div>

<div id="ch009.xhtml#exercícios-19" class="section level2 unnumbered">

Exercícios
----------

1.  Uma empresa de pesquisa de mercado usou uma amostra de indivíduos
    para avaliar o potencial de compra de determinado produto antes e
    depois de as pessoas virem um novo comercial de televisão a respeito
    do produto. As avaliações do potencial de compra basearam-se em uma
    escala de 0 a 10, e os valores mais altos indicavam maior potencial
    de compra. A hipótese nula declarava que a avaliação média depois
    seria igual a avaliação média antes. A rejeição dessa hipótese
    demonstraria que o comercial melhorou a avaliação do potencial médio
    de compra. Use $\alpha = 0,05$ e os dados apresentados abaixo para
    testar a hipótese e comentar o valor do comercial.

<!-- -->

    # A tibble: 8 x 3
        ind Depois Antes
      <int>  <dbl> <dbl>
    1     1      6     5
    2     2      6     4
    3     3      7     7
    4     4      4     3
    5     5      3     5
    6     6      9     8
    7     7      7     5
    8     8      6     6

2.  Os preços por galçao (3,78 litros) de gasolina para carros de
    aluguel foram amostrados em oito grandes aeroportos. Os dados
    relativos às empresas de carros de aluguel Hertz e National são
    apresentados a seguir

<!-- -->

    # A tibble: 8 x 3
      Aero                   Hertz National
      <chr>                  <dbl>    <dbl>
    1 Boston                  1.55     1.56
    2 Chicago                 1.62     1.59
    3 " Los Angeles"          1.72     1.78
    4 Miami                   1.65     1.49
    5 Nova York (JFK)         1.72     1.51
    6 Nova York (La Guardia)  1.67     1.5 
    7 Orange County           1.68     1.77
    8 Washington              1.52     1.41

Use $\alpha = 0,05$ para testar a hipótese de que não há diferença entre
os preços médios populacionais por galão em relação às duas empresas.

3.  Na Western University, a média histórica das pontuações nos exames
    para obtenção de bolsas de estudo correspondente às inscrições
    feitas por calouros é 900. Presume-se que o desvio padrão histórico
    da população é $\sigma = 180$ seja conhecido. Anualmente, o
    vice-reitor usa uma amostra das inscrições para determinar se a
    média da pontuação nos exames dos calouros se modificou.
    -   Estabeleça as hipóteses.
    -   Qual é a estimação pontual e o intervalo de confiança de $95\%$
        da média populacional nos exames se a seguinte amostra de
        tamanho 50 for observada.

<!-- -->

    # A tibble: 10 x 1
       `matrix(x, 10, 5)`[,1]  [,2]  [,3]  [,4]  [,5]
                        <dbl> <dbl> <dbl> <dbl> <dbl>
     1                   799. 1120.  708.  977.  775.
     2                   859.  965.  861.  847.  863.
     3                  1181.  972.  715. 1061.  672.
     4                   913.  920.  769. 1058. 1290.
     5                   923.  800.  787. 1048. 1117.
     6                  1209. 1222.  596. 1024.  698.
     7                   983.  990. 1051. 1000.  827.
     8                   672.  546.  928.  889.  816.
     9                   776. 1026.  695.  845. 1040.
    10                   820.  815. 1126.  832.  885.

-   Realize um teste de hipótese para verificar a suspeita do
    vice-reitor. Use $\alpha = 0,05$. Qual é a sua conclusão?

4.  Mensalmente o governo federal publica uma série de estatísticas
    sobre o número de pessoas que estão desempregadas e a média de tempo
    em que estão desempregadas. Em relação a novembro de 1998, o governo
    divulgou que a duração média nacional de desemprego era 14,6
    semanas. O prefeito de Curitiba solicitou um estudo sobre a situação
    de desemprego na cidade. Uma amostra de 50 habitantes desempregados
    em Curitiba incluiu dados sobre a idade e o número de semanas em que
    estavam desempregados. O conjunto de dados é apresentado abaixo:

<!-- -->

       Idade.1.10. Semanas.1.10. Idade.11.20. Semanas.11.20. Idade.21.30.
    1           36             9           32              7           30
    2           34             7           47              8           38
    3           34             7           27              8           34
    4           43            11           36              9           30
    5           33            12           37             12           36
    6           43             6           35              9           34
    7           25            13           40              7           35
    8           28            10           47              8           37
    9           36             9           32              4           32
    10          37             4           29              6           30
       Semanas.21.30. Idade.31.40. Semanas.31.40. Idade.41.50. Semanas.41.50.
    1               7           36             10           32             10
    2               6           41              7           44              5
    3              11           37             14           33              7
    4               5           33             14           28              8
    5              10           41             10           45             11
    6               8           40              6           35             12
    7               9           38              6           41             11
    8               5           36              9           31              9
    9               9           31              6           34             13
    10              6           42              8           30              8

-   Use estatísticas descritivas para resumir os dados.
-   Desenvolva uma estimação por intervalo de confiança de $95\%$ da
    média de idade e semanas desempregadas em Curitiba.
-   Realize um teste de hipótese para determinar se a duração média do
    desemprego em Curitiba é maior que a duração média nacional de 14,6
    semanas. Use um nível de confiança de 0,01. Qual a sua conclusão.
-   Há uma relação entre a idade do individuo desempregado e o número de
    semanas de desemprego? Explique.

<!--chapter:end:08-inferencia.Rmd-->

</div>

</div>

[]{#ch010.xhtml}

<div id="ch010.xhtml#apêndice" class="section level1 unnumbered">

Apêndice
========

</div>

[]{#ch011.xhtml}

<div id="ch011.xhtml#documentos-dinâmicos" class="section level1">

[9]{.header-section-number} Documentos dinâmicos
================================================

A ideia geral de um documento dinâmico é a de que ele pode ser gerado a
partir de um **código-fonte**:

-   Da mesma forma que um *software* possui seu código-fonte, um
    documento dinâmico é o código-fonte de um relatório.
-   É uma combinação de código de computador e as correspondentes
    narrativas descrevendo o resultado que o código está gerando
    (números, tabelas, figuras, ...).
-   Quando **compilamos** o documento dinâmico, o código de computador é
    executado, e as saídas são apresentadas. Portanto obtemos um
    documento final que mistura **código** e **texto**.

Como gerenciamos apenas o código-fonte do documento, ficamos livres de
etapas manuais como ter que refazer um gráfico ou uma tabela após
qualquer alteração na análise.

<div id="ch011.xhtml#literate-programming" class="section level2">

[9.1]{.header-section-number} Literate Programming
--------------------------------------------------

> *Instead of imagining that our main task is to instruct a computer
> what to do, let us concentrate rather on explaining to humans what we
> want the computer to do.*
>
> > Donald Knuth

O ideia básica por trás de documentos dinâmicos decorre diretamente do
conceito de *literate programming* ("programação letrada"), um paradigma
concebido por [Donald Knuth](https://en.wikipedia.org/wiki/Donald_Knuth)
em 1984.

  ----------------------- -----------------------
  ![](media/file49.jpg)   ![](media/file50.jpg)
  ----------------------- -----------------------

O objetivo da *literate programming* é criar um documento que
"entrelaça" (mistura) texto e código. O texto é legível para humanos e o
código é legível para máquinas. A análise é descrita em uma série de
texto e blocos de código (*code chunks*). Cada bloco de código irá
executar uma etapa da análise, e estará diretamente associado ao texto
explicativo acima ou abaixo do bloco.

<!-- - O conceito é o de misturar **literatura** (o texto em uma -->
<!--   linguagem humana) com **códigos de programação**, tornando claro cada -->
<!--   etapa de um programa e/ou análise -->
O processo de *literate programming* ocorre em duas vias, chamadas de
**weaving** e **tangling**. O importante é que, **com um único
código-fonte** podemos:

-   Produzir documentos para humanos (HTML, PDF, ...) $\Rightarrow$
    *weave*
-   Produzir "documentos" (*scripts*) para máquinas (código)
    $\Rightarrow$ *tangle*

Para podermos usar um sistema como esse, é necessário então uma
linguagem de documentação para humanos (*e.g.* LaTeX ou Markdown), e uma
linguagem de programação que será compilada com o documento (*e.g.* R ou
Python).

Knuth criou inicialmente um sistema chamado **WEB** para fazer essa
mistura dos seus textos em $TeX$ com a linguagem Pascal. Atualmente
muitos outros sistemas existem para misturar códigos com texto em várias
linguagens de documentação e de programação.

</div>

<div id="ch011.xhtml#literate-programming-no-r" class="section level2">

[9.2]{.header-section-number} Literate Programming no R
-------------------------------------------------------

Com a ascensão do R no início dos anos 2000, [Friedrich
Leisch](http://www.statistik.lmu.de/~leisch) criou o
[Sweave](https://www.statistik.lmu.de/~leisch/Sweave) em 2002

-   S + weave
-   Permite "entrelaçar" textos do LaTeX com códigos do R
-   Ainda é muito utilizado e já é distribuído como uma função do R
    dentro do pacote `utils`

No final de 2011, [Yihui Xie](http://yihui.name/) criou o pacote
[knitr](http://yihui.name/knitr) como uma extensão do Sweave, e com a
proposta de ser mais flexível, fácil e **preparado para a Web**. Segundo
o próprio autor, o knitr é resultado dessa equação:

<div class="sourceCode">

``` {.sourceCode .r}
knitr = Sweave + cacheSweave + pgfSweave + weaver +
    animation::saveLatex + R2HTML::RweaveHTML +
    highlight::HighlightWeaveLatex + 0.2 * brew +
    0.1 * SweaveListingUtils + more
```

</div>

Resumidamente, o knitr possui as seguintes vantagens sob o Sweave:

-   knit + R
-   Uma re-implementação mais moderna do Sweave
-   Permite "entrelaçar" textos do LaTeX, HTML e **Markdown** com
    códigos do R
-   Também permite misturar texto com códigos de **outras linguagens**:
    Python, awk, C++, shell.
-   Adiciona muitas facilidades como
    -   Cache
    -   Decoração e formatação automática de códigos
    -   Geração de gráficos mais direta

Podemos fazer uma comparação entre arquivos LaTeX escritos em Sweave e
knitr. Exemplos simples podem ser vistos nos arquivos
[Exemplo0-Sweave.Rnw](exemplos/Exemplo0-Sweave.Rnw) escrito com Sweave e
[Exemplo0-knitr.Rnw](exemplos/Exemplo0-knitr.Rnw) escrito com a sintaxe
do knitr. Para compilar estes documentos, usamos

<div class="sourceCode">

``` {.sourceCode .r}
Sweave("Exemplo0-Sweave.Rnw")
library(knitr)
knit("Exemplo0-knitr.Rnw")
```

</div>

Posteriormente, os arquivos `.tex` gerados podem ser compilados com
qualquer distribuição LaTeX, (*e.g* TeXLive, MikTeX), por exemplo

<div class="sourceCode">

``` {.sourceCode .sh}
pdflatex Exemplo0-Sweave.Rnw
pdflatex Exemplo0-knitr.Rnw
```

</div>

Os resultados podem ser vistos nos respectivos arquivos:
[Exemplo0-Sweave.pdf](exemplos/Exemplo0-Sweave.pdf) e
[Exemplo0-knitr.pdf](exemplos/Exemplo0-knitr.pdf)

</div>

<div id="ch011.xhtml#markdown" class="section level2">

[9.3]{.header-section-number} Markdown
--------------------------------------

Segundo o próprio criador da linguagem:

> *Markdown is a text-to-HTML conversion tool for web writers. Markdown
> allows you to write using an easy-to-read, easy-to-write plain text
> format, then convert it to structurally valid XHTML (or HTML).*
>
> > John Gruber

-   [Markdown](http://daringfireball.net/projects/markdown) é uma
    [linguagem de
    marcação](https://pt.wikipedia.org/wiki/Linguagem_de_marcação/)
    simples para escrever textos
-   O texto pode ser lido sem nenhum processamento, ou seja, da maneira
    como está escrito
-   Outras linguagens de marcação como HTML e LaTeX requerem um grande
    número de *tags* para formatar o texto, muitas vezes dificultando a
    leitura do código-fonte
-   A proposta do Markdown é que o escritor se concentre no texto e não
    na formatação
-   Pode ser convertido para **vários outros formatos** além de HTML

<div id="ch011.xhtml#sintaxe-do-markdown" class="section level3">

### [9.3.1]{.header-section-number} Sintaxe do Markdown

A sintaxe do Markdown é muito simples, e pode ser resumida da seguinte
forma:

<div id="ch011.xhtml#cabeçalhos" class="section level4 unnumbered">

#### Cabeçalhos

    # Título
    ## Sub-título
    ### Sub-sub-título

</div>

<div id="ch011.xhtml#itálico" class="section level4 unnumbered">

#### Itálico

    *Este texto aparecerá em itálico.*

*Este texto aparecerá em itálico.*

</div>

<div id="ch011.xhtml#negrito" class="section level4 unnumbered">

#### Negrito

    **Este texto aparecerá em negrito.**

**Este texto aparecerá em negrito.**

</div>

<div id="ch011.xhtml#listas-não-ordenadas"
class="section level4 unnumbered">

#### Listas não-ordenadas

    - Primeiro item
    - Segundo item
    - Terceiro item

-   Primeiro item
-   Segundo item
-   Terceiro item

</div>

<div id="ch011.xhtml#listas-ordenadas"
class="section level4 unnumbered">

#### Listas ordenadas

    1. Primeiro item
    2. Segundo item
    3. Terceiro item

1.  Primeiro item
2.  Segundo item
3.  Terceiro item

</div>

<div id="ch011.xhtml#sub-listas" class="section level4 unnumbered">

#### Sub-listas

Utilize 4 espaços para criar uma sub-lista:

    1. Primeiro item
        - Um sub-item
        - Outro sub-item
    2. Segundo item
    3. Terceiro item

1.  Primeiro item
    -   Um sub-item
    -   Outro sub-item
2.  Segundo item
3.  Terceiro item

</div>

<div id="ch011.xhtml#links" class="section level4 unnumbered">

#### Links

Links para endereços Web podem ser inseridos com `[texto](link)`:

    O criador do conceito de "literate programming" foi
    [Donald Knuth](https://en.wikipedia.org/wiki/Donald_Knuth).

O criador do conceito de "literate programming" foi [Donald
Knuth](https://en.wikipedia.org/wiki/Donald_Knuth).

    Devemos instalar o pacote [knitr](http://yihui.name/knitr) para poder
    usar o R Markdown.

Devemos instalar o pacote [knitr](http://yihui.name/knitr) para poder
usar o R Markdown.

</div>

<div id="ch011.xhtml#imagens" class="section level4 unnumbered">

#### Imagens

Para inserir uma imagem, a sintaxe é a mesma de inserir um link, mas com
uma exclamação (`!`) na frente: `![texto](imagem)`.

O link para a imagem pode ser um enderço Web:

    ![Logo do R](img/Rlogo-5.png)

<figure>
![Logo do R](media/file51.png)
<figcaption>
Logo do R
</figcaption>
</figure>
Ou um endereço local:

    ![Logo do Markdown](img/markdown.png)

<figure>
![Logo do Markdown](media/file52.png)
<figcaption>
Logo do Markdown
</figcaption>
</figure>

</div>

<div id="ch011.xhtml#parágrafo" class="section level4 unnumbered">

#### Parágrafo

Para criar parágrafos basta pular uma linha:

    O criador do conceito de "literate programming" foi
    [Donald Knuth](https://en.wikipedia.org/wiki/Donald_Knuth).

    Devemos instalar o pacote [knitr](http://yihui.name/knitr) para poder
    usar o R Markdown.

O criador do conceito de "literate programming" foi [Donald
Knuth](https://en.wikipedia.org/wiki/Donald_Knuth).

Devemos instalar o pacote [knitr](http://yihui.name/knitr) para poder
usar o R Markdown.

</div>

<div id="ch011.xhtml#códigos" class="section level4 unnumbered">

#### Códigos

Para apresentar códigos na própria linha, colocamos o texto entre duas
crases (`` ` ``):

    Para gerar números aleatórios de uma distribuição normal no R, use a
    função `rnorm()`.

Para gerar números aleatórios de uma distribuição normal no R, use a
função `rnorm()`.

Para apresentar blocos de código, coloque o texto entre três crases
seguidas (```` ``` ````) no início e no final. O bloco

    ```
    x <- rnorm(n = 10, mean = 100, sd = 5)
    hist(x, main = "")
    ```

Irá gerar

    x <- rnorm(n = 10, mean = 100, sd = 5)
    hist(x, main = "")

Note que esse código não será interpretado, ele apenas será mostrado no
texto. Esse será o papel do R aqui mais adiante!

</div>

<div id="ch011.xhtml#tabelas" class="section level4 unnumbered">

#### Tabelas

Tabelas podem ser escritas da seguinte forma:

        Caracter | Permissão
        ---------|----------
        `r`      | Permissão de leitura (*read*)
        `w`      | Permissão de escrita (*write*)
        `x`      | Permissão de execução (*execute*)
        `-`      | Permissão desabilitada

Para gerar o seguinte resultado:

  Caracter   Permissão
  ---------- -----------------------------------
  `r`        Permissão de leitura (*read*)
  `w`        Permissão de escrita (*write*)
  `x`        Permissão de execução (*execute*)
  `-`        Permissão desabilitada

</div>

<div id="ch011.xhtml#equações-matemáticas"
class="section level4 unnumbered">

#### Equações matemáticas

Equações matemáticas podem ser escritas em formato LaTeX. A página HTML
resultante irá renderizar as equações através do
[MathJax](http://www.mathjax.org).

Equações na própria linha podem ser inseridas entre `$`:

    Um modelo de regressão linear simples:  $Y = \beta_0 + \beta_1 x + \epsilon$.

Um modelo de regressão linear simples:
$Y = \beta_{0} + \beta_{1}x + \epsilon$.

Equações podem ser exibidas entre `$$` para ficarem centralizadas em uma
linha própria:

    $$
    f(x;\mu,\sigma^2) = \frac{1}{\sigma\sqrt{2\pi}}
    e^{ -\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2 }
    $$

$$f(x;\mu,\sigma^{2}) = \frac{1}{\sigma\sqrt{2\pi}}e^{- \frac{1}{2}{(\frac{x - \mu}{\sigma})}^{2}}$$

</div>

</div>

<div id="ch011.xhtml#escrevendo-um-documento-em-markdown"
class="section level3">

### [9.3.2]{.header-section-number} Escrevendo um documento em Markdown

Um documento Markdown possui a extensão `.md` (embora não seja a única
possível).

Veja o arquivo de exemplo [Exemplo1.md](exemplos/Exemplo1.md):

    # Um documento em Markdown

    ## Sobre o Markdown

    O Markdown é uma linguagem de marcação muito simples, desenvolvida por
    John Gruber.

    A ideia básica por trás da linguagem é fazer com que o escritor se
    preocupe mais com o **conteúdo** do texto do que com a *formatação*.

    ## Mais um título

    Aqui vamos tentar descrever uma análise.

    ## Simulando variáveis aleatórias

    No R podemos simular valores de uma distribuição normal padrão através
    da função `rnorm()`.

    Seja $X \sim \text{N}(0,1)$, então para gerar 30 valores dessa variável
    aleatório normal, fazemos

    ```
    (x <- rnorm(30))
    ```

    Com o resultado dessa simulação, podemos calcular a média e a variância
    dessa VA $X$ para conferir se o resultado fica próximo de 0 e 1,
    respectivamente.

    Também podemos fazer um histograma dessa VA $X$ simulada

    ```
    hist(x)
    ```

Para converter um documento Markdown em HTML (ou outro formato) é
necessário um **conversor**. O conversor padrão do Markdown é escrito em
Perl, e pode ser integrado em diversas ferramentas, mas não é apropriado
para usuários comuns. Para testar a conversão do documento, copie e cole
na página do
[Dingus](http://daringfireball.net/projects/markdown/dingus).

</div>

</div>

<div id="ch011.xhtml#pandoc" class="section level2">

[9.4]{.header-section-number} Pandoc
------------------------------------

O [Pandoc](http://pandoc.org/) é um conversor extremamente versátil,
capaz de converter diversos formatos, incluindo Markdown para HTML.

Se o Pandoc estiver instalado no seu sistema (Unix) é possível converter
o documento na linha de comando (shell) com

<div class="sourceCode">

``` {.sourceCode .sh}
pandoc -f markdown -t html Exemplo1.md -o Exemplo1.html
```

</div>

O pacote `knitr` possui a função `pandoc()` que é um *wrapper* para
executar o programa `pandoc` no sistema.

<div class="sourceCode">

``` {.sourceCode .r}
pandoc(input = "exemplos/Exemplo1.md", format = "html")
```

</div>

Em ambos os casos, o resultado pode ser visualizado ao abrir o arquivo
[Exemplo1.html](exemplos/Exemplo1.html) no navegador.

</div>

<div id="ch011.xhtml#documentos-dinâmicos-com-markdown-e-r"
class="section level2">

[9.5]{.header-section-number} Documentos dinâmicos com Markdown e R
-------------------------------------------------------------------

No exemplo anterior, escrevemos um documento em Markdown (`.md`) e
inserimos códigos do R, que são apenas apresentados no documento final.
Desse forma temos um documento **estático**, pois os códigos não são
interpretados. Para fazermos esse documento ser **dinâmico**, vamos usar
o pacote **knitr** a nosso favor, fazedo com que ele interprete e
retorne resultados dos códigos que inserimos. Vamos denominar
genericamente essa combinação de texto em Markdown e códigos do R de "R
Markdown".

Arquivos escritos em R Markdown não podem ser compilados usando
ferramentas padrão de conversão de Markdown. O código R deve ser
avaliado antes da conversão usando o Pandoc, por exemplo. R Markdown
pode ser convertido para Markdown através do knitr. Os resultados de
códigos do R são inseridos entre o texto em Markdown, que pode então ser
convertido para HTML (ou outros formatos) usando o Pandoc.

O uso do R Markdown para criar documentos dinâmicos tem se tornado uma
ferramenta chave atualmente em *literate statistical programming*, e
substituiu largamente ferramentas anteriores como o Sweave.

Os detalhes e opções do pacote knitr serão descritas mais adiante. Por
enquanto, o que precisamos fazer para tornar esse documento dinâmico é
alterar a extensão do arquivo de `.md` para `.Rmd`, e alterar a forma
dos blocos de código. Os blocos de códigos (ou *chunks*) agora devem
conter uma marcação especial para indicar que devem ser interpretados
pelo R, através do knitr. Para isso, colocamos `{r}` no início de cada
bloco, que agora ficam

    ```{r}
    x <- rnorm(30)
    ```

Usando o mesmo exemplo anterior, vamos renomear o arquivo `Exemplo1.md`
para `Exemplo1-knitr.Rmd` e incluir a marção `{r}` nos blocos de código.

Também é possível colocar códigos do R para serem renderizados na
própria linha de texto com `` `r ` ``. Por exemplo, `` `r 2+2` `` gera o
resultado 4 no documento.

Veja o arquivo [Exemplo1-knitr.Rmd](exemplos/Exemplo1-knitr.Rmd).

    # Um documento em Markdown

    ## Sobre o Markdown

    O Markdown é uma linguagem de marcação muito simples, desenvolvida por
    John Gruber.

    A ideia básica por trás da linguagem é fazer com que o escritor se
    preocupe mais com o **conteúdo** do texto do que com a *formatação*.

    ## Mais um título

    Aqui vamos tentar descrever uma análise.

    ## Simulando variáveis aleatórias

    No R podemos simular valores de uma distribuição normal padrão através
    da função `rnorm()`.

    Seja $X \sim \text{N}(0,1)$, então para gerar 30 valores dessa variável
    aleatório normal, fazemos

    ```{r}
    (x <- rnorm(30))
    ```

    ## Comentários

    Com o resultado dessa simulação, podemos calcular a média e a variância
    dessa VA $X$ para conferir se o resultado fica próximo de 0 e 1,
    respectivamente.

    ## Visualização

    Também podemos fazer um histograma dessa VA $X$ simulada

    ```{r}
    hist(x)
    ```

    A média de $X$ é `r round(mean(x), 3)`.

Agora usamos o knitr, através da função `knit()` para compilar o
documento `.Rmd` em um documento com sintaxe Markdown `.md`

<div class="sourceCode">

``` {.sourceCode .r}
knit("exemplos/Exemplo1-knitr.Rmd", output = "exemplos/Exemplo1-knitr.md")


processing file: exemplos/Exemplo1-knitr.Rmd

  |                                                                            
  |                                                                      |   0%
  |                                                                            
  |..............                                                        |  20%
  ordinary text without R code


  |                                                                            
  |............................                                          |  40%
label: unnamed-chunk-451

  |                                                                            
  |..........................................                            |  60%
  ordinary text without R code


  |                                                                            
  |........................................................              |  80%
label: unnamed-chunk-452

  |                                                                            
  |......................................................................| 100%
   inline R code fragments
output file: exemplos/Exemplo1-knitr.md
[1] "exemplos/Exemplo1-knitr.md"
```

</div>

![](media/file53.png){width="80%"}

O resultado da compilação pode ser vista no arquivo
[Exemplo1-knitr.md](exemplos/Exemplo1-knitr.md).

    # Um documento em Markdown

    ## Sobre o Markdown

    O Markdown é uma linguagem de marcação muito simples, desenvolvida por
    John Gruber.

    A ideia básica por trás da linguagem é fazer com que o escritor se
    preocupe mais com o **conteúdo** do texto do que com a *formatação*.

    ## Mais um título

    Aqui vamos tentar descrever uma análise.

    ## Simulando variáveis aleatórias

    No R podemos simular valores de uma distribuição normal padrão através
    da função `rnorm()`.

    Seja $X \sim \text{N}(0,1)$, então para gerar 30 valores dessa variável
    aleatório normal, fazemos

    ```r
    (x <- rnorm(30))
     [1] -0.50219235  0.13153117 -0.07891709  0.88678481  0.11697127  0.31863009
     [7] -0.58179068  0.71453271 -0.82525943 -0.35986213  0.08988614  0.09627446
    [13] -0.20163395  0.73984050  0.12337950 -0.02931671 -0.38885425  0.51085626
    [19] -0.91381419  2.31029682 -0.43808998  0.76406062  0.26196129  0.77340460
    [25] -0.81437912 -0.43845057 -0.72022155  0.23094453 -1.15772946  0.24707599
    ```

    ## Comentários

    Com o resultado dessa simulação, podemos calcular a média e a variância
    dessa VA $X$ para conferir se o resultado fica próximo de 0 e 1,
    respectivamente.

    ## Visualização

    Também podemos fazer um histograma dessa VA $X$ simulada

    ```r
    hist(x)
    ```

    <img src="figures/unnamed-chunk-452-1.png" style="display: block; margin: auto;" />

    A média de $X$ é 0.029.

Agora temos um documento em Markdown com os códigos do R avaliados. Mas
ainda precisamos processar esse arquivo para gerar o arquivo `.html`
através do Pandoc

<div class="sourceCode">

``` {.sourceCode .r}
pandoc(input = "exemplos/Exemplo1-knitr.md", format = "html")
Executing: pandoc -t html -o 'exemplos/Exemplo1-knitr.html' 'exemplos/Exemplo1-knitr.md'
[1] "exemplos/Exemplo1-knitr.html"
```

</div>

que gera o arquivo [Exemplo1-knitr.html](exemplos/Exemplo1-knitr.html)
que pode ser visualizado no navegador.

</div>

<div id="ch011.xhtml#r-markdown-e-knitr" class="section level2">

[9.6]{.header-section-number} R Markdown e knitr
------------------------------------------------

O pacote knitr, como já mencionado, é uma combinação de várias ideias
desenvolvidas separadamente em pacotes do R para *literate programming*,
especialmente o Sweave. Este pacote suporta LaTeX, Markdown e HTML como
**linguagem de documentação**, e algumas linguagens de programação, além
do R, como por exemplo shell e Python. O resultado destes documentos
pode ser exportado para PDF, HTML, ou até mesmo arquivos do MS Word.
Daqui em diante, o nosso foco será no uso do knitr com Markdown e R,
pela simplicidade e versatilidade dessa linguagem, gerando documentos
dinâmicos em HTML. No entanto, a maioria das opções e o funcionamento
geral do pacote é similar para LaTeX (e compilação para PDF) e HTML.

Na seção anterior, nós criamos um arquivo com a extensão `.Rmd`, que é
apropriada para documentos escritos em Markdown com R. Nós também usamos
as funções `knitr()` para converter o documento para Markdown, e
posteriormente a função `pandoc()` para gerar o HTML resultante. Esse é
o processo básico para gerar documentos dinâmicos no R. No entanto,
podemos estender esse processo para incorporar mais controle tanto sob
os códigos que são gerados, quanto na apresentação do documento final.

Para facilitar a criação de documentos dinâmicos no R, a equipe do
RStudio desenvolveu o pacote [rmarkdown](http://rmarkdown.rstudio.com),
que é baseado no knitr e Pandoc, e contém opções padrão para gerar
documentos em vários formatos de maneira mais aprimorada.

A principal função para gerar documentos em R Markdown do pacote
rmarkdown é a `render()`. A função `render()` é uma *wrapper* que
internamente chama a `knitr::knit()` e posteriormente converte o
documento para `.html` usando o Pandoc. A diferença é que, além de ser
um processo mais direto, a saída em formato HTML utiliza temas mais
amigáveis, como o Twitter Bootstrap, que possibilita grandes opções de
configuração mais avançada.

Para usar esse função você precisa:

1.  Instalar o pacote `rmarkdown` com `install.packages("rmarkdown")`
2.  Instalar o Pandoc no seu sistema

No RStudio, esse pacote já vem instalado, assim como uma versão embutida
do Pandoc.

Usando o exemplo anterior, vamos compilar o arquivo
[Exemplo2-knitr.Rmd](exemplos/Exemplo2-knitr.Rmd). O primeiro argumento
da função é o nome (e local) do arquivo, e o segundo argumento é o
formato de saída, que por padrão é HTML.

<div class="sourceCode">

``` {.sourceCode .r}
library(rmarkdown)
render("exemplos/Exemplo2-knitr.Rmd",  output_format = "html_document")


processing file: Exemplo2-knitr.Rmd

  |                                                                            
  |                                                                      |   0%
  |                                                                            
  |..............                                                        |  20%
  ordinary text without R code


  |                                                                            
  |............................                                          |  40%
label: unnamed-chunk-1-2

  |                                                                            
  |..........................................                            |  60%
  ordinary text without R code


  |                                                                            
  |........................................................              |  80%
label: unnamed-chunk-3-4

  |                                                                            
  |......................................................................| 100%
   inline R code fragments
output file: Exemplo2-knitr.knit.md
/usr/bin/pandoc +RTS -K512m -RTS Exemplo2-knitr.utf8.md --to html4 --from markdown+autolink_bare_uris+tex_math_single_backslash --output Exemplo2-knitr.html --smart --email-obfuscation none --self-contained --standalone --section-divs --template /home/travis/R/Library/rmarkdown/rmd/h/default.html --no-highlight --variable highlightjs=1 --variable 'theme:bootstrap' --include-in-header /tmp/RtmpmKPuzt/rmarkdown-str30b22bcffc7c.html --mathjax --variable 'mathjax-url:https://mathjax.rstudio.com/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML' 

Output created: Exemplo2-knitr.html
```

</div>

![](media/file54.png){width="80%"}

E o resultado pode ser visto no arquivo
[Exemplo2-knitr.html](exemplos/Exemplo2-knitr.html).

No RStudio, esse processo todo pode ser feito pelo botão <kbd>Knit<kbd>.

<div id="ch011.xhtml#metadados" class="section level3">

### [9.6.1]{.header-section-number} Metadados

Uma opção interessante ao utilizar o Pandoc é incluir metados no formato
[YAML](http://yaml.org/) (*Yet Another Markup Language*). Os metadados
em YAML são escritos em formato de lista aninhada, e o Pandoc usa essas
informações para incluir, por exemplo, título, autor, e data em um
documento.

A opção mais importante para o `rmarkdown` é o campo `output`, que
permite especificar o formato desejado de saída, o mesmo especificado no
argumento `output_format =` da função `render()`.

Os metadados em YAML são colocados sempre no **início** de um documento,
e são delimitados por `---`. Um exemplo típico seria:

    ---
    title: "Meu primeiro documento em R Markdown"
    author: "Fernando Mayer"
    date: "Abril, 2018"
    output: html_document
    ---

Com isso, não é mais necessário especificar o argumento
`output_format =` na chamada da função `render()`.

Veja o arquivo [Exemplo1-yaml.Rmd](exemplos/Exemplo1-yaml.Rmd). Para
renderizar esse aquivo, usamos:

<div class="sourceCode">

``` {.sourceCode .r}
render("exemplos/Exemplo1-yaml.Rmd")


processing file: Exemplo1-yaml.Rmd

  |                                                                            
  |                                                                      |   0%
  |                                                                            
  |..............                                                        |  20%
  ordinary text without R code


  |                                                                            
  |............................                                          |  40%
label: unnamed-chunk-1-2

  |                                                                            
  |..........................................                            |  60%
  ordinary text without R code


  |                                                                            
  |........................................................              |  80%
label: unnamed-chunk-3-4

  |                                                                            
  |......................................................................| 100%
   inline R code fragments
output file: Exemplo1-yaml.knit.md
/usr/bin/pandoc +RTS -K512m -RTS Exemplo1-yaml.utf8.md --to html4 --from markdown+autolink_bare_uris+tex_math_single_backslash --output Exemplo1-yaml.html --smart --email-obfuscation none --self-contained --standalone --section-divs --template /home/travis/R/Library/rmarkdown/rmd/h/default.html --no-highlight --variable highlightjs=1 --variable 'theme:bootstrap' --include-in-header /tmp/RtmpmKPuzt/rmarkdown-str30b22efa6901.html --mathjax --variable 'mathjax-url:https://mathjax.rstudio.com/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML' 

Output created: Exemplo1-yaml.html
```

</div>

O resultado final pode ser visto no arquivo
[Exemplo1-yaml.html](exemplos/Exemplo1-yaml.html).

</div>

<div id="ch011.xhtml#convertendo-r-markdown-para-outros-formatos"
class="section level3">

### [9.6.2]{.header-section-number} Convertendo R Markdown para outros formatos

Por padrão, a função `render()` gera um arquivo `.html`, mas existem
outros formatos finais possíveis graças ao **Pandoc**.

O pacote `rmarkdown` possui uma série de formatos de saída, que possuem
os sufixos `_document` para documentos, e `_presentation` para
apresentações (slides). Alguns deles:

-   Documentos:
    -   `html_document`
    -   `pdf_document`
    -   `word_document`
-   Apresentações:
    -   `ioslides_presentation`
    -   `slidy_presentation`
    -   `beamer_presentation`

Podemos converter um documento em R Markdown para PDF com

<div class="sourceCode">

``` {.sourceCode .r}
render("exemplos/Exemplo1-yaml.Rmd", output_format = "pdf_document")
```

</div>

O resultado é o arquivo [Exemplo1-yaml.pdf](exemplos/Exemplo1-yaml.pdf).
A função `render()` usa o Pandoc para converter Markdown para LaTeX, e
depois para PDF.

Um documento do Word pode ser gerado com

<div class="sourceCode">

``` {.sourceCode .r}
render("exemplos/Exemplo1-yaml.Rmd", output_format = "word_document")
```

</div>

Para gerar [Exemplo1-yaml.docx](exemplos/Exemplo1-knitr.docx).

Apresentações em slides HTML podem ser geradas em diversos formatos, um
deles é o `ioslides`

<div class="sourceCode">

``` {.sourceCode .r}
render("exemplos/Exemplo1-yaml.Rmd",
       output_format = "ioslides_presentation",
       output_file = "Exemplo1-yaml-ioslides.html")
```

</div>

Veja o resultado em
[Exemplo1-knitr-ioslides.html](exemplos/Exemplo1-knitr-ioslides.html).

Apresentações em Beamer também podem ser geradas com

<div class="sourceCode">

``` {.sourceCode .r}
render("exemplos/Exemplo1-yaml.Rmd",
       output_format = "beamer_presentation",
       output_file = "Exemplo1-yaml-beamer.pdf")
```

</div>

Com resultado no arquivo
[Exemplo1-yaml-beamer.pdf](exemplos/Exemplo1-yaml-beamer.pdf).

</div>

<div id="ch011.xhtml#opções-do-knitr" class="section level3">

### [9.6.3]{.header-section-number} Opções do knitr

O pacote knitr possui diversas opções para controlar a saída dos
resultados de códigos do R. Estas opções funcionam igualmente em blocos
de código inseridos entre texto escrito em Markdown ou LaTeX.

Para controlar a saída de código de um único *chunk*, coloque as opções
individualmente

    ```{r, opt1=val1, opt2=val2}
    # código
    ```

Para controlar globalmente **todos** os *chunks* de um documento, use a
função `knitr::opts_chunk$set()`:

    ```{r, echo=FALSE}
    knitr::opts_chunk$set(opt1 = val1,
                          opt2 = val2
    )
    ```

As opções mais importantes são:

-   `eval = FALSE` para não avaliar o código, apenas mostrar
-   `echo = FALSE` para não mostrar o código, apenas as saídas
-   `results = "hide"` para não mostrar as saídas
-   `warning = FALSE` e `message = FALSE` para suprimir as mensagens de
    aviso
-   `fig.width = 5` and `fig.height = 5` para alterar o tamanho dos
    gráficos gerados pelo R (em polegadas)
-   `out.width = "80%"` para dimensionar a largura dos gráficos
-   `cache = TRUE` para armazenar os resultados, e evitar com que eles
    sejam executados todas as vezes que o documento é compilado

Tabelas podem ser também geradas automaticamente a partir de resultados
de funções do R. Para gerar uma tabela a partir de um objeto do R,
podemos usar a função `knitr::kable()`. Para isso, também é necesário
utilizar a opção `results = "asis"` no *chunk*, para que o resultado
seja tratado como texto literal em Markdown.

    ```{r, results="asis"}
    kable(head(iris))
    ```

  Sepal.Length   Sepal.Width   Petal.Length   Petal.Width   Species
  -------------- ------------- -------------- ------------- ---------
  5.1            3.5           1.4            0.2           setosa
  4.9            3.0           1.4            0.2           setosa
  4.7            3.2           1.3            0.2           setosa
  4.6            3.1           1.5            0.2           setosa
  5.0            3.6           1.4            0.2           setosa
  5.4            3.9           1.7            0.4           setosa

A lista completa de opções está em <http://yihui.name/knitr/options>.

Utilizando a opção `output:` um cabeçalho YAML, podemos informar mais de
um formato para ser **gerado ao mesmo tempo** pelo rmarkdown. Por
exemplo, para gerar documentos de saída em HTML e PDF, podemos
especificar

    ---
    title: "Meu primeiro documento em R Markdown"
    author: "Fernando Mayer"
    date: "Abril, 2018"
    output:
      html_document: default
      pdf_document: default
    ---

E compilar todos eles ao mesmo tempo com

<div class="sourceCode">

``` {.sourceCode .r}
render("exemplos/Exemplo1-yaml2.Rmd", output_format = "all")
```

</div>

Veja [Exemplo1-yaml2.html](exemplos/Exemplo1-yaml2.html), e
[Exemplo1-yaml2.pdf](exemplos/Exemplo1-yaml2.pdf).

Existem ainda alguns outros formatos disponíveis pelo pacote
**rmarkdown**, que podem ser consultados
[aqui](https://rmarkdown.rstudio.com/formats.html). Para cada formato,
ainda existem diversas opções que podem ser modificadas através do YAML.
Estas opções podem ser conferidas nos links específicos de cada formato
na página citada anteriormente.

</div>

<div id="ch011.xhtml#citações" class="section level3">

### [9.6.4]{.header-section-number} Citações

Também é possível escrever documentos que com referências
bibliográficas. Isso é possível pois o Pandoc suporta arquivos
**BibTeX** (`.bib`), que é o formato padrão de armazenamento e
gerenciamento de referências no LaTeX.

Para isso, basta então especificar o arquivo `.bib` no YAML com a *tag*:

    bibliography: referencias.bib

As citações são então feitas com `@<identificador>`. Veja o arquivo
[Exemplo3-knitr.Rmd](exemplos/Exemplo3-knitr.Rmd).

<div class="sourceCode">

``` {.sourceCode .r}
render("exemplos/Exemplo3-knitr.Rmd", output_format = "all")
```

</div>

Dessa forma serão gerados 3 formatos diferentes: HTML, PDF e MS Word.
Note que o tema usado para o HTML (`journal`) é uma possibilidade entre
algumas disponíveis em <https://bootswatch.com/>.

</div>

<div id="ch011.xhtml#extraindo-código-fonte" class="section level3">

### [9.6.5]{.header-section-number} Extraindo código-fonte

Uma característica importante do **knitr** é a habilidade de extrair
somente o código R de um documento dinâmico (*tangle*). Muitas vezes
você só precisa do código e não do texto (e.g. para enviar para um
colaborador).

Para fazer isso, use a função `purl()`:

<div class="sourceCode">

``` {.sourceCode .r}
purl("exemplos/Exemplo3-knitr.Rmd")


processing file: exemplos/Exemplo3-knitr.Rmd

  |                                                                            
  |                                                                      |   0%
  |                                                                            
  |..............                                                        |  20%
  |                                                                            
  |............................                                          |  40%
  |                                                                            
  |..........................................                            |  60%
  |                                                                            
  |........................................................              |  80%
  |                                                                            
  |......................................................................| 100%
output file: Exemplo3-knitr.R
[1] "Exemplo3-knitr.R"
```

</div>

    [1] TRUE

Isso criará um script R [Exemplo3-knitr.R](exemplos/Exemplo3-knitr.R)
com apenas os códigos presentes nos *chunks* do documento.

</div>

<div id="ch011.xhtml#outras-linguagens" class="section level3">

### [9.6.6]{.header-section-number} Outras linguagens

O R Markdown (por meio do pacote **knitr**) suporta também o uso de
outras linguagens diferentes do R, como:

-   Python
-   C (Rcpp)
-   Fortran
-   SQL
-   awk
-   ruby
-   Haskell
-   Bash
-   Perl
-   Dot
-   tikz
-   SAS
-   Coffeescript

Para isso, basta mudar a *engine* (primeira definição do chunk) para a
linguagem desejada.

Exemplos do uso de diferentes *engines* podem ser consultadas
[aqui](https://yihui.name/knitr/demo/engines/). Este outro
[link](https://rmarkdown.rstudio.com/authoring_knitr_engines.html)
mostra mais alguns exemplos.

No arquivo [Exemplo-python.Rmd](exemplos/Exemplo-python.Rmd) pode-se ver
um exemplo de documento que mistura códigos em Python e R. Também é
utilizado o pacote
[feather](https://blog.rstudio.com/2016/03/29/feather/) do Python e do
R, para exportar/importar data frames de uma linguagem para outra dentro
do mesmo documento.

<!-- links --> <!--chapter:end:documentos-dinamicos.Rmd-->

</div>

</div>

</div>

[]{#ch012.xhtml}

<div id="ch012.xhtml#programação-orientada-a-objetos"
class="section level1">

[10]{.header-section-number} Programação Orientada a Objetos
============================================================

Como vimos anteriormente, o R é uma linguagem de programação orientada à
objetos. Dois conceitos fundamentais desse tipo de linguagem são os de
**classe** e **método**. Já vimos também que todo objeto no R possui uma
classe (que define sua estrutura) e analisamos algumas delas. O que
seria então um método? Para responder essa pergunta precisamos entender
inicialmente os tipos de orientação a objetos que o R possui.

O R possui 3 sitemas de orientação a objetos: **S3**, **S4**, e **RC**:

-   **S3**: implementa um estilo de programação orientada a objeto
    chamada de *generic-function*. Esse é o estilo mais básico de
    programação em R (e também o mais utilizado). A ideia é que existam
    **funções genéricas** que decidem qual método aplicar de acordo com
    a classe do objeto. Os métodos são definidos da mesma forma que
    qualquer função, mas chamados de amenira diferente. É um estilo de
    programação mais "informal", mas possibilita uma grande liberdade
    para o programador.
-   **S4**: é um estilo mais formal, no sentido que que as funções
    genéricas devem possuir uma classe formal definida. Além disso, é
    possível também fazer o **despacho múltiplo de métodos**, ao
    contrário da classe S3.
-   **RC**: (*Reference Classes*, antes chamado de R5) é o sistema mais
    novo implementado no R. A principal diferença com os sistemas S3 e
    S4 é que métodos pertencem à objetos, não à funções. Isso faz com
    que objetos da classe RC se comportem mais como objetos da maioria
    das linguagens de programação, como Python, Java, e C\#.

Nesta sessão vamos abordar como funcionam os métodos como definidos pelo
sistema S3, por ser o mais utilizado na prática para se criar novas
funções no R. Para saber mais sobre os outros métodos, consulte o livro
[Advanced R](http://adv-r.had.co.nz/OO-essentials.html).

Vamos entender como uma função genérica pode ser criada através de um
exemplo. Usando a função `methods()`, podemos verificar quais métodos
estão disponíveis para uma determinada função, por exemplo, para a
função `mean()`:

<div class="sourceCode">

``` {.sourceCode .r}
methods(mean)
[1] mean.Date        mean.default     mean.difftime    mean.POSIXct    
[5] mean.POSIXlt     mean.quosure*    mean.vctrs_vctr*
see '?methods' for accessing help and source code
```

</div>

O resultado são expressões do tipo `mean.<classe>`, onde `<classe>` é
uma classe de objeto como aquelas vistas anteriormente. Isso significa
que a função `mean()`, quando aplicada à um objeto da classe `Date`, por
exemplo, pode ter um comportamento diferente quando a mesma função for
aplicada à um objeto de outra classe (numérica).

Suponha que temos o seguinte vetor numérico:

<div class="sourceCode">

``` {.sourceCode .r}
set.seed(1)
vec <- rnorm(100)
class(vec)
[1] "numeric"
```

</div>

e queremos calcular sua média. Basta aplicar a função `mean()` nesse
objeto para obtermos o resultado esperado

<div class="sourceCode">

``` {.sourceCode .r}
mean(vec)
[1] 0.1088874
```

</div>

Mas isso só é possível porque existe um método definido espcificamente
para um vetor da classe `numeric`, que nesse caso é a função
`mean.default`. A função genérica nesse caso é a `mean()`, e a função
método é a `mean.default`. Veja que não precisamos escrever onome
inteiro da função genérica para que ela seja utilizada, como por
exemplo,

<div class="sourceCode">

``` {.sourceCode .r}
mean.default(vec)
[1] 0.1088874
```

</div>

Uma vez passado um objeto para uma função, é a classe do objeto que irá
definir qual método utilizar, de acordo com os métodos disponíveis. Veja
o que acontece se forcarmos o uso da função `mean.Date()` nesse vetor

<div class="sourceCode">

``` {.sourceCode .r}
mean.Date(vec)
[1] "1970-01-01"
```

</div>

O resultado não faz sentido pois ele é específico para um objeto da
classe `Date`.

Tudo isso acontece por causa de um mecanismo chamado de **despacho de
métodos** (*method dispatch*), que é responsável por identificar a
classe do objeto e utilizar ("despachar") a função método correta para
aquela classe. Toda função genérica possui a mesma forma: uma chamada
para a função `UseMethod()`, que especifica o nome genérico e o objeto a
ser despachado. Por exemplo, veja o código fonte da função `mean()`

<div class="sourceCode">

``` {.sourceCode .r}
mean
function (x, ...) 
UseMethod("mean")
<bytecode: 0x2cd9938>
<environment: namespace:base>
```

</div>

Agora veja o código fonte da função `mean.default`, que é o método
específico para vetores numéricos

<div class="sourceCode">

``` {.sourceCode .r}
mean.default
function (x, trim = 0, na.rm = FALSE, ...) 
{
    if (!is.numeric(x) && !is.complex(x) && !is.logical(x)) {
        warning("argument is not numeric or logical: returning NA")
        return(NA_real_)
    }
    if (na.rm) 
        x <- x[!is.na(x)]
    if (!is.numeric(trim) || length(trim) != 1L) 
        stop("'trim' must be numeric of length one")
    n <- length(x)
    if (trim > 0 && n) {
        if (is.complex(x)) 
            stop("trimmed means are not defined for complex data")
        if (anyNA(x)) 
            return(NA_real_)
        if (trim >= 0.5) 
            return(stats::median(x, na.rm = FALSE))
        lo <- floor(n * trim) + 1
        hi <- n + 1 - lo
        x <- sort.int(x, partial = unique(c(lo, hi)))[lo:hi]
    }
    .Internal(mean(x))
}
<bytecode: 0x6849080>
<environment: namespace:base>
```

</div>

Agora suponha que você ddeseja criar uma função que calcule a média para
um objeto de uma classe diferente daquelas previamente definidas. Por
exemplo, suponha que você quer que a função `mean()` retorne a média das
linhas de uma matriz.

<div class="sourceCode">

``` {.sourceCode .r}
set.seed(1)
mat <- matrix(rnorm(50), nrow = 5)
mean(mat)
[1] 0.1004483
```

</div>

O resultado é a média de todos os elementos, e não de cada linha. Nesse
caso, podemos definir nossa própria função método para fazer o cálculo
que precisamos. Por exemplo:

<div class="sourceCode">

``` {.sourceCode .r}
mean.matrix <- function(x, ...) rowMeans(x)
```

</div>

Uma função método é sempre definida dessa forma:
`<funçãogenérica>.<classe>`. Agora podemos ver novamente os métodos
disponíveis para a função `mean()`

<div class="sourceCode">

``` {.sourceCode .r}
methods(mean)
[1] mean.Date        mean.default     mean.difftime    mean.matrix     
[5] mean.POSIXct     mean.POSIXlt     mean.quosure*    mean.vctrs_vctr*
see '?methods' for accessing help and source code
```

</div>

e simplesmente aplicar a função genérica `mean()` à um objeto da classe
`matrix` para obter o resultado que desejamos

<div class="sourceCode">

``` {.sourceCode .r}
class(mat)
[1] "matrix"
mean(mat)
[1]  0.09544402  0.12852087  0.06229588 -0.01993810  0.23591872
```

</div>

Esse exemplo ilustra como é simples criar funções método para diferentes
classes de objetos. Poderíamos fazer o mesmo para objetos das classes
`data.frame` e `list`

<div class="sourceCode">

``` {.sourceCode .r}
mean.data.frame <- function(x, ...) sapply(x, mean, ...)
mean.list <- function(x, ...) lapply(x, mean)
```

</div>

Aplicando em objetos dessas classes específicas, obtemos:

<div class="sourceCode">

``` {.sourceCode .r}
## Data frame
set.seed(1)
da <- data.frame(c1 = rnorm(10),
                 c2 = runif(10))
class(da)
[1] "data.frame"
mean(da)
       c1        c2 
0.1322028 0.4183230 
## Lista
set.seed(1)
dl <- list(rnorm(10), runif(50))
class(dl)
[1] "list"
mean(dl)
[[1]]
[1] 0.1322028

[[2]]
[1] 0.4946632
```

</div>

Obviamente esse processo todo é extremamente importante ao se criar
novas funções no R. Podemos tanto criar uma função genérica (como a
`mean()`) e diversos métodos para ela usando classes de objetos
existentes, quanto (inclusive) criar novas classes e funções método para
elas. Essa é uma das grandes lberdades que o método S3 de orientação à
objetos permite, e possivelmente um dos motivos pelos quais é
relativamente simples criar pacotes inteiros no R.

<!--chapter:end:poo.Rmd-->

</div>

[]{#ch013.xhtml}

<div id="ch013.xhtml#scripts" class="section level1">

[11]{.header-section-number} Scripts
====================================

Scripts que faltam ser convertidos para capítulos:

-   [inferencia\_regressao.Rmd](scripts/inferencia_regressao.Rmd)
-   [inferencia\_regressao2.Rmd](scripts/inferencia_regressao2.Rmd)
-   [script\_gapminder.R](scripts/script_gapminder.R)

Scripts que ainda podem ser úteis

-   [probabilidade.R](scripts/probabilidade.R)

<!--chapter:end:scripts.Rmd-->

</div>
