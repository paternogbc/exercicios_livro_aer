# Cap. 4 - Introdução ao R {-}

**4.1**
Use o R para verificar o resultado da operação `7 + 7 ÷ 7 + 7 x 7 - 7`.

Solução:

```r
7 + 7 / 7 + 7 * 7 - 7
#> [1] 50
```

**4.2**
Verifique através do R se `3x2³` é maior que `2x3²`.

Solução:

```r
3 * 2^3 > 2 * 3^2
#> [1] TRUE
```

**4.3**
Crie dois objetos (qualquer nome) com os valores 100 e 300. Multiplique esses objetos (função `prod()`) e atribuam ao objeto **mult**. Faça o logaritmo natural (função `log()`) do objeto **mult** e atribuam ao objeto **ln**.

Solução:

```r
obj1 <- 100
obj2 <- 300
mult <- prod(obj1, obj2)
ln <- log(obj1, obj2)
```

**4.4**
Quantos pacotes existem no CRAN nesse momento? Execute essa combinação no Console: `nrow(available.packages(repos = "http://cran.r-project.org"))`.

 Solução:

```r
nrow(available.packages(repos = "http://cran.r-project.org"))
#> [1] 18897
```

**4.5**
Instale o pacote `tidyverse` do CRAN.

Solução:

```r
install.packages("tidyverse", dependencies = TRUE)
```

**4.6**
Escolha números para jogar na mega-sena usando o R, nomeando o objeto como **mega**. Lembrando: são 6 valores de 1 a 60 e atribuam a um objeto.

Solução:

```r
mega <- sample(x = 1:60, size = 6, replace = FALSE)
mega
#> [1]  8 48 19  1 51 41
```

**4.7** Crie um fator chamado **tr**, com dois níveis ("cont" e "trat") para descrever 100 locais de amostragem, 50 de cada tratamento. O fator deve ser dessa forma `cont, cont, cont, ...., cont, trat, trat, ...., trat`.

Solução:

```r
tr <- factor(c(rep("cont", each = 50), rep("trat", each = 50)))
tr
#>   [1] cont cont cont cont cont cont cont cont cont cont cont
#>  [12] cont cont cont cont cont cont cont cont cont cont cont
#>  [23] cont cont cont cont cont cont cont cont cont cont cont
#>  [34] cont cont cont cont cont cont cont cont cont cont cont
#>  [45] cont cont cont cont cont cont trat trat trat trat trat
#>  [56] trat trat trat trat trat trat trat trat trat trat trat
#>  [67] trat trat trat trat trat trat trat trat trat trat trat
#>  [78] trat trat trat trat trat trat trat trat trat trat trat
#>  [89] trat trat trat trat trat trat trat trat trat trat trat
#> [100] trat
#> Levels: cont trat
```

**4.8**
Crie uma matriz chamada **ma**, resultante da disposição de um vetor composto por 1000 valores aleatórios entre 0 e 10. A matriz deve conter 100 linhas e ser disposta por colunas.

Solução:

