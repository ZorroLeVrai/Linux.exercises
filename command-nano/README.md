# Nano 

Nano est un outil disponible dans le terminal qui permet d'ouvrir, de créer et d'éditer des fichiers textuels sans avoir à quitter le terminal. Via son apprentissage et son utilisation, il devient possible de créer des fichiers texte plus ou moins complexe de façon assez rapide et aisée.

Dans les grandes lignes, il est assez simple d'utiliser nano. Il suffit d'entrer la commande `nano` suivie d'un nom de fichier que l'on veut soit ouvrir soit créer de toute pièce. Une fois nano ouvert, alors il est possible de sauvegarder les lignes de texte entrées via l'utilisation de `CTRL+O` ou de `CTRL+S`. Le premier cas va demander où sauvegarder le fichier actuel alors que le second va sauvegardé dans le nom de fichier demandé en ouverture.

Si l'on demande à nano d'ouvrir un fichier qui n'existe pas encore, il est alors possible d'entrer des informations puis de sauvegarder dans le nom de fichier que l'on avait passé en argument dans un premier temps. De la sorte, il est quasiment possible de créer des fichiers avec nano également.

### Les raccourcis

Lorsque l'on utilise nano, il existe plusieurs raccourcis permettant une utilisation plus poussée de l'éditeur nano. Pour accéder à la liste des raccourcis dans l'éditeur nano, il est nécessaire d'appuyer sur la combinaison de touches `CTRL+G`.

Pour activer le soft-wrapping, la raccourcis se trouve être `Meta+$` (la touche méta se trouvant être soit **ESC** sur Mac ou **ALT** sur un clavier Windows dépourvu de cette touche). Egalement parmi les raccourcis utiles se trouve également la capacité de rechercher des éléments dans un fichier. Pour ce faire, il faut utiliser le raccourcis `CTRL+W`. Chaque recherche se fera à partir de l'élément trouvé dans le cas de recherche de l'occurence suivante d'un mot. De base, la recherche ne prend pas en compte la casse, mais il est possible de l'ajouter avec `Meta+C`. Pour rechercher la précédente occurence, il faut utiliser `Meta+B`. Il est aussi possible de remplacer via l'utilisation de `Ctrl+\`.

### Spellchecking

Lorsque l'on utilise nano, il est possible d'activer le vérificateur orthographique. Pour ce faire, il est nécessaire de personnaliser nano. En effet, de base, cette feature est désactivée dans l'éditeur. Pour modifier nano, il nous faut éditer le fichier **/etc/nanorc**. Suite à des histoires de permissions, il est nécessaire, pour l'éditer, d'entrer par exemple la commande ci-dessous dans le but de se voir accorder pour cette commande des privilèges administrateurs:

```bash
sudo nano /etc/nanorc
```

Une fois fait, il est possible d'utiliser par exemple ce fichier de configuration pour ajouter le **correcteur orthographique** dans notre éditeur. Cette fonctionnalité est accessible via l'utilisation de `F12`.

---

[Retour](../README.md)