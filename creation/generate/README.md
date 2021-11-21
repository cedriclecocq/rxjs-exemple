# generate
La fonction "**generate**" permet de générer un observable émettant une séquence de nombres
personnalisés.

Pour cela on précise (à la manière d'une boucle "**for**") :
- le nombre de départ
- une fonction pour conditionner la poursuite de la boucle (doit retourner oui pour autoriser la poursuite 
  de la boucle non)
- une fonction pour itérer le nombre à chaque passage de la boucle

```javascript
generate(
    // partons de la valeur 5
    5,
    // tant que la valeur est inférieur à 30
    x => x < 30,
    // à chaque passage, augmentez la valeur de 2
    x => x + 2
)
```
La fonction "**generate**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable.
2. Initialisation d'une valeur à la valeur de départ.
3. Lance la fonction condition pour déterminer si la boucle continue, si oui passe à l'étape suivante 
   sinon passe à l'étape 7.
4. Envoi la valeur à l'observer.
5. Lance la fonction d'itération pour modifier la valeur.
6. Retourne à l'étape 3.
7. Envoi de la notification "**complete**" à l'observer.

![generate](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/creation/generate/generate.puml)

N.B. : Les valeurs sont envoyées de manière synchrone. (Pour les envoyer de manière asynchrone,
voir les "**Scheduler**")

### Voir aussi

- [interval](https://github.com/cedriclecocq/rxjs-exemple/tree/main/creation/interval) :
  pour générer une sequence de nombre en partant de zéro, asynchrone.
  (chaque valeur envoyée toutes les X millisecondes)
- [range](https://github.com/cedriclecocq/rxjs-exemple/tree/main/creation/range) :
  pour générer une sequence de nombre en partant d'un nombre spécifique.
- [timer](https://github.com/cedriclecocq/rxjs-exemple/tree/main/creation/timer) :
  pour envoyer la valeur zéro après un délai ou à partir d'une date, puis potentiellement
  la valeur incrémentée toutes les X millisecondes.
- Les "**Scheduler**"
