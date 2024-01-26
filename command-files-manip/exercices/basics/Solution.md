# Supprimer / Déplacer / Copier des Fichiers

### Partie 1 : Création des dossiers et des fichiers

Avant de pouvoir supprimer, déplacer ou copier des éléments... nous avons besoin d'éléments ! Il est temps de pratiquer l'utilisation de `touch` et de `mkdir`.

Veuillez créer un nouveau répertoire quelque part sur votre machine appelé `Bootcamp`. À l'intérieur, créez les dossiers et fichiers indiqués ci-dessous :

```bash
Bootcamp/
	FallCohort/
		Italo.txt
		Edgar.txt
		Linus.txt
		Sara.txt
		Silvio.txt
		Waitlist/
			Hanna.txt
			Haris.txt
			Netta.txt
	WinterCohort/
		Santiago.txt
		Iris.txt
		Naomi.txt
```

Utilisez les commandes suivantes

```bash
mkdir Bootcamp && cd Bootcamp
mkdir -p FallCohort/Waitlist/
mkdir WinterCohort
cd FallCohort
touch Italo.txt Edgar.txt Linus.txt Sara.txt Silvio.txt
cd Waitlist
touch Hanna.txt Haris.txt Netta.txt
cd ../../WinterCohort
touch Santiago.txt Iris.txt Naomi.txt
cd ..
```

- Malheureusement, `Edgar` a dû abandonner le cours. Supprimez le fichier `Edgar.txt` de `FallCohort`.

```bash
rm FallCohort/Edgar.txt
```

- Cela signifie que nous avons maintenant de la place dans notre cohorte d'automne pour retirer quelqu'un de la liste d'attente. Veuillez déplacer `Netta.txt` du dossier `Waitlist` dans le dossier `FallCohort`.

```bash
mv FallCohort/Waitlist/Netta.txt FallCohort
```

- Veuillez supprimer le dossier `Waitlist` et son contenu.

```bash
rm -r FallCohort/Waitlist
```

- Il s'avère que j'ai mal orthographié Sara. Elle écrit son nom "Sarah" avec un "h" à la fin. Veuillez renommer le fichier `Sara.txt` en `Sarah.txt`.

```bash
mv FallCohort/Sara.txt FallCohort/Sarah.txt
```

- Malheureusement, Italo a une urgence personnelle et il souhaite rejoindre notre cohorte d'hiver. Veuillez déplacer le fichier `Italo.txt` de `FallCohort` dans le dossier `WinterCohort`.

```bash
mv FallCohort/Italo.txt WinterCohort
```

- Oh non, notre cohorte d'hiver entière a dû être annulée en raison d'une pandémie mondiale :( Nous avons décidé de déplacer tous les étudiants prévus pour l'hiver au printemps. Dans le répertoire `Bootcamp`, créez une copie du dossier `WinterCohort` appelée `SpringCohort`.

```bash
cp -r WinterCohort SpringCohort
```

- Veuillez renommer le dossier WinterCohort en `WinterCohortCANCELLED`.

```bash
mv WinterCohort WinterCohortCANCELLED
```

- Oh non ! Nous allons mettre la clé sous la porte. Veuillez supprimer tout le répertoire `Bootcamp` 😢

```bash
rm -r Bootcamp
```
