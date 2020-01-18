---
id: circle
title: Circle
---

## Algoritmus

Body jsou rozmístěny rovnoměrně na kružnici.

```js
                    const slice = 2 * Math.PI / itemsLength
                    
                    for (var i = 0; i < itemsLength; i++) {
                        const angle = slice * i

                        const x =  r * Math.cos(angle);
                        const y =  r * Math.sin(angle);
                        sortedGraph[i].x = x;
                        sortedGraph[i].y = y;
                    }
```

## Poznamky

Při použití [komunit](louvain) se body podle nich uspořádají.