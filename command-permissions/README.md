# Les permissions
Contrairement à un ordinateur de type Windows classique, les systèmes d'exploitation de type Unix sont des systèmes multi-utilisateurs. Lorsqu'une personne se connecte à un ordinateur Linux, il est possible qu'une autre personne soit déjà en train d'utiliser l'ordinateur. En effet, plusieurs personnes peuvent travailler de concert sur une même machine. 

> Cette capacité vient des début de l'informatique, où les universités ne pouvaient pas se permettrent d'acheter plusieurs ordinateurs. Il y avait à la place plusieurs terminaux reliés tous au même ordinateur. 

Chaque utilisateur possèdera son propre rapport aux fichiers, et il est évidemment possible d'éditer ses propres fichiers, mais si une autre personne cherche à modifier les fichiers que l'on a créé, alors il risque de se heurter à une erreur de droits utilisateurs. Pour connaitre les droits utilisateurs simplement, il suffit de regarder les valeurs de la première colonne d'un affichage en liste étendue des fichiers d'un emplacement donné:

```bash
drwxrwxrwx
```

Les droits se séparent en trois catégories majeures, qui permettent de mieux comprendre l'affichage sous forme de liste étendue vu précédemment et dont la structure est `TAAABBBCCC`:
- `T`: Le type de fichier (**-**: Fichier standard, **d**: dossier, **c**: fichier au caractère spécial, **l**: lien symbolique)
- `AAA`: Les droits de l'utilisateur sur un fichier
- `BBB`: Les droits d'un groupe d'utilisateur sur un fichier
- `CCC`: Les droits de toutes les autres personnes sur un fichier

Parmis les trois groupes de droits, on va donc trouver trois droits:
- `r` Le droit de lecture, qui spécifique qu'il est possible pour cette catégorie d'utilisateurs de lire et de lister le contenu d'un fichier
- `w` Le droit d'écriture, qui spécifie qu'il est possible de modifier le contenu d'un fichier (il faudra cependant la capacité d'exécuter le fichier pour pouvoir par exemple le faire passer dans la commande **nano**)
- `x` Le droit d'exécution permettant à une personne de se déplacer dans le dossier ou de se servir de ce fichier dans le cadre d'une commande
- `-` L'absence de droits, spécifiant que le dossier ou le contenu du fichier ne peuvent ni être vu, ni modifié et que l'on ne pourra pas se déplacer dans le dossier. 

### chmod

Dans le ca où l'on souhaiterai modifier les droits d'un fichier ou d'un dossier, il est possible de le faire via l'utilisation de la commande `chmod`. Cette commande fonctionne de plusieurs façon, mais la syntaxe de base est la suivante: 

```bash
chmod type_utilisateur+droits_accordés fichier_ou_dossier # Pour ajouter à une catégorie un droit sur un fichier ou un dossier

chmod type_utilisateur=droits_accordés fichier_ou_dossier # Pour fixer à une catégorie un droit sur un fichier ou un dossier et retirer les autres

chmod type_utilisateur-droits_accordés fichier_ou_dossier # Pour retirer à une catégorie un droit sur un fichier ou un dossier
```

Le type d'utilisateur peut être de 4 valeurs: 
- `u`: On cible l'utilisateur
- `g`: On cible le groupe d'utilisateurs
- `o`: On cible les autres utilisateurs
- `a`: On cible toutes les valeurs précédentes en même temps

Il est possible d'ajouter plusieurs droits en même temps en les concaténant à droite de l'opérateur. De même, on peut cibler plusieurs catégorie en les concaténant à gauche de ce même opérateur. Les droits à accordés correspondent aux lettres vues précédemment: `r`, `w` et `x`

L'autre notation disponible est une notation basée sur une valeur octale. Pour s'en servir, il convient de connaitre le fonctionnement du stockage des valeurs de droits dans la machine. En effet, le système de droit utilisateur est stocké via l'utilisation d'un octet par catégorie, qui de façon binaire va donner plusieurs possibilités:
- `000` => **0**: `---` => Aucun droit
- `001` => **1**: `--x` => Droit d'exécution uniquement
- `010` => **2**: `-w-` => Droit d'écriture uniquement
- `011` => **3**: `-wx` => Droit d'écriture et d'exécution
- `100` => **4**: `r--` => Droit de lecture uniquement
- `101` => **5**: `r-x` => Droit de lecture et d'exécution
- `110` => **6**: `rw-` => Droit de lecture et d'écriture
- `111` => **7**: `rwx` => Tous les droits

Via cette notation, la syntaxe pour modifier devient un peu plus concise, mais requiert de bien retenir le système octal pour être maîtrisée: 

```bash
chmod 755 file.txt # -rwxr-xr-x
chmod 777 folder/ # drwxrwxrwx
```

### su

Si l'on désire changer notre identité utilisateur, il faut utiliser la commande `su` avec une syntaxe de la sorte:

```bash
su - nom_utilisateur
```

On se verra ensuite demandé le mot de passe de l'utilisateur, puis un nouveau shell sera ouvert en tant que cet utilisateur. Pour pouvoir quitter une session utilisateur, il nous faut quitter le terminal en utilisant la commande `exit`.

Dans un système d'exploitation Linux, il existe un utilisateur spécifique, nommé `root`. Cet utilisateur dispose d'absolument tous les droits et il faut donc faire très attention lorsque l'on se logue en tant que tel. Par défaut, un système Linux verrouille l'accès à cet utilisateur. 

### sudo

La commande `sudo` permet de se voir accordé temporairement les droits administrateur pour les commandes passées en argument à notre commande **sudo**. De la sorte, il n'est pas nécessaire de se loguer en tant qu'utilisateur root, et on évite ainsi de détruire par inadvertance notre machine. Si l'on utilise la commande sudo suivie uniquement de l'option `-l`, alors on se voit présenter la liste des commandes que l'on peut exécuter. 

### chown

Si l'on souhaite désormais changer non pas les droits d'un dossier ou d'un fichier, mais qui en est le possesseur, il va nous falloir utiliser la commande `chown`. Via cette commande, on peut alterer quel groupe d'utilisateur est le possesseur d'un dossier, ou quel utilisateur possède un fichier donné. Sa syntaxe est relativement simple: 

```bash
chown user:group filepaths
```

Son utilisateur peut cependant demander de posséder des droits utilisateurs, et il sera sans doute nécessaire de précéder la commande d'une commande **sudo**:

```bash
sudo chown moi:mon_groupe mon_fichier.txt

sudo chown :un_groupe un_dossier/
```

### groups / addgroup / adduser

Si l'on souhaite connaitre à quels groupes appartiennent des utilisateur, il va nous falloir utiliser la commande `groups` suivie de l'utillisateur dont on cherche à connaitre les affiliations:

```bash
groups username
```

Pour pouvoir créer un groupe, il va nous falloir utiliser la commande `addgroup`:

```bash
addgroup nouveau_groupe
```

Une fois le groupe créé, on va pouvoir y ajouter des utilisateurs via la commande `adduser`:

```bash
adduser utilisateur nom_groupe
```

A contrario, pour retirer un utilisateur d'un groupe, la commande à utiliser se trouve être `deluser`:

```bash
sudo deluser utilisateur nom_groupe
```


---

[Retour](../README.md)