```r
ma <- matrix(sample(0:10, 1000, rep = TRUE), nrow = 100, byrow = FALSE)
ma
#>        [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
#>   [1,]    7    3    7    9    1    4    6    0    3     2
#>   [2,]    0    5   10    0    3    5    9    0    4     7
#>   [3,]    0    0    4    4    5    0    5    5    7     2
#>   [4,]    2    9   10    6    6    0    1    5    5     8
#>   [5,]    6    2    9    2    3    8    6    4    8     6
#>   [6,]   10    7   10    2    1    5    6    7    1     6
#>   [7,]    7    0   10    8    4    4    7    0    1     8
#>   [8,]    0    6   10    6    5    8    2    3    2     9
#>   [9,]    6    5    6    9    9    1    9    5    4     3
#>  [10,]    7    0    7    2    7    4    5    9    5     0
#>  [11,]   10    1    4    0    8    5    7    5    2     5
#>  [12,]    0    4    3    0    4    6    5    6    4     3
#>  [13,]    6    1    7    2    5    0    4    9    6     1
#>  [14,]    0    1    8    6    9    1    0    6   10     1
#>  [15,]    3    1    5    5    1    1    5    8    1     6
#>  [16,]    8    8    0    6   10    9    7    2   10     0
#>  [17,]    3    7    2    9    1    9    2    5    3     3
#>  [18,]    3    9    7    0    0    2    5    9    6     1
#>  [19,]    1    5    4    3    0    1    0    9    6     2
#>  [20,]    0    9    8    4    0    5    8    9    9     4
#>  [21,]    9   10    3    4    2    9    8    2   10     5
#>  [22,]    4    4    5    4    7    0    9    5    8     4
#>  [23,]    0    8    2    1    3    4    3    1    7     3
#>  [24,]   10    9    8    5    2    7    0    0    1     3
#>  [25,]    0    8   10    1    3    7    2    0    6     4
#>  [26,]    9    6    4    3    1    9    7    5    0     2
#>  [27,]    3    7    4    6    0    3    3    1    5     7
#>  [28,]    2    3   10    2    1    9    7    1    8     7
#>  [29,]    6    7    4    0    8    2    9   10    5     6
#>  [30,]    7    6    5    7    4    0    3    9    9     7
#>  [31,]    6    2    1    3    1   10    9    4    9     1
#>  [32,]    1   10    1    0    0    8   10   10    8     8
#>  [33,]    6    3    3    9    4    8    9    2    0     3
#>  [34,]    5    7    6    0   10    4    1    3    8     6
#>  [35,]    3    1    5    8    6    0   10    1    9     9
#>  [36,]    7    0    1    9    6    1    4    1    6     9
#>  [37,]    6    6   10    5    3    6    4   10    8     0
#>  [38,]    4    1    6    8    5    8    4    9    1     6
#>  [39,]   10    0    6    1    3    2    4    1    5     6
#>  [40,]    0    3    5    8    6    0    7    1    9     7
#>  [41,]    5    6    4    9    9    1    7   10    3     8
#>  [42,]    5    1    0    8    6    4    1    0    2     3
#>  [43,]    9    3    2    3    7    8    9    8    7     1
#>  [44,]    4   10    0    9   10    0    3    5    3     8
#>  [45,]   10    9    1    7    6    9   10    8    9     3
#>  [46,]   10    9   10    1    6    1    4    7    9     5
#>  [47,]    0   10    2    7    8    1    9    8    4     9
#>  [48,]    2   10    7    7    9    0    0    4    1    10
#>  [49,]    7    0    2    7    5    1    1    7    5     3
#>  [50,]   10    9    8    6   10   10    6    7   10     8
#>  [51,]    4    9    0   10    5    1    8    3    9    10
#>  [52,]    1    6    5    9    3    0    0   10    9    10
#>  [53,]    2    8   10    6    1    8    2    3    3     7
#>  [54,]    4    1    6    4    2    7    4    7    8     9
#>  [55,]    7    4    9    8    0    8    3    7    6     6
#>  [56,]    1    4   10    1    8    8    0    5    1     5
#>  [57,]    7    6    9    0    7    2    0    6    2     4
#>  [58,]    7    0    2    0    8    2    0    9    6     0
#>  [59,]    6    2    7    3    2    6    8    8    1     6
#>  [60,]    5    8    1    4    7    3    7    5    0    10
#>  [61,]    3    0    2    7    3    3    6    1    0     9
#>  [62,]    1    6    8    7    9   10    1    3    9    10
#>  [63,]   10    7    7    3   10    5    1    8    9     7
#>  [64,]   10    8    9    6    0    6    4   10    7     6
#>  [65,]   10    2    7    7    1    5    4    6   10     4
#>  [66,]    7   10    0    5    2    5   10    0    5     4
#>  [67,]    7    0   10   10    6    9    0    3    3    10
#>  [68,]    1    4    6    1    2    8    5   10    8     9
#>  [69,]    7    7    9    5    6    5    3    0    9     0
#>  [70,]    5    8    0    3    2    3    2    2    3     2
#>  [71,]    8    2    9   10    4    4    4    6    0     3
#>  [72,]    9    3    0    9    4    7    7    4    4     8
#>  [73,]    7    0    7    8    5    2   10    8    3     1
#>  [74,]    9   10    2   10    3    0    3    2    8    10
#>  [75,]    8    2    1    0    1    1    4    9    6     3
#>  [76,]    3    2    7    6   10    2    4    0    8     5
#>  [77,]   10    0    3    5    3    9    5    6    6     9
#>  [78,]    9    9   10    1    8    1    6    8   10     8
#>  [79,]    3    6    2    7    4    9    4   10    4     7
#>  [80,]    6    1    2    5    9    8    0    2    5     6
#>  [81,]    6    0    1    7    6    3    0    7    0     1
#>  [82,]    4    0    9    4    5    8   10   10    8    10
#>  [83,]    0    1    7    6   10    9   10    1    9     2
#>  [84,]    2    6    8    9    0    9    1    7    4     1
#>  [85,]    1   10    9    5    9    4    4    1    0     3
#>  [86,]   10    2    3    4   10    4    0    1    4     9
#>  [87,]    2    5    0    2    8    5    1    8    1     8
#>  [88,]    2    4    4    1    6    4   10    4    2     1
#>  [89,]    2    7   10   10    6    9    9    0    4     4
#>  [90,]    5   10   10    6    7    8    7    0    2     2
#>  [91,]    3    5    1    5    0    7    0    3    2     4
#>  [92,]    5    2    8    2    4    9    0    0    8     7
#>  [93,]    5   10    9    8    1    4    4    2    6     4
#>  [94,]    0    4    7    8    7    6    9    3    7     7
#>  [95,]   10    1    3    7   10    8    0    9    2     6
#>  [96,]    0    6   10    7    5    8    1    9    5    10
#>  [97,]    2   10    0    4    6    3    4    6    8     9
#>  [98,]   10    6    2    0    8    4    1    4    4     9
#>  [99,]    1    2    1    9    2    4    9    8    6    10
#> [100,]    0    2   10    2    0    4    3   10    4    10
```

