# Les Extensions

Lorsque l'on manipule le shell, il est intéressant de noter que nous avons à notre disposition des caractères spéciaux qui peuvent être utiles dans le cadre de notre manipulation du terminal.

Par exemple, l'utilisation du caractère `*` peut être utile dans le cas où l'on souhaite obtenir un matching de plusieurs noms de fichiers en même temps. Via son utilisation, on peut cibler par exemple tous les fichiers qui ont pour extension **.html**:

```bash
ls *.html
```

Ou alors cibler tous les fichiers dont le nom commence par **test**, ou qui commencent par **log_** et portent l'extension **.txt**:

```bash
ls test*

echo log_*.txt
```

Si l'on désire être plus précis, il est possible de cibler des mots dont X caractères peuvent être de n'importe quelle valeur. Pour ce faire, il faut utiliser le wildcard `?`. Par exemple, pour obtenir le nom des fichiers de toutes les pistes MP3 inférieures à la piste 100, on pourrait procéder de la sorte:

```bash
echo trach_0??.mp3
```

De même, des pattern empruntés aux expressions régulières sont disponibles: 
- Pour sélectionner des valeurs fixes, on peut utiliser ce genre de syntaxe: `picture[123].png`
- Pour sélectionner des valeurs allant de X à Y, on peut utiliser ce genre de syntaxe: `picture[1-9].png`, `grading[A-F].txt`
- L'ajout du caractère `^` en début d'utilisation de ces patterns provoquera une sélection par exclusion du pattern: Pour obtenir toutes les images ne finissant pas par une lettre allant de W à Z, on aurait par exemple: `picture[^W-Z].png`

### Tilde

Le caractère `~` peut également servir à obtenir des informations rapidement. Par exemple, en nous déplaçant à `~`, nous atteignons notre dossier personnel. Cependant, en cherchant `~utilisateur`, alors nous tentons d'atteindre le dossier personnel d'un utilisateur de l'ordinateur. Si ce dossier existe, alors le chemin sera remplacé par `/home/utilisateur`. Dans le cas contraire, cela sera seulement `~utilisateur`.

### Brace

Via l'utilisation des caractères `{` et `}`, il est possible de créer des multitudes de textes rapidement. Par exemple, si l'on veut avoir des fichiers du style de **testA.txt**, **testB.txt** et **testC.txt**, alors on peut se servir de `test{A,B,C}.txt` dans le cadre d'une commande touch:

```bash
touch test{A,B,C}.txt
```

Il est même possible de créer des patterns plus complexes comme par exemple avec l'utilisation des portées `{debut...fin...pas}`: 

```bash
ls My_{secret,public}_music{00..20}.{mp3,wav,ogg}

ls My_{secret,public}_music{00..20..2}.{mp3,wav,ogg}
```

Ces patterns peuvent également être imbriqués, pour procéder à des structures répétitives plus sélectives:

```bash
echo {x,y{1..5},z}.txt
```

### Extension arithmétique

Si l'on le veut, il est aussi possible de faire passer au shell une expression mathématique dont le résultat sera ensuite utilisé en place d'un texte. Pour ce faire, la syntaxe est la suivante:

```bash
echo $((expression))

echo $((1 + 2 * 6)).txt # 13.txt
```

### Ssimples vs Doubles guillemets

Lorsque l'on veut utiliser le terminal et prendre en compte des espaces, il est préférable de se servir de guillemets. Cependant, les simples et les doubles guillemets n'ont pas les mêmes capacités. En effet, lorsque l'on veut pouvoir tout de même placer des valeurs, par exemple des variables (auquelles on peut accéder via le caractère `$`) ou des résultats de commandes, il nous faut utiliser les doubles guillemets. A contrario, si l'on souhaite pouvoir écrire des signes de dollars, alors on doit utiliser les simples guillemets.

```bash
echo This        is # This is
echo "This        is" # This        is
echo 'This        is' # This        is
```

### La substitution de commande

Dans le cas où l'on le voudrait, il est possible, à la place de variables, de se servir du caractère `$` combiné avec des parenthèses pour placer à un emplacement donné de notre commande le résultat d'une commande plus ou moins complexe:

```bash
echo Today $(date) # Today Thu Mar 2 15:07:23 CET 2023
echo "Today $(date)" # Today Thu Mar 2 15:07:23 CET 2023
echo 'Today $(date)' # Today $(date)
```

---

[Retour](../README.md)