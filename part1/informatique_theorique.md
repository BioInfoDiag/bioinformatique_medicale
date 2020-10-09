# Informatique théorique 

## Comment representer l'information ? 

### Le système binaire

Dans un langage, Pour representer l'information, nous utilisons des symboles. En les combinant ensemble nous pouvons leurs donner du sens.  
Par exemple, notre alphabet est composé de 26 symboles pour representer des mots. Et le système de numération que nous utilisons est composé de 10 symboles (0,1,2,3,4,5,6,8,9) pour représenter n'importe quelle nombre entier naturel. 
Les ordinateurs quant à eux, utilisent 2 symboles (le 1 et le 0), appelé bit, pour representer n'importe quoi.
Par exemple pour representer 4 couleurs, un ordinateur pourrait utiliser une combinaison de 2 bits:

	00 : Noir 
	01:  Gris foncé 
	10:  Gris clair
	11 : Blanc


De façon général, avec N bits, nous pouvons representer 2^N choses différentes. 

La table associant les bits à leurs signifiant est appelé une norme de codage. 
Cette norme est définie dans la specification du format d'un fichier informatique. Tous vos fichiers, que ce soit des vidéos, des images ou du texte sont representés de façon binaire en utilisant des normes spécifiques.
Les ordinateurs actuels ne manipulent pas directement les bits. Mais plutôt des groupes de 8 bits appelé octets (ou bytes en anglais).

### L'encodage ASCII 
L'encodage ASCII est une norme de codage pour définir les caractères alpha-numériques. Ils sont définis sur un octet et permettent de representer 128 caractères. Nous verrons plus tard, que cet encodage est utilisé astucieusement pour définir la qualité de séquençage. 

### L'ADN une séquence numérique 
L'ADN est une séquence numérique au même titre que l'information circulant dans votre ordinateur. A l'instar du binaire qui utilise 2 symboles, l'ADN utilise 4 symboles via les 4 nucléotides A,C,G,T pour décrire le contenu en acide-aminé d'une protéine.  
Et comme en informatique, il existe une norme de codage permettant la traduction de 3 nucléotides (ou triplets) en acide aminée. 
La comparaison est tellement vraie, qu'il existe comme avec le codage ASCII des caractères de ponctuation comme les codons stops. 
Des études recentes, ont reussi à écrire de l'information dans de l'ADN..
D'autre, on reussi à pirater un sequenceur ... 
des sociétés comme ... 

## Comment mesurer l'information ? 
### L'entropie de Shannon
Claude shannon est ... 
Imaginez un phare .... 
L'information dépend du contexte ....  

## Comment transformer de l'information ? 
### La machine de Turing 

Une machine de Turing fonctionne .... 

### Complexité algorithmique 
Complexité algorithmique 
Thèse de Church et truc 

## L'architecture d'un ordinateur

### Définitions de base

Pour les définitions de base, je vous ivite à consulter wikipedia qui contient énormément d'informations (les liens sont dans les noms).

* Un **[bit](https://fr.wikipedia.org/wiki/Bit)** est l'unité d'énumération la plus simple, prenant deux valeurs (0/1 ou faux/vrai). 
* Le **[transistor](https://fr.wikipedia.org/wiki/Transistor)** est le composant électronique qui donne corps au concept de bit puisqu'il peut avoir deux états : bloqué ou conducteur. Par exemple, un processeur *i7 Haswell* contient 2,7 milliards de transistors.
* Un **[octet](https://fr.wikipedia.org/wiki/Octet)** (ou **byte**), constitué de 8 bits, est l'unité de base pour coder une information. Il est utilisé pour définir la taille des mémoires (exprimée en Kilo-octet, Mega-octet, Giga-octet...). 
* La **[mémoire](https://fr.wikipedia.org/wiki/Mémoire_(informatique))** (vive, morte, cache, etc) peut être vue comme une suite d'octets posés les uns à côté des autres. On parlera de **tableau** (ou **array**) à une dimension dans lequel chaque case possède un numéro (son **[adresse](https://fr.wikipedia.org/wiki/Adressage_mémoire)**) et un contenu (la **valeur** de l'octet).

### Le processeur

Le **[processeur](https://fr.wikipedia.org/wiki/Processeur)** est le composant qui réalise des calculs sur des octets. Il possède des petites mémoires internes sur lesquelles il peut appliquer des instructions : les **[registres](https://fr.wikipedia.org/wiki/Processeur#Fonctionnement)**. La taille des registres défini le *type* de processeur : si les registres font 1 octet, on parlera de système 8 bits (comme les premières Nintendo) ; si les registres font 8 octet, on parlera de système 64 bits (comme les processeurs actuels).

Le processeur possède également une **unité de contrôle**, qui organise la distribution des instructions à effectuer et une **horloge**, qui permet de synchroniser les instructions. La vitesse d'horloge s'exprime en **hertz** (Gigahertz pour les processeurs actuels). Pour simplifier, on peut considérer qu'à chaque *bip* de l'horloge, le processeur effectue une opération sur ses registres (attention, ce n'est pas si simple).

La **vitesse** de traitement d'un processeur s'exprime par le nombre d'instructions qu'il est capable d'effectuer par seconde. On pourrait croire que cette vitesse est directement lié à la vitesse de l'horloge et au nombre de registres mais c'est plus compliqué qu'il n'y paraît. 

En effet, les processeurs modernes embarquent généralement la possibilité de *vectoriser* les calculs. Par exemple, si vous avez la même opération à effectuer sur toutes les cases d'un tableau, le processeur pourra toutes les calculer en un seul *bip* d'horloge. Cette capacité est intégrée dans beaucoup de langages pour l'analyse de données comme Python (Pandas), R, Julia, etc. Il ne faut pas négliger la vectorisation qui permet d'accélérer drastiquement les calculs (on peut passer de 5h de calcul à moins d'une minute).

### La mémoire vive

Je vous conseille la lecture de [What every programmer should know about memory](https://www.akkadia.org/drepper/cpumemory.pdf). Datant de 2007 mais toujours d'actualité, ce document très technique explique les concepts clés des communications entre CPU, RAM, Disque, bref tout ce qui se passe dans les mémoires de l'ordinateur. Même si vous ne comprenez pas tout, il me semble important de l'avoir lu au moins une fois pour votre culture générale en informatique.

La mémoire vive (ou RAM pour Random Access Memory) est basée sur un élément physique que vous avez sans doute rencontré : la barrette de RAM. Il s'agit d'un circuit électronique sur lequel sont soudés des composants qui permettent de stocker des octets tant qu'ils sont alimentés en électricité. Une fois qu'on débranche le courant, tout est effacé.

La mémoire vive a donc une certaine capacité en octets quelle ne peut pas dépasser. Aujourd'hui, les ordinateurs du commerce ont entre 4Go et 8Go de RAM de base.

La mémoire vive sert de relais entre le processeur, les disques et les autres périphériques, bref c'est le centre de communication de l'ordinateur. Lorsque vous allumez un ordinateur, le système d'exploitation (Windows, Linux, MacOs...) est d'abord chargé dans la mémoire vive pour pouvoir s'exécuter. Ensuite, dès que vous allez chercher des fichiers ou que vous lancez une application, un bout de la mémoire vive est dédié à cette tâche.

### Les disques durs

## Les languages de programmation 
### Les languages interprété 
### Les languages compilées