**4.9**
Crie um data frame chamado **df**, resultante da composição dos vetores: 

1. `id: 1:50`
1. `sp: sp01, sp02, ..., sp49, sp50`
1. `ab: 50 valores aleatórios entre 0 a 5`

 Solução:

```r
df <- data.frame(id = 1:50,
                  sp = c(paste0("sp0", 1:9), paste0("sp", 10:50)),
                  ab = sample(0:5, 50, rep = TRUE))
df
#>    id   sp ab
#> 1   1 sp01  0
#> 2   2 sp02  2
#> 3   3 sp03  4
#> 4   4 sp04  0
#> 5   5 sp05  1
#> 6   6 sp06  4
#> 7   7 sp07  2
#> 8   8 sp08  1
#> 9   9 sp09  2
#> 10 10 sp10  2
#> 11 11 sp11  2
#> 12 12 sp12  5
#> 13 13 sp13  3
#> 14 14 sp14  1
#> 15 15 sp15  5
#> 16 16 sp16  1
#> 17 17 sp17  2
#> 18 18 sp18  5
#> 19 19 sp19  0
#> 20 20 sp20  4
#> 21 21 sp21  1
#> 22 22 sp22  1
#> 23 23 sp23  2
#> 24 24 sp24  2
#> 25 25 sp25  3
#> 26 26 sp26  5
#> 27 27 sp27  0
#> 28 28 sp28  1
#> 29 29 sp29  2
#> 30 30 sp30  0
#> 31 31 sp31  3
#> 32 32 sp32  3
#> 33 33 sp33  0
#> 34 34 sp34  4
#> 35 35 sp35  4
#> 36 36 sp36  2
#> 37 37 sp37  1
#> 38 38 sp38  4
#> 39 39 sp39  4
#> 40 40 sp40  2
#> 41 41 sp41  2
#> 42 42 sp42  5
#> 43 43 sp43  3
#> 44 44 sp44  3
#> 45 45 sp45  2
#> 46 46 sp46  3
#> 47 47 sp47  3
#> 48 48 sp48  4
#> 49 49 sp49  2
#> 50 50 sp50  3
```


