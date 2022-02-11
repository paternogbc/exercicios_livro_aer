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
#> [1] 18913
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
#> [1] 10 55  9 24 29 36
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
#>   [1,]    2    2   10    5    1    5    9    5    3     2
#>   [2,]    7   10    4    3    6    1    9    8    5     8
#>   [3,]    2   10    5   10   10    6    4    5    1     3
#>   [4,]   10    4    7   10    6    6    9    8    3     7
#>   [5,]   10    6    4    7    3    0   10    3   10     4
#>   [6,]    0    0    8    4    8    7    6    5    3     3
#>   [7,]    7    2    7    0    0    5    2    2    9     2
#>   [8,]    8    8    8    8    3    1    2    1    8     1
#>   [9,]    2    4    6    8    6    7    4    8    0     1
#>  [10,]    7    6    7    3    9    0    6    2    4     3
#>  [11,]    6    4    5    0    7   10    7    9    6     5
#>  [12,]    0   10    5    3    6    8    4    0    0     1
#>  [13,]    2    2   10    7    9    1    6    4    8     6
#>  [14,]    5    0    3    8    0    5    1    8    9     4
#>  [15,]    5    8    9    8    3    1    4    5    8     0
#>  [16,]    5    2    0    1    0    4    2   10    1     0
#>  [17,]    0    3    0    3    0    3    6    9    2    10
#>  [18,]    6    2    1    4    7    1    5    9    9     4
#>  [19,]    2    3    6    6    9    3    4    4    1     5
#>  [20,]    2    3    6    8    1    6    1   10    7    10
#>  [21,]    9    7    4    7    0    3    9    0    3     5
#>  [22,]    4    2    3    0   10    6    5    3    4     9
#>  [23,]   10    6   10    5    2    0   10    1    5     5
#>  [24,]    3    1    5    2    6    1   10    4    5     8
#>  [25,]   10    0   10    6    0    5    6    3    3     7
#>  [26,]    7    3    9    6    9    6    5    7    9     1
#>  [27,]    3    8    1    3    3    3    8    3    0     8
#>  [28,]    5    7    4    1    6    4    8    8   10     2
#>  [29,]   10    5    8    4    8    3    8    8    7     3
#>  [30,]   10    9    8    8    5    4    0    4   10     9
#>  [31,]   10    6    4    8    2    7    0    3    7     7
#>  [32,]    8    7    0    8   10    7    7    4    6     1
#>  [33,]   10   10    9    8    5    5    1    1    4     9
#>  [34,]    1    7    3    4    7    3    8    5    6     9
#>  [35,]    5    6    0    9    8    8    0    1    8     9
#>  [36,]    0    1    9    4    3    2    5   10    3     8
#>  [37,]    2    6    4    9    8    5    6    9    1     2
#>  [38,]    9    8    8    2    1    1   10    0   10     8
#>  [39,]    0    2    4    8    4    8   10   10    2     4
#>  [40,]    5    6    0    5    8    1    5    5    2     4
#>  [41,]    0    9    8   10    7    2    4    0    8     8
#>  [42,]    7    6    7    1    6    0    1    2   10     2
#>  [43,]    9    8    7    9    3    9    7    4    9     2
#>  [44,]    7    4    2    7    1    2    9   10    8     9
#>  [45,]    2    4   10    9    3    8    5    7    5     1
#>  [46,]    2    2    2    0    0   10    7    4    1    10
#>  [47,]    0    1    2    6   10    0    7    0    0     3
#>  [48,]    4    7    0    6    8   10    5    7    6     6
#>  [49,]   10    1    1    0    0    5   10   10   10     7
#>  [50,]   10    7    1    1    9    2    1    8   10     7
#>  [51,]    7    0    7    0    7    2    7    1   10     0
#>  [52,]    1    7    8    7    4    0    7    7    2     0
#>  [53,]    0    9    5    6    0    5    6    2    5    10
#>  [54,]    9   10    0    9    5    4    0    5    5     8
#>  [55,]    8    5    1    9    0    9    9    1    6     3
#>  [56,]    8    5    0    7    6    6    7    0    4     3
#>  [57,]    0    1    5    5    5    6    6    5    2    10
#>  [58,]    2    9    5    1   10    1    4    0    6     8
#>  [59,]    2    5    6    3    3    3    8    0    6     1
#>  [60,]    4    5    9    8   10    5    4    3   10     8
#>  [61,]    7    9    4    9    5    5    8    5    8     8
#>  [62,]    7    6    5    1    5    8    5    3    9     5
#>  [63,]    7   10    7   10    1    8   10    3    2     3
#>  [64,]    8    8    7    1    2    5    7   10    3     7
#>  [65,]    6    7    7    2    5    2    7    4    0     4
#>  [66,]    7    8   10    8    4    8    9    7    2     9
#>  [67,]    9    8    1    3    7    8    3    8    9     2
#>  [68,]    0    5    6   10    5    7    9    9    0     3
#>  [69,]    0   10    1    5    4    6    9    0    5     7
#>  [70,]    7    4    9    6    3    3    6   10    0     7
#>  [71,]    0    4    5    8    1    2    9    0    5     4
#>  [72,]    4    5    8    3    7    0    8    4    5     8
#>  [73,]    7    6   10    6    1   10    2    3    6    10
#>  [74,]    6   10    8    1    8    6    4    5    5     0
#>  [75,]    6    9    8   10    4    2    4    0    6     5
#>  [76,]    6    3    4    4    9    5    8    1    3     2
#>  [77,]    0    0    4    2    3   10    0    4    6     7
#>  [78,]    4    0    6    3    6    8    5    2    0     7
#>  [79,]    9    0    0    1    3   10    0    0    0     6
#>  [80,]    0    7   10    6    7    7    0    3    6     7
#>  [81,]    3    1    5    1    5    0    4    9    6     5
#>  [82,]    7    2    3    8    8    5    2    9    2     1
#>  [83,]    3    9   10    6    9    6    8    0    0     7
#>  [84,]    6    1    1    9    8    5    1    7    9    10
#>  [85,]    7    0    9    7    4    9   10    8   10     0
#>  [86,]    7    5    9    4    8    1    0    7    5     2
#>  [87,]    0    4    8    6    7    6    7    7    0    10
#>  [88,]    8    3    5    0    5    6    6    0    8     2
#>  [89,]    8   10    7    3    4   10    6    0    2     0
#>  [90,]    7    1    0    2    2    4    2    2    5     2
#>  [91,]    4    1   10    3    1    9    3    6    5     4
#>  [92,]    2    5    0    2    9    6    1    2    2    10
#>  [93,]    9    2    3    4    3    6   10    1    5     0
#>  [94,]    3    8    7    4    6    6    9    7    6     9
#>  [95,]    4    0    8    3    5    2    7    9    2    10
#>  [96,]   10    6    6    6    4    2    8   10   10     3
#>  [97,]    2    9   10    8    0    5    6    4    9     5
#>  [98,]    2    1    8   10    5    7    0    1    2     9
#>  [99,]   10    1    1    1    2    9    2    6    4     6
#> [100,]    2    4    3    2    4    6    9    9    1     1
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
#> 3   3 sp03  2
#> 4   4 sp04  1
#> 5   5 sp05  2
#> 6   6 sp06  0
#> 7   7 sp07  1
#> 8   8 sp08  3
#> 9   9 sp09  4
#> 10 10 sp10  5
#> 11 11 sp11  2
#> 12 12 sp12  2
#> 13 13 sp13  5
#> 14 14 sp14  1
#> 15 15 sp15  1
#> 16 16 sp16  3
#> 17 17 sp17  4
#> 18 18 sp18  4
#> 19 19 sp19  4
#> 20 20 sp20  0
#> 21 21 sp21  4
#> 22 22 sp22  4
#> 23 23 sp23  4
#> 24 24 sp24  3
#> 25 25 sp25  5
#> 26 26 sp26  4
#> 27 27 sp27  5
#> 28 28 sp28  2
#> 29 29 sp29  2
#> 30 30 sp30  2
#> 31 31 sp31  4
#> 32 32 sp32  0
#> 33 33 sp33  5
#> 34 34 sp34  5
#> 35 35 sp35  5
#> 36 36 sp36  1
#> 37 37 sp37  1
#> 38 38 sp38  2
#> 39 39 sp39  4
#> 40 40 sp40  4
#> 41 41 sp41  0
#> 42 42 sp42  2
#> 43 43 sp43  3
#> 44 44 sp44  4
#> 45 45 sp45  4
#> 46 46 sp46  3
#> 47 47 sp47  5
#> 48 48 sp48  2
#> 49 49 sp49  2
#> 50 50 sp50  1
```


**4.10**
Crie uma lista com os objetos criados anteriormente: **mega**, **tr**, **ma** e **df**.

Solução:

```r
lis <- list(mega, tr, ma, df)
lis
#> [[1]]
#> [1] 10 55  9 24 29 36
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
#>   [1,]    2    2   10    5    1    5    9    5    3     2
#>   [2,]    7   10    4    3    6    1    9    8    5     8
#>   [3,]    2   10    5   10   10    6    4    5    1     3
#>   [4,]   10    4    7   10    6    6    9    8    3     7
#>   [5,]   10    6    4    7    3    0   10    3   10     4
#>   [6,]    0    0    8    4    8    7    6    5    3     3
#>   [7,]    7    2    7    0    0    5    2    2    9     2
#>   [8,]    8    8    8    8    3    1    2    1    8     1
#>   [9,]    2    4    6    8    6    7    4    8    0     1
#>  [10,]    7    6    7    3    9    0    6    2    4     3
#>  [11,]    6    4    5    0    7   10    7    9    6     5
#>  [12,]    0   10    5    3    6    8    4    0    0     1
#>  [13,]    2    2   10    7    9    1    6    4    8     6
#>  [14,]    5    0    3    8    0    5    1    8    9     4
#>  [15,]    5    8    9    8    3    1    4    5    8     0
#>  [16,]    5    2    0    1    0    4    2   10    1     0
#>  [17,]    0    3    0    3    0    3    6    9    2    10
#>  [18,]    6    2    1    4    7    1    5    9    9     4
#>  [19,]    2    3    6    6    9    3    4    4    1     5
#>  [20,]    2    3    6    8    1    6    1   10    7    10
#>  [21,]    9    7    4    7    0    3    9    0    3     5
#>  [22,]    4    2    3    0   10    6    5    3    4     9
#>  [23,]   10    6   10    5    2    0   10    1    5     5
#>  [24,]    3    1    5    2    6    1   10    4    5     8
#>  [25,]   10    0   10    6    0    5    6    3    3     7
#>  [26,]    7    3    9    6    9    6    5    7    9     1
#>  [27,]    3    8    1    3    3    3    8    3    0     8
#>  [28,]    5    7    4    1    6    4    8    8   10     2
#>  [29,]   10    5    8    4    8    3    8    8    7     3
#>  [30,]   10    9    8    8    5    4    0    4   10     9
#>  [31,]   10    6    4    8    2    7    0    3    7     7
#>  [32,]    8    7    0    8   10    7    7    4    6     1
#>  [33,]   10   10    9    8    5    5    1    1    4     9
#>  [34,]    1    7    3    4    7    3    8    5    6     9
#>  [35,]    5    6    0    9    8    8    0    1    8     9
#>  [36,]    0    1    9    4    3    2    5   10    3     8
#>  [37,]    2    6    4    9    8    5    6    9    1     2
#>  [38,]    9    8    8    2    1    1   10    0   10     8
#>  [39,]    0    2    4    8    4    8   10   10    2     4
#>  [40,]    5    6    0    5    8    1    5    5    2     4
#>  [41,]    0    9    8   10    7    2    4    0    8     8
#>  [42,]    7    6    7    1    6    0    1    2   10     2
#>  [43,]    9    8    7    9    3    9    7    4    9     2
#>  [44,]    7    4    2    7    1    2    9   10    8     9
#>  [45,]    2    4   10    9    3    8    5    7    5     1
#>  [46,]    2    2    2    0    0   10    7    4    1    10
#>  [47,]    0    1    2    6   10    0    7    0    0     3
#>  [48,]    4    7    0    6    8   10    5    7    6     6
#>  [49,]   10    1    1    0    0    5   10   10   10     7
#>  [50,]   10    7    1    1    9    2    1    8   10     7
#>  [51,]    7    0    7    0    7    2    7    1   10     0
#>  [52,]    1    7    8    7    4    0    7    7    2     0
#>  [53,]    0    9    5    6    0    5    6    2    5    10
#>  [54,]    9   10    0    9    5    4    0    5    5     8
#>  [55,]    8    5    1    9    0    9    9    1    6     3
#>  [56,]    8    5    0    7    6    6    7    0    4     3
#>  [57,]    0    1    5    5    5    6    6    5    2    10
#>  [58,]    2    9    5    1   10    1    4    0    6     8
#>  [59,]    2    5    6    3    3    3    8    0    6     1
#>  [60,]    4    5    9    8   10    5    4    3   10     8
#>  [61,]    7    9    4    9    5    5    8    5    8     8
#>  [62,]    7    6    5    1    5    8    5    3    9     5
#>  [63,]    7   10    7   10    1    8   10    3    2     3
#>  [64,]    8    8    7    1    2    5    7   10    3     7
#>  [65,]    6    7    7    2    5    2    7    4    0     4
#>  [66,]    7    8   10    8    4    8    9    7    2     9
#>  [67,]    9    8    1    3    7    8    3    8    9     2
#>  [68,]    0    5    6   10    5    7    9    9    0     3
#>  [69,]    0   10    1    5    4    6    9    0    5     7
#>  [70,]    7    4    9    6    3    3    6   10    0     7
#>  [71,]    0    4    5    8    1    2    9    0    5     4
#>  [72,]    4    5    8    3    7    0    8    4    5     8
#>  [73,]    7    6   10    6    1   10    2    3    6    10
#>  [74,]    6   10    8    1    8    6    4    5    5     0
#>  [75,]    6    9    8   10    4    2    4    0    6     5
#>  [76,]    6    3    4    4    9    5    8    1    3     2
#>  [77,]    0    0    4    2    3   10    0    4    6     7
#>  [78,]    4    0    6    3    6    8    5    2    0     7
#>  [79,]    9    0    0    1    3   10    0    0    0     6
#>  [80,]    0    7   10    6    7    7    0    3    6     7
#>  [81,]    3    1    5    1    5    0    4    9    6     5
#>  [82,]    7    2    3    8    8    5    2    9    2     1
#>  [83,]    3    9   10    6    9    6    8    0    0     7
#>  [84,]    6    1    1    9    8    5    1    7    9    10
#>  [85,]    7    0    9    7    4    9   10    8   10     0
#>  [86,]    7    5    9    4    8    1    0    7    5     2
#>  [87,]    0    4    8    6    7    6    7    7    0    10
#>  [88,]    8    3    5    0    5    6    6    0    8     2
#>  [89,]    8   10    7    3    4   10    6    0    2     0
#>  [90,]    7    1    0    2    2    4    2    2    5     2
#>  [91,]    4    1   10    3    1    9    3    6    5     4
#>  [92,]    2    5    0    2    9    6    1    2    2    10
#>  [93,]    9    2    3    4    3    6   10    1    5     0
#>  [94,]    3    8    7    4    6    6    9    7    6     9
#>  [95,]    4    0    8    3    5    2    7    9    2    10
#>  [96,]   10    6    6    6    4    2    8   10   10     3
#>  [97,]    2    9   10    8    0    5    6    4    9     5
#>  [98,]    2    1    8   10    5    7    0    1    2     9
#>  [99,]   10    1    1    1    2    9    2    6    4     6
#> [100,]    2    4    3    2    4    6    9    9    1     1
#> 
#> [[4]]
#>    id   sp ab
#> 1   1 sp01  0
#> 2   2 sp02  2
#> 3   3 sp03  2
#> 4   4 sp04  1
#> 5   5 sp05  2
#> 6   6 sp06  0
#> 7   7 sp07  1
#> 8   8 sp08  3
#> 9   9 sp09  4
#> 10 10 sp10  5
#> 11 11 sp11  2
#> 12 12 sp12  2
#> 13 13 sp13  5
#> 14 14 sp14  1
#> 15 15 sp15  1
#> 16 16 sp16  3
#> 17 17 sp17  4
#> 18 18 sp18  4
#> 19 19 sp19  4
#> 20 20 sp20  0
#> 21 21 sp21  4
#> 22 22 sp22  4
#> 23 23 sp23  4
#> 24 24 sp24  3
#> 25 25 sp25  5
#> 26 26 sp26  4
#> 27 27 sp27  5
#> 28 28 sp28  2
#> 29 29 sp29  2
#> 30 30 sp30  2
#> 31 31 sp31  4
#> 32 32 sp32  0
#> 33 33 sp33  5
#> 34 34 sp34  5
#> 35 35 sp35  5
#> 36 36 sp36  1
#> 37 37 sp37  1
#> 38 38 sp38  2
#> 39 39 sp39  4
#> 40 40 sp40  4
#> 41 41 sp41  0
#> 42 42 sp42  2
#> 43 43 sp43  3
#> 44 44 sp44  4
#> 45 45 sp45  4
#> 46 46 sp46  3
#> 47 47 sp47  5
#> 48 48 sp48  2
#> 49 49 sp49  2
#> 50 50 sp50  1
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
#> 4      4 sp04  1
#> 6      6 sp06  0
#> 8      8 sp08  3
#> 10    10 sp10  5
#> 12    12 sp12  2
#> 14    14 sp14  1
#> 16    16 sp16  3
#> 18    18 sp18  4
#> 20    20 sp20  0
#> 22    22 sp22  4
#> 24    24 sp24  3
#> 26    26 sp26  4
#> 28    28 sp28  2
#> 30    30 sp30  2
#> 32    32 sp32  0
#> 34    34 sp34  5
#> 36    36 sp36  1
#> 38    38 sp38  2
#> 40    40 sp40  4
#> 42    42 sp42  2
#> 44    44 sp44  4
#> 46    46 sp46  3
#> 48    48 sp48  2
#> 50    50 sp50  1
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
#> 46 46 sp46  3
#> 17 17 sp17  4
#> 27 27 sp27  5
#> 11 11 sp11  2
#> 4   4 sp04  1
#> 42 42 sp42  2
#> 41 41 sp41  0
#> 25 25 sp25  5
#> 43 43 sp43  3
#> 21 21 sp21  4
```

**4.14**
Amostre 10 linhas do objeto **ma**, mas utilizando as linhas amostradas do **df_amos10** e atribua ao objeto **ma_amos10**.

 Solução:

```r
ma_amos10 <- ma[df_amos10$id, ]
ma_amos10
#>       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
#>  [1,]    2    2    2    0    0   10    7    4    1    10
#>  [2,]    0    3    0    3    0    3    6    9    2    10
#>  [3,]    3    8    1    3    3    3    8    3    0     8
#>  [4,]    6    4    5    0    7   10    7    9    6     5
#>  [5,]   10    4    7   10    6    6    9    8    3     7
#>  [6,]    7    6    7    1    6    0    1    2   10     2
#>  [7,]    0    9    8   10    7    2    4    0    8     8
#>  [8,]   10    0   10    6    0    5    6    3    3     7
#>  [9,]    9    8    7    9    3    9    7    4    9     2
#> [10,]    9    7    4    7    0    3    9    0    3     5
```

**4.15** 
Una as colunas dos objetos **df_amos10** e **ma_amos10** e atribua ao objeto **dados_amos10**.

Solução:

```r
dados_amos10 <- cbind(df_amos10, ma_amos10)
dados_amos10
#>    id   sp ab  1 2  3  4 5  6 7 8  9 10
#> 46 46 sp46  3  2 2  2  0 0 10 7 4  1 10
#> 17 17 sp17  4  0 3  0  3 0  3 6 9  2 10
#> 27 27 sp27  5  3 8  1  3 3  3 8 3  0  8
#> 11 11 sp11  2  6 4  5  0 7 10 7 9  6  5
#> 4   4 sp04  1 10 4  7 10 6  6 9 8  3  7
#> 42 42 sp42  2  7 6  7  1 6  0 1 2 10  2
#> 41 41 sp41  0  0 9  8 10 7  2 4 0  8  8
#> 25 25 sp25  5 10 0 10  6 0  5 6 3  3  7
#> 43 43 sp43  3  9 8  7  9 3  9 7 4  9  2
#> 21 21 sp21  4  9 7  4  7 0  3 9 0  3  5
```
