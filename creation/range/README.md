# range
La fonction "**range**" permet de générer un observable émettant une séquence de nombres
en partant du chiffre X.

Notez qu'il est possible de préciser combien de nombre doivent être générés, 
sinon les nombres seront générés indéfiniment.

```javascript
// Sequence de nombre partant de 5
range(5)

// Sequence de 10 nombres partant de 3
range(3, 10)
```

La fonction "**range**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable.
2. Initialisation d'une valeur à X.
3. Tant que N valeurs n'ont pas été envoyées ou si pas de limite, envoi de la valeur 
et ajout de 1 à celle-ci.
4. Envoi de la notification "**complete**" à l'observer.

![range](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/creation/range/range.puml)

N.B. : Les valeurs sont envoyées de manière synchrone. (Pour les envoyer de manière asynchrone,
voir les "**Scheduler**")

### Voir aussi

- [interval](https://github.com/cedriclecocq/rxjs-exemple/tree/main/creation/interval) :
  pour générer une sequence de nombre en partant de zéro, asynchrone. 
  (chaque valeur envoyée toutes les X millisecondes)
- [generate](https://github.com/cedriclecocq/rxjs-exemple/tree/main/creation/generate) :
  pour générer une séquence de nombre personnalisée.
- Les "**Scheduler**"
