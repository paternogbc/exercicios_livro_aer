# Cap. 5 - Tidyverse {-}

**5.1** 
Reescreva as operações abaixo utilizando pipes `%>%`.
-   `log10(cumsum(1:100))`
-   `sum(sqrt(abs(rnorm(100))))`
-   `sum(sort(sample(1:10, 10000, rep = TRUE)))`

 Solução:

```r
library(tidyverse)
#> ── Attaching packages ─────────────────── tidyverse 1.3.1 ──
#> ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
#> ✓ tibble  3.1.6     ✓ dplyr   1.0.7
#> ✓ tidyr   1.1.4     ✓ stringr 1.4.0
#> ✓ readr   2.1.1     ✓ forcats 0.5.1
#> ── Conflicts ────────────────────── tidyverse_conflicts() ──
#> x dplyr::filter() masks stats::filter()
#> x dplyr::lag()    masks stats::lag()

1:100 %>% 
    cumsum() %>% 
    log10()
#>   [1] 0.0000000 0.4771213 0.7781513 1.0000000 1.1760913
#>   [6] 1.3222193 1.4471580 1.5563025 1.6532125 1.7403627
#>  [11] 1.8195439 1.8920946 1.9590414 2.0211893 2.0791812
#>  [16] 2.1335389 2.1846914 2.2329961 2.2787536 2.3222193
#>  [21] 2.3636120 2.4031205 2.4409091 2.4771213 2.5118834
#>  [26] 2.5453071 2.5774918 2.6085260 2.6384893 2.6674530
#>  [31] 2.6954817 2.7226339 2.7489629 2.7745170 2.7993405
#>  [36] 2.8234742 2.8469553 2.8698182 2.8920946 2.9138139
#>  [41] 2.9350032 2.9556878 2.9758911 2.9956352 3.0149403
#>  [46] 3.0338257 3.0523091 3.0704073 3.0881361 3.1055102
#>  [51] 3.1225435 3.1392492 3.1556396 3.1717265 3.1875207
#>  [56] 3.2030329 3.2182729 3.2332500 3.2479733 3.2624511
#>  [61] 3.2766915 3.2907022 3.3044905 3.3180633 3.3314273
#>  [66] 3.3445887 3.3575537 3.3703280 3.3829171 3.3953264
#>  [71] 3.4075608 3.4196254 3.4315246 3.4432630 3.4548449
#>  [76] 3.4662743 3.4775553 3.4886917 3.4996871 3.5105450
#>  [81] 3.5212689 3.5318619 3.5423274 3.5526682 3.5628874
#>  [86] 3.5729877 3.5829719 3.5928427 3.6026025 3.6122539
#>  [91] 3.6217992 3.6312408 3.6405808 3.6498215 3.6589648
#>  [96] 3.6680130 3.6769678 3.6858313 3.6946052 3.7032914

rnorm(100) %>% 
    abs() %>% 
    sqrt() %>% 
    sum()
#> [1] 78.93276

sample(1:10, 10000, rep = TRUE) %>% 
    sort() %>% 
    sum()
#> [1] 54747
```

