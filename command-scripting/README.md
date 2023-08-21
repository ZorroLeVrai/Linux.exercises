# Créer nos propres scripts

Pour créer des scripts bash, il est nécéssaire de connaitre un minimum les lignes de commandes, d'écrire un fichier compatible, puis de gérer ses droits afin que le shell puisse le trouver et l'exécuter. Pour créer un script, il faut que la première ligne de ce fichier soit `#! /bin/bash` (Cette ligne de code sert à définir quel sera le chemin du programme devant exécuter le script de sorte à ne plus avoir à préfixer son nom du lien vers le programme lors de son appel dans le terminal):

```bash
#! /bin/bash

echo "Hello world!"
```

Pour exécuter ensuite le fichier, il suffit de le passer en argumant à la commande `bash`:

```bash
bash mon_script
```

Pour rendre la chose plus simple, il va nous falloir modifier la variable d'environnement `$PATH` de sorte à avoir le dossier actuel adjoint à la liste des sources disponible pour la récupération des commandes. De la sorte, pour exécuter notre commande, nous pourrons simplement utiliser la ligne de commande correspondant au nom de notre script. Il ne nous reste plus qu'à gérer les droits utilisateur pour que tous les utilisateurs que l'on veuille rendre capable d'utiliser notre script le puissent.

Pour ce faire, il va nous falloir utiliser la commande `chmod +x mon_script`

---

[Retour](../README.md)