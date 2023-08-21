# Les Redirections avec Wildlife

Téléchargez les fichiers pour cet exercice :
[Wildlife.zip](./Wildlife.zip)

Décompressez le dossier `Wildlife` et naviguez jusqu'à celui-ci via la ligne de commande.

### Votre tâche
Vous participez à une enquête sur la faune sauvage dans une partie isolée de la forêt amazonienne péruvienne ! Ce matin, trois de vos assistants de recherche ont effectué chacun des promenades de transect où ils ont enregistré les espèces individuelles qu'ils ont observées. Votre travail (simple) consiste à combiner leurs résultats dans un nouveau fichier qui contient toutes les espèces qui ont été observées !

Créez un nouveau fichier appelé `all-species.txt` qui contient le contenu combiné de `angela-survey.txt`, `nico-survey.txt` et `juan-survey.txt`. Faites ceci en utilisant une seule commande !
Le problème avec le fichier `all-species.txt` est qu'il contient des entrées en double ! Utilisez une seule commande pour trier les lignes par ordre alphabétique, en ne triant que les éléments uniques, et envoyez la sortie dans un nouveau fichier appelé `sorted-animals.txt`.
Maintenant, vous allez faire une belle promenade matinale et vous tombez sur une grande anaconda qui se prélassait sur une bûche. Vous devriez ajouter cette observation à la liste des espèces !
Commencez par ajouter la date actuelle à la fin du fichier `sorted-animals.txt` en utilisant une commande (ne pas ouvrir le fichier manuellement !).
Ajoutez ensuite le texte "Green Anaconda" à la fin de `sorted-animals.txt`.
Exécutez la commande inexistante `ughhh` et redirigez tous les messages d'erreur pour qu'ils soient **ajoutés** au fichier `sorted-animals.txt`.