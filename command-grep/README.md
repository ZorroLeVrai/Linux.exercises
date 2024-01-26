# La commande Grep

La commande `grep` est une commande très importante lorsque l'on travaille avec un terminal car elle a pour but de permettre la recherche de patterns dans le contenu d'un fichier. Lorsqu'elle trouve un pattern recherché, son fonctionnement de base est d'afficher chaque ligne qui mentionne le pattern recherché:

```bash
grep pattern path
```

Via l'ajout de l'option `-i` on élimine la sensibilité à la casse de la commande de base. Si l'on veut rechercher des mots exacts, il faut utiliser l'option `-w` de sorte à éviter la recherche d'une portion de mot. Si l'on le veut, il est même possible de rechercher de façon récursive via l'utilisation de l'option `-r` de sorte à ce que la commande recherche dans chaque fichiers d'un dossier en particulier (le second paramètre de la commande de base étant un chemin à chercher).

En utilisant l'option `-c` il devient possible de compter le nombre d'occurence au lieu de les afficher. Si l'on veut avoir un peut de contexte en plus des occurences, il est possible de demander un nombre de lignes avant `-B nombre` et un nombre de lignes après `-A nombre` l'occurence (De sorte à séparer les groupements de lignes, il est possible de se servir de l'option `-C`). Pour connaître la ligne sur laquelle a eu lieu l'occurence, il nos faut utiliser l'option `-n`.

### Les expressions régulières

Supportant l'utilisation d'expression régulière, cette commande peut être utilisée pour faire des recherches plus complexes telles que:

```bash
grep -ri "parm[ae]san" Test/
```

Parmi les bases de l'utilisation d'expressions régulière, il est important de connaître les patterns suivants:

- `.`: Va servir à matcher un caractère unique de n'importe quelle valeur
- `^`: Va matcher le début d'une ligne
- `$`: Va matcher la fin d'une ligne
- `[abc]`: Va matcher n'importe quel caractère dans un set donné
- `[^abc]`: Va matcher n'importe quel caractère n'étant pas dans un set donné
- `[a-z]`: Va matcher n'importe quel caractère dans une étendue donnée
- `*`: Permet de répéter l'expression régulière de 0 à une infinité de fois lors de la recherche
- `\`: Permet d'échapper des caractères spéciaux

Attention cependant, la commande **grep** de base ne prendra pas en compte certaines règles des expressions régulières. Pour que la portée de nos connaissances en **regex** soit compatible avec la commande **grep**, il peut être préférable d'utiliser sa variante se servant d'expressions régulières étendues via l'option `-E`. De la sorte, les caractères tels que `?` suivront les règles des **regex**.

```bash
grep "birds?" -E  my_text.txt

grep "[A-Z]{1,8}" -E  my_text.txt
```

[Regex CheatSheet](https://www.rexegg.com/regex-quickstart.html)

# La commande AWK

La commande AWK est un outil puissant de traitement de texte en ligne de commande.  
Elle permet de manipuler, filtrer et formater des données, en particulier dans le contexte des fichiers CSV (Comma-Separated Values).

## Principe de base

AWK fonctionne en parcourant chaque ligne d'un fichier texte, divisant chaque ligne en champs (colonnes) en fonction d'un séparateur (par défaut, l'espace ou la tabulation), et permettant d'appliquer des conditions et des actions spécifiques à ces champs.

## Exemples pratiques

Supposons que nous ayons un fichier CSV nommé donnees.csv avec les colonnes suivantes : Prénom, Age, Salaire, Département.

```
Prénom,Age,Salaire,Département
Adam,28,50000,IT
Lise,35,60000,Sales
John,32,42000,Support
Zebra,45,75000,Marketing
```

**Exemple 1**  
Afficher tous les employées avec un salaire supérieur à 50000

```bash
awk -F, 'NR > 1 && $3 > 50000' donnees.csv
```

NR > 1 est utilisé pour sauter l'entête du fichier CSV.

**Exemple 2**  
Afficher tous les employées dont le prénom est "John" et l'age supérieur à 30

```bash
awk -F, '$1 == "John" && $2 > 30' donnees.csv
```

**Exemple 3**  
Afficher tous les employées dont l'age est supérieur à 40 ou que le nom du département commence par la lettre `S`

```bash
awk -F, 'NR > 1 && ($2 > 40 || $4 ~ /^S/)' donnees.csv
```

**Exemple 4**  
Afficher le nom et le département des employés n'étant pas du département Marketing

```bash
awk -F, 'NR > 1 && $4 != "Marketing" { print $1, $4 }' donnees.csv
```

---

[Retour](../README.md)