**4.10**
Crie uma lista com os objetos criados anteriormente: **mega**, **tr**, **ma** e **df**.

Solução:

```r
lis <- list(mega, tr, ma, df)
lis
#> [[1]]
#> [1]  8 48 19  1 51 41
#> 
#> [[2]]
#>   [1] cont cont cont cont cont cont cont cont cont cont cont
#>  [12] cont cont cont cont cont cont cont cont cont cont cont
#>  [23] cont cont cont cont cont cont cont cont cont cont cont
#>  [34] cont cont cont cont cont cont cont cont cont cont cont
#>  [45] cont cont cont cont cont cont trat trat trat trat trat
#>  [56] trat trat trat trat trat trat trat trat trat trat trat
#>  [67] trat trat trat trat trat trat trat trat trat trat trat
#>  [78] trat trat trat trat trat trat trat trat trat trat trat
#>  [89] trat trat trat trat trat trat trat trat trat trat trat
#> [100] trat
#> Levels: cont trat
#> 
#> [[3]]
#>        [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
#>   [1,]    7    3    7    9    1    4    6    0    3     2
#>   [2,]    0    5   10    0    3    5    9    0    4     7
#>   [3,]    0    0    4    4    5    0    5    5    7     2
#>   [4,]    2    9   10    6    6    0    1    5    5     8
#>   [5,]    6    2    9    2    3    8    6    4    8     6
#>   [6,]   10    7   10    2    1    5    6    7    1     6
#>   [7,]    7    0   10    8    4    4    7    0    1     8
#>   [8,]    0    6   10    6    5    8    2    3    2     9
#>   [9,]    6    5    6    9    9    1    9    5    4     3
#>  [10,]    7    0    7    2    7    4    5    9    5     0
#>  [11,]   10    1    4    0    8    5    7    5    2     5
#>  [12,]    0    4    3    0    4    6    5    6    4     3
#>  [13,]    6    1    7    2    5    0    4    9    6     1
#>  [14,]    0    1    8    6    9    1    0    6   10     1
#>  [15,]    3    1    5    5    1    1    5    8    1     6
#>  [16,]    8    8    0    6   10    9    7    2   10     0
#>  [17,]    3    7    2    9    1    9    2    5    3     3
#>  [18,]    3    9    7    0    0    2    5    9    6     1
#>  [19,]    1    5    4    3    0    1    0    9    6     2
#>  [20,]    0    9    8    4    0    5    8    9    9     4
#>  [21,]    9   10    3    4    2    9    8    2   10     5
#>  [22,]    4    4    5    4    7    0    9    5    8     4
#>  [23,]    0    8    2    1    3    4    3    1    7     3
#>  [24,]   10    9    8    5    2    7    0    0    1     3
#>  [25,]    0    8   10    1    3    7    2    0    6     4
#>  [26,]    9    6    4    3    1    9    7    5    0     2
#>  [27,]    3    7    4    6    0    3    3    1    5     7
#>  [28,]    2    3   10    2    1    9    7    1    8     7
#>  [29,]    6    7    4    0    8    2    9   10    5     6
#>  [30,]    7    6    5    7    4    0    3    9    9     7
#>  [31,]    6    2    1    3    1   10    9    4    9     1
#>  [32,]    1   10    1    0    0    8   10   10    8     8
#>  [33,]    6    3    3    9    4    8    9    2    0     3
#>  [34,]    5    7    6    0   10    4    1    3    8     6
#>  [35,]    3    1    5    8    6    0   10    1    9     9
#>  [36,]    7    0    1    9    6    1    4    1    6     9
#>  [37,]    6    6   10    5    3    6    4   10    8     0
#>  [38,]    4    1    6    8    5    8    4    9    1     6
#>  [39,]   10    0    6    1    3    2    4    1    5     6
#>  [40,]    0    3    5    8    6    0    7    1    9     7
#>  [41,]    5    6    4    9    9    1    7   10    3     8
#>  [42,]    5    1    0    8    6    4    1    0    2     3
#>  [43,]    9    3    2    3    7    8    9    8    7     1
#>  [44,]    4   10    0    9   10    0    3    5    3     8
#>  [45,]   10    9    1    7    6    9   10    8    9     3
#>  [46,]   10    9   10    1    6    1    4    7    9     5
#>  [47,]    0   10    2    7    8    1    9    8    4     9
#>  [48,]    2   10    7    7    9    0    0    4    1    10
#>  [49,]    7    0    2    7    5    1    1    7    5     3
#>  [50,]   10    9    8    6   10   10    6    7   10     8
#>  [51,]    4    9    0   10    5    1    8    3    9    10
#>  [52,]    1    6    5    9    3    0    0   10    9    10
#>  [53,]    2    8   10    6    1    8    2    3    3     7
#>  [54,]    4    1    6    4    2    7    4    7    8     9
#>  [55,]    7    4    9    8    0    8    3    7    6     6
#>  [56,]    1    4   10    1    8    8    0    5    1     5
#>  [57,]    7    6    9    0    7    2    0    6    2     4
#>  [58,]    7    0    2    0    8    2    0    9    6     0
#>  [59,]    6    2    7    3    2    6    8    8    1     6
#>  [60,]    5    8    1    4    7    3    7    5    0    10
#>  [61,]    3    0    2    7    3    3    6    1    0     9
#>  [62,]    1    6    8    7    9   10    1    3    9    10
#>  [63,]   10    7    7    3   10    5    1    8    9     7
#>  [64,]   10    8    9    6    0    6    4   10    7     6
#>  [65,]   10    2    7    7    1    5    4    6   10     4
#>  [66,]    7   10    0    5    2    5   10    0    5     4
#>  [67,]    7    0   10   10    6    9    0    3    3    10
#>  [68,]    1    4    6    1    2    8    5   10    8     9
#>  [69,]    7    7    9    5    6    5    3    0    9     0
#>  [70,]    5    8    0    3    2    3    2    2    3     2
#>  [71,]    8    2    9   10    4    4    4    6    0     3
#>  [72,]    9    3    0    9    4    7    7    4    4     8
#>  [73,]    7    0    7    8    5    2   10    8    3     1
#>  [74,]    9   10    2   10    3    0    3    2    8    10
#>  [75,]    8    2    1    0    1    1    4    9    6     3
#>  [76,]    3    2    7    6   10    2    4    0    8     5
#>  [77,]   10    0    3    5    3    9    5    6    6     9
#>  [78,]    9    9   10    1    8    1    6    8   10     8
#>  [79,]    3    6    2    7    4    9    4   10    4     7
#>  [80,]    6    1    2    5    9    8    0    2    5     6
#>  [81,]    6    0    1    7    6    3    0    7    0     1
#>  [82,]    4    0    9    4    5    8   10   10    8    10
#>  [83,]    0    1    7    6   10    9   10    1    9     2
#>  [84,]    2    6    8    9    0    9    1    7    4     1
#>  [85,]    1   10    9    5    9    4    4    1    0     3
#>  [86,]   10    2    3    4   10    4    0    1    4     9
#>  [87,]    2    5    0    2    8    5    1    8    1     8
#>  [88,]    2    4    4    1    6    4   10    4    2     1
#>  [89,]    2    7   10   10    6    9    9    0    4     4
#>  [90,]    5   10   10    6    7    8    7    0    2     2
#>  [91,]    3    5    1    5    0    7    0    3    2     4
#>  [92,]    5    2    8    2    4    9    0    0    8     7
#>  [93,]    5   10    9    8    1    4    4    2    6     4
#>  [94,]    0    4    7    8    7    6    9    3    7     7
#>  [95,]   10    1    3    7   10    8    0    9    2     6
#>  [96,]    0    6   10    7    5    8    1    9    5    10
#>  [97,]    2   10    0    4    6    3    4    6    8     9
#>  [98,]   10    6    2    0    8    4    1    4    4     9
#>  [99,]    1    2    1    9    2    4    9    8    6    10
#> [100,]    0    2   10    2    0    4    3   10    4    10
#> 
#> [[4]]
#>    id   sp ab
#> 1   1 sp01  0
#> 2   2 sp02  2
#> 3   3 sp03  4
#> 4   4 sp04  0
#> 5   5 sp05  1
#> 6   6 sp06  4
#> 7   7 sp07  2
#> 8   8 sp08  1
#> 9   9 sp09  2
#> 10 10 sp10  2
#> 11 11 sp11  2
#> 12 12 sp12  5
#> 13 13 sp13  3
#> 14 14 sp14  1
#> 15 15 sp15  5
#> 16 16 sp16  1
#> 17 17 sp17  2
#> 18 18 sp18  5
#> 19 19 sp19  0
#> 20 20 sp20  4
#> 21 21 sp21  1
#> 22 22 sp22  1
#> 23 23 sp23  2
#> 24 24 sp24  2
#> 25 25 sp25  3
#> 26 26 sp26  5
#> 27 27 sp27  0
#> 28 28 sp28  1
#> 29 29 sp29  2
#> 30 30 sp30  0
#> 31 31 sp31  3
#> 32 32 sp32  3
#> 33 33 sp33  0
#> 34 34 sp34  4
#> 35 35 sp35  4
#> 36 36 sp36  2
#> 37 37 sp37  1
#> 38 38 sp38  4
#> 39 39 sp39  4
#> 40 40 sp40  2
#> 41 41 sp41  2
#> 42 42 sp42  5
#> 43 43 sp43  3
#> 44 44 sp44  3
#> 45 45 sp45  2
#> 46 46 sp46  3
#> 47 47 sp47  3
#> 48 48 sp48  4
#> 49 49 sp49  2
#> 50 50 sp50  3
```

