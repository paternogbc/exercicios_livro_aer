# Exercícios do capítulo 4 - Introdução ao R

## 4.1 Use o R para verificar o resultado da operação `7 + 7 ÷ 7 + 7 x 7 - 7`.

### Solução

```r
7 + 7 / 7 + 7 * 7 - 7
#> [1] 50
```

## 4.2 Verifique através do R se `3x2³` é maior que `2x3²`.

### Solução

```r
3 * 2^3 > 2 * 3^2
#> [1] TRUE
```

## 4.3 Crie dois objetos (qualquer nome) com os valores 100 e 300. Multiplique esses objetos (função `prod()`) e atribuam ao objeto **mult**. Faça o logaritmo natural (função `log()`) do objeto **mult** e atribuam ao objeto **ln**.

### Solução

```r
obj1 <- 100
obj2 <- 300
mult <- prod(obj1, obj2)
ln <- log(obj1, obj2)
```

## 4.4 Quantos pacotes existem no CRAN nesse momento? Execute essa combinação no Console: `nrow(available.packages(repos = "http://cran.r-project.org"))`.

### Solução

```r
nrow(available.packages(repos = "http://cran.r-project.org"))
#> [1] 18897
```

## 4.5 Instale o pacote `tidyverse` do CRAN.

### Solução

```r
install.packages("tidyverse", dependencies = TRUE)
```

## 4.6 Escolha números para jogar na mega-sena usando o R, nomeando o objeto como **mega**. Lembrando: são 6 valores de 1 a 60 e atribuam a um objeto.

### Solução

```r
mega <- sample(x = 1:60, size = 6, replace = FALSE)
mega
#> [1] 21 53 39 51 18 48
```

## 4.7 Crie um fator chamado **tr**, com dois níveis ("cont" e "trat") para descrever 100 locais de amostragem, 50 de cada tratamento. O fator deve ser dessa forma `cont, cont, cont, ...., cont, trat, trat, ...., trat`.

### Solução

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

## 4.8 Crie uma matriz chamada **ma**, resultante da disposição de um vetor composto por 1000 valores aleatórios entre 0 e 10. A matriz deve conter 100 linhas e ser disposta por colunas.

### Solução

