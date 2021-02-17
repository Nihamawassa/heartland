---
title: "Economy"
weight: 2
geekdocCollapseSection: true
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

The economic model is the basic game system which powers the production of goods, the distribution of produced goods by [trade](docs/trade-system/) and [transport](docs/transport-system), and the consumption of goods.

## Definitions

The central economic spheres are production, trade and transport, and consumption:

* **Production:** localized entities (mostly farmers and industries) convert input (labour and commodities) to output commodities.
* **Trade and Transport:** the process of allocation of commodities between the production and consumption locations.
* **Consumption:** localized entities . Examples:
  * Populations provide labour as a production input and are the most important consumers of commodities.
  * Industries consume commodities only to convert them into other commodities.

Production and population entities can be sources and sinks of commodities. The sources and sinks of a province are assigned to markets. Markets are the nodes of a trade network connecting all markets. The edges between the nodes are the trade lines travelled by various forms of [transporters](docs/transport-system/transporter/) (ox-wagon, boat, train).

Definitions of the economic model:

* **Network:** the network is where all trade activity happens. It consists of nodes and edges connecting the nodes. There is a set of edges per node. The amount of edges per node may depend on the economic activity or relative location of the node. The network is procedurally generated during map creation. The player can restructure the network by building infrastructure like railways and canals.
* **Node/Market:** a market bundles all sources and sinks of a province.
* **Edge:** an edge connects two nodes. Goods are transported along edges between nodes.
* **Source:** all sources produce output. Output is added to the total supply at the source location. In general all sources are settlements. Their output is defined by the local inhabitants and buildings.
* **Sink:** all sinks need input. In the first game implementation, sinks calculate their demanded input amount and composition regardless of supply prices. In a future implementation they may calculate their demand with their respective utility function. Taking into account the current supply prices at their locations.
* **Transport cost:** the cost for transporting one unit of goods along an edge between two nodes. It is calculated by the time needed to travel between both nodes and the medium of transport.
* **Production cost:** the cost to produce one unit of a good. It is influenced by local supply cost of input resources, labour cost, and profit margin.
* **Supply amount:** the amount of goods at a location.
* **Supply price:** location dependent price of a unit of goods. It is equal to the production cost at the source of the good. At a node different from the source node the supply price is the sum of production cost and transport costs of each edge travelled from source node to the node.
* **Demand amount:** the amount the sinks want to buy
* **Demand price:** the price the sinks want to pay per one unit of requested good

## Sources and Sinks: Core of the Game Model

All economy happens at good sources and good sinks, represented on the game map as settlements.

Output efficiency: Output rate per input. Inputs can be raw resources or labour (workers).
