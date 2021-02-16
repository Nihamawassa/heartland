---
title: "Settlements"
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

A settlement is defined by its population. The population is divided in different occupations:

* **Farmers:** this is the default occupation.
* **Aristocrats:** consume food and clothes.
* **Workers:** work in factories and mines.
* **Soldiers:** man divisions located in barracks

Details on settlements and populations are described in section 2.4 Population and Communities
Depending on the available resources, individuals slowly shift between occupations. If there is not enough food at a settlement and there is farmable land available, the population shifts to farming. Otherwise the population slowly shifts to the highest earning occupation (it takes some time to learn a new trade). Populations also shift between occupations if they are unemployed.

Settlement name: [Markov Name Generator](https://www.samcodes.co.uk/project/markov-namegen/)

## Growth Function

populationGrowth(population, food, time): all communities have a growth function. If food is available, the population grows dependent on the current population amount. If no food is available, the population decreases. The population grows with a base pre-industrial growth percentage, which may be modified by some positive factors (advances in medicine) or negative factors (epidemies).

See also: [Demographic transition](https://en.wikipedia.org/wiki/Demographic_transition)

## Consumption Functions

foodConsumption(population, time): food is consumed by the population. Food is measured in one monthly ration per person.

60 kg rice per person per month -> 2 kg rice per person per day -> 2,600 calories per person per day (recommended daily intake of a man: 2,500 calories, of a woman: 2,000)

clothesConsumption(population, time): clothes are consumed by the population.

## Future Implementation

All settlements have a core, which is represented on the map as a city center tile. When the settlement grows in population, additional city tiles get added to the settlement:

* City Center
* Suburban City
