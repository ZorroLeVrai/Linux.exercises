# Les Redirections

Les trois modes de base de canaux de communication entre un programme et son environnement sont:
- Le canal de l'entrée standard
- Le canal de la sortie standard 
- Le canal d'erreur standard

### La sortie standard
Ce canal est par défaut le terminal, ce qui fait que l'on observe le résultat de la commande dans notre terminal. Il est cependant possible de rediriger la sortie vers un autre ordinateur, un fichier, une imprimante, etc...

Si l'on souhaite modifier la sortie standard de notre commande pour stocker le résultat dans un fichier, il est possible de le faire via le catactère `>`.

Par défault, le contenu du base du fichier sera perdu. Il est possible que cela ne soit pas le shéma de fonctionnement désiré. Dans ce cas, il faut utiliser `>>`. 

### L'entrée standard
Ce canal défini d'où provient l'information que la commande utilise pour fonctionner. Par défault il s'agit du texte tapé par l'utilisateur sur son clavier, mais il est possible de changer cela pour un fichier ou même par une autre commande.

Pour rediriger l'entrée standard, il est possible de se servir de `<`. Ce mode de fonctionnement est sensiblement la même chose que de passer l'élément en tant qu'argument, et il n'y a pas de différence majeure entre les deux syntaxes ci-dessous: 

```bash
cat mon_fichier.txt

cat < mon_fichier.txt
```

### L'erreur standard
Par défaut, les erreurs seront également affichées dans le terminal. Il est cependant aussi possible de modifier ce comportement pour qu'elle ne viennent pas poluer notre affichage (par exemple les envoyer dans un fichier de log).

Si notre objectif est la redirection du flux d'erreur, il est nécessaire de se srvir de `2>` ou `2>>`. 

### Combiner les flux

Il est possible de procéder à la combinaisons des différentes notions vues précemment, par exemple, on pourrait avoir une syntaxe de la sorte: 

```bash
sort test.txt > mon_resultat.txt 2> errors.txt
```

Si l'on le veut, il est possible d'user de `2>&1` ou de `&>` dans le but de rediriger à la fois la sortie standard et l'erreur standard vers le même chemin.

```bash
sort test.txt &> result_and_errors.txt
```

---

[retour](../README.md)