---
title: Transport Network
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

The Transport Network is part of the [Transport System](articles/transport-system).

At startup the game generates a Transport Network. This network includes roads, sea lanes, and waterways.

## Nodes and Edges

* **Nodes**: tile location and type of transport (e.g. road crossing, rail crossing, train station, port)
* **Edges**: links between to adjacent tiles. The nodes of the edge define its type. E.g. if both nodes are of type road crossing, the edge is a road. The cost of the edge is the time (in hours) a [transporter](focs/transport-system/transporter/) needs to move from node to node.

## Use and Notes

* To pathfind routes for transporters
* To move transporters from tile to tile
* To change the transporter’s type (cart, train, boat, ship)
* Transporters consume goods based on time. Therefore they choose the shortest path. Some transport types may be cheaper than others per hour. This may have to be considered when calculating the path!
