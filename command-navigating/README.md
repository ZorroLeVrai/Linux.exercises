# Naviguer en ligne de commande

L'utilisation du terminal n'empêche pas qu'il soit possible de passer d'une structure de dossier à une autre. Bien entendu, il ne sera pas possible de double-cliquer sur un dossier pour l'ouvrir, mais ce n'est pas grave. 

### Le dossier 'home'

Pour appréhender la navigation dans le système de fichier, il est important de connaître certains dossier importants. Par exemple, dans une hierarchie de dossiers sous Linux, le dossier **home** est le dossier contenant les différents dossier de chaque utilisateur de l'ordinateur. 

Lorsque l'on ouvre le terminal Linux, nous nous trouvons par défaut dans le dossier de l'utilisateur lançant le terminal. Ce dossier est représenté par le caractère `~`.  

### Le dossier racine

A côté de ce dossier se trouve le dossier racine de l'ordinateur, qui est symbolisé par le caractère `/`. De ce dossier découle tous les autres, et il est possible d'atteindre un dossier en particulier avec un chemin dit **absolu** qui est en réalité un chemin relatif au dossier racine. 

### pwd

La commande `pwd` sert à connaître le dossier actuel ouvert dans le terminal. Le chemin affiché sera un chemin relatif au dossier racine, donc un chemin de type **absolu**.

### ls

La commande `ls` est extrèmement utile car elle permet de connaître les fichiers et/ou dossiers se trouvant dans le dossier actuel de notre terminal. Adjointe d'options, elle permet de connaître tout un tas d'informations sur les fichiers rapidement, ce qui pour le coup ne serait pas permit par une interface graphique standard.

Parmi ces options, certaines sont très importantes: 
- **ls -l**: Cette option permet d'obtenir un affichage des éléments sous la forme d'une liste présentant, en plus du nom des éléments, les droits utilisateurs, le créateur de l'élément, sa taille ainsi que d'autres informations.
- **ls -a**/ Via cette option, on peut voir les dossier et fichiers cachés.
- **ls --sort=option**: Via cette option, il est possible de spécifier un système de tri autre que celui par défault (qui est d'ordre alphabéthique)

En argument de la commande ls, il est tout à fait possible de spécifier un chemin de sorte à observer sa structure interne sans avoir à déplacer notre terminal.

### cd

Pour pouvoir changer l'emplacement de notre terminal, la commande à utiliser est la commande `cd` dans laquelle on passe en argument la direction à emprunter. Dans le cas d'une direction montante, il va falloit utiliser `..` pour spécifier que l'on souhaite remonter d'un dossier. Chaque dossier sera séparé d'un caractère `/` et un élément se trouvant dans le même dossier que celui dans lequel nous travaillons aura pour chemin un chemin pouvant débuté par `./`.

---

[Retour](../README.md)