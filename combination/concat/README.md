# concat
La fonction "**concat**" permet de consommer des observables en séquence.


```javascript
concat(timer, sequence)
```

La fonction "**concat**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable
2. Souscription au premier observable fournit en paramètre
3. Lorsque l'observable envoie une valeur, transmission directe à l'observer
4. Lorsque l'observable envoie sa notification "**complete**"
   * si il y a un autre observable en paramètre ==> 2
   * sinon envoi de la notification "**complete**" à l'observer

![concat](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/combination/concat/concat.puml)

### Usage

Cette fonction est utile pour consommer plusieurs observables en séquence.