# Manipuler les fichiers (Copie, Suppression, Déplacement)

Lorsque l'on manipule des fichiers dans un terminal Linux, il n'est pas possible de "**Drag n' Drop**" nos fichiers comme nous le ferrions dans une interface graphique. Pour réaliser le même genre de manipulations que sur une interface visuelle, il est nécessaire de bien connaître trois commandes : 

### rm
La commande de suppression dans le terminal se trouve être la commande `rm`. Cette commande peut être très dangeureuse si elle est utilisée sans contrôle car contrairement à la suppression dans une interface graphique, elle ne demande pas de confirmation. Dans le cas de son utilisation dans un dossier système, en partant du principe que nous disposions des droits administrateurs, il est possible de tout simplement rendre notre ordinateur unitilisable de par la suppression des binaires essentiels à son fonctionnement !. 

C'est pour cela qu'il est recommandé de ne pas utiliser cette commande, ni même le reste du terminal d'ailleurs, en tant qu'administrateur. De la sorte, nous sommes obligé, lors de l'utilsation de certaines commandes, de nous attribuer le temps de la commande les droits administrateurs. 

Cela étant dit, il est donc tout à fait possible de supprimer un fichier via la commande de suppression:

```bash
rm nom_fichier.extension
```

Si l'on souhaite supprimer un dossier ainsi que ses sous dossiers / fichiers, il faut utiliser l'option `-r` pour supprimer toute la structure interne du dossier en supplément:

```bash
rm -r chemin/du/dossier
```

Il est aussi possible d'utiliser l'option `-d` pour supprimer des dossiers vide. De la même façon, il est possible d'utiliser la commande `rmdir`:

```bash
rm -d nom_dossier_vide

rmdir nom_dossier_vide
```

Si l'on veut, il est possible de faire une suppression en 'step-by-step' via l'utilisation de l'option `-i`. De la sorte, il nous sera demandé pour chaque fichier si l'on veut effectuer la suppression et pour chaque sous-dossier si l'on souhaite le parcourir dans le cas où l'on aurait aussi utilisé l'option `-r`.

### mv

Dans le cas où notre objectif est le déplacement de fichiers / dossier, il convient d'utiliser la commande `mv`. Son utilisation passe par le passage de deux arguments - la source et la destination. Il est possible de déplacer plusieurs éléments en même temps car le paramètre de la source est un paramètre multiple, le dernier étant la destination:  

```bash
mv chemin/sourceA chemin/sourcB chemin/sourceC chemin/destination
```

Quand il s'agit de déplacer des dossiers, la syntaxe et les règles d'utilisation de la commande sont les mêmes. Il est possible dedéplacer ainsi plusieurs dossiers dans un seul et même dossier. Attention cependant, le dossier doit exister au préalable sous peine de causer une erreur lors de l'exécution de la commande: 

```bash
mv chemin/dossierA/ chemin/dossierB/ chemin/dossierC/ chemin/destination/
```

Si l'on le veut, il est aussi possible de se servir de cette commande dans le but de renommer des fichiers:

```bash
mv ancien_nom.extension nouveau_nom.extension
```

### cp

Enfin, il est tout à fait possible de copier des fichiers ou des dossiers via l'utilisation de la commande `cp`. Dans le cadre de son utilisation, il convient cependant de faire attention lorsque l'on copie un fichier vers un chemin pré-existant. Dans ce cas de figure, le fichier de base sera ecrasé et les données seront donc perdues. 

Mis à part cela, l'utilisation de la commande est somme toute assez classique, avec le passage de deux arguments - la source et la destination. Si l'on le veut, il est aussi possible de copier d'un coup plusieurs fichiers vers un dossier:

```bash
cp chemin/source.extension chemin/destination.extension

cp chemin/sourceA.ext chemin/sourceB.ext chemin/destination/
```

Il est également possible de copier un dossier en entier vers un autre dossier en se servant de l'option `-r` pour une copie **récursive**:

```bash
cp chemin/dossierA/ chemin/dossierB/
```

---

[Retour](../README.md)