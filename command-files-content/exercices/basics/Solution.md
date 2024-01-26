# Travailler avec des fichiers

[FileExecices.zip](./FilesExercise.zip)
Une fois que vous avez téléchargé le fichier zip ci-dessus, décompressez-le ! Il contient deux fichiers : `poem.txt` et `purchases.txt`

### Partie 1

- Utilisez une commande pour afficher l'intégralité du contenu du fichier `poem.txt`. Utilisez une option pour que la sortie inclut également les numéros de ligne.

```bash
cat -n poem.txt
```

- C'est une douleur de tout lire d'un coup ! Lisez poem.txt en utilisant `less` à la place.
  - Faites défiler une ligne à la fois vers le bas
  - Faites défiler une ligne à la fois vers le haut
  - Faites défiler une "page" vers le bas
  - Faites défiler une "page" vers le haut

`j` et `k` pour défiler d'une ligne vers le bas ou vers le haut. Vous pouvez également utiliser les flêches du haut et du bas.  
`f` et `b` pour défiler d'une page vers le bas ou vers le haut.  
`q` pour quitter le programme `less`

```bash
less -N poem.txt
```

- Recherchez le terme "Dog" dans less. Pouvez-vous trouver la ligne qui le contient ?

```bash
less -N poem.txt
puis tapez la commande
/dog
```

- BONUS : pouvez-vous effectuer une recherche insensible à la casse ? Le poème contient à la fois "dog" et "Dog" sur des lignes distinctes.

```bash
less -NI poem.txt
puis tapez la commande
/dog
```

Pour avancer ou reculer dans la recherche, utilisez les touches `n` et `N`.

- Il est maintenant temps de faire des recherches ! Trouvez l'option pour indiquer à less d'ouvrir avec les numéros de ligne affichés. Ouvrez `poem.txt` de cette façon.

```bash
less -N poem.txt
```

- Ensuite, trouvez la "commande" que vous pouvez taper dans less pour aller exactement à 50 % du fichier.

```bash
less +50% poem.txt
```

- Utilisez une commande pour trouver le nombre de mots dans `poem.txt`.

```bash
wc -w poem.txt
```

- Exécutez une commande pour afficher les 4 premières lignes de `poem.txt`.

```bash
head -n 4 poem.txt
```

- Exécutez une commande pour afficher les 8 dernières lignes de `poem.txt`.

```bash
tail -n 8 poem.txt
```

### Partie 2

- Exécutez une commande pour afficher les lignes dans `purchases.txt` dans l'ordre inverse (la dernière ligne imprimée en premier).

```bash
tac purchases.txt
```

Pour bien voir l'inversement des lignes on peut utiliser la commande

```bash
cat -n purchases.txt | tac
```

- Exécutez une commande pour afficher les lignes dans `purchases.txt`, triées par ordre alphabétique.

```bash
sort purchases.txt
ou
cat purchases.txt | sort
```

- Exécutez une commande pour compter le nombre de lignes dans `purchases.txt`.

```bash
wc -l purchases.txt
```

- Exécutez une commande pour afficher les lignes dans `purchases.txt`, triées par prix (la dernière colonne) dans l'ensemble de données dans l'ordre INVERSE (du prix le plus élevé au prix le plus bas).

```bash
sort -rnk 3 purchases.txt
```
