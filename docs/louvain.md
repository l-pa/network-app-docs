---
id: louvain
title: Louvain community detection
---

Louvainova metoda je jednoduchá, efektivní a snadno implementovatelná metoda pro identifikaci komunit ve velkých sítích.

## Algoritmus

Algoritmus je rozdělen na dvě fáze.

Nejprve vytvoříme pro každý vrchol komunitu. Každý vrchol je ve své vlastní komunitě. Poté se pro každého souseda vrcholu vyhodnotí, jakou by získal modularitu, kdyby se přesunul ze své komunity do komunity souseda.

Vrchol je přesunut do komunity s největší kladnou modularitou,
pokud nezíská žádnou kladnou modularitou tak zůstává ve své komunitě.

Tento proces se opakuje pro všechny vrcholy do doby, dokud již není možné získat lepší výsledek, neexistuje lepší modularita pro vrchol.

Tímto je ukončena první fáze.

Ve druhé fázi se tvoří síť, kde vrcholy jsou komunity vytvořené v první části. Váhy hran mezi novými vrcholy jsou dány jako součet vah hran vrcholů ve dvou odpovídajících komunitách.

Počet komunit se snižuje a výpočetní čas je menší s každým opakováním těchto dvou fází.

Opakování fází probíhá do doby, dokud již není možné získat lepší modularitu a nenastávají změny v komunitách.

![Formula](https://wikimedia.org/api/rest_v1/media/math/render/svg/fb8524ddd4e6441ac4aea720d93f4aa8b9efa28a)

## Zdroj

https://github.com/upphiminn/jLouvain

https://arxiv.org/pdf/0803.0476.pdf

https://en.wikipedia.org/wiki/Louvain_modularity