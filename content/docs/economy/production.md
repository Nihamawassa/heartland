---
title: "Production"
weight: 1
geekdocCollapseSection: true
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

Production is separated in production by population and production in production buildings like factories and mines. Production by population is defined in [Population](docs/the-nation/population/).

The Leontief production function is used for output calculation. All production functions are defined in a “Production” class.

Agricultural Production:

* Parameters:
  * maxCerealsYield: amount of the maximum cereal production of a tile
  * cerealsYieldRate: percentage per tile: 100% best place to grow cereals, 0% no cereals grow here
  * f(farmers): triangle function with maximum value of 1. If possible the optimal amount of famers is used to work on the respective tile
* Food per tile = maxCerealsYield x cerealsYieldRate x f(farmers)

The same formula is used for cloth production by farmers. The parameters are instead maxGrazingYield and grazingYieldRate and output is clothing per tile.

Farmers are assigned to field tiles and pasture tiles.

### Production Functions of Populations

production(raw materials, supporting materials, work, limiting factors):

* Raw materials are required input factors get transformed into production output.
* Supporting materials are dispensable input factors. They may increase the conversion rate from raw materials into production output. They may reduce the amount of work needed per production output.
* Work is the amount of farmers/artisans/workers available per time unit.
* Limiting factors: available farmland, factory size, and others
