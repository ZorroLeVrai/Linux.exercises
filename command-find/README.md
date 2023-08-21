# Trouver des choses avec Find

La première façon de trouver des choses sur notre machine est via l'utilisation de la commande `locate` qui doit généralement être installée pour être accessible. Se servant d'une base de données relativement à jour en permanence et référençant nos fichiers, cette commande fonctionne du coup très rapidement. A contrario, cette base de données n'étant pas complètement à jour, il se peut qu'il lui manque des informations. Son utilisation est assez simple, il suffit de passer en argument ce que l'on cherche: 

```bash
locate nom_fichier
```

Cette commande est sensible à la casse, mais va placer un wildcard autour du début et de la fin du chemin demandé. Certaines options sont également disponible. Par exemple, via l'option `-e`, la commande va chercher des éléments existant au moment où la commande est lancée. Avec l'option `-i`, la casse se voit être ignorée, alors qu'avec l'option `-l` on peut choisir de limiter le nombre d'éléments que **locate** va devoir trouver.

### find

A côté de la commande **locate** se trouve la commande `find`. Cette commande est bien plus puissante que son homologue mais demande une connaissance plus étendue de son fonctionnement pour être utilisée à son plein potentiel. De base, elle va afficher tous les fichiers et dossiers se trouvant actuellement dans le dossier courant. Si on lui indique un emplacement, elle va réaliser le même processus à cet emplacement: 

```bash
find 

find my_folder/
```

Pour réaliser une recherche par nom, il est nécessaire de passer entre guillemets ce que l'on cherche après avoir ajouté l'option `-name` à notre commande. Si l'on préfère une approche non sensible à la casse, l'option `-iname` est également disponible. Pour n'obtenir que les fichiers, il est possible de spécifier le type recherché via l'option `-type f`

Dans le cas où l'on souhaiterait trouver un fichier dont la taille est spécifique, il est possible de le faire via l'utilisation de l'option `-size` suivi d'une valeur. Plusieurs possibilités s'offrent alors à nous: 

```bash
find -size 20k # Taille égale à 20Ko

find -size -1G # Taille inférieure à 1Go

find -size +20M # Taille supérieure à 20Mo
```

On peut également faire une recherche par possesseur du ou des fichiers. Pour ce faire, il faut utiliser l'option `-user` suivi du nom de l'utilisateur dont nous souhaitons trouver les fichiers possédés. Enfin, pour chercher les dossiers vides, il est possible d'utiliser l'option `-empty`.

### Timestamps

Si l'on veut, il est possible de voir trois méta-données de type **timestamps** pour les fichiers. Pour ce faire, trois commandes sont à notre disposition **mtime**, **ctime** et **atime**. 
- `mtime`: Sert à voir la date et l'heure de la dernière modification du fichier (`ls -l`)
- `ctime`: Sert à voir la date et l'heure du dernier changement concernant un fichier. Cela prend en compte la modification de son contenu mais aussi si l'on change son nom, qu'on le déplace, etc... (`ls -lc`)
- `atime`: Sert à voir la date et l'heure du dernier accès du fichier, comme par exemple si le fichier est envoyé à la commande **cat** (`ls -lu`). 

Pour se servir de la commande **find** en compagnie des timestamps, il va falloir nous servir d'options supplémentaires. Ces options sont très nombreuses, mais sont facilement regroupables par objectif: 
- `amin`, `cmin`, `mmin`: Pour pouvoir spécifier un temps supérieur, inférieur ou égal à X minutes (accessed, changed, used)
- `anewer`, `cnewer`, `mnewer`: Se base sur un système de lien de réference (accessed, changed, used)
- `atime`, `ctime`, `mtime`: Pour pouvoir spécifier un temps supérieur, inférieur ou égal à X jours (accessed, changed, used)

### Les opérateurs logiques

Lorsque l'on se sert de la commande **find** il est possible de se servir d'opérateurs logiques pour rendre notre sélection ou notre recherche plus complexe. De la sorte, il est possible de cumuler les conditions de recherche. Ces opérateurs sont accessible via des options `-and`, `-or` et `-not`. Si l'on utilise plusieurs options, de base, l'opérateur **AND** est implicite:

```bash
find -name "*chick*" -or -name "*kitty*"

find -type f (-and) -not "*.mp3"
```

### -exec

Si l'on le veut, il est possible d'ajouter une exécution de commande pour chaque élément trouvé par la commande **find**. Pour ce faire, il suffit d'ajouter l'option `-exec` lors de l'utilisation de find et de spécifier avant une syntaxe semblable à `'{}' ';'` la commande à lancer pour chaque occurence trouvée. Les accolades servent à définir les arguments de la commande à exécuter (elles seront remplacées par l'élément en cours d'itération), et le point virgule à définir la fin de la commande. Si l'on préfère avoir un prompt avant l'exécution de chaque commande, il va nous falloir utiliser à la place de `-exec` l'option `-ok`:

```bash
find ~ -type f -empty -exec ls -l '{}' ';'

find -type f -name "*.html" -exec cp '{}' '{}_copy' ';'
```

### xargs

Cette commande est complémentaire à l'option **-exec** de **find** car elle permet de faire à peut près la même chose mais de façon groupée. En effet, l'option d'exécution standard de la commande **find** se fera indépendamment pour chaque élément trouvé. En utilisant `xargs`, il est possible de passer tous les éléments d'un coup en paramètre d'une autre commande.

```bash
find -empty -exec ls '{}' ';' # Chaque élément va être envoyé indépendamment à la commande 'ls'

find -empty | xargs ls # 'ls' va recevoir en arguments tous les éléments trouvé d'un coup
echo hello world | xargs mkdir # Va créer deux dossier: 'hello' et 'world'
```

---

[Retour](../README.md)