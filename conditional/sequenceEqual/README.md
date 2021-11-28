# sequenceEqual
L'opérateur "**sequenceEqual**" permet de retourner un observable envoyant la valeur
true si l'observable source retournent la même séquence de valeurs qu'un deuxième observable
(mêmes valeurs dans le même ordre). 

N.B. : il est possible de fournir une fonction pour comparer deux par deux les valeurs émises.

```javascript
sourceObservable.pipe(
    deuxieme_observable
);

sourceObservable.pipe(
    deuxieme_observable,
    (valeur_source, valeur_deuxieme_observable) => true_si_identique_sinon_false
);
```
L'opérateur "**sequenceEqual**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable
2. Création d'une variable résultat ayant la valeur true
3. Compare les premières valeurs émises par l'observable source et le second observable, 
   s'ils sont différents, affectation de la valeur **false** à
   la variable résultat... Et ainsi de suite pour les 2 valeurs suivantes
4. Si l'observable source et le second observable n'émettent pas le même nombre de valeurs, 
   affectation de la valeur **false** à a variable résultat
6. Envoi de la valeur résultat à l'observer
7. Envoi de la notification "**complete**" à l'observer

![sequenceEqual](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/conditional/sequenceEqual/sequenceEqual.puml)

### Usage

Cet opérateur peut être utile pour vérifier si deux observables émettent la même sequence de valeurs,
ou si un observable émet une séquence de valeurs attendue.