**4.11**
Selecione os elementos ímpares do objeto **tr** e atribua ao objeto **tr_impar**.

Solução:

```r
tr_impar <- tr[seq(1, 99, 2)]
tr_impar
#>  [1] cont cont cont cont cont cont cont cont cont cont cont
#> [12] cont cont cont cont cont cont cont cont cont cont cont
#> [23] cont cont cont trat trat trat trat trat trat trat trat
#> [34] trat trat trat trat trat trat trat trat trat trat trat
#> [45] trat trat trat trat trat trat
#> Levels: cont trat
```

**4.12**
Selecione as linhas com ids pares do objeto **df** e atribua ao objeto **df_ids_par**.

Solução:

```r
df_ids_par <- df[seq(2, 100, 2), ]
df_ids_par
#>       id   sp ab
#> 2      2 sp02  2
#> 4      4 sp04  0
#> 6      6 sp06  4
#> 8      8 sp08  1
#> 10    10 sp10  2
#> 12    12 sp12  5
#> 14    14 sp14  1
#> 16    16 sp16  1
#> 18    18 sp18  5
#> 20    20 sp20  4
#> 22    22 sp22  1
#> 24    24 sp24  2
#> 26    26 sp26  5
#> 28    28 sp28  1
#> 30    30 sp30  0
#> 32    32 sp32  3
#> 34    34 sp34  4
#> 36    36 sp36  2
#> 38    38 sp38  4
#> 40    40 sp40  2
#> 42    42 sp42  5
#> 44    44 sp44  3
#> 46    46 sp46  3
#> 48    48 sp48  4
#> 50    50 sp50  3
#> NA    NA <NA> NA
#> NA.1  NA <NA> NA
#> NA.2  NA <NA> NA
#> NA.3  NA <NA> NA
#> NA.4  NA <NA> NA
#> NA.5  NA <NA> NA
#> NA.6  NA <NA> NA
#> NA.7  NA <NA> NA
#> NA.8  NA <NA> NA
#> NA.9  NA <NA> NA
#> NA.10 NA <NA> NA
#> NA.11 NA <NA> NA
#> NA.12 NA <NA> NA
#> NA.13 NA <NA> NA
#> NA.14 NA <NA> NA
#> NA.15 NA <NA> NA
#> NA.16 NA <NA> NA
#> NA.17 NA <NA> NA
#> NA.18 NA <NA> NA
#> NA.19 NA <NA> NA
#> NA.20 NA <NA> NA
#> NA.21 NA <NA> NA
#> NA.22 NA <NA> NA
#> NA.23 NA <NA> NA
#> NA.24 NA <NA> NA
```

