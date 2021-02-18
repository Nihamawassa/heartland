---
title: "Trade Network"
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

The trade network is a “minimum spanning tree” of all markets on the map. The Dijkstra-algorithm is used for pathfinding, since it is not possible to use an heuristic as in the A*-algorithm (is that true?).

## Nodes and Edges

* **Nodes**: markets as in tile location of a [market](docs/trade-system/market)
* **Edges**: transport cost in money of transporting one ton of goods between two markets

## Usage and Notes

* To calculate the total price of a good offered on another market
* This network should be regularly updated to get it as close as possible to a [complete graph](https://en.wikipedia.org/wiki/Complete_graph).
