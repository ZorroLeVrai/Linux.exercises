# Gérer les fichiers et dossiers

Pour pouvoir créer un fichier très simplement, il convient d'utiliser la commande `touch` suivie du nom du fichier que l'on souhaite créer en argument:

```bash
touch nom_fichier.extension
```

> Il est intéressant de savoir que la commande **touch** n'a pas pour but de créer des fichiers, mais aura pour objectif de modifier la date d'édition d'un fichier pour qu'elle corresponde à la date et l'heure du lancement de la commande. La création d'un fichier vide n'est qu'un effet secondaire de l'utilisation de la commande avec un nom de fichier non existant.

### file

La commande **file** est une commande ayant pour but de déterminer le type de fichier d'un chemin de fichier particulier. Via cette commande, il est possible de connaître par exemple le format d'encodage d'un fichier texte. Le fichier aurait beau changer d'extension, le système Linux est capable de comprendre en survolant le contenu et les méta-données qu'il s'agit par exemple d'une image de type JPEG.

```bash
file nom_fichier.extension
```

### mkdir

Si l'on veut pouvoir créer un ou plusieurs dossier, la commande à utiliser est la commande **mkdir** qui permet la création de dossier un par un. 

```bash
mkdir nom_dossier
```

Il n'est pas possible de créer une structure complexe directement via la commande mkdir, mais cela devient possible en cas d'utilisation de l'option `-p`. Les parents seront ainsi créé en même temps que les dossiers enfants. 

```bash
mkdir -p nom_dossier/nom_sous_dossier
```

--

[Retour](../README.md)