**4.13**
Faça uma amostragem de 10 linhas do objeto **df** e atribua ao objeto **df_amos10**.

 Solução:

```r
df_amos10 <- df[sample(nrow(df), 10), ]
df_amos10
#>    id   sp ab
#> 5   5 sp05  1
#> 21 21 sp21  1
#> 43 43 sp43  3
#> 10 10 sp10  2
#> 50 50 sp50  3
#> 37 37 sp37  1
#> 30 30 sp30  0
#> 38 38 sp38  4
#> 18 18 sp18  5
#> 31 31 sp31  3
```

**4.14**
Amostre 10 linhas do objeto **ma**, mas utilizando as linhas amostradas do **df_amos10** e atribua ao objeto **ma_amos10**.

 Solução:

```r
ma_amos10 <- ma[df_amos10$id, ]
ma_amos10
#>       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
#>  [1,]    6    2    9    2    3    8    6    4    8     6
#>  [2,]    9   10    3    4    2    9    8    2   10     5
#>  [3,]    9    3    2    3    7    8    9    8    7     1
#>  [4,]    7    0    7    2    7    4    5    9    5     0
#>  [5,]   10    9    8    6   10   10    6    7   10     8
#>  [6,]    6    6   10    5    3    6    4   10    8     0
#>  [7,]    7    6    5    7    4    0    3    9    9     7
#>  [8,]    4    1    6    8    5    8    4    9    1     6
#>  [9,]    3    9    7    0    0    2    5    9    6     1
#> [10,]    6    2    1    3    1   10    9    4    9     1
```

**4.15** 
Una as colunas dos objetos **df_amos10** e **ma_amos10** e atribua ao objeto **dados_amos10**.

Solução:

```r
dados_amos10 <- cbind(df_amos10, ma_amos10)
dados_amos10
#>    id   sp ab  1  2  3 4  5  6 7  8  9 10
#> 5   5 sp05  1  6  2  9 2  3  8 6  4  8  6
#> 21 21 sp21  1  9 10  3 4  2  9 8  2 10  5
#> 43 43 sp43  3  9  3  2 3  7  8 9  8  7  1
#> 10 10 sp10  2  7  0  7 2  7  4 5  9  5  0
#> 50 50 sp50  3 10  9  8 6 10 10 6  7 10  8
#> 37 37 sp37  1  6  6 10 5  3  6 4 10  8  0
#> 30 30 sp30  0  7  6  5 7  4  0 3  9  9  7
#> 38 38 sp38  4  4  1  6 8  5  8 4  9  1  6
#> 18 18 sp18  5  3  9  7 0  0  2 5  9  6  1
#> 31 31 sp31  3  6  2  1 3  1 10 9  4  9  1
```
