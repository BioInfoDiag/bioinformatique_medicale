# Informatique théorique 

> It's not magic, you just don't understand it yet - Ryan Oglesby 

L'informatique est omniprésente de nos jour aussi bien dans nos loisir que nos métiers. Les fondements théoriques sont pourtant rarement enseigné et l'outil est souvent utilisé comme une boite noire cachant un incroyable mystère. 
En tant que formation en bioinformatique, il nous parait importer d'aborder certain concepte théorique en science de l'information qui pourrons être utilisé come un socle pour comprendre le fonctionnement et les containtes des algorithmes utilisé en bioinformatique. 
NSans entrer dans les détails,  nous définirons dans ce chapitre la nature de l'information et comment la quantifier. Puis nous détaillerons le fonctionnement d'une machine d'une turing, l'ancêtre de nos ordinateurs, qui nous conduira à la définition des algorithmes et de leurs complexités. Nous détaillerons enfin l'architecture et les différents composants d'un ordinateur moderne.

## Comment representer l'information ? 

### Le système binaire
Dans un langage, Pour representer l'information, nous utilisons des symboles appartenant à un alphabet. En les combinant ensemble, nous formons des mots qui portent du sens.
Par exemple, notre alphabet est composé de 26 symboles avec lequels nous pouvons representer sur papier n'importe quel object du monde réel. Et le système de numération que nous utilisons est composé de 10 symboles (0,1,2,3,4,5,6,8,9) et permet de présenter n'importe quelle nombre entier naturel. 
Les ordinateurs quant à eux, utilisent 2 symboles (le 1 et le 0) appelé bit. En assemblant les bits, il est de la même façon possible de representer n'importe quoi.
De façon général, avec N bits, il y a 2^N  combinaisons et autant de signifiant possible.
Par exemple pour representer une image en noir et blanc, nous pourrions utiliser 2 bits par pixel. 

	0 : Noir 
	1 : Blanc

Avec 2 bits, nous pouvons representer 4 nuances de gris :

	00 : Noir 
	01:  Gris foncé 
	10:  Gris clair
	11 : Blanc

Avec 4 bits, nous pouvons 16 couleurs différents.

De la même façon, les nombres entiers peuvent être representer en utilisant un système binaire ou décimale. 
L'exemple suivant montre comment representer un entier compris entre 0 et 7 ( 8 = 2^3) à l'aide des deux systèmes.

Representation décimale : 
0,1,2,3,4,5,6,7

Representation binaire :  
000, 001, 010, 011, 100, 101, 110, 111 

#### octets 
Historiquement, les premiers ordinateurs manipulaient les bits par paquet de 8 qu'on appelle des octets ou bytes. 
Avec un octet, il y a donc 255 combinaisons possibles. 
Cette unité est largement utilisé notaemment dans la representation des caractères via l'encodage ASCII. 

### L'hexadecimal 
Un système courrament utilisé en informatique est le système hexadécimal composé des 16 symboles suivantes: 
0,1,2,3,4,5,6,7,8,9,A,B,C,E,F.
En effet, ce système permet de representer efficacement 1 octect en utilisant 2 symboles au lieu des 8 symboles requis par le binaire. 
Par exemple : 
11111111 = FF
10011101 = 9D 
Cette notation est particulierement utilisé dans la representation des couleurs. Une couleur est composé de 3 valeurs differents (Rouge, Vert, Bleu) comprise entre 0 et 255, soit 1 octect par couleur. 
Ainsi la couleur violette peut s'écrire : 
(00000111, 01110111, 00010111 )  soit en hexadecimal  #3D 33 C3

### L'ADN une séquence numérique 
L'ADN est une séquence numérique au même titre que l'information circulant dans votre ordinateur. A l'instar du binaire qui utilise 2 symboles, l'ADN utilise 4 symboles via les 4 nucléotides A,C,G,T pour décrire le contenu en acide-aminé d'une protéine.  
Et comme en informatique, il existe une norme de codage permettant la traduction de 3 nucléotides (ou triplets) en acide aminée. 
La comparaison est tellement vraie, qu'il existe comme avec le codage ASCII des caractères de ponctuation comme les codons stops. 
Des études recentes, ont reussi à écrire de l'information dans de l'ADN..
D'autre, on reussi à pirater un sequenceur ... 
des sociétés comme ... 

