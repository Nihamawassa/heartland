---
title: "Map Generation"
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

Detailed information about the map generation.

## River Generation
* Rivers flow in straight lines from tile to tile. They do not flow diagonally to another tile.
* Generation:
  * For every tile find the neighboring tile with the steepest decline between both tiles. This sets the flow direction of the tile.
  * Set a base water amount to every tile using the respective moisture values.
  * Go through all tiles according to their hight value starting at the highest tile. For each tile set the flow amount of the flow direction to the base water amount. Add the base water amount to the base water amount of the tile targeted by the flow direction.
  * Set river tiles to all tile with a flow amount above a set threshold value.

## Farmland and Pasture Generation
* The total of the farmland amount and pasture amount of a tile has a max amount of 100 (percent)
* Farmland is always calculated first, pasture is calculated for the remaining total
* Both values are influenced by moisture, temperature, and elevation (more mountainous regions have less space to do agriculture and herding)
* Farmland needs medium moisture and medium to high temperatures. It drops fast in high altitudes
* Pasture needs lower moisture than farming and is also less sensitive to lower temperatures and high altitudes