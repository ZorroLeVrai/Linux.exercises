# Obtenir de l'aide

Si l'on veut obtenir le descriptif, les arguments ainsi que les options possibles d'une commande, il est possible de passer par la commande d'appel du manuel. Cette commande prend en argument le nom de la commande dont on veut obtenir la documentation sous la forme suivante: 

```bash
man nom_commande
```

- Pour sortir du manuel, il faut appuyer sur la touche `q`
- Pour monter ou descendre dans la page actuelle, il faut utiliser les flèches du clavier `Haut` / `Bas`
- Pour passer d'une page à la suivante, on peut se servir de la touche `Espace` / `F` pour aller vers l'avant ou la touche `B` pour aller vers l'arrière
- En appuyant sur `H`, on obtient toutes les commandes possible pour naviguer le manuel

Si l'on veut, il est aussi possible de rechercher dans le manuel via l'utilisation du caractère `/` suivi d'une entrée utilisateur. En cas de correspondance, la ou les correspondances seront mises en valeur.

### Les sections

Le manuel utilisateur propose plusieurs sections, la liste des commandes n'étant que la première et celle affichée par défaut. Nous avons donc à notre disposition les sections suivantes:
- Commandes utilisateurs
- Appels système
- Fonction de libraries C
- Fichiers spéciaux
- Formulaires de fichiers
- Jeux
- Autre
- Commandes administrateur

Si l'on le veut, il est possible d'accéder non pas à la section 1 du manuel lorsqu'on demande la page manuel d'une commande, mais à une section spécifique. Pour ce faire, la syntaxe est légèrement différente: 

```bash
man numero_section nom_commande
```

### type / which

Il existe plusieurs types de commandes: 
- Les programmes exécutables généralement stockés dans **/bin**, **/usr/bin**, **/usr/local/bin**
- Les commandes associées au shell (dans notre cas bash)
- Les fonctions de shell
- Les alias

Via l'utilisation de la commande `type` on peut connaitre quel est le type de la commande qu'on passe en argument:

```bash
type nom_commande
```

D'un autre côté, la commande `which` est une commande permettant de connaître l'emplacement des exécutables. Elle ne marchera donc que pour les exécutables.

```bash
which cd # Ne renvoie rien

which mkdir # /usr/bin/mkdir
```

### help

Si aucune page de manuel n'existe pour une certaine commande, il est possible qu'une aide soit cependant disponible. Pour accéder à cette aide, la commande `help` suivie en argument du nom de la commande dont nous désirons l'aide est disponible. La plupart des commandes intégrées au shell possèdent une version **help** et non une version **man**: 

```bash
help nom_commande
```

---

[Retour](../README.md)