# first
L'opérateur "**first**" permet de retourner la première valeur (qui passe potentiellement 
une condition) envoyée par l'observable source.

On peut fournir à l'opérateur une fonction de test qui reçoit une valeur
et doit dire si cette valeur vérifie la condition ou non (en renvoyant respectivement
true ou false).


```javascript
sourceObservable.pipe(
    // retourne la première valeur
    filter()
);

sourceObservable.pipe(
	// retourne la première valeur paire
	filter(val => val % 2 === 0)
);
```

L'opérateur "**filter**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable
2. À la première valeur envoyée par l'observable source (et qui potentiellement satisfait
   une fonction de test), envoi de la valeur à l'observer
3. Envoi de la notification "**complete**" à l'observer


![first](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/filtering/first/first.puml)

### Usage

Cet opérateur est utile pour retourner la première valeur d'un observable (qui potentiellement
satisfait une condition).