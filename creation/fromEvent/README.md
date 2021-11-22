# fromEvent
La fonction "**fromEvent**" permet d'encapsuler des événements DOM ou un EventEmitter Node.js 
dans un observable.

Pour cela, on va préciser :
- la cible DOM ou l'EventEmitter Node.js
- le nom de l'événement à écouter

```javascript
fromEvent(document, 'click')
```

### Usage

Cette fonction permet d'encapsuler un événement natif pour l'exploiter avec les opérateurs
RxJS.
