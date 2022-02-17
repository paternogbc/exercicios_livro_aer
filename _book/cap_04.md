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
Crie dois objetos (qualquer nome) com os valores 100 e 300. Multiplique esses objetos (função `prod()`) e atribuam ao objeto `mult`. Faça o logaritmo natural (função `log()`) do objeto `mult` e atribuam ao objeto `ln`.

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
#> [1] 18916
```

**4.5**
Instale o pacote `tidyverse` do CRAN.

Solução:

```r
install.packages("tidyverse", dependencies = TRUE)
```

**4.6**
Escolha números para jogar na mega-sena usando o R, nomeando o objeto como `mega`. Lembrando: são 6 valores de 1 a 60 e atribuam a um objeto.

Solução:

```r
mega <- sample(x = 1:60, size = 6, replace = FALSE)
mega
#> [1] 11 10 30  1 46 52
```

**4.7**
Crie um fator chamado `tr`, com dois níveis ("cont" e "trat") para descrever 30 locais de amostragem, 15 de cada tratamento. O fator deve ser dessa forma `cont, cont, cont, ...., cont, trat, trat, ...., trat`.

Solução:

```r
tr <- factor(c(rep("cont", each = 15), rep("trat", each = 15)))
tr
#>  [1] cont cont cont cont cont cont cont cont cont cont cont
#> [12] cont cont cont cont trat trat trat trat trat trat trat
#> [23] trat trat trat trat trat trat trat trat
#> Levels: cont trat
```

**4.8**
Crie uma matriz chamada `ma`, resultante da disposição de um vetor composto por 300 valores aleatórios entre 0 e 10. A matriz deve conter 30 linhas e ser disposta por colunas.

Solução:

```r
ma <- matrix(sample(0:10, 300, rep = TRUE), nrow = 30, byrow = FALSE)
ma
#>       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
#>  [1,]    5    2    0    6    5    8    0    6    0     1
#>  [2,]    9    0    7    8    5    2    3    4    7     0
#>  [3,]    3    5    7    6    4    8    3    4    0     2
#>  [4,]    7    8    7    8    9    8   10    5    9     3
#>  [5,]    2   10    0    7    9    2    5    1    2     2
#>  [6,]    2    7    5    7    6   10    9    2    4     7
#>  [7,]    4    0    8    9    0    3    1    1    4     0
#>  [8,]    6    5    9    4    7    3   10    1    5     9
#>  [9,]    1    8    1    0    2    6    9    8    4     4
#> [10,]    3    9    7    6    2    0    8    8    6     2
#> [11,]    6    1    4    0    9    6    3   10    0     4
#> [12,]    4    6    5    7    6    7    9    7    0     5
#> [13,]    6    5    2    9    1   10    4    3   10     6
#> [14,]    7    8    8    6    1    0    6    1    4     7
#> [15,]    4    5   10    9   10    5    8    6    7     0
#> [16,]    9    7    0    5    9    5    9    1    9     0
#> [17,]    3   10    1    7    8    4    3    9    7     9
#> [18,]    1    3    9   10    4    3    0    5    4     2
#> [19,]    4    2    9    5    3    2   10    3    7     2
#> [20,]   10    2    1    6    6   10    4    1    5     9
#> [21,]    2    7    1    8    2    5    2    8    8     6
#> [22,]    3   10    7    6    5    1    4    6    2     6
#> [23,]    4   10    7    9    5    0    1   10    5     6
#> [24,]    1    7    4    6    3    7    2    3    7     8
#> [25,]   10    7    1   10    9    6    7    8    4     3
#> [26,]    1    4    8    1    7    3    4    0    7     7
#> [27,]    6    9    4   10   10    1    8    1    1     8
#> [28,]    1    2    2    6    0    5   10    7    9     5
#> [29,]    2    2    1    1   10    8    2    9    1    10
#> [30,]    6    6    3    3    8    5    7    8    4     6
```

**4.9**
Crie um data frame chamado `df`, resultante da composição dos vetores: 

1. `id: 1:30`
1. `sp: sp01, sp02, ..., sp29, sp30`
1. `ab: 30 valores aleatórios entre 0 a 5`

 Solução:

```r
df <- data.frame(id = 1:30,
                  sp = c(paste0("sp0", 1:9), paste0("sp", 10:30)),
                  ab = sample(0:5, 30, rep = TRUE))
