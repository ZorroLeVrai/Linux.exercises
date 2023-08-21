# Les commandes de base

Le terminal de Linux se trouve être le moyen le plus permissif de manipuler notre machine. En effet, via les lignes de commande et l'utilisation de **bash**, il est possible de réaliser des actions sur notre machine bien plus ardues à faire en se servant de l'interface graphique de base. Lorsque l'on veut ouvrir le terminal, il suffit d'appuyer sur le menu en bas à droite de notre bureau (où d'appuyer sur `Windows` ou `CMD` en fonction de si notre clavier est un clavier basé Windows / Mac) et de taper ensuite **terminal**.

La structure du terminal se trouve être de base un prompt permettant d'apprécier le nom d'utilisateur lançant le terminal ainsi que son nom d'hôte (la machine sur laquelle le terminal est lancé):

```bash
# Si l'on est logué en tant qu'utilisateur simple
utilisateur@hote:~$ 

# Si l'on est logué en tant que root
root@hote:~# 
```

### clear

Dans le cas où l'on souhaiterai nettoyer le terminal et retourner à un terminal vide, il est possible de le faire via l'utilisation de la commande suivante:

```bash
user@host:~$ clear 
```

### date

Si l'on souhaite connaître la date du jour, ainsi que l'heure et d'autres informations similaires, il est possible de le faire via la commande `date`:
```bash
user@host:~$ date
```

### ncal / cal

Si l'on veut avoir accès au calendrier, il est possible de se le voir présenté sous la forme d'un tableau via la commande `ncal / cal`:

```bash
user@host:~$ ncal

user@host:~$ cal
```

### La structure de base d'une commande

La plupart des commandes Linux sont utilisable via des arguments et / ou des options. Cette syntaxe se présente sous cette forme:

```bash
command -options arguments
```

Les arguments servent à envoyer des paramètres à notre commande. Via ces arguments, il est possible de par exemple spécifier le contexte d'une commande, comme ci dessous avec la commande `echo` qui va répéter simplement l'argument qu'on lui passe:

```bash
echo MonTexte # MonTexte
```

Via l'utilisation d'arguments, dans les commandes précédentes, il est par exemple possible d'avoir le calendrier complet d'une année ou d'un mois précis: 

```bash
ncal 2022

ncal march 2022
```

Il faut cependant faire attention à l'ordre des arguments, par exemple, la commande ci-dessous ne fonctionnera pas:

```bash
ncal 2022 march
```

A côté des arguments sont les options. Les options servent à "transformer" les commandes pour en altérer leur fonctionnement. Pour se servir d'une option et non passer un argument, il est nécéssaire d'utiliser un tiret `-` en préfixe de notre texte. Par exemple, lorsque l'on veut avoir le calendrier avec le numéro du jour basé non par sur sont rapport au mois (nombre du calendrier Julien) mais à l'année, on peut utiliser la commande `ncal -j`:

```bash
ncal -j
```

Si l'on veut, on peut cumuler plusieurs options pour notre utilisation des commandes. Pour ce faire, il est possible de les faire se suivre, soit especées, soit avec une syntaxe regroupant derrière un même tiret les différentes options concaténées: 

```bash
ncal -3 -M

ncal -3M 
```

Certaines options supportent également une syntaxe plus verbeuse, qui demande un argument en plusieurs lettres. Dans ce genre de cas, l'option sera appellée via une syntaxe usant de deux tirets, de sorte à la diférencier de la syntaxe usant de plusieurs options concaténées:

```bash
date -u

date --universal
```

Certaines options requièrent l'ajout d'un paramètre. Par exemple, pour obtenir le calendrier avec X mois avant et / ou X mois après le mois actuel, il convient d'utiliser les options `-A` et / ou `-B` mais ces options requièrent de leur côté l'ajout d'une valeur numérique. Il existe donc plusieurs syntaxes possible pour faire appel à ce genre options:

```bash
ncal -A 1 -B 2

ncal -A1 -B2
```

Lorsque l'on compte utiliser à la fois les options et les arguments, il est préférable de placer les options en premier et de donner les arguments en dernier dans un soucis de lisibilité.


---

[Retour](../README.md)