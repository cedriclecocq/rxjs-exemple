# empty
La fonction "**empty**" permet de générer un observable qui envoie directement 
la notification "**complete**" à l'observer.

```javascript
empty()
```

La fonction "**from**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable.
2. Envoie la notification "**complete**" à l'observer.

![empty](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/creation/empty/empty.puml)

### Usage

Cette fonction a d'utilité qu'associée avec d'autres opérateurs RxJS de plus haut niveau.

Par exemple: si tel observable répond à telle condition, lance tel observable sinon retourne un observable vide.
