Introduction à la plateforme GitHub
================
zcoulibali
2019-04-05

Petites astuces
---------------

Le YAML (ci-dessus), c'est l'information qui permettra d'exporter le document.

Mettre du texte en *italique*.

Ce texte est en **gras**.

L'ordre des titres selon le nombre de carrés.

Texte en `largeur fixe`.

Insérrer un bloc de code `ctrl+alt+i`.

Insérrer une équation seule, l'encadrer par 2$ avant et 2$ après. Dans un paragraphe, seulement par un $. Les équation utilise le `Latin`:

$$ \\alpha = \\frac{a}{b^2} $$

L'Équation dans le paragraphe est *c*<sup>2</sup> = *a*<sup>2</sup> + *b*<sup>3</sup> et c'est même très beau à voir. La racine carrée est donc $\\sqrt{a^2 + b^3}$.

-   `{r, filtre-outliers}` donne le nom `filtre-outliers` au bloc de code, qui permet nommément de nommer les images créer dans le bloc de code.

-   `{r, eval = FALSE, include = FALSE}` permet d’activer (`TRUE`, valeur par défaut) ou de désactiver (`FALSE`) le calcul de la cellule, puis inclure ou ne pas inclure ...

-   `{r, echo = FALSE}` permet de n’afficher que la sortie de la cellule de code en n’affichant pas le code, par exemple un graphique ou le sommaire d’une régression.

-   `{r, results = FALSE}` permet de n’afficher que le code, mais pas la sortie.

-   `{r, warning = FALSE, message = FALSE, error = FALSE}` n’affichera pas les avertissements, les messages automatiques et les messages d’erreur.

-   `{r, fig.width = 10, fig.height = 5, fig.align = "center"}` affichera les graphiques dans les dimensions voulues, alignée au centre (`"center"`), à gauche (`"left"`) ou à droite (`"right"`).

On peut également exécuter rapidement du code sur une ligne avec la formulation `r`, par exemple la moyenne des nombres `\r a<-round(runif(4, 0, 10)); a` est de `\r mean(a)`, en enlevant les `\` devant les r (ajoutées artificiellement pour éviter que le code soit calculé) sera la moyenne des nombres 7, 2, 2, 8 est de 4.75

La moyenne des nombres 3, 1, 9, 5 est de 4.5.

Charger le fichier de travail
-----------------------------

``` r
library(tidyverse)
```

    ## -- Attaching packages ----------------------------------------------------- tidyverse 1.2.1 --

    ## v ggplot2 3.1.0     v purrr   0.2.5
    ## v tibble  1.4.2     v dplyr   0.7.8
    ## v tidyr   0.8.2     v stringr 1.3.1
    ## v readr   1.3.1     v forcats 0.3.0

    ## -- Conflicts -------------------------------------------------------- tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
hawai <- read_csv("hawai.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   time = col_double(),
    ##   CO2 = col_double()
    ## )

Directives de l’évaluation
--------------------------

Les données du fichier `hawai.csv` comprennent les moyennes des mesures mensuelles de **CO2 atmosphérique** en ppm-volume collectées au Mauna Loa Observatory à Hawaii de mars 1958 à juillet 2001, inclusivement.

Trvail à faire
--------------

Votre travail consiste à :

1.  créer une série temporelle du CO2 à partir des données de hawai.csv
2.  séparer la série en parties d'entraînement (environ 70% des données) et en partie test
3.  créer un modèle ETS sur les données d'entraînement, puis projeter la prévision de CO2 atmosphérique pour comparer aux données test
4.  effectuer une analyse des résidus
5.  commenter: le modèle est-il fiable ? Comment pourrait-il être amélioré ?

Vous devez me remettre un lien vers un répertoire git de votre choix (GitHub, GitLab, etc.) comprenant un code reproductible de votre démarche en format R-markdown.
