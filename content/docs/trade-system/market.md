---
title: "Market"
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

The markets are organised in the same way as the nation. On the national level, there is the National Market. On the provincial level, there are the Provincial Markets. One at each market town (settlement). Each population group and each industry (sources) acts as an individual trader. They are provincial traders.

The mechanism for trading is a kind of simulation of the behaviour at farmer’s markets. The mechanism is designed to provide a more ‘natural’ model of markets (some randomness, fixed ask prices, preference to trade locally). The disadvantages of this approach are inefficient allocations, a harder to implement mechanism, and a higher difficulty to calculate and display market prices.

High-level description of the features: 
* The markets are two-tiered: the national market on the higher level and provincial markets on the lower level.
* The ask price is fixed after the sellers have provided their offers. Buyers do not have to pay more than the ask price.
* Sellers only put offers on the national market, if there was no sale possible on the provincial market.
* Choose the bids of buyers randomly and check if a trade transaction is possible (bid unit price is equal or higher than the lowest ask unit price). The highest bid not going first is supposed to simulate some market inefficiency.

Update cycle of the trading mechanism:
1. All sources (farmers, ports, mines, factories) produce output. Output is added to the total supply of the source. All sources have the trading ability and are provincial traders.
2. All sinks calculate their demand for goods. Sinks have the trading ability as well and are provincial traders.

First: provincial level:
1. Sellers (provincial traders) offer their surplus goods on their local provincial market.
2. Buyers (provincial traders) bid on goods on their local provincial markets.
3. Offers and bids are cleared at the provincial market. There are no transport costs for trade transactions at the provincial market (maybe added in future implementations).

Second: national level:
1. If sellers still have goods left, they offer them on the national market.
2. If buyers still demand goods, they bid on goods on the national market.
3. Offers and bids are cleared at the national market. Buyers have to pay transport costs between the provincial markets of sellers and buyers.

Third: update of prices:
1. Sellers adjust their ask prices. If they were able to sell all their surplus, the ask prices increase. Otherwise, aks prices decrease.
2. Buyers adjust their bid price (good valuation). If they were able to fulfill their demand, they will decrease their bid prices. Otherwise, bid prices increase.