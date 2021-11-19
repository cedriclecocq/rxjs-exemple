# of
La fonction "**of**" permet de générer un observable émettant en séquence les valeurs 
qu'on lui donne en arguments.

```javascript
of(10, 20, 30)
```

La fonction "**of**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable
2. Envoi du premier argument à l'observer
3. Envoi de l'argument suivant et ainsi de suite
4. Si il n'y a plus d'arguments, envoie la notification "**complete**" à l'observer

*N.B. : les arguments sont envoyés tel-quel : pas de transformation. 
Si vous fournissez un tableau de valeurs, c'est le tableau en entier qui sera envoyé.*

![of](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/creation/of/of.puml)

### Usage

Cette fonction est souvent utilisée pour créer simplement un Observable à partir d'une valeur 
et ainsi l'utiliser dans des opérateurs par exemple.
