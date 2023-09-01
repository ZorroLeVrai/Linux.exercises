## Scripts shell

### Exercice 1

Ecrivez un script qui demande à un utilisateur d'entrer son prénom puis son nom.  
Puis affichez un texte de ce format.  
`Bonjour <prénom> <nom>`

```bash
#!/bin/sh

echo "Entrez votre prénom:"
read prenom
echo "Entrez votre nom:"
read nom
printf "Bonjour %s %s\n" $prenom $nom

```

### Exercice 2

Ecrivez un script qui prend n arguments en entrée et qui affiche chaque argument dans une ligne.

```bash
#!/bin/bash

# Check if at least one argument is provided
if [ $# -eq 0 ]; then
    echo "Syntaxe: $0 <arg1> <arg2> ..."
    exit 1
fi

# Loop through the arguments and write each one on a separate line
for arg in "$@"; do
    echo "$arg"
done
```