```r
ma <- matrix(sample(0:10, 1000, rep = TRUE), nrow = 100, byrow = FALSE)
ma
#>        [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
#>   [1,]    6    1    5    9    3    7    2    3    2     0
#>   [2,]    5    4    2    0   10    1    3    5    2     5
#>   [3,]    1    2    9    6    6    4    0    1    5     3
#>   [4,]    2    9    3    4    5   10    7   10   10     5
#>   [5,]    4    4    6    2    0    9    4    8    7     3
#>   [6,]    8    0    1    9    0    3    3   10    6     0
#>   [7,]    6    7    1   10    5    3    7    7    3     3
#>   [8,]    2    9    6    2    8    6    0    8    4     9
#>   [9,]   10    2    8    1   10    2    2    6    2     9
#>  [10,]    0   10    7    6    8   10    6    0    9     9
#>  [11,]    6    7    3    9    0    6    5    2    1     2
#>  [12,]    4   10    5    9    5    8    2    2    0     3
#>  [13,]    7    1    9    2    5    9    2    5    8     5
#>  [14,]    4    3    1    9   10    1    2    9    0     4
#>  [15,]    1   10    9    4    0    5    9    8    1     0
#>  [16,]    6    3    3    5    8    2    2    0    8     6
#>  [17,]    4    8    3    3    2    7    3    7    4     5
#>  [18,]    1    0    8    4    5    0    9    6    6     6
#>  [19,]    9    8    6    9    1    2   10    7    6     1
#>  [20,]    6   10   10   10    5    0    4    6    3     0
#>  [21,]    3    5    1    7    3    3    2    5    6     2
#>  [22,]   10    8    0    0    0    8    3    4   10     2
#>  [23,]    5    6    1    1    0    2    8    9    3     5
#>  [24,]    7    4    9    3    3    7    1    4    1     3
#>  [25,]    4    9    4   10    3    1    1    9   10     7
#>  [26,]    7    0    6    3    8    8    2    2    7     7
#>  [27,]    4    3    4    4    4    6    0    0   10     7
#>  [28,]    1    0    9    1    7    3    6    2   10     7
#>  [29,]    4    2    2    0    0    0   10    4    2     9
#>  [30,]    0    6    3    1   10    7    0    2    3     2
#>  [31,]    0    2    3    3    6    8   10    2    6     2
#>  [32,]    9    8    3    0    2    2    2    8    5     0
#>  [33,]    4    2    6    8    6    4    4    1    1     8
#>  [34,]    5    9   10    6    2    8    0    6    2     1
#>  [35,]    5    8    5    6    2    9    1    4    3     3
#>  [36,]    3    4    6   10    7    7    5    2    5    10
#>  [37,]    2    0    0    3    0    8    2   10    0     4
#>  [38,]    8    2    2    5    0    5   10    5    7     8
#>  [39,]    4    6   10    3    4   10    7    9    2     4
#>  [40,]    2    7    1    0   10    0    6    3    5     9
#>  [41,]   10    6    8    3    4   10    5    4    3     2
#>  [42,]    8    0    2    5    9    1    0    4    6     9
#>  [43,]    9    7    8    2    3    1    2    3    5     8
#>  [44,]    8    2    7    1    1    5    7    7    3     3
#>  [45,]    0    3    3   10    5    0    1    7    8     4
#>  [46,]    6    6    8    6    2    6    5    8    2     5
#>  [47,]    9   10    1    4    5    1    4    0    5     7
#>  [48,]    0    9    9    6    7    3    0    3    4     8
#>  [49,]    4    8    5    8    9    2    2    0    3     8
#>  [50,]    6    5    7    3    7    5    1    0    9     6
#>  [51,]    9    9    6    3    6   10    3    2    8     9
#>  [52,]    7    7    3    3    2    9    4    7    7     0
#>  [53,]    9    7    1    9    9    5    6    8   10     5
#>  [54,]    0    9    7    6    6    3    1    2    1     5
#>  [55,]    1    7    6    6    7    0    2    3    7     9
#>  [56,]    7   10    0    1    2    0    6    3    6     7
#>  [57,]    4    5    9   10    2    1    3    9    7     4
#>  [58,]    4    0    1   10    9    9    1    2    9     0
#>  [59,]    8   10    8    2    2    4    8    1    2     4
#>  [60,]    5    1    7    9    0    7    3    1    9     9
#>  [61,]    9    0    8    9    6    1    3    8    7     5
#>  [62,]    6    7    9    4    1    2    1    4    1     1
#>  [63,]    7    6    8    7    0    0    1    8    8    10
#>  [64,]    1    6    0    8    8    1    8    8    0     9
#>  [65,]    1    2    4    7    0    3    4    5    7     2
#>  [66,]    9    4    3    9    2    5    5    9    5    10
#>  [67,]    5    7    6    7    4    6    0    9    1     3
#>  [68,]    6   10    0    4    2    4    3    6    0     6
#>  [69,]    3    2    1    6   10    4    2    2    1     1
#>  [70,]    5   10    0    4   10    4    0   10    3     8
#>  [71,]    4   10    5    5    5    5    5    6    3     3
#>  [72,]    1    2   10    0    9    0    4    4    6     0
#>  [73,]    1    4    6   10    4    2   10    3    9     9
#>  [74,]    2    5    6    4    2    3    9    1    4     4
#>  [75,]    4    7   10    8    7    9    2    7    3     8
#>  [76,]    6    8    7    6    8    6    5    9    9     4
#>  [77,]    8    3    7    6    4    9    1    2   10     2
#>  [78,]    9    1    1    6    2    0    3    5    6     6
#>  [79,]    0    8    9    3    0    3    8   10    7     9
#>  [80,]    3    6    0   10    3    2    0    9   10     2
#>  [81,]   10    7    2    4    0    7    1    8    4     8
#>  [82,]    3    9    9    0    4    6    2    0    7     9
#>  [83,]    8    2    9    2    2    1   10    2    8     6
#>  [84,]   10    3    8    4    1    0    7    9    6     0
#>  [85,]    6    5    2    5   10    0    8    8    3     8
#>  [86,]    8    8    9    9   10   10    4    0    8     8
#>  [87,]    3    3    4    3    4   10    0    5   10     7
#>  [88,]    3    9    6    0    3    8    9    5   10     9
#>  [89,]    4    9   10    4    1    6   10    0    9     3
#>  [90,]    3    5    4    1    9    8    7   10    1     0
#>  [91,]    6    9    8    2    8    3    6    4    1     0
#>  [92,]    0    3    6    7    0    0    7   10   10     8
#>  [93,]    2    5    7    3    6    8    2    9    5     0
#>  [94,]   10    6    5    3    8    8    3    4    6     8
#>  [95,]    7    2    0    0    5    7    4    2    9     7
#>  [96,]    3   10   10    4    9    9    8    6   10     5
#>  [97,]    9    2    9    1    1    8    7    7    4     1
#>  [98,]    1    5    2    6    1    1    5    7    4     8
#>  [99,]    7    2   10    2    9    8    6    8   10     4
#> [100,]   10   10    0    4    3    3    8    1    3     9
```

