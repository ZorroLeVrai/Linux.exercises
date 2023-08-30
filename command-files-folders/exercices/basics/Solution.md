# Exercice de création de fichiers et de dossiers

Pour pratiquer la création de fichiers et de dossiers à partir de la ligne de commande, nous allons créer une structure de fichiers de projet standard pour React. Ne vous inquiétez pas du tout si vous ne connaissez pas React, nous allons simplement créer un tas de fichiers et de dossiers vides !

- Créez un nouveau dossier appelé `my-app`.

mkdir my-app

- Accédez à `my-app` et à l'intérieur, créez deux nouveaux fichiers vides appelés `README.md` et `package.json`.

cd my-app  
touch README.md package.json

- Toujours à l'intérieur de `my-app`, créez un nouveau dossier appelé `public`. Sans utiliser `cd` pour vous déplacer dans `public`, créez un fichier `index.html` à l'intérieur de celui-ci.

mkdir public  
touch public/index.html

- Créez un nouveau dossier appelé src à l'intérieur de `my-app`. Accédez à l'intérieur.

mkdir src  
cd src

- En une seule ligne, créez les quatre fichiers suivants à l'intérieur de `src`: `App.css`, `App.js`, `index.css` et `index.js`.

touch App.css App.js index.css index.js

Votre structure de dossier devrait maintenant ressembler à ceci :

```bash
my-app/
  README.md
  package.json
  public/
    index.html
  src/
    App.css
    App.js
    index.css
    index.js
```

Vous pouvez vérifier votre arborescence en exécutant la commande  
`tree .`  
dans votre répertoire.

### BONUS

> 💡 En utilisant une seule commande, créez un nouveau répertoire à l'intérieur de `src` appelé `components`, et à l'intérieur de ce nouveau répertoire `components`, créez un nouveau répertoire appelé `Navbar`. Faites ceci en une seule commande, sans créer au préalable le répertoire `components`.

mkdir -p components/Navbar

Votre structure de dossier devrait maintenant ressembler à ceci :

```bash
my-app/
  README.md
  package.json
  public/
    index.html
  src/
    components/
      Navbar/
    App.css
    App.js
    index.css
    index.js
```
