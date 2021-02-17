---
title: Trade System
weight: 2
geekdocCollapseSection: true
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

The markets are organised in the same way as the nation. On the national level, there is the National Market. On the provincial level, there are the Provincial Markets. One at each market town (settlement). Each population group and each industry (sources) acts as an individual trader. They are provincial traders.

{{< mermaid class="text-center">}}
graph TD
    N[National Market] --- A[Provincial Market A]
    N --- B[Provincial Market B]
    N --- C[Provincial Market C]
    A --- T1[Trader]
    A --- T2[Trader]
    B --- T3[Trader]
    B --- T4[Trader]
    C --- T5[Trader]
    C --- T6[Trader]
{{< /mermaid >}}

The trade system has the components:
{{< toc-tree >}}

## Definitions

* **Unit price:** valuation of one unit of a good by the trader. A seller sets the ask unit price as the lowest amount of money he wants to sell a good for. A buyer sets an offer unit price as the highest amount of money he is willing to purchase a good for.
* **Offer:** contains the following pieces of information: source trader, trade good type, amount, ask unit price
* **Bid:** contains the following pieces of information: sink trader, trade good type, amount, bid unit price
* **Transport costs:** Markets know the “shortest” path to all other connected markets. This knowledge is stored in transport cost tables. Markets may update these tables regularly.

## Simplifications of the trade model

* All sinks and sources are located in a province (settlement). For example a coal mine is represented on the map as a tile in the vicinity of a settlement. But in the model the mine belongs to the settlement. From the viewpoint of the economic model the source and sink of the mine is located at the settlement location. The same is valid for the fields of a settlement. There are no costs and time delays in moving goods between the tiles belonging to a settlement.

## Some Statistics on Trading

* 1000 people need 60t of food per month. 60 kg rice per person per month -> 2 kg rice per person per day -> 2,600 calories per person per day (recommended daily intake of a man: 2,500 calories, of a woman: 2,000).
* 1 steel mill needs 60t of iron ore and 210t coke per month to produce 60t of pig iron. A historical German blast furnace (1800) produced 2t of pig iron with 7t of coke as fuel per day (see [Hochofen](https://de.wikipedia.org/wiki/Hochofen)).

## Possible Features of Future Iterations

* Demand calculation by influence maps... (simulating the spread of information)
* Broaden the trade system, not only cities are trade nodes…

Instead of the trading mechanism described above, one could also use the [double auction](https://en.wikipedia.org/wiki/Double_auction). Stock exchanges are examples of double auctions, therefore, this mechanism may be considered when implementing a stock exchange or commodity exchange.

Advantages of the double auction:

* It is a mechanical and abstract method which seems to be easy to implement. This could also be a negative point, due to not being an intuitively understandable mechanism.
* It is easy to calculate a market price. This makes it also easy to display the market price.
* It seems to provide an efficient allocation (lowest offer and highest bid go first).
* There is a mechanism to update ask and bid prices.

Disadvantages of the double auction:

* Trading has to be centralised. A central authority clears the market.
* For the player the mechanism probably does not feel like a natural model of what happens on a farmer’s market.
* Does not simulate frictions, fluctuations and other market inefficiencies.

Other Ideas:

* If the ask price of a produced good falls below the input prices, a producer (source) may stop production. Similarly a producer may increase the ask price (and therefore his profit margin), if he consistently trades away all his supply. There may be some special sources and sinks with other price mechanics.
* The player is able to choose manual price adjustment at his factories and mines. He also can choose the automated price adjustment.
* For an in-depth economic simulation see bazaarBot:
  * [post on reddit](https://www.reddit.com/r/gamedev/comments/1fldav/bazaarbot_an_opensource_economics_engine/)
  * [post on gamasutra](https://www.gamasutra.com/blogs/LarsDoucet/20130603/193491/BazaarBot_An_OpenSource_Economics_Engine.php)
  * [bazaarBot on github](https://github.com/larsiusprime/bazaarBot)
