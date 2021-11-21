# timer
La fonction "**timer**" permet de générer un observable émettant le nombre 0 après un délai, 
voir les nombres suivants tout les X millisecondes.

N.B. : Il est possible de préciser une date à la place du délai de départ. Mais il est à noter
que si la date est passée, l'observable enverra sa valeur immédiatement.

```javascript
// Envoyer 0 après 1000 millisecondes
timer(1000)

// Envoyer 0 après 1000 millisecondes, puis les nombres suivantes
// tout les 2 secondes
timer(1000, 2000)

// Envoyer 0 à telle date
timer(new Date('2021-11-21T23:12:00'))
```
La fonction "**timer**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable.
2. Après X millisecondes, envoi de la valeur 0.
3. Si une valeur d'intervalle est fournie, ajouter 1 à la valeur et l'envoyer après Y millisecondes.
4. Sinon, envoie la notification "**complete**" à l'observer.

![timer](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/creation/timer/timer.puml)

### Usage

L'observable, généré par cette fonction, peut être utile pour créer des délais dans une exécution, 
voir de déclencher une exécution planifiée à une date précise. 

### Voir aussi

- [interval](https://github.com/cedriclecocq/rxjs-exemple/tree/main/creation/interval) :
  pour générer une sequence de nombre en partant de zéro, asynchrone.
  (chaque valeur envoyée toutes les X millisecondes)
- [range](https://github.com/cedriclecocq/rxjs-exemple/tree/main/creation/range) :
  pour générer une sequence de nombre en partant d'un nombre spécifique.
- [generate](https://github.com/cedriclecocq/rxjs-exemple/tree/main/creation/generate) :
  pour générer une séquence de nombre personnalisée.
