# La théorie des probabilités
 
La théorie des probabilités fourni un outil mathématique permettant de quantifier notre incertitude par des chiffres. 
Elle est le fondement des statistiques. Comprendre ses lois et le vocabulaire associé est donc essentiel avant d'allez plus loin.
Afin d'appréhender plus facilement ce chapitre, la plus part des formules mathématique seront illustré  par un graphique et des exemples.

## Loi de probabilité

Les calculs des probabilités reposent essentiellement sur des calculs de dénombrement de l'ensemble des éventualités possible. 
Par exemple, si nous lançons un dé, l'évenement observé est 1 possibilité  parmi les 6 possibilités. On notera alors p = 1/6.
Si nous lançons 2 dés, quel est la probabilité de faire un double 6 ? 
Pour illustré ce problème, nous pouvons dessiner l'ensemble des possibilités sur l'arbre suivant et simplement compter.

DESSIN 

Un autre exercice de dénombrement, plus difficile cette fois. Quel est la probabilité de tomber sur un paquet de carte contenant 3 as en haut du paquet?

DESSIN

### Probabilité conditionnel 
Supposons que si le premier lancé de dé est un 6, alors au deuxième lancé, nous choississons un dé à 3 faces. Le deuxièmes évenement est dépendant du premier. On peut alors écrire : 

$$ p(A|B) = p(A) * p(B) $$

DESSIN

Lorsque deux variables sont indépendante, on a ....

```{note}
Le désequilibre de liaison en génétique ....
```

### Chain Rule 

### La loi de Bayes 

```{note}
Un test de dépistage covid
```

## Variable aléatoire 
On peut définir une variable aléatoire comme la mesure d'un évenement observée pouvant prendre sa valeur parmi un ensemble de possibilités..   
En pratique, il s'agit d'une suite de mesures dont chaque eventualités est associé à une probabilités décrite par sa distribution. Par exemple l'observation des faces d'un dé ou chacune est associé à la probabilité de 1/6.

```{warning}
Le sens du mot aléatoire n'est pas que le même que celui utilisé dans le langage courrant. En effet, aléatoire ne veut pas dire equiprobable. Les mesures d'un dé tombant préferentiellement sur le 6 reste une variable aléatoire mais dont la distribution n'est pas equiprobable.
```

On distingue les variables aléatoires discrêtes et continue.

### Variable discrète
Une variable aléatoire est discrète lorsque ses valeurs sont des nombre entier. Par exemple un pièce peut prendre des valeurs compris entre Pile et Face. 

$$ X \in {Pile,Face} $$

Chaque évenements peut alors être associé à une probabilité de sorte que la somme des probabibités de chaque évenement soit égale à 1. L'ensembe de ces probabilités défini une **distribution de probabilité**. Plus précisément, dans das le cas d'une variable discrête, on parler de fonction de masse.

$$ X \in {Pile,Face} $$

$$\sum p(x) = 1$$

Shema 

### Variable continue
Une variable aléatoire est dite continue, lorsque la variable est décrite par un nombre décimal. Par exemple, la taille d'un étudiant dans une classe peut prendre une valeur entre 0 et disons 2 mètre 30.     
La distribution des probabilités est appelé ici une fonction de densité dont l'intégrale entre ses bornes est de 1. 

$$ \int_{0}^{230}p(x)dx = 1 $$


### Loi de probabilité conjointe 
### Loi de probabilité marginale 

## Le bestiaire des distributions 
Paramètres , domaine, bornes 

### Loi Normale
### Loi binomiale
### Loi de Poisson
### Loi Beta 

## Estimation des paramètre
La vraissemblance 
Maximum Posteriori truc ...



