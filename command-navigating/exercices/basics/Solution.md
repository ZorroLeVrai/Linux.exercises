# La Navigation en lignes de commande

[Farm.zip](./Farm.zip)

Téléchargez le fichier ci-dessus, décompressez-le, et faites glisser le dossier résultant `Farm` sur votre **Bureau**. Le dossier Farm contient les sous-répertoires suivants :

```bash
Farm/
	Coop/
		Chickens/
		Geese/
	Stable/
		Horses/
```

À partir de ce point, n'utilisez QUE le terminal pour accomplir ce qui suit :

- Ouvrez une nouvelle fenêtre de terminal. Naviguez jusqu'au dossier `Farm`.

```
Si le fichier Zip `Farm.zip` est décompressé dans `~/Documents/Linux_exercices/`
Tapez la commande `cd ~/Documents/Linux_exercices/Farm/`
```

- Listez le contenu du répertoire `Farm`.

```
Tapez la commande `ls`
```

- "Déplacez-vous" dans le dossier `Coop`.

```bash
cd Coop
```

- Liste le contenu du dossier `Coop`.

```bash
ls
```

- "Déplacez-vous" dans le dossier `Chickens`.

```bash
cd Chickens
```

- Liste les poulets dans le dossier `Chickens`. Combien y en a-t-il ?

```bash
Tapez la commande `ls` ou `ls | wc -w`
```

Il y en a 6

- Un des poulets est très très vieux, lequel est-ce ? (quel fichier dans le dossier `Chickens` a la date de modification la plus ancienne ?) Utilisez une commande pour le découvrir !

Pour déterminer le fichier le plus vieux, vous pouvez taper la commande suivante
`ls -alr --sort=time`

Le fichier Elvis est le plus ancien (la plus ancienne date de modification)

- En une seule commande, déplacez-vous du répertoire `Chickens` vers le répertoire `Geese`. Consultez la structure des dossiers écrite ci-dessus si nécessaire.

```bash
cd ../Geese
```

- Combien d'oies (fichiers) y a-t-il dans le dossier `Geese` ?

Tapez la commande `ls` ou `ls | wc -w`  
Il y en a 4

- Une des oies est assise sur un œuf en or ! Il est plus gros que les autres. Laquelle est-ce ? (quel fichier dans le dossier `Geese` est le plus grand ?) Utilisez une commande pour le découvrir !

`ls -lS`  
ou  
`ls -l --sort=size`

Le fichier le plus volumineux est `Muffin`

- Accédez au dossier `Horses`. Consultez la structure des dossiers écrite ci-dessus si nécessaire.

```bash
cd ../../Stable/Horses
```

- Combien de chevaux y a-t-il dans le dossier `Horses` ?

Tapez la commande `ls`  
ou  
`ls | wc -w`  
Il y en a 4

- Attendez ! Il y a un cheval caché dans le dossier `Horses` ! Comment s'appelle-t-il ?

Tapez la commande `ls -a` pour lister tous les fichiers y compris les fichiers cachés.  
Les fichiers cachés débutent avec le caractère `.`  
Le Cheval caché est `Troy`
