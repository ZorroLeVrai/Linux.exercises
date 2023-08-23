# Exercice Extensions

### Partie 1 - Création de fichiers

Créez les 60 fichiers suivants **en une seule commande** avec les pouvoirs d'extension !

```bash

morning-day-1
morning-day-2
...
morning-day-30

afternoon-day-1
afternoon-day-2
...
afternoon-day-30
```

touch {morning,afternoon}-day-{1..30}

Pour cette prochaine partie, vous devrez utiliser la commande suivante : `date +"%m-%d-%y"`. Cette commande affichera la date actuelle en utilisant le format mois-jour-année, comme 09-19-21. Utilisez cette commande pour créer un nouveau fichier avec le nom todos-DATE.txt, où DATE est la sortie de la commande date ci-dessus. Par exemple, si nous avons exécuté la commande le 19 septembre 2021, le fichier résultant s'appellera `todos-09-19-21.txt`.

touch $(date +"todos-%m-%d-%y.txt")

### Partie 2

En utilisant les fichiers que nous avons créés dans la section précédente...

- Liste tous les fichiers qui se terminent par le chiffre `9`

ls \*9

- Liste tous les noms de fichiers où l'avant-dernier caractère est `1`

ls \*1?

- Liste tous les fichiers qui commencent par "afternoon" et se terminent par le chiffre `7`

ls afternoon\*7

- Créez un nouveau dossier appelé `Mornings` et déplacez tous les fichiers qui commencent par `morning` à l'intérieur.

mkdir Mornings  
mv morning\* Mornings/

### Partie 3

En utilisant une SEULE commande (avec extension), créez la structure de dossier suivante. Vous devrez utiliser l'option `-p` avec `mkdir` !

```bash
Year/
	Winter/
		Yard/
		House/
	Spring/
		Yard/
		House/
	Summer/
		Yard/
		House/
	Fall/
		Yard/
		House/
```

mkdir -p Year/{Winter,Spring,Summer,Fall}/{Yard,House}

Enfin, dans chacun des dossiers `Yard/` et `House/`, créez un fichier `todos.txt` et un fichier `done.txt`. Faites ceci en une seule ligne, sans changer de répertoire ! Utilisez l'extension ! La structure de dossier/fichier résultante devrait ressembler à ceci :

```bash
Year/
	Winter/
		Yard/
			todos.txt
			done.txt
		House/
			todos.txt
			done.txt
	Spring/
		Yard/
			todos.txt
			done.txt
		House/
			todos.txt
			done.txt
	Summer/
		Yard/
			todos.txt
			done.txt
		House/
			todos.txt
			done.txt
	Fall/
		Yard/
			todos.txt
			done.txt
		House/
			todos.txt
			done.txt
```

touch Year/{Winter,Spring,Summer,Fall}/{Yard,House}/{todos,done}.txt
