# iif
La fonction "**iif**" permet de retourner un observable X si une condition est vérifiée,
sinon un observable Y. 

Pour cela on fournit à la fonction une méthode de test qui doit dire si la condition 
est vérifiée ou non.

N.B. : si vous ne fournissez que l'observable de succès et que la méthode de test retourne faux, 
une erreur sera envoyée à l'observer.

```javascript
iif(
    // fonction test
    () => vrai_ou_faux,
    observable_si_vrai,
    observable_si_faux
);

iif(
    // fonction test
    () => vrai_ou_faux,
    observable_si_vrai,
);

```

L'opérateur "**iif**" fonctionne de la manière suivante :
1. Creation d'une instance d'Observable
2. Lancement de la fonction de test
3. Si la fonction de test retourne **true**, souscrit au 1er observable et retransmet 
   les valeurs, erreurs et notification "**complete**" envoyées par celui-ci
4. Si la fonction de test retourne **false**, souscrit au 2ème observable et retransmet
   les valeurs, erreurs et notification "**complete**" envoyées par celui-ci

![iif](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/cedriclecocq/rxjs-exemple/main/conditional/iif/iif.puml)

### Usage

Cet opérateur peut être utile pour déclencher une opération ou une autre en fonction
d'une condition, ou pour déclencher une opération seulement si une condition est vérifiée.
