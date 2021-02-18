---
title: "Infrastructure Construction Cost"
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

Cost for constructing infrastructure is implemented as a [network](docs/gameworld/networks/) graph.

## Nodes and Edges

* **Nodes**: tile locations
* **Edges**: links between two adjacent tiles. The cost of the edge is the construction cost in money to connect two tiles.

## Use and Notes

* There are separate networks for land and sea tiles
* There are separate networks for each transport type: roads, railroads, sea lanes, waterways
