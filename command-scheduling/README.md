# Planifier des tâches dans le terminal

Si l'on le veut, il est possible de planifier l'exécution de tâches dans notre terminal. Par exemple, si l'on le veut, il est possible d'automatiser l'exécution d'un listing des processus tournant sur notre machine et leur stockage dans un fichier toutes les soirées à 22h.

Pour ce faire, il va nous falloir utiliser la commande `crontab -e`, qui va permettre d'éditer le fichier dédié à la planification de tâches. La syntaxe à utiliser ressemble à `minute hour day month day_of_week command`. Dans ces valeurs, il est possible de placer des valeurs spéciales, comme par exemple:
- `*` pour placer un wildcard
- `a,b` pour lister des valeurs
- `a-b` pour donner une etendue
- `*/a` pour créer un pas (tous les **a**)

Par exemple, pour exécuter la commande **ls** toutes les 30 minutes, il faudrait utiliser ce genre de syntaxe:
```text
30 * * * * ls
```

Pour lancer la même commande tous les jours à minuit, il faudrait ce genre de syntaxe:
```text
0 0 * * * ls
```

Pour pouvoir gérer les erreurs des tâches planifiées (cronjobs), il est nécessaire de se rappeller les capacités de redirection, avec par exemple la redirection vers un fichier de logging des erreurs via `2> fichier_log.txt`

---

[Retour](../README.md)