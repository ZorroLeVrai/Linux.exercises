# Le Piping avec les Pokémons

Téléchargez les fichiers de départ ici :
[PokemonExercise](./PokemonExercise.zip)

Dézippez le fichier. Le dossier résultant contient un sous-dossier appelé `PokeDex/` qui contient à son tour un tas de fichiers, chacun portant le nom d'un Pokémon spécifique comme :

```bash
PokemonExercise/
	PokeDex/
		100Voltorb
		101Electrode
	  619Mienfoo
		...
```

### Votre tâche
Effectuez les défis suivants en utilisant les fichiers de départ. Assurez-vous de naviguer vers le répertoire `PokemonExercise/`, **mais ne lancez AUCUNE des commandes suivantes à l'intérieur du dossier** `PokeDex/`. Je répète : tous les fichiers que vous créez pour l'exercice doivent se trouver dans `PokemonExercise/` et non dans `PokeDex/`.

* Comptez le nombre de fichiers Pokemon dans le dossier `PokeDex/`. Vous devrez combiner des commandes pour que cela fonctionne !
* Ensuite, créez un nouveau fichier unique appelé `all-pokemon.txt` dans le dossier `PokemonExercise` (et NON dans le dossier `PokeDex`) qui contient le nom de chaque fichier Pokemon en minuscules dans le répertoire, trié par ordre numérique ! Le résultat final devrait ressembler à ceci :

```bash
1bulbasaur
2ivysaur
3venusaur
4charmander
5charmeleon
6charizard
7squirtle
8wartortle
9blastoise
10caterpie
11metapod
12butterfree
...
```

* Maintenant que nous avons ce fichier qui inclut tous les Pokemon dans l'ordre numérique, imprimons les trois Pokemon liés aux pigeons : pidgey, pidgeotto et pidgeot. En utilisant la ligne de commande, imprimez les lignes 16-18. Ça devrait ressembler à ça :

```bash
16pidgey
17pidgeotto
18pidgeot
```

* Ensuite, isolons les 151 premiers Pokemon. En utilisant un pipeline unique...
  * imprimez les 151 premières lignes du fichier `all-pokemon.txt`
  * supprimez tous les chiffres de 0 à 9 des lignes (en utilisant `tr` )
  * triez les lignes sans chiffres par ordre alphabétique
  * stockez le nouveau résultat dans un fichier appelé `original-151.txt` dans `PokemonExercise`

```bash
abra
aerodactyl
alakazam
...
wigglytuff
zapdos
zubat
```