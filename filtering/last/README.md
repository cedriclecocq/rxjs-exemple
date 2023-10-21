# last
L'opérateur "**last**" permet de retourner la dernière valeur (qui passe potentiellement
une condition) envoyée par l'observable source.

On peut fournir à l'opérateur une fonction de test qui reçoit une valeur
et doit dire si cette valeur vérifie la condition ou non (en renvoyant respectivement
true ou false).


```javascript
sourceObservable.pipe(
    // retourne la dernière valeur
    last()
);

sourceObservable.pipe(
	// retourne la dernière valeur paire
	last(val => val % 2 === 0)
);
```

L'opérateur "**filter**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable 
2. Création d'une variable last ayant la valeur undefined
3. À chaque envoi de valeur par l'observable source, mise à jour de cette variable avec cette valeur
   (et si celle-ci potentiellement satisfait une fonction de test)
4. Lorsque l'observable source envoi sa notification "**complete**"
   * Si la variable last contient une valeur, envoi de la valeur et de la notification 
     "**complete**" à l'observer
   * Sinon
     * si une valeur par défaut a été définie, envoi de la valeur par défaut et de la notification
       "**complete**" à l'observer
     * sinon envoi d'une erreur à l'observer


![first](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/filtering/last/last.puml)

### Usage

Cet opérateur est utile pour retourner la dernière valeur d'un observable (qui potentiellement
satisfait une condition).