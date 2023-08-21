# L'Environnement et sa manipulation

Durant l'exécution du shell, ce dernier nous permet d'utiliser ce que l'on appelle un environnement. Cet environnement prend en compte un certain nombre de variables qui sont stockées sous la forme d'un ensemble clé-valeur. Par exemple, dans notre environnement, on pourrait trouver ce genre de variables:
- Notre dossier personnel
- Le dossier dans lequel nous sommes en train de travailler
- Le nom de notre shell
- Le nom de l'utilisateur actuellement logué

Si l'on désire voir les variables actuellement disponible dans notre environnement, il est possible de le faire via la commande `printenv`, qu'il est conseiller de piper via la commande **less** pour rendre la chose plus lisible. Ces variables sont récupérable lors de l'execution de commandes via l'utilisation du caractère `$`:

```bash
echo $NOM_VARIABLE # Cette commande va afficher la valeur de NOM_VARIABLE dans le shell
```

Pour définir des variables, la syntaxe est très simple. Il suffit de donner le nom de la variable, de la précéder d'un opérateur d'affectation, puis de lui donner la valeur qu'elle est censé prendre:

```bash
nom_variable=valeurvariable
```

Les variables seront accessible durant la session actuelle, mais ne pourrons pas être héritées dans les shell enfants qui pourraient être demandés via l'exécution de la commande `bash` par exemple. Pour rendre cela possible, il convient de créer nos variables en les préfixant d'un `export`:

```bash
export nom_variable=valeurvariable
```

### les fichiers de startup

Via l'édition des fichiers de startup, il est possible de modifier le fonctionnement et/ou les préférences utilisateurs de notre terminal. Par exemple, pour changer les couleurs de notre terminal, il faut changer les valeurs de variables d'environnement de nos shells. Ces variables se retrouvent injectées dans le shell par lecture automatique des fichiers:
- `etc/bash.bashrc` pour définir les valeurs de tous les utilisateurs et `~/.bashrc` pour définir celles de l'utilisateur actuel dans le cadre d'une utilisation du shell sans logging. Ce type de session est généralement démarré lorsque l'on lance le terminal via l'interface graphique.
- `/etc/profile` pour tous les utilisateurs, `~/.bash_profile` pour le fichier de config' personnel de l'utilisateur, `~/.bash_login` qui sera lu si le fichier précédent est manquant, `~/.profile` qui sera lu si les deux précédents n'existent pas.

### Les aliases

Si l'on le veut, il est possible de créer ce que l'on appelle des **alias**, qui serviront en place des lignes de commande classiques. Via leur utilisation, on peut transformer en un seul mot toute une série de commande pipées. Leur utilisation par du principe que l'on veut ré-utiliser à l'avenir plusieurs commandes et donc nous simplifier la tâche en n'ayant à écrire qu'un seul mot. Pour en créer un, il faut utiliser une syntaxe similaire à celle des variables:

```bash
alias nom_alias='command arguments'
```

---

[Rtour](../README.md)