## 4.9 Crie um data frame chamado **df**, resultante da composição dos vetores: 

1. `id: 1:50`
1. `sp: sp01, sp02, ..., sp49, sp50`
1. `ab: 50 valores aleatórios entre 0 a 5`

### Solução

```r
df <- data.frame(id = 1:50,
                  sp = c(paste0("sp0", 1:9), paste0("sp", 10:50)),
                  ab = sample(0:5, 50, rep = TRUE))
df
#>    id   sp ab
#> 1   1 sp01  2
#> 2   2 sp02  3
#> 3   3 sp03  4
#> 4   4 sp04  5
#> 5   5 sp05  3
#> 6   6 sp06  0
#> 7   7 sp07  2
#> 8   8 sp08  4
#> 9   9 sp09  5
#> 10 10 sp10  4
#> 11 11 sp11  1
#> 12 12 sp12  2
#> 13 13 sp13  2
#> 14 14 sp14  3
#> 15 15 sp15  0
#> 16 16 sp16  5
#> 17 17 sp17  2
#> 18 18 sp18  1
#> 19 19 sp19  0
#> 20 20 sp20  0
#> 21 21 sp21  5
#> 22 22 sp22  4
#> 23 23 sp23  0
#> 24 24 sp24  4
#> 25 25 sp25  3
#> 26 26 sp26  5
#> 27 27 sp27  5
#> 28 28 sp28  1
#> 29 29 sp29  4
#> 30 30 sp30  0
#> 31 31 sp31  4
#> 32 32 sp32  3
#> 33 33 sp33  0
#> 34 34 sp34  1
#> 35 35 sp35  2
#> 36 36 sp36  0
#> 37 37 sp37  2
#> 38 38 sp38  1
#> 39 39 sp39  1
#> 40 40 sp40  2
#> 41 41 sp41  1
#> 42 42 sp42  2
#> 43 43 sp43  0
#> 44 44 sp44  3
#> 45 45 sp45  0
#> 46 46 sp46  5
#> 47 47 sp47  1
#> 48 48 sp48  4
#> 49 49 sp49  1
#> 50 50 sp50  4
```


## 4.10 Crie uma lista com os objetos criados anteriormente: **mega**, **tr**, **ma** e **df**.

### Solução

