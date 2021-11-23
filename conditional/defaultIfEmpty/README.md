# defaultIfEmpty
L'opérateur "**defaultIfEmpty**" permet de créer un observable qui envoie une valeur par défaut 
si l'observable source n'envoie pas de valeur, sinon les valeurs de l'observable source
sont simplement retransmis.

```javascript
sourceObservable.pipe(
    defaultIfEmpty('Valeur par défaut')
);
```

L'opérateur "**defaultIfEmpty**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable
2. Tant que l'observable source envoie une valeur, envoi de cette valeur à l'observer
3. Reception de la notification "**complete**" émise par l'observable source
4. Si aucune valeur a été transmise par la source, envoi de la valeur par défaut à l'observer
5. Envoi de la notification "**complete**" à l'observer

![defaultIfEmpty](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/conditional/defaultIfEmpty/defaultIfEmpty.puml)

### Usage

Cet opérateur est utile, comme son nom l'indique, pour retourner une valeur par défaut
si une opération ne retourne pas de valeur.
