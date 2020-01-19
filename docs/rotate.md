---
id: rotate
title: Rotate
---

Natočení grafu o daná uhel.

## Algoritmus


```js
          const sin = Math.sin((-angle.current * Math.PI) / 180);
          const cos = Math.cos((-angle.current * Math.PI) / 180);

          window.network.graph.nodes().forEach(n => {
            const dx = n.x;
            const dy = n.y;

            n.x = dx * cos - dy * sin;
            n.y = dy * cos + dx * sin;
          });
```