```r
lis <- list(mega, tr, ma, df)
lis
#> [[1]]
#> [1] 21 53 39 51 18 48
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
#>   [1,]    6    1    5    9    3    7    2    3    2     0
#>   [2,]    5    4    2    0   10    1    3    5    2     5
#>   [3,]    1    2    9    6    6    4    0    1    5     3
#>   [4,]    2    9    3    4    5   10    7   10   10     5
#>   [5,]    4    4    6    2    0    9    4    8    7     3
#>   [6,]    8    0    1    9    0    3    3   10    6     0
#>   [7,]    6    7    1   10    5    3    7    7    3     3
#>   [8,]    2    9    6    2    8    6    0    8    4     9
#>   [9,]   10    2    8    1   10    2    2    6    2     9
#>  [10,]    0   10    7    6    8   10    6    0    9     9
#>  [11,]    6    7    3    9    0    6    5    2    1     2
#>  [12,]    4   10    5    9    5    8    2    2    0     3
#>  [13,]    7    1    9    2    5    9    2    5    8     5
#>  [14,]    4    3    1    9   10    1    2    9    0     4
#>  [15,]    1   10    9    4    0    5    9    8    1     0
#>  [16,]    6    3    3    5    8    2    2    0    8     6
#>  [17,]    4    8    3    3    2    7    3    7    4     5
#>  [18,]    1    0    8    4    5    0    9    6    6     6
#>  [19,]    9    8    6    9    1    2   10    7    6     1
#>  [20,]    6   10   10   10    5    0    4    6    3     0
#>  [21,]    3    5    1    7    3    3    2    5    6     2
#>  [22,]   10    8    0    0    0    8    3    4   10     2
#>  [23,]    5    6    1    1    0    2    8    9    3     5
#>  [24,]    7    4    9    3    3    7    1    4    1     3
#>  [25,]    4    9    4   10    3    1    1    9   10     7
#>  [26,]    7    0    6    3    8    8    2    2    7     7
#>  [27,]    4    3    4    4    4    6    0    0   10     7
#>  [28,]    1    0    9    1    7    3    6    2   10     7
#>  [29,]    4    2    2    0    0    0   10    4    2     9
#>  [30,]    0    6    3    1   10    7    0    2    3     2
#>  [31,]    0    2    3    3    6    8   10    2    6     2
#>  [32,]    9    8    3    0    2    2    2    8    5     0
#>  [33,]    4    2    6    8    6    4    4    1    1     8
#>  [34,]    5    9   10    6    2    8    0    6    2     1
#>  [35,]    5    8    5    6    2    9    1    4    3     3
#>  [36,]    3    4    6   10    7    7    5    2    5    10
#>  [37,]    2    0    0    3    0    8    2   10    0     4
#>  [38,]    8    2    2    5    0    5   10    5    7     8
#>  [39,]    4    6   10    3    4   10    7    9    2     4
#>  [40,]    2    7    1    0   10    0    6    3    5     9
#>  [41,]   10    6    8    3    4   10    5    4    3     2
#>  [42,]    8    0    2    5    9    1    0    4    6     9
#>  [43,]    9    7    8    2    3    1    2    3    5     8
#>  [44,]    8    2    7    1    1    5    7    7    3     3
#>  [45,]    0    3    3   10    5    0    1    7    8     4
#>  [46,]    6    6    8    6    2    6    5    8    2     5
#>  [47,]    9   10    1    4    5    1    4    0    5     7
#>  [48,]    0    9    9    6    7    3    0    3    4     8
#>  [49,]    4    8    5    8    9    2    2    0    3     8
#>  [50,]    6    5    7    3    7    5    1    0    9     6
#>  [51,]    9    9    6    3    6   10    3    2    8     9
#>  [52,]    7    7    3    3    2    9    4    7    7     0
#>  [53,]    9    7    1    9    9    5    6    8   10     5
#>  [54,]    0    9    7    6    6    3    1    2    1     5
#>  [55,]    1    7    6    6    7    0    2    3    7     9
#>  [56,]    7   10    0    1    2    0    6    3    6     7
#>  [57,]    4    5    9   10    2    1    3    9    7     4
#>  [58,]    4    0    1   10    9    9    1    2    9     0
#>  [59,]    8   10    8    2    2    4    8    1    2     4
#>  [60,]    5    1    7    9    0    7    3    1    9     9
#>  [61,]    9    0    8    9    6    1    3    8    7     5
#>  [62,]    6    7    9    4    1    2    1    4    1     1
#>  [63,]    7    6    8    7    0    0    1    8    8    10
#>  [64,]    1    6    0    8    8    1    8    8    0     9
#>  [65,]    1    2    4    7    0    3    4    5    7     2
#>  [66,]    9    4    3    9    2    5    5    9    5    10
#>  [67,]    5    7    6    7    4    6    0    9    1     3
#>  [68,]    6   10    0    4    2    4    3    6    0     6
#>  [69,]    3    2    1    6   10    4    2    2    1     1
#>  [70,]    5   10    0    4   10    4    0   10    3     8
#>  [71,]    4   10    5    5    5    5    5    6    3     3
#>  [72,]    1    2   10    0    9    0    4    4    6     0
#>  [73,]    1    4    6   10    4    2   10    3    9     9
#>  [74,]    2    5    6    4    2    3    9    1    4     4
#>  [75,]    4    7   10    8    7    9    2    7    3     8
#>  [76,]    6    8    7    6    8    6    5    9    9     4
#>  [77,]    8    3    7    6    4    9    1    2   10     2
#>  [78,]    9    1    1    6    2    0    3    5    6     6
#>  [79,]    0    8    9    3    0    3    8   10    7     9
#>  [80,]    3    6    0   10    3    2    0    9   10     2
#>  [81,]   10    7    2    4    0    7    1    8    4     8
#>  [82,]    3    9    9    0    4    6    2    0    7     9
#>  [83,]    8    2    9    2    2    1   10    2    8     6
#>  [84,]   10    3    8    4    1    0    7    9    6     0
#>  [85,]    6    5    2    5   10    0    8    8    3     8
#>  [86,]    8    8    9    9   10   10    4    0    8     8
#>  [87,]    3    3    4    3    4   10    0    5   10     7
#>  [88,]    3    9    6    0    3    8    9    5   10     9
#>  [89,]    4    9   10    4    1    6   10    0    9     3
#>  [90,]    3    5    4    1    9    8    7   10    1     0
#>  [91,]    6    9    8    2    8    3    6    4    1     0
#>  [92,]    0    3    6    7    0    0    7   10   10     8
#>  [93,]    2    5    7    3    6    8    2    9    5     0
#>  [94,]   10    6    5    3    8    8    3    4    6     8
#>  [95,]    7    2    0    0    5    7    4    2    9     7
#>  [96,]    3   10   10    4    9    9    8    6   10     5
#>  [97,]    9    2    9    1    1    8    7    7    4     1
#>  [98,]    1    5    2    6    1    1    5    7    4     8
#>  [99,]    7    2   10    2    9    8    6    8   10     4
#> [100,]   10   10    0    4    3    3    8    1    3     9
#> 
#> [[4]]
#>    id   sp ab
#> 1   1 sp01  2
#> 2   2 sp02  3
#> 3   3 sp03  4
#> 4   4 sp04  5
#> 5   5 sp05  3
#> 6   6 sp06  0
#> 7   7 sp07  2
#> 8   8 sp08  4
#> 9   9 sp09  5
#> 10 10 sp10  4
#> 11 11 sp11  1
#> 12 12 sp12  2
#> 13 13 sp13  2
#> 14 14 sp14  3
#> 15 15 sp15  0
#> 16 16 sp16  5
#> 17 17 sp17  2
#> 18 18 sp18  1
#> 19 19 sp19  0
#> 20 20 sp20  0
#> 21 21 sp21  5
#> 22 22 sp22  4
#> 23 23 sp23  0
#> 24 24 sp24  4
#> 25 25 sp25  3
#> 26 26 sp26  5
#> 27 27 sp27  5
#> 28 28 sp28  1
#> 29 29 sp29  4
#> 30 30 sp30  0
#> 31 31 sp31  4
#> 32 32 sp32  3
#> 33 33 sp33  0
#> 34 34 sp34  1
#> 35 35 sp35  2
#> 36 36 sp36  0
#> 37 37 sp37  2
#> 38 38 sp38  1
#> 39 39 sp39  1
#> 40 40 sp40  2
#> 41 41 sp41  1
#> 42 42 sp42  2
#> 43 43 sp43  0
#> 44 44 sp44  3
#> 45 45 sp45  0
#> 46 46 sp46  5
#> 47 47 sp47  1
#> 48 48 sp48  4
#> 49 49 sp49  1
#> 50 50 sp50  4
```

