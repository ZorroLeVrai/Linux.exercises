# Travailler avec le contenu de Fichiers

Lorsque l'on veut manipuler les fichiers, il est intéressant de pouvoir les visionner dans un terminal. Pour ce faire, au lieu d'ouvrir l'éditeur de texte **nano**, il est possible de nous servir de la commande `cat` dans le but d'afficher le texte dans le terminal directement:

```bash
cat nom_fichier.extension
```

Si l'on utilise cette commande en offrant en argument deux fichiers, alors on observera la concaténation des deux contenus les uns au dessous des autres:

```bash
cat fichierA.ext fichierB.ext
```

### tac / rev

Une autre commande, `tac`, propose le même fonctionnement que **cat** mais l'ordre de la concaténation se verra inverser. De la sorte, il est possible d'avoir un résultat différent dans le but où l'on souhaite par la suite sauvegarder ce résultat dans un nouveau fichier.

A côté de **cat** et de **tac**, il existe également la commande `rev` qui va garder l'ordre des lignes que proposait **cat** mais inverse de son côté l'ordre des lettres, on aura ainsi un rendu en mirroir de nos fichiers.

### less

La commande `less` permet de parcourir un fichier de façon à pouvoir au moyen des flèches directionnelles scroller dans la hauteur de notre terminal pour observer le contenu du fichier page par page de la même façon que lorsque l'on observe le manuel.

```bash
less nom_fichier.extension
```

Il est du coup possible de faire une recherche d'occurence via l'utilisation de la touche `/` suivie d'une entrée utilisateur. Pour quitter cette interface, il faut utiliser la touche `q`.

### head / tail

Si l'on souhaite n'avoir que le début ou la fin d'un fichier, alors il est possible de se servir de la commande `head` ou de la commande `tail`. Ces deux commandes vont par défaut ne proposer que les 10 premières / dernières lignes d'un fichier en visionnage. 

```bash
head nom_fichier.txt

tail nom_fichier.txt
```

Via l'utilisation de l'option `-n` suivie d'un nombre, il est possible de spécifier que l'on veut plus ou moins de lignes que la valeur par défaut (10 lignes). Il est également possible de mettre directement le nombre en tant qu'option, ou alors de se servir de l'option `-c` pour que ce nombre soit un nombre de bytes:

```bash
head -n 15 nom_fichier.txt

tail -5 nom_fichier.txt

head -c 8 test.txt
```

Si notre but est de suivre l'évolution d'un fichier, il existe également l'option `-f`. Cette option est particulièrement utile si l'on veut pouvoir voir par exemple l'évolution d'un fichier de logs, les informations se voyant être ajoutée au fur et à mesure dans le terminal, qui restera en attente de changements jusqu'à annulation du suivi (**CTRL+C**):

```bash
tail -f logs.txt
```

### wc

Si l'on veut connaitre le nombre de mots dans notre fichier, il est possible de le savoir facilement via la commande `wc`. Cette commande va offrir à l'utilisateur trois nombres: Le nombre de lignes (de caractère **\n**), le nombre de mots et le nombre de bytes.

```bash
wc nom_fichier.txt
```

### sort

Si l'on veut trier les lignes d'un fichier, il est possible de le faire via la commande `sort`. De base, le tri se ferra de façon alphabéthique mais les lettres majuscules ne seront pas séparées des lettres minuscules, elles seront simplement après les minuscules pour chaque lettre indépendamment (a A, b B, etc...).

```bash
sort test.txt
```

Si l'on est dans le besoin de trier des nombres, alors il nous faut utiliser une option: `-n` pour que ce tri soit de type numérique. Si l'on ne veut pas avoir les duplicats, il est possible de trier de façon unique via l'option `-u`.

Dans le cas où notre fichier possède une structure particulière, par exemple chaque ligne comporte une colonne "prénom" et une colonne "nom de famille", alors il est possible de spécifier à notre tri comment il doit se faire et quelle colonne trier en priorité. Pour ce faire, il nous faut utiliser l'option `-k` suivie du numéro de la colonne: 

```bash
sort -k 5 test.txt

sort -k5 test.txt
```

---

[Retour](../README.md)