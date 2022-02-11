# Cap. 15 - Dados geoespaciais no R {-}

**15.1**
Importe o limite dos estados brasileiros no formato **sf** com o nome **br**. Para isso, use a função **ne_states** do pacote **rnaturalearth**. Crie um mapa simples cinza utilizando a função **plot()**, selecionando a coluna **geometry** com o operador **$** e com os argumentos **axes** e **graticule** verdadeiros.

 Solução:

```r
library(rnaturalearth)
br <- rnaturalearth::ne_states(country = "Brazil", returnclass = "sf")
plot(br$geometry, col = "gray", axes = TRUE, graticule = TRUE)
```

<img src="cap_15_files/figure-html/unnamed-chunk-1-1.png" width="672" />

**15.2**
Dados vetoriais podem ser criados com diversos erros de topologia, e.g., sobreposição de linhas ou polígonos ou buracos. Algumas funções exigem que os objetos vetoriais aos quais são atribuídos esses dados não possuam esses erros para que o algoritmo funcione. Para verificar se há erros, podemos usar a função **st_is_valid()** do pacote **sf**. Há diversas forma de correções desses erros, mas vamos usar uma correção simples do R, com a função **st_make_valid()**. Vamos fazer essa correção para o **br** importado anteriormente e atribuindo ao objeto **br_valid**. Podemos conferir para saber se há erros e fazer um plot.

 Solução:

```r
library(sf)

sf::st_is_valid(br)
#>  [1]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
#> [10]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
#> [19]  TRUE  TRUE  TRUE  TRUE  TRUE FALSE  TRUE  TRUE  TRUE

br_valid <- sf::st_make_valid(br)
sf::st_is_valid(br_valid)
#>  [1] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
#> [12] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
#> [23] TRUE TRUE TRUE TRUE TRUE

plot(br_valid$geometry, col = "gray", axes = TRUE, graticule = TRUE)
```

<img src="cap_15_files/figure-html/unnamed-chunk-2-1.png" width="672" />

**15.3**
Crie um objeto RasterLayer vazio chamado **ra** com reSolução: de 5º (~600 km). Atribua um sistema de referência de coordendas com o código **4326**. Atribua valores aleatórios de uma distribuição normal e plote o mesmo.

 Solução:

```r
library(raster)
ra <- raster::raster(res = 5, crs = 4326)
raster::values(ra) <- rnorm(raster::ncell(ra))
plot(ra)
```

<img src="cap_15_files/figure-html/unnamed-chunk-3-1.png" width="672" />

**15.4**
Reprojete o limite dos estados brasileiros do exercício anterior para o CRS SIRGAS 2000/Brazil Polyconic, utilizando o código EPSG:5880 e chamando de **br_poly**. Faça um mapa simples como no exercício 1. Atente para as curvaturas das linhas.

 Solução:

```r
library(sf)
library(rnaturalearth)

br_valid_poly <- sf::st_transform(br_valid, crs = 5880)
plot(br_valid_poly$geometry, col = "gray", axes = TRUE, graticule = TRUE)
```

<img src="cap_15_files/figure-html/unnamed-chunk-4-1.png" width="672" />

**15.5**
Utilizando a função **st_centroid** do pacote **sf**, crie um vetor chamado **br_valid_cen** que armazenará o centroide de cada estado brasileiro do objeto **br_valid** do exercício 2 e plot o resultado.

 Solução:

```r
library(sf)
library(rnaturalearth)

br_valid_poly_cen <- sf::st_centroid(br_valid_poly)

plot(br_valid_poly$geometry, col = "gray", axes = TRUE, graticule = TRUE)
plot(br_valid_poly_cen$geometry, pch = 20, add = TRUE)
```

<img src="cap_15_files/figure-html/unnamed-chunk-5-1.png" width="672" />

**15.6**
Ajuste o limite e máscara do objeto raster criado no exercício 3 para o limite do Brasil, atribuindo ao objeto **ra_br**. Depois reprojete esse raster para a mesma projeção utilizada no exercício 4 com o nome **ra_br_poly** e plote o mapa resultante.

 Solução:

```r
library(raster)

ra_br <- ra %>% 
    raster::crop(br_valid) %>% 
    raster::mask(br_valid)

ra_br_poly <- raster::projectRaster(ra_br, crs = "+init=epsg:5880")

plot(ra_br_poly)
plot(br_valid_poly$geometry, add = TRUE)
plot(br_valid_poly_cen$geometry, pch = 20, add = TRUE)
```

<img src="cap_15_files/figure-html/unnamed-chunk-6-1.png" width="672" />

**15.7**
Extraia os valores de cada pixel do raster criado no exercício 6 para os centroides dos estados do Brasil criado no exercício 5, atribuindo à coluna **val** do objeto espacial chamado **br_valid_poly_cent_ra**.

 Solução:

```r
br_valid_poly_cent_ra <- br_valid_poly_cen %>% 
    dplyr::mutate(val = raster::extract(ra_br_poly, .))
head(br_valid_poly_cent_ra$val)
#> [1]  1.0238284 -1.0381480 -0.4493325  0.3284137 -0.1762245
#> [6]  0.7180757
```

**15.8**
Crie um mapa final usando os resultados dos exercícios 4, 5 e 6. Utilize o pacote **tmap** e inclua todos os principais elementos de um mapa.

 Solução:

```r
library(tmap)

tm_shape(ra_br_poly) +
    tm_raster(title = "Raster") +
    tm_shape(br_valid_poly) +
    tm_borders() +
    tm_shape(br_valid_poly_cent_ra) +
    tm_bubbles(col = "val", size = .2, legend.col.show = FALSE) +
    tm_graticules(lines = FALSE, 
                  labels.format = list(big.mark = ""), 
                  labels.rot = c(0, 90),
                  labels.size = .7) +
    tm_compass(position = c("right", "top"), size = 2) +
    tm_scale_bar(size = 1) +
    tm_xlab("Longitude", size = 1) +
    tm_ylab("Latitude", size = 1) +
    tm_credits("CRS: SIRGAS2000/Policônica", position = c(.6, .15), size = .6) +
    tm_credits("Fonte: Natural Earth (2022)", position = c(.6, .12), size = .6) +
    tm_layout(main.title = "Estados do Brasil",
              main.title.position = c(.1, .95),
              main.title.size = 1.5,
              title.fontface = "bold",
              legend.position = c("left", "bottom"),
              legend.title.fontface = "bold")
```

<img src="cap_15_files/figure-html/unnamed-chunk-8-1.png" width="672" />
