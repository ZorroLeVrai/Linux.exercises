# Detective Find

Veuillez télécharger le fichier zip suivant, dézippez-le et naviguez jusqu'au répertoire `Cases/`.
[Cases.zip](./Cases.zip)
**Remarque : pour que cet exercice fonctionne correctement, veuillez éviter de modifier l'un des fichiers de cas !**

### Votre tâche

Bienvenue détective ! Le dossier `Cases` contient des milliers de fichiers de cas, ouverts et fermés. Utilisez la commande `find` pour vous aider dans les tâches suivantes :

- En utilisant `find` (et une autre commande), comptez le nombre de fichiers de cas qui incluent "closed", en minuscules, dans leur nom. Vous devriez trouver **980** cas.

ls -1 Cases/\*closed\* | wc -l

- Oh non, l'un de nos nouveaux détectives étiquette ses affaires en utilisant "CLOSED" en majuscules. Trouvez les 3 cas qui ont "CLOSED" dans leur nom.

ls -1 Cases/\*CLOSED\*

- Obtenez un décompte total de tous les cas fermés qui incluent "closed" dans leur nom, en majuscules ou en minuscules. Vous devriez obtenir un total de 983 !

ls -1 Cases/\*{closed,CLOSED}\* | wc -l

- Obtenez un décompte pour le nombre total de cas **ouverts** avec des numéros de cas impairs (trouver les cas ouverts qui ont 1, 3, 5, 7 ou 9 comme dernier chiffre dans leur numéro de cas). Vous devriez obtenir 519 cas.

ls -1 Cases/\*{1,3,5,7,9}\_{open,OPEN}.txt | wc -l

- Trouvez les trois cas vides.

find Cases -empty

- La plupart de ces fichiers sont assez petits, mais il y a 3 fichiers de cas assez volumineux. Trouvez les trois fichiers qui ont une taille supérieure à 20ko.

find Cases -type f -size +20k

- Trouvez le fichier de cas qui a une taille supérieure à 150ko et qui est fermé.

find Cases -name \*\_closed.txt -type f -size +150k

- Personne n'a touché à ces fichiers de cas depuis des années, ou du moins personne ne devrait avoir touché à ces fichiers, mais malheureusement, un détective corrompu a récemment altéré l'un des fichiers. Aujourd'hui, il a changé un seul cas de "closed" à "open" pour nuire à l'un de ses ennemis. Trouvez le cas qui a été modifié plus récemment que le fichier `yesterday.txt`. Regardez la vidéo d'introduction de l'exercice si vous êtes confus ! Vous devrez peut-être lire les pages man pour trouver la commande correcte.

find Cases -anewer Cases/yesterday.txt -type f