## 4.11 Selecione os elementos ímpares do objeto **tr** e atribua ao objeto **tr_impar**.

### Solução

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

## 4.12 Selecione as linhas com ids pares do objeto **df** e atribua ao objeto **df_ids_par**.

### Solução

```r
df_ids_par <- df[seq(2, 100, 2), ]
df_ids_par
#>       id   sp ab
#> 2      2 sp02  3
#> 4      4 sp04  5
#> 6      6 sp06  0
#> 8      8 sp08  4
#> 10    10 sp10  4
#> 12    12 sp12  2
#> 14    14 sp14  3
#> 16    16 sp16  5
#> 18    18 sp18  1
#> 20    20 sp20  0
#> 22    22 sp22  4
#> 24    24 sp24  4
#> 26    26 sp26  5
#> 28    28 sp28  1
#> 30    30 sp30  0
#> 32    32 sp32  3
#> 34    34 sp34  1
#> 36    36 sp36  0
#> 38    38 sp38  1
#> 40    40 sp40  2
#> 42    42 sp42  2
#> 44    44 sp44  3
#> 46    46 sp46  5
#> 48    48 sp48  4
#> 50    50 sp50  4
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

## 4.13 Faça uma amostragem de 10 linhas do objeto **df** e atribua ao objeto **df_amos10**.

### Solução

```r
df_amos10 <- df[sample(nrow(df), 10), ]
df_amos10
#>    id   sp ab
#> 26 26 sp26  5
#> 31 31 sp31  4
#> 38 38 sp38  1
#> 14 14 sp14  3
#> 34 34 sp34  1
#> 40 40 sp40  2
#> 28 28 sp28  1
#> 19 19 sp19  0
#> 39 39 sp39  1
#> 30 30 sp30  0
```

## 4.14 Amostre 10 linhas do objeto **ma**, mas utilizando as linhas amostradas do **df_amos10** e atribua ao objeto **ma_amos10**.

### Solução

```r
ma_amos10 <- ma[df_amos10$id, ]
ma_amos10
#>       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
#>  [1,]    7    0    6    3    8    8    2    2    7     7
#>  [2,]    0    2    3    3    6    8   10    2    6     2
#>  [3,]    8    2    2    5    0    5   10    5    7     8
#>  [4,]    4    3    1    9   10    1    2    9    0     4
#>  [5,]    5    9   10    6    2    8    0    6    2     1
#>  [6,]    2    7    1    0   10    0    6    3    5     9
#>  [7,]    1    0    9    1    7    3    6    2   10     7
#>  [8,]    9    8    6    9    1    2   10    7    6     1
#>  [9,]    4    6   10    3    4   10    7    9    2     4
#> [10,]    0    6    3    1   10    7    0    2    3     2
```

## 4.15 Una as colunas dos objetos **df_amos10** e **ma_amos10** e atribua ao objeto
 **dados_amos10**.

### Solução

```r
dados_amos10 <- cbind(df_amos10, ma_amos10)
dados_amos10
#>    id   sp ab 1 2  3 4  5  6  7 8  9 10
#> 26 26 sp26  5 7 0  6 3  8  8  2 2  7  7
#> 31 31 sp31  4 0 2  3 3  6  8 10 2  6  2
#> 38 38 sp38  1 8 2  2 5  0  5 10 5  7  8
#> 14 14 sp14  3 4 3  1 9 10  1  2 9  0  4
#> 34 34 sp34  1 5 9 10 6  2  8  0 6  2  1
#> 40 40 sp40  2 2 7  1 0 10  0  6 3  5  9
#> 28 28 sp28  1 1 0  9 1  7  3  6 2 10  7
#> 19 19 sp19  0 9 8  6 9  1  2 10 7  6  1
#> 39 39 sp39  1 4 6 10 3  4 10  7 9  2  4
#> 30 30 sp30  0 0 6  3 1 10  7  0 2  3  2
```
