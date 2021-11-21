# interval
La fonction "**interval**" permet de générer un observable émettant une séquence de nombres
tout les X millisecondes.

```javascript
interval(250)
```

La fonction "**interval**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable.
2. Initialisation d'une valeur à 0.
3. Après X millisecondes, envoi de la valeur.
4. Ajout de 1 à la valeur de N.
5. Aller à l'étape 3.

![interval](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/creation/interval/interval.puml)

### Usage

L'observable, généré par cette fonction, peut être utilisé pour déclencher des traitements
à intervalles réguliers par exemple.

### Voir aussi

- [range](https://github.com/cedriclecocq/rxjs-exemple/tree/main/creation/range) :
pour générer une sequence de nombre en partant d'un nombre spécifique.
- [generate](https://github.com/cedriclecocq/rxjs-exemple/tree/main/creation/generate) :
pour générer une séquence de nombre personnalisée.
