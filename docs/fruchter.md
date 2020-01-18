---
id: fruchter
title: Fruchterman Reingold
---

The Fruchterman-Reingold Algorithm je *force-directed* *layout*. V tomto algoritmu jsou vrcholy reprezentovány jako kroužky a hrany mezi nimi jako pružiny. Základní myšlenka je minimalizovat "energii" přesouváním vrcholů a měnění síly mezi nimi.

Součet vektorů síly určuje, kterým směrem se má vrchol pohybovat. Šířka kroku je dána konstantou a určuje jak daleko se vrchol posune v jednom kroku. *Když je energie systému minimalizována, tak se vrcholy přestanou pohybovat, systém dosáhl rovnováhy.*

## Nastaveni

### autoArea

Velikost plochy grafu je **počet bodů ^ 2**

### area

Pokud je vybrána možnost **autoArea**, tak není **area** použita.

Velikost plochy grafu.

### gravity

Síla přitahující vrcholy ke středu.

Zabraňuje odpojování, odlétávaní komponent grafu.

### speed !!!!!!

Vyšší hodnota = nižší přesnost

### iterations

Počet opakování algoritmu.

## Zdroj

https://github.com/Linkurious/linkurious.js/tree/develop/plugins/sigma.layouts.fruchtermanReingold

https://github.com/gephi/gephi/wiki/Fruchterman-Reingold

http://citeseer.ist.psu.edu/viewdoc/download;jsessionid=19A8857540E8C9C26397650BBACD5311?doi=10.1.1.13.8444&rep=rep1&type=pdf