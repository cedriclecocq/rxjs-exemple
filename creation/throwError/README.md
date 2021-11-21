# throwError
La fonction "**throwError**" permet de générer un observable qui envoie directement
une erreur à l'observer.

```javascript
throwError("Message d'erreur")

throwError(new Error("Message d'erreur"))
```

La fonction "**throwError**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable.
2. Envoie l'erreur à l'observer.

![throwError](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/creation/throwError/throwError.puml)

### Usage

Cette fonction a d'utilité qu'associée avec d'autres opérateurs RxJS de plus haut niveau.

Par exemple: si tel observable répond à telle condition, lance tel observable sinon retourne tel erreur.
(si l'erreur de l'observable test ne peut être retourné directement)
