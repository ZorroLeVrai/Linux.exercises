# Trouver de l'aide en lignes de commande

- Il y a une commande appelée `whoami`. **Avant de l'exécuter**, lisez l'entrée de la page du manuel la concernant. À partir de l'entrée de la page du manuel, pouvez-vous dire si elle nécessite des options ou des arguments ? Que fait-elle ?

En exécutant la commande  
`man whoami`  
ou
`whoami --help`  
On peut voir que cette commande affiche la nom de l'utilisateur.
Elle n'a pas besoin de paramètres mais elle peut prendre une option.

- Maintenant, essayez de l'exécuter ! Que se passe-t-il ?

```
Le nom de l'utilisateur courant s'affiche.
```

- Il y a une autre commande appelée `who`. Sans utiliser Google, découvrez ce qu'elle fait ! Nécessite-t-elle des arguments ou des options pour s'exécuter ?

En exécutant la commande  
`man who`  
ou
`who --help`

On peut voir que cette commande affiche des informations concernant l'utilisateur qui est actuellement loggé.

- Utilisez la commande `who` pour afficher l'heure du dernier démarrage du système. Vous devrez trouver une option pour vous aider à le faire !

La commande à exécuter est  
`who -b`

- Exécutez une commande pour déterminer si la commande `echo` est un binaire, une commande intégrée au shell ou un alias.

Exécutez la commande  
`type echo`  
On obtient  
_echo is a shell builtin_  
Ce qui veut dire que cette commande est intégrée au shell.

- Faites de même pour la commande `date`.

Exécutez la commande  
`type date`  
On obtient  
_date is hashed (/usr/bin/date)_  
Ce qui veut dire que cette commande est un binaire.