df
#>    id   sp ab
#> 1   1 sp01  3
#> 2   2 sp02  1
#> 3   3 sp03  4
#> 4   4 sp04  2
#> 5   5 sp05  0
#> 6   6 sp06  3
#> 7   7 sp07  1
#> 8   8 sp08  5
#> 9   9 sp09  5
#> 10 10 sp10  0
#> 11 11 sp11  3
#> 12 12 sp12  2
#> 13 13 sp13  0
#> 14 14 sp14  5
#> 15 15 sp15  2
#> 16 16 sp16  5
#> 17 17 sp17  0
#> 18 18 sp18  1
#> 19 19 sp19  3
#> 20 20 sp20  0
#> 21 21 sp21  1
#> 22 22 sp22  5
#> 23 23 sp23  3
#> 24 24 sp24  3
#> 25 25 sp25  4
#> 26 26 sp26  3
#> 27 27 sp27  0
#> 28 28 sp28  0
#> 29 29 sp29  3
#> 30 30 sp30  5
```

**4.10**
Crie uma lista com os objetos criados anteriormente: `mega`, `tr`, `ma` e `df`.

Solução:

```r
lis <- list(mega, tr, ma, df)
lis
#> [[1]]
#> [1] 11 10 30  1 46 52
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
#>   [1,]    5    0    2    7    8    5    6    8    3    10
#>   [2,]    9    7    4    3    1    6    2    4    2     6
#>   [3,]    3    9    1    1    2    0    6    9    3     4
#>   [4,]    7    6    2    6    4    3    6    6    3     3
#>   [5,]    2    9    7   10    4    4    8    9    0     0
#>   [6,]    2    5    4    8    7    2    1    9    3     7
#>   [7,]    4    7    8    3    8    2    7    5    2     0
#>   [8,]    6   10   10    7    9    8    3    3    3     4
#>   [9,]    1    5    2    9    0    6    9    3    2     3
#>  [10,]    3    6    7    7    5    5    0   10    2     7
#>  [11,]    6    8    6    5    9   10    8    9    0    10
#>  [12,]    4    6    4    5    1    2    8    9    8     1
#>  [13,]    6    9    4    8    9    6    0    5    1     7
#>  [14,]    7    6    5    6    1   10    1    8   10    10
#>  [15,]    4   10    1    3    1    5    7    7    5     3
#>  [16,]    9    1    2   10    7    2    9    3    4     6
#>  [17,]    3   10    1    8    0    3    2    2    1    10
#>  [18,]    1    6    1    7    1    8    0    1    5     4
#>  [19,]    4    1    8   10    3    7    1    6    5     7
#>  [20,]   10    3    8    0    8    2    0    4    8     2
#>  [21,]    2    5   10    1    2   10    1    0   10     8
#>  [22,]    3    5    7    3    4    3    2    0    9     8
#>  [23,]    4    4    3    0    7    6    5    6    8     3
#>  [24,]    1    9    1    1    2    2    2    8    4     4
#>  [25,]   10    9    6    5    7    4   10    0    8     9
#>  [26,]    1    6    1    3    9    6    7    3    0     5
#>  [27,]    6    0    9    4   10    7    4   10    4     7
#>  [28,]    1    7    5    3    4    8    8    2    0    10
#>  [29,]    2    2    3    8    8    7    1    3    7     5
#>  [30,]    6    2    1    8    4    1    8    1    8     2
#>  [31,]    2    9    8    3    9    5    0    9    8     9
#>  [32,]    0    6    6    5    1    2    6    9    9     4
#>  [33,]    5    1   10    2   10    5    6    0    9     4
#>  [34,]    8    1    3    1   10    2    2    9    5     2
#>  [35,]   10   10    8    3    6    4    9    3    6     2
#>  [36,]    7    9    0    3    5   10    5    5    8     7
#>  [37,]    0    8    1    7    9    9    5    4    5     5
#>  [38,]    5    4    7    4   10    1    4    9    9     2
#>  [39,]    8    3    9    3    0    5    7    9    6     2
#>  [40,]    9    6    8    3    4    2    1    1    1     2
#>  [41,]    1    2    0    9    5    8    8    9    1    10
#>  [42,]    6    5    7    4    9    3    5    2    0     7
#>  [43,]    5    5    0    7    4    0   10    8    7     9
#>  [44,]    8    3    9    1    4    5    0    2    1     8
#>  [45,]    5    9    2    1    0    7    3   10    2     7
#>  [46,]    7    7    4   10    0    2    9    7    6     3
#>  [47,]   10   10    4    4    4    6    2    3    6     3
#>  [48,]    3    0    5    3    9    3    2    2    6     1
#>  [49,]    2   10    4    3    5    8    6    6    5     2
#>  [50,]    2    8    6   10    3    1    3    7    6     6
#>  [51,]    7    8    0    7    8   10    6    7    7     4
#>  [52,]   10    2    0    3    0    3    2    1    1     7
#>  [53,]   10    8   10    3    8    8    4    8    1     1
#>  [54,]    7    8    4    1    5    3    2    9    7    10
#>  [55,]    7    2    7    1    7    6    0   10    1     0
#>  [56,]    4   10    9    2    6    3    2    4    7     5
#>  [57,]    9    3    7    0   10    0    1    3    1     7
#>  [58,]    2    3    4    3    8   10    4   10    6     6
#>  [59,]    2    6    7    4    4    4    5    9    1     2
#>  [60,]    6    0    5    1    8    8    7    7    0     5
#>  [61,]    0    6    8    4   10    6    2    4    6     4
#>  [62,]    7    7    2    0    9    9    3    2   10     1
#>  [63,]    7   10    5    3    8    0    8    2    8     2
#>  [64,]    7    0    7    1   10    5    6    7    3     6
#>  [65,]    0    5    4    9    0    5    3    0   10     6
#>  [66,]    5    5    7    0    7    2    7   10    1    10
#>  [67,]    8    4    1    4   10    0    6    7    6    10
#>  [68,]    9    3    9    5    4    2    4    8    1     4
#>  [69,]    1    2    1    9    7    5    0    2    7     4
#>  [70,]    7   10    4    6   10    0    2    1    9     3
#>  [71,]    4    5    1    6    4    3    3    7   10     8
#>  [72,]    5    1    0    6    9   10    0    3    1     5
#>  [73,]    2    0    2    2    9    3    3    9    5     8
#>  [74,]    8    7    3    6    7   10    2    6    8     3
#>  [75,]   10    6    2    0    9    0    2    8    5     7
#>  [76,]    0    3    7   10    5    3    8    9    5     2
#>  [77,]    1    1    0    8    1    8    1    3    8     0
#>  [78,]    9    5    9    2    3    3    9    9    4     7
#>  [79,]    9    8    4    0    7    7    6    0    0     6
#>  [80,]    1    5    2    3    2    5    6    8    5     2
#>  [81,]    1    0    4    5    8    4    4   10    1     2
#>  [82,]    7    3    5    2    0    4    6    1    0     7
#>  [83,]    7    3    6    4    8    0    5    2    4     9
#>  [84,]    4   10    7    5    6    1    7    5    3     0
#>  [85,]    1    5    0    2    0    9    4    7   10     3
#>  [86,]    8    9    0    7    8    7    6    1    3     3
#>  [87,]    4    1    9    7    2    7    8    4    4     4
#>  [88,]    2   10    2    8    0    1   10    9    3     6
#>  [89,]    1    9    2    5    0    9    4    0    0     3
#>  [90,]    3    8    9    7    9    7    2    1    9     1
#>  [91,]    6    3    6    7    5    6    7    2    6     3
#>  [92,]    8    9    6    5   10   10    4    4    4     1
#>  [93,]    6    4    6    8    1    0    5    6    0     8
#>  [94,]    8    6    8    0    6    7    6    0    3     6
#>  [95,]    7    8    3   10    0    2    2    7    6     7
#>  [96,]    7    9    7    4   10    8    3    5    5     4
#>  [97,]    9    3    8    0   10   10    0    1    5     4
#>  [98,]    4    0    5    6    5    8    0    8    7     0
#>  [99,]    0   10   10    8    4    2    3    8    6     0
#> [100,]    6    4    6    4    7    4    8    2    4     2
#> 
#> [[4]]
#>    id   sp ab
#> 1   1 sp01  4
#> 2   2 sp02  2
#> 3   3 sp03  2
#> 4   4 sp04  1
#> 5   5 sp05  4
#> 6   6 sp06  3
#> 7   7 sp07  3
#> 8   8 sp08  5
#> 9   9 sp09  2
#> 10 10 sp10  0
#> 11 11 sp11  1
#> 12 12 sp12  5
#> 13 13 sp13  3
#> 14 14 sp14  3
#> 15 15 sp15  2
#> 16 16 sp16  4
#> 17 17 sp17  0
#> 18 18 sp18  1
#> 19 19 sp19  4
#> 20 20 sp20  0
#> 21 21 sp21  0
#> 22 22 sp22  1
#> 23 23 sp23  4
#> 24 24 sp24  5
#> 25 25 sp25  4
#> 26 26 sp26  2
#> 27 27 sp27  4
#> 28 28 sp28  0
#> 29 29 sp29  4
#> 30 30 sp30  1
#> 31 31 sp31  1
#> 32 32 sp32  4
#> 33 33 sp33  3
#> 34 34 sp34  0
#> 35 35 sp35  5
#> 36 36 sp36  5
#> 37 37 sp37  5
#> 38 38 sp38  2
#> 39 39 sp39  1
#> 40 40 sp40  2
#> 41 41 sp41  2
#> 42 42 sp42  0
#> 43 43 sp43  0
#> 44 44 sp44  3
#> 45 45 sp45  2
#> 46 46 sp46  1
#> 47 47 sp47  4
#> 48 48 sp48  2
#> 49 49 sp49  4
#> 50 50 sp50  4
```

**4.11**
Selecione os elementos ímpares do objeto `tr` e atribua ao objeto `tr_impar`.

Solução:

```r
tr_impar <- tr[seq(1, 29, 2)]
tr_impar
#>  [1] cont cont cont cont cont cont cont cont trat trat trat
#> [12] trat trat trat trat
#> Levels: cont trat
```

**4.12**
Selecione as linhas com ids pares do objeto `df` e atribua ao objeto `df_ids_par`.

Solução:

```r
df_ids_par <- df[seq(2, 30, 2), ]
df_ids_par
#>    id   sp ab
#> 2   2 sp02  1
#> 4   4 sp04  2
#> 6   6 sp06  3
#> 8   8 sp08  5
#> 10 10 sp10  0
#> 12 12 sp12  2
#> 14 14 sp14  5
#> 16 16 sp16  5
#> 18 18 sp18  1
#> 20 20 sp20  0
#> 22 22 sp22  5
#> 24 24 sp24  3
#> 26 26 sp26  3
#> 28 28 sp28  0
#> 30 30 sp30  5
```

**4.13**
Faça uma amostragem de 10 linhas do objeto `df` e atribua ao objeto `df_amos10`. Use a função `set.seed()` para fixar a amostragem.

 Solução:

```r
set.seed(42)
df_amos10 <- df[sample(nrow(df), 10), ]
df_amos10
#>    id   sp ab
#> 17 17 sp17  0
#> 5   5 sp05  0
#> 1   1 sp01  3
#> 25 25 sp25  4
#> 10 10 sp10  0
#> 4   4 sp04  2
#> 18 18 sp18  1
#> 30 30 sp30  5
#> 15 15 sp15  2
#> 7   7 sp07  1
```

**4.14**
Amostre 10 linhas do objeto `ma`, mas utilizando as linhas amostradas do `df_amos10` e atribua ao objeto `ma_amos10`.

 Solução:

```r
ma_amos10 <- ma[df_amos10$id, ]
ma_amos10
#>       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
#>  [1,]    6   10   10    7    9    8    3    3    3     4
#>  [2,]    7    6    2    6    4    3    6    6    3     3
#>  [3,]    7    9    0    3    5   10    5    5    8     7
#>  [4,]    1    6    1    7    1    8    0    1    5     4
#>  [5,]    1    2    0    9    5    8    8    9    1    10
#>  [6,]    5    4    7    4   10    1    4    9    9     2
#>  [7,]    2    8    6   10    3    1    3    7    6     6
#>  [8,]    3    6    7    7    5    5    0   10    2     7
#>  [9,]    7    6    5    6    1   10    1    8   10    10
#> [10,]    1    6    1    3    9    6    7    3    0     5
```

**4.15**
Una as colunas dos objetos `df_amos10` e `ma_amos10` e atribua ao objeto `dados_amos10`.

Solução:

```r
dados_amos10 <- cbind(df_amos10, ma_amos10)
dados_amos10
#>    id   sp ab 1  2  3  4  5  6 7  8  9 10
#> 8   8 sp08  5 6 10 10  7  9  8 3  3  3  4
#> 4   4 sp04  1 7  6  2  6  4  3 6  6  3  3
#> 36 36 sp36  5 7  9  0  3  5 10 5  5  8  7
#> 18 18 sp18  1 1  6  1  7  1  8 0  1  5  4
#> 41 41 sp41  2 1  2  0  9  5  8 8  9  1 10
#> 38 38 sp38  2 5  4  7  4 10  1 4  9  9  2
#> 50 50 sp50  4 2  8  6 10  3  1 3  7  6  6
#> 10 10 sp10  0 3  6  7  7  5  5 0 10  2  7
#> 14 14 sp14  3 7  6  5  6  1 10 1  8 10 10
#> 26 26 sp26  2 1  6  1  3  9  6 7  3  0  5
```
