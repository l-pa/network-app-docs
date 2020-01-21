---
id: import
title: Import
---

Importovat je možné následující soubory

## JSON

Používá [sigma.parsers.json.min.js](https://github.com/l-pa/network-app/blob/master/public/libs/plugins/sigma.parsers.json.min.js).

Může obsahovat část nastavení, které bylo nastaveno při exportu.

| Vrchol        | Popis           |
| ------------- |:-------------:|
| label      | popis |
| x      | pozice x      |
| y | pozice y      |
| attributes | Specificke nastaveni vrcholu - TODO      |
| color | barva      |
| size | velikost      |
| id | id      |

| Hrana        | Popis           |
| ------------- |:-------------:|
| attributes      | Specificke nastaveni hrany - TODO  |
| color      | barva      |
| size | velikost      |
| id | id      |
| source | zdrojovy vrchol      |
| target | koncovy vrchol      |

[Nastaveni](nastaveni.md)

Nutné atributy **nodes** a **edges**.
```
{
    "nodes":[{"label":"Popis","x":1,"y":1,"attributes":{},"color":"rgb(0,0,0)","":10,"id":"11"}],
    "edges":[{"attributes":{},"color":"rgb(0,0,0)","size":1,"id":"19","source":"11","target":"5"}],
    "settings":{"defaultNodeType":"def","defaultNodeColor":"#000","labelSizeRatio":0.8,"labelSize":"fixed","defaultEdgeType":"def","defaultEdgeColor":"#000","labelThreshold":3,"defaultLabelColor":"#fff","maxNodeSize":3,"nodeSize":"default","borderSize":2,"defaultNodeBorderColor":"#fff","defaultEdgeHoverColor":"#fff","edgeHoverSizeRatio":3,"edgeHoverColor":"default","edgeColor":"default","minArrowSize":10,"drawLabels":true}
}
```

## GEXF

Používá upravený [sigma.parsers.json.min.js](https://github.com/l-pa/network-app/blob/master/public/libs/plugins/sigma.parsers.gexf.min.js).

Popis formátu [GEXF](https://gephi.org/gexf/format/).

Minimální verze GEXF **1.2**. 

Idealně vyexportovat graf z aktuální verze [Gephi](https://gephi.org).


## GML

Pro zpracování se používá [Parser Generator for JavaScript](http://pegjs.org/), s následující gramatikou.

```
Graph = graph: _ "graph" _ "[" _ directed:("directed" _ Integer)? _ nodes:Node _ edges:Edge "]" _ {return {nodes, edges}}

Node = ( _ "node" _ "[" _ id: ("id" _ Integer) _ label: ("label" _ "\""[^"]* "\"")? _ value: ("value" _ Value )? _ source: ("source" _ "\""[^"]* "\"")? _ "]" _ {return {"id": id[2], "x": Math.random(), "y": Math.random(), "label": label == null ? "" : label[3].join(""), "size": value == null ? 1 : isNaN(value[2]) ? 1 : value[2], "source": source == null ? null : source[3].join("")}})*

Edge = ( _ "edge" _ "[" _ source: ("source" _ Integer) _ target:("target" _ Integer) _ value:("value" _ Value)? _"]" _ { return {"source": source[2], "target": target[2], 'size': value == null ? 1 : isNaN(value[2]) ? 1 : value[2] } })*

Integer "integer"
  = _ [0-9.]+ { return parseFloat(text()); }
  
Value "value"
  = _ [0-9.a-z"]+ { return parseFloat(text()) }

_ "whitespace"
  = [ \t\n\r]*
  
 __ = [ \t\r\n]+

```

## Možnosti

### Načtení pouze největší kopomenty

Zobrazení pouze největší komponenty v grafu, využívá prohledávaní do hloubky.

```js
    function DFS(node) {
      visited.push(node);
      edges.forEach(edge => {
        if (node == edge.source) {
          if (!visited.includes(edge.target)) {
            DFS(edge.target);
          }
        }

        if (node == edge.target) {
          if (!visited.includes(edge.source)) {
            DFS(edge.source);
          }
        }
      });
    }
```