# filter
L'opérateur "**filter**" permet de filtrer les valeurs envoyées par
l'observable source et de transmettre seulement celles qui passent une condition.

Pour cela, on fournit à l'opérateur une fonction de test qui reçoit une valeur
et doit dire si cette valeur vérifie la condition ou non (en renvoyant respectivement
true ou false).


```javascript
sourceObservable.pipe(
    // ne garde que les nombres pairs
    filter(val => val % 2 === 0)
);
```

L'opérateur "**filter**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable
2. A chaque fois que l'observable source envoie une valeur, test de cette valeur avec
   la fonction de condition
3. Si la fonction de condition retourne **true**, envoi de la valeur à l'observer
4. Reception de la notification "**complete**" émise par l'observable source
5. Envoi de la notification "**complete**" à l'observer

![filter](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/filtering/filter/filter.puml)

### Usage

Cet opérateur est utile pour filtrer les valeurs d'un observable selon une condition.