## Comment mesurer l'information ? 
### L'entropie de Shannon
L'entropie est une mesure emprunter de la thermodynamique pour quantifier l'information d'une séquence de symbole. 
Ennoncé par Claude Shannon en 1948 dans "A mathematical theory of communication", cette fonction mathématique a permis l'essort des communications 
modernes et le développement d'algorithme de compression.     
L'entropie de Shannon peut être vu comme le nombre de bit minimum, en moyenne, nécessaire pour lever une incertitude dans un contexte donné. 
Imaginons par exemple, un carnet ou vous avez noté depuis un an la météo du jour comme deux évenements ( Soleil ou Pluie ). Vivant à rennes, vous constatez alors qu'il pleut 50% du temps. Demain, il y a donc 1 chance sur 2 qu'il pleuve. Votre incertitude est de 1/2. Combien de question minimum devrez vous poser à une station météo pouvant vous répondre uniquement par oui ou par non ? Dis autrement, combien de bit la sation météo devra vous transmettre afin de lever votre incertitude. Dans ce cas précis, l'entropie noté H est de 1 bit. 1 seul bit est suffisant pour réduire votre incertitude.
Si cette fois, nous avions noté 4 évenements différents, tous équiprobable et exclusive (25% de soleil, 25% pluie, 25% neige, 25%nuageux). Combien de question minimum devrait vous poser pour lever votre incertitude qui est ici de 1/4 ? La plus part des gens répondent 3. Mais en réalité, 2 questions suffisents si on les pose correctement. 

- Neige ou soleil demain ?  NON
- nuage ? Non... Donc grele 

De façon général, l'entropie de shannon d'une suite d'évènement i , se calcul comme la somme des probabilités de chaque évenements multiplié par son log. 

$$
wow = H(X) = -\sum_i P_i \log_2(P_i)
$$


## Comment transformer de l'information ? 
### La machine de Turing 
Un ordinateur n'est rien d'autre qu'une machine transformant de l'information vers une autre information . 
Imaginons par exemple l'image en noir et blanc vu plus haut et trouvons une machine capable d'en faire le négatif. Par exemple une machine qui lirait de façon procédurale chaque bit un par un et remplacerait le 0 par un 1 et le 1 par un 0. On pourait constuire cette machine à l'aide des composant suivant:
- Un ruban de lecture composé de 1 et 0.  
- une tête de lecture et d'écriture pouvant lire et écrire sur le ruban
- Un registre d'état 
- D'une table de vérité 

Une machine de Turing universelle est une machine de Turing capable de simuler n'importe quel machine de Turing. 
La thèse de Church stipule que tout ce qui est calculable dans l'univers peut être calculer par une machine de Turing. 
Théorie de la calculabilité / algorithme / procedure ... 



