---
id: forceatlas2
title: Force atlas 2
---

ForceAtlas2 je *force-directed* *layout*. Vrcholy se navzájem odráží, jako nabité částice, zatím co hrany jsou přitahovány jejími vrcholy jako "pružiny".

Proces nastavení pozice vrcholu je závislý pouze na hranách vrcholů, atributy vrcholu nejsou brány v potaz.

Výsledek závisí na **počátečním stavu**, může skončit ve skorém stadiu. 

Cílem je přiblížit špatně připojené vrcholy k velmi připojeným vrcholům. Vyladit odpudivou sílu tak, aby byla slabší mezi velmi spojenými vrcholy a méně u spojených vrcholů.

![Formula](https://journals.plos.org/plosone/article/file?type=thumbnail&id=info:doi/10.1371/journal.pone.0098679.e028)

## Nastavení

### LinLog mod

Místo přitažlivé síly, jako vzdálenost mezi body je použita následující formule.

![Formula](https://journals.plos.org/plosone/article/file?type=thumbnail&id=info:doi/10.1371/journal.pone.0098679.e030)

### Gravitace

Zabraňuje odpojování, odlétávaní komponent grafu.

<!-- ![Formula](https://journals.plos.org/plosone/article/file?type=thumbnail&id=info:doi/10.1371/journal.pone.0098679.e033) -->


### Silná gravitace

Nastaví sílu, která přitahuje více vrcholy, které jsou od centra vzdálenější.

![Formula](https://journals.plos.org/plosone/article/file?type=thumbnail&id=info:doi/10.1371/journal.pone.0098679.e036)

### Měřítko

Čím vyšší hodnota, tím bude graf větší, rozptýlenější.

![Graf](https://journals.plos.org/plosone/article/figure/image?size=large&id=info:doi/10.1371/journal.pone.0098679.g004)

(Měřítko 1, 2, 10)

### Outbound attraction distribution

Distributes attraction along outbound edges. Hubs attract less and thus are pushed to the borders.

### Barnes hut

https://jheer.github.io/barnes-hut/

## Poznamky

Musí se ručně zastavit.

## Zdroj

https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0098679

https://github.com/jacomyal/sigma.js/tree/master/plugins/sigma.layout.forceAtlas2