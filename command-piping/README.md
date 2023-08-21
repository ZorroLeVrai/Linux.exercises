# Le Piping

Via l'utilisation du caractère `|`, il est possible de passer le résultat d'une première commande à la suivante. Ce processus, répétable autant de fois qu'on le veut, et combiné avec les redirections, est au coeur des capacités bien plus grandes du terminal par rapport à une interface graphique classique. La syntaxe, dans ses grande ligne, ressemble à ceci:

```bash
commandeA | commandeB
```

Contrairement à la syntaxe de la redirection classique `>`, l'utilisation des pipes sert pour relier une commande ou son résultat à une autre commande. La redirection, elle, vise àconnecter un fichier à une commande. 

Dans la grande majorité des cas, le résultat d'un visionnage d'informations multiples sera pipé en direction de la commande **less** de sorte à offrir un visuel plus aggréable et plus de fonctionnalité qu'un simple affichage:

```bash
ls -l /usr/bin | less
```

### tr

La commande `tr` demande à l'utilisateur de lui transmettre des information via l'entrée standard. Son objectif est de transformer du texte en un autre. Compatible avec les expressions régulière, cette commande est assez pratique lorsque l'on veut manipuler rapidement un fichier. Si les expressions régulières ne sont notre tasse de thé, il est possible de se servir de classes de caractères, dont la syntaxe ressemble à `[:alpha:]`, `[:blank:]`, etc...

### Chainer les commandes

Via l'utilisation des pipes, il devient donc possible de réaliser des demander complexe à notre terminal, comme par exemple de demander quel est le plus gros fichier se trouvant à un certain emplacement de la structure des fichiers système : 

```bash
ls -lh /usr/bin | sort -hk5 | tail -1 > largest_file.txt

du -h /usr/bin | sort -h | tail -1 > largest_file.txt
```

### tee

Imaginons maintenant que l'on veuille passer la sortie d'une commande intermédiaire dans un fichier mais également se servir de ce résultat dans une commande chainée. La syntaxe à utiliser sera différente et demandera l'utilisation de la commande `tee`. qui sert à convertir une entrée standard en un fichier tout en la laissant disponible en tant que sortie standard: 

```python
commandA | tee filename.txt | commandB
```

---

[Retour](../README.md)