![machine de Turing](https://i.gifer.com/9dzg.gif)

### Complexité algorithmique 
Complexité algorithmique 
Thèse de Church et truc 

## L'architecture d'un ordinateur

### Définitions de base

Pour les définitions de base, je vous invite à consulter wikipedia qui contient énormément d'informations (les liens sont dans les noms).

* Un **[bit](https://fr.wikipedia.org/wiki/Bit)** est l'unité d'énumération la plus simple, prenant deux valeurs (0/1 ou faux/vrai). 
* Le **[transistor](https://fr.wikipedia.org/wiki/Transistor)** est le composant électronique qui donne corps au concept de bit puisqu'il peut avoir deux états : bloqué ou conducteur. Par exemple, un processeur *i7 Haswell* contient 2,7 milliards de transistors.
* Un **[octet](https://fr.wikipedia.org/wiki/Octet)** (ou **byte**), constitué de 8 bits, est l'unité de base pour coder une information. Il est utilisé pour définir la taille des mémoires (exprimée en Kilo-octet, Mega-octet, Giga-octet...). 
* La **[mémoire](https://fr.wikipedia.org/wiki/Mémoire_(informatique))** (vive, morte, cache, etc) peut être vue comme une suite d'octets posés les uns à côté des autres. On parlera de **tableau** (ou **array**) à une dimension dans lequel chaque case possède un numéro (son **[adresse](https://fr.wikipedia.org/wiki/Adressage_mémoire)**) et un contenu (la **valeur** de l'octet).

### Le processeur

Le **[processeur](https://fr.wikipedia.org/wiki/Processeur)** est le composant qui réalise des calculs sur des octets. Il possède des petites mémoires internes sur lesquelles il peut appliquer des instructions : les **[registres](https://fr.wikipedia.org/wiki/Processeur#Fonctionnement)**. La taille des registres défini le *type* de processeur : si les registres font 1 octet, on parlera de système 8 bits (comme les premières Nintendo) ; si les registres font 8 octet, on parlera de système 64 bits (comme les processeurs actuels).

![Processeur](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Micro-processeur.JPG/320px-Micro-processeur.JPG)

Le processeur possède également une **unité de contrôle**, qui organise la distribution des instructions à effectuer et une **horloge**, qui permet de synchroniser les instructions. La vitesse d'horloge s'exprime en **hertz** (Gigahertz pour les processeurs actuels). Pour simplifier, on peut considérer qu'à chaque *bip* de l'horloge, le processeur effectue une opération sur ses registres (attention, ce n'est pas si simple).

La **vitesse** de traitement d'un processeur s'exprime par le nombre d'instructions qu'il est capable d'effectuer par seconde. On pourrait croire que cette vitesse est directement lié à la vitesse de l'horloge et au nombre de registres mais c'est plus compliqué qu'il n'y paraît. 

En effet, les processeurs modernes embarquent généralement la possibilité de *vectoriser* les calculs. Par exemple, si vous avez la même opération à effectuer sur toutes les cases d'un tableau, le processeur pourra toutes les calculer en un seul *bip* d'horloge. Cette capacité est intégrée dans beaucoup de langages pour l'analyse de données comme Python (Pandas), R, Julia, etc. Il ne faut pas négliger la vectorisation qui permet d'accélérer drastiquement les calculs (on peut passer de 5h de calcul à moins d'une minute).

### La mémoire vive

Je vous conseille la lecture de [What every programmer should know about memory](https://www.akkadia.org/drepper/cpumemory.pdf). Datant de 2007 mais toujours d'actualité, ce document très technique explique les concepts clés des communications entre CPU, RAM, Disque, bref tout ce qui se passe dans les mémoires de l'ordinateur. Même si vous ne comprenez pas tout, il me semble important de l'avoir lu au moins une fois pour votre culture générale en informatique.

![barrette de ram](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6e/Atari_STE_256kB_RAM_1.jpg/320px-Atari_STE_256kB_RAM_1.jpg)

La mémoire vive (ou RAM pour Random Access Memory) est basée sur un élément physique que vous avez sans doute rencontré : la barrette de RAM. Il s'agit d'un circuit électronique sur lequel sont soudés des composants qui permettent de stocker des octets tant qu'ils sont alimentés en électricité. Une fois qu'on débranche le courant, tout est effacé.

La mémoire vive a donc une certaine capacité en octets quelle ne peut pas dépasser. Aujourd'hui, les ordinateurs du commerce ont entre 4Go et 8Go de RAM de base.

La mémoire vive sert de relais entre le processeur, les disques et les autres périphériques, bref c'est le centre de communication de l'ordinateur. Lorsque vous allumez un ordinateur, le système d'exploitation (Windows, Linux, MacOs...) est d'abord chargé dans la mémoire vive pour pouvoir s'exécuter. Ensuite, dès que vous allez chercher des fichiers ou que vous lancez une application, un bout de la mémoire vive est dédié à cette tâche.

### Les disques durs

## Les languages de programmation 
### Les languages interprété 
### Les languages compilées
