# from
La fonction "**from**" permet de générer un observable emettant des valeurs à partir 
d'un tableau, d'une promesse ou d'un objet Iterable.

*N.B. : pour les tableaux et les objets itérables, les valeurs sont émises en séquence, valeur par valeur.*

```javascript
// Tableau
from([10, 20, 30])

// Iterable
from("abcdef")

// Promesse
from(Promise.resolve(123))
```

La fonction "**from**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable.
2. Si le paramètre est un tableau, itère sur le tableau et retourne chaque valeur séparement à l'observer.
3. Si le paramètre est un Iterable, itère sur celui-ci et retourne chaque valeur séparement à l'observer.
   * Quand il n'y a plus de valeurs, envoie la notification "**complete**" à l'observer.
4. Si le paramètre est une Promesse, attend qu'elle soit résolue pour retourner la valeur. 
   * Si la promesse est rejetée, retourne l'erreur à l'observer.

![from](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/creation/from/from.puml)

### Usage

Cette fonction est souvent utilisée pour créer simplement un Observable à partir d'un tableau de valeur 
(ou d'un Iterable) et ainsi d'utiliser la séquence de valeur dans des opérateurs RxJS.

Cette fonction est aussi utilisée pour transformer une promesse en observable et de l'utiliser 
ainsi dans des opérateurs RxJS.