**5.2** 
Use a função `download.file()` e `unzip()` para baixar e extrair o arquivo do data paper de médios e grandes mamíferos: [ATLANTIC MAMMALS](https://doi.org/10.1002/ecy.2785). Em seguinda, importe para o R, usando a função `readr::read_csv()`.

 Solução:

```r
library(tidyverse)
download.file(url = "https://esajournals.onlinelibrary.wiley.com/action/downloadSupplement?doi=10.1002%2Fecy.2785&file=ecy2785-sup-0001-DataS1.zip", 
              destfile = "ecy2785-sup-0001-DataS1.zip", mode = "wb")

unzip("ecy2785-sup-0001-DataS1.zip")

dp_lm <- readr::read_csv("ATLANTIC_MAMMAL_MID_LARGE _assemblages_and_sites.csv")
#> Warning: One or more parsing issues, see `problems()` for
#> details
#> Rows: 4680 Columns: 40
#> ── Column specification ────────────────────────────────────
#> Delimiter: ","
#> chr (27): ID, Country, State, Municipality, Study_locati...
#> dbl (11): Reference_paper_number, Publication_year, Year...
#> 
#> ℹ Use `spec()` to retrieve the full column specification for this data.
#> ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
```

**5.3**
Use a função `tibble::glimpse()` para ter uma noção geral dos dados importados no item anterior.

 Solução:

```r
library(tidyverse)
dplyr::glimpse(dp_lm)
#> Rows: 4,680
#> Columns: 40
#> $ ID                     <chr> "AML01", "AML01", "AML01", …
#> $ Reference_paper_number <dbl> 1, 1, 1, 1, 1, 1, 1, 1, 1, …
#> $ Country                <chr> "Brazil", "Brazil", "Brazil…
#> $ State                  <chr> "rio_grande_do_sul", "rio_g…
#> $ Municipality           <chr> "Sinimbu", "Sinimbu", "Sini…
#> $ Study_location         <chr> "Reserva Particular do Patr…
#> $ Latitude               <dbl> -29.38333, -29.38333, -29.3…
#> $ Longitude              <dbl> -52.53333, -52.53333, -52.5…
#> $ Precision              <chr> "not_precise", "not_precise…
#> $ Size_ha                <chr> "221", "221", "221", "221",…
#> $ Temperature            <chr> "18", "18", "18", "18", "18…
#> $ Altitude               <chr> "150-650", "150-650", "150-…
#> $ Annual_rainfall        <chr> NA, NA, NA, NA, NA, NA, NA,…
#> $ Vegetation_type        <chr> "Semideciduous forest", "Se…
#> $ Protect_area           <chr> "yes", "yes", "yes", "yes",…
#> $ Matrix                 <chr> NA, NA, NA, NA, NA, NA, NA,…
#> $ Reference              <chr> "Abreu-Junior, E.F. and Koh…
#> $ Publication_year       <dbl> 2009, 2009, 2009, 2009, 200…
#> $ Type_of_publication    <chr> "Article", "Article", "Arti…
#> $ Month_start            <chr> "November", "November", "No…
#> $ Year_start             <dbl> 2007, 2007, 2007, 2007, 200…
#> $ Month_finish           <chr> "April", "April", "April", …
#> $ Year_finish            <dbl> 2009, 2009, 2009, 2009, 200…
#> $ Total_of_months        <dbl> 6, 6, 6, 6, 6, 6, 6, 6, 6, …
#> $ Sampling_habitat       <chr> "Interior", "Interior", "In…
#> $ Effort                 <dbl> 109.00, 109.00, 109.00, 109…
#> $ Effort_method          <chr> "camera_days", "camera_days…
#> $ Method                 <chr> "mixed_method", "mixed_meth…
#> $ Order                  <chr> "Carnivora", "Rodentia", "C…
#> $ Genus_on_paper         <chr> "Cerdocyon", "Cuniculus", "…
#> $ Species_name_on_paper  <chr> "Cerdocyon thous", "Cunicul…
#> $ Actual_species_Name    <chr> "Cerdocyon thous", "Cunicul…
#> $ Number_of_record       <chr> NA, NA, NA, NA, NA, NA, NA,…
#> $ `Density(groups/km2)`  <dbl> NA, NA, NA, NA, NA, NA, NA,…
#> $ `Density(ind/km2)`     <chr> NA, NA, NA, NA, NA, NA, NA,…
#> $ `Density(ind/km10)`    <dbl> NA, NA, NA, NA, NA, NA, NA,…
#> $ `Abundance(%)`         <dbl> NA, NA, NA, NA, NA, NA, NA,…
#> $ Abudance_relative      <dbl> NA, NA, NA, NA, NA, NA, NA,…
#> $ `Abundance(10/km)`     <dbl> NA, NA, NA, NA, NA, NA, NA,…
#> $ Voucher_Specimens      <chr> NA, NA, NA, NA, NA, NA, NA,…
```

**5.4**
Compare os dados de penguins (*palmerpenguins::penguins_raw* e *palmerpenguins::penguins*). Monte uma série de funções dos pacotes *tidyr* e `dplyr` para limpar os dados e fazer com que o primeiro dado seja igual ao segundo.

 Solução:

```r
library(tidyverse)
library(palmerpenguins)

penguins_raw
#> # A tibble: 344 × 17
#>    studyName `Sample Number` Species    Region Island Stage 
#>    <chr>               <dbl> <chr>      <chr>  <chr>  <chr> 
#>  1 PAL0708                 1 Adelie Pe… Anvers Torge… Adult…
#>  2 PAL0708                 2 Adelie Pe… Anvers Torge… Adult…
#>  3 PAL0708                 3 Adelie Pe… Anvers Torge… Adult…
#>  4 PAL0708                 4 Adelie Pe… Anvers Torge… Adult…
#>  5 PAL0708                 5 Adelie Pe… Anvers Torge… Adult…
#>  6 PAL0708                 6 Adelie Pe… Anvers Torge… Adult…
#>  7 PAL0708                 7 Adelie Pe… Anvers Torge… Adult…
#>  8 PAL0708                 8 Adelie Pe… Anvers Torge… Adult…
#>  9 PAL0708                 9 Adelie Pe… Anvers Torge… Adult…
#> 10 PAL0708                10 Adelie Pe… Anvers Torge… Adult…
#> # … with 334 more rows, and 11 more variables:
#> #   Individual ID <chr>, Clutch Completion <chr>,
#> #   Date Egg <date>, Culmen Length (mm) <dbl>,
#> #   Culmen Depth (mm) <dbl>, Flipper Length (mm) <dbl>,
#> #   Body Mass (g) <dbl>, Sex <chr>,
#> #   Delta 15 N (o/oo) <dbl>, Delta 13 C (o/oo) <dbl>,
#> #   Comments <chr>
penguins
#> # A tibble: 344 × 8
#>    species island    bill_length_mm bill_depth_mm
#>    <fct>   <fct>              <dbl>         <dbl>
#>  1 Adelie  Torgersen           39.1          18.7
#>  2 Adelie  Torgersen           39.5          17.4
#>  3 Adelie  Torgersen           40.3          18  
#>  4 Adelie  Torgersen           NA            NA  
#>  5 Adelie  Torgersen           36.7          19.3
#>  6 Adelie  Torgersen           39.3          20.6
#>  7 Adelie  Torgersen           38.9          17.8
#>  8 Adelie  Torgersen           39.2          19.6
#>  9 Adelie  Torgersen           34.1          18.1
#> 10 Adelie  Torgersen           42            20.2
#> # … with 334 more rows, and 4 more variables:
#> #   flipper_length_mm <int>, body_mass_g <int>, sex <fct>,
#> #   year <int>

penguins_raw %>% 
    dplyr::select(Species, Island, `Culmen Length (mm)`:Sex, `Date Egg`) %>% 
    dplyr::rename(species = Species,
                  island = Island,
                  bill_length_mm = `Culmen Length (mm)`,
                  bill_depth_mm = `Culmen Depth (mm)`,
                  flipper_length_mm = `Flipper Length (mm)`,
                  body_mass_g = `Body Mass (g)`,
                  sex = Sex,
                  year = `Date Egg`) %>% 
    tidyr::separate(species, c("species", NA, NA, NA, NA)) %>% 
    dplyr::mutate(sex = stringr::str_to_lower(sex),
                  year = lubridate::year(year))
#> # A tibble: 344 × 8
#>    species island    bill_length_mm bill_depth_mm
#>    <chr>   <chr>              <dbl>         <dbl>
#>  1 Adelie  Torgersen           39.1          18.7
#>  2 Adelie  Torgersen           39.5          17.4
#>  3 Adelie  Torgersen           40.3          18  
#>  4 Adelie  Torgersen           NA            NA  
#>  5 Adelie  Torgersen           36.7          19.3
#>  6 Adelie  Torgersen           39.3          20.6
#>  7 Adelie  Torgersen           38.9          17.8
#>  8 Adelie  Torgersen           39.2          19.6
#>  9 Adelie  Torgersen           34.1          18.1
#> 10 Adelie  Torgersen           42            20.2
#> # … with 334 more rows, and 4 more variables:
#> #   flipper_length_mm <dbl>, body_mass_g <dbl>, sex <chr>,
#> #   year <dbl>
```

**5.5**
Usando os dados de penguins (*palmerpenguins::penguins*), calcule a correlação de Pearson entre comprimento e profundidade do bico para cada espécie e para todas as espécies. Compare os índices de correlação para exemplificar o Paradoxo de Simpsom.

 Solução:

```r
library(tidyverse)
library(palmerpenguins)

cor(penguins$bill_length_mm, penguins$bill_depth_mm, use = "na.or.complete")
#> [1] -0.2350529

penguins %>%
    dplyr::group_split(species) %>% 
    purrr::map(~cor(.x$bill_length_mm, .x$bill_depth_mm, use = "na.or.complete"))
#> [[1]]
#> [1] 0.3914917
#> 
#> [[2]]
#> [1] 0.6535362
#> 
#> [[3]]
#> [1] 0.6433839
```

**5.6**
Oficialmente a pandemia de COVID-19 começou no Brasil com o primeiro caso no dia 26 de fevereiro de 2020. Calcule quantos anos, meses e dias se passou desde então. Calcule também quanto tempo se passou até você ser vacinado.

 Solução:

```r
covid_inicio_br <- lubridate::dmy("26-02-2020")
vacina <- lubridate::dmy("20-07-2021")

intervalo_covid <- lubridate::interval(covid_inicio_br, lubridate::today())
intervalo_vacina <- lubridate::interval(covid_inicio_br, vacina)

lubridate::as.period(intervalo_covid)
#> [1] "1y 11m 16d 0H 0M 0S"
lubridate::as.period(intervalo_vacina)
#> [1] "1y 4m 24d 0H 0M 0S"
```
