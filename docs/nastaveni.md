---
id: nastaveni
title: Nastaveni
---

Nastavení grafu, pravý panel.

# Select nodes

[sigma.plugins.lasso.js](https://github.com/s0md3v/Quark/tree/master/libs/plugins/sigma.plugins.lasso)

Vytvoří novou vrstvu, na které lze vymezit plochu, ze které se vyberou body a hrany a přidají do nové [skupiny](skupiny.md).

# Export

[Export](export.md)

## Node

### Detail

Po kliknutí na vrchol, lze změnit nastavení vrcholu

- Nazev
- Barva
- Velikost

### Node type

Default - kruh

- pacman
- star - hvězda
- equiteral - 5tiuhelnik
- cross - kříz
- diamond - diamand
- cricle - kruh - default
- square - čtverec

### Node size

#### Default

Používá velikost nastavenou ze vstupního souboru.

#### Fixed

Pevná velikost pro všechny vrcholy.

#### Degree

Velikost podle počtu stupně vrcholu.

#### Degree In

Velikost podle počtu hran přicházejícího do vrcholu.


#### Degree Out

Velikost podle počtu hran vycházejícího z bodu.

### Min size of nodes

Relativní minimální velikost vrcholů, vzhledem k velikostem ostatních vrcholů.

### Max size of nodes

Relativní maximální velikost vrcholů, vzhledem k velikostem ostatních vrcholů.

## Label

### Show labels

Zobrazit popis u vrcholu.

### Label threshold

Minimální velikost vrcholu, aby byl zobrazený jeho popis.

### Label size

Velikost popisu.

#### Fixed

Pevná velikost, pro všechny vrcholy.

#### Proportional

Velikost popisu, podle velikosti vrcholu.

### Label color

Barva popisu.

## Edge

### Edge color

Pokud není specifikována barva hrany ve vstupním souboru, lze jí změnit.

### Edge size

Velikost hrany

#### Default

Výchozí velikost, podle velikosti uvedené s souboru.

#### sizeAsNode

Velikost hrany je stejná jako velikost zdrojového vrcholu hrany.


### Edga shape

Tvar hrany.

#### Def

Rovná hrana.

#### Curve

Zahnutá hrana.

### Directed

Možnost zobrazit směr jednotlivých hran.

### Min size of edges

Relativní minimální velikost hran, vzhledem k velikostem ostatních hran.

### Max size of edges

Relativní maximální velikost hran, vzhledem k velikostem ostatních hran.

## Komunity

[Komunity](louvain.md)

## Layouty

[Layouty](forceatlas2.md)