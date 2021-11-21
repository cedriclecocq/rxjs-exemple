# NEVER
La constante "**NEVER**" contient un observable qui n'envoie aucune valeur 
ni de notification "**complete**" à l'observer à l'observer.

```javascript
NEVER
```

### Usage

Cette constante peut être utilisée pour faire des tests.
(Notez que cet observable n'émettant pas de notification "**complete**", 
les "**subscriptions**" doivent être fermées manuellement).
