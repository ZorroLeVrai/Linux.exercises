# Liste d'étudiants

`students.csv`

```csv
Lastname,Firstname,Age,Favorite_animal
Smith,John,20,Dog
Johnson,Lisa,22,Cat
Brown,David,21,Rabbit
Garcia,Maria,20,Fish
Jones,Emily,23,Horse
Wilson,James,19,Hamster
Davis,Michael,21,Bird
Rodriguez,Samantha,24,Dog
Miller,Kevin,20,Cat
Martinez,Andrea,22,Fish
Hernandez,Jose,23,Rabbit
Lopez,Ashley,19,Horse
Jackson,Kimberly,21,Bird
Perez,Carlos,24,Dog
Moore,Sarah,20,Cat
Taylor,Daniel,22,Fish
Anderson,Karen,23,Rabbit
Thomas,Brian,19,Horse
Jackson,Michelle,21,Bird
White,Amanda,24,Dog
```

Via l'utilisation du terminal et du fichier CSV **students.csv**, vous allez devoir récupérer diverses informations au moyen de la commande `grep`.

- Trouvez toutes les lignes contenant le nom de famille "Smith"

```bash
grep "^Smith" students.csv
ou
awk -F, '$1 == "Smith"' students.csv
```

- Trouvez tous les élèves agés de 20 ans

```bash
awk -F, '$3 == 20' students.csv
ou
grep -E "^([^,]+,){2}20," students.csv
```

- Trouvez tous les élèves dont l'animal préféré est un chat

```bash
grep "Cat$" students.csv
ou
awk -F, '$4 == "Cat"' students.csv
```

- Trouvez tous les élèves dont l'animal préféré n'est pas un poisson

```bash
grep -v "Fish$" students.csv
ou
awk -F, '$4 != "Fish"' students.csv
```

- Trouvez toutes les personnes dont le prénom est "Maria" et dont l'animal préféré est un poisson.

```bash
awk -F, '$2 == "Maria" && $4 == "Fish"' students.csv
ou
grep -E "^[^,]+,Maria.*Fish$" students.csv
```
