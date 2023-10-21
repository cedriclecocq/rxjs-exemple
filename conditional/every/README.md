# every
L'opérateur "**every**" permet de vérifier si toutes les valeurs envoyées par
l'observable source passe une condition : si c'est le cas, le booléen **true**
est envoyé à l'observer, sinon c'est le booléen **false** qui est envoyé.

Pour cela, on fournit à l'opérateur une fonction de test qui reçoit une valeur
et doit dire si cette valeur vérifie la condition ou non (en renvoyant respectivement
true ou false).

N.B. : si aucune valeur n'est envoyée par l'observable source, l'opérateur envoie
la valeur true.

```javascript
sourceObservable.pipe(
    // vérifie que toutes les valeurs sont inférieurs ou équales à 20
    every(val => val <= 20)
);
```

L'opérateur "**every**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable
2. Création d'une variable résultat ayant la valeur true
3. A chaque fois que l'observable source envoie une valeur, test de cette valeur avec 
   la fonction de condition
4. Si la fonction de condition retourne **false**, affectation de la valeur **false** à
   la variable résultat
5. Reception de la notification "**complete**" émise par l'observable source
6. Envoi de la valeur résultat à l'oberver
7. Envoi de la notification "**complete**" à l'observer

![every](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/conditional/every/every.puml)

### Usage

Cet opérateur peut être utile pour vérifier que toutes les valeurs d'un observable
vérifie une même condition.
