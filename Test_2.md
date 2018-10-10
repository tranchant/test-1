Introduction au logiciel R
================
Dr Mamadou Ciss
10 octobre 2018

-   [Environnement de travail](#environnement-de-travail)
    -   [Connaitre son rÃ©pertoire de travail actuel](#connaitre-son-rÃ©pertoire-de-travail-actuel)
    -   [Changer de rÃ©pertoire de travail](#changer-de-rÃ©pertoire-de-travail)
-   [Les packages sous R](#les-packages-sous-r)
    -   [Installation de package](#installation-de-package)
    -   [TÃ©lÃ©chargement de package](#tÃ©lÃ©chargement-de-package)
-   [Importation de donnÃ©es](#importation-de-donnÃ©es)
    -   [DonnÃ©es texte simple](#donnÃ©es-texte-simple)
    -   [DonnÃ©es au format CSV](#donnÃ©es-au-format-csv)
-   [ReprÃ©sentation de donnÃ©es sous R](#reprÃ©sentation-de-donnÃ©es-sous-r)
    -   [EntÃªte d'un fichier](#entÃªte-dun-fichier)
    -   [Fin d'un fichier](#fin-dun-fichier)
-   [Statistiques basiques d'une base donnÃ©es](#statistiques-basiques-dune-base-donnÃ©es)
    -   [Taille d'un fichier](#taille-dun-fichier)
    -   [Nombre de lignes d'un fichier](#nombre-de-lignes-dun-fichier)
    -   [Nombre de colonnes d'un fichier](#nombre-de-colonnes-dun-fichier)
    -   [Longueur d'un vecteur](#longueur-dun-vecteur)
    -   [Sommaire de la base de donnÃ©es](#sommaire-de-la-base-de-donnÃ©es)
    -   [Minimum d'un vecteur](#minimum-dun-vecteur)
    -   [Moyenne d'un vecteur](#moyenne-dun-vecteur)
    -   [Maximum d'un vecteur](#maximum-dun-vecteur)
    -   [Somme d'un vecteur](#somme-dun-vecteur)
    -   [Variance d'un vecteur](#variance-dun-vecteur)
    -   [Ecart-type d'un vecteur](#ecart-type-dun-vecteur)
-   [Including Plots](#including-plots)

Environnement de travail
------------------------

### Connaitre son rÃ©pertoire de travail actuel

    getwd()

### Changer de rÃ©pertoire de travail

``` r
setwd("C:/Users/hp/Google Drive/ISRA/Formation/Dispensees/R/Test_Rmarkdown")
```

Les packages sous R
-------------------

### Installation de package

    install.packages('ggplot2')

### TÃ©lÃ©chargement de package

    library('ggplot2')

Importation de donnÃ©es
----------------------

### DonnÃ©es texte simple

``` r
myfile<-read.table("pheno.txt",h=T,dec=".")
```

### DonnÃ©es au format CSV

ReprÃ©sentation de donnÃ©es sous R
--------------------------------

### EntÃªte d'un fichier

``` r
head(myfile)
```

    ##   Populations Floraison Poids_sec Nb_involucres Poids_graines
    ## 1        pop1        28         8            15          3.22
    ## 2        pop1        29        10            21          2.56
    ## 3        pop1        29         8            18          2.79
    ## 4        pop1        28        10            16          2.65
    ## 5        pop1        32         9            17          2.51
    ## 6        pop1        34         9            18          2.75

### Fin d'un fichier

``` r
tail(myfile)
```

    ##     Populations Floraison Poids_sec Nb_involucres Poids_graines
    ## 505      pop_17        23        13            17          1.91
    ## 506      pop_17        30        12             7          1.33
    ## 507      pop_17        25        11            15          1.62
    ## 508      pop_17        28         8            10          1.28
    ## 509      pop_17        27        12            16          1.23
    ## 510      pop_17        26        13            11          0.60

Statistiques basiques d'une base donnÃ©es
----------------------------------------

### Taille d'un fichier

``` r
dim(myfile)
```

    ## [1] 510   5

``` r
names(myfile)
```

    ## [1] "Populations"   "Floraison"     "Poids_sec"     "Nb_involucres"
    ## [5] "Poids_graines"

``` r
colnames(myfile)
```

    ## [1] "Populations"   "Floraison"     "Poids_sec"     "Nb_involucres"
    ## [5] "Poids_graines"

### Nombre de lignes d'un fichier

``` r
nrow(myfile)
```

    ## [1] 510

### Nombre de colonnes d'un fichier

``` r
ncol(myfile)
```

    ## [1] 5

### Longueur d'un vecteur

``` r
length(myfile$Poids_sec)
```

    ## [1] 510

### Sommaire de la base de donnÃ©es

``` r
summary(myfile)
```

    ##   Populations    Floraison       Poids_sec     Nb_involucres  
    ##  pop_10 : 30   Min.   :11.00   Min.   : 1.00   Min.   : 1.00  
    ##  pop_11 : 30   1st Qu.:21.00   1st Qu.: 9.00   1st Qu.:10.00  
    ##  pop_12 : 30   Median :25.00   Median :11.00   Median :15.00  
    ##  pop_13 : 30   Mean   :25.75   Mean   :10.95   Mean   :14.76  
    ##  pop_14 : 30   3rd Qu.:31.00   3rd Qu.:13.00   3rd Qu.:19.00  
    ##  pop_15 : 30   Max.   :41.00   Max.   :22.00   Max.   :29.00  
    ##  (Other):330                                                  
    ##  Poids_graines  
    ##  Min.   :0.420  
    ##  1st Qu.:1.742  
    ##  Median :2.300  
    ##  Mean   :2.278  
    ##  3rd Qu.:2.780  
    ##  Max.   :4.530  
    ## 

### Minimum d'un vecteur

``` r
min(myfile$Poids_graines)
```

    ## [1] 0.42

### Moyenne d'un vecteur

``` r
mean(myfile$Nb_involucres)
```

    ## [1] 14.76471

### Maximum d'un vecteur

``` r
max(myfile$Floraison)
```

    ## [1] 41

### Somme d'un vecteur

``` r
sum(myfile$Poids_graines)
```

    ## [1] 1161.93

### Variance d'un vecteur

``` r
var(myfile$Poids_graines)
```

    ## [1] 0.5224067

### Ecart-type d'un vecteur

``` r
sd(myfile$Poids_graines)
```

    ## [1] 0.7227771

Including Plots
---------------

You can also embed plots, for example:

![](test2_files/figure-markdown_github/pressure-1.png)

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.
