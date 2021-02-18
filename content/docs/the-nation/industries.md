---
title: "Industries"
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

Industries belong to a [province (settlement)](docs/the-nation/settlements/).

## Industry Types

* **Trade Port:** Trade ports are ports used for international sea-going trade. They are a source of cotton and a sink for clothes, machine parts, and weapons. The state gets tariffs from imports and exports at the port. The prices at the port are set externally. For example the naval power of the state has an influence on prices.
* **Coal Mine:** Source of coal by using workers. Its output efficiency is increased by scientific advance. The player can build these on top of coal seams.
* **Iron Mines:** Source of iron ore by using workers. Its output efficiency is increased by scientific advance. The player can build these on top of iron ore seams.
* **Steel Mills:** Source of steel. Uses coal, iron ore, and labour (workers) as inputs. Its output efficiency is increased by scientific advance. The player can build steel mills. A historical German blast furnace (1800) produced 2t of pig iron with 7t of coke as fuel per day [Hochofen](https://de.wikipedia.org/wiki/Hochofen).
* **Textile Mills:** Source of clothes. Uses cotton and labour (workers) as inputs. Its output efficiency is increased by scientific advance. The player can build textile mills.
* **Machine Parts Factories:** Source of machine parts. Uses steel and labour (workers) as inputs. Its output efficiency is increased by scientific advance. The player can build machine parts factories.
* **Weapon Factories:** Source of weapons. Uses steel and labour (workers) as inputs. Its output efficiency is increased by scientific advance. The player can build weapon factories.

## Construction of Industries

The player builds new structures on the map to increase production. He earns money by selling the produced goods. Buildings cost steel and money to pay for workers. Steel has to be provided by the player from the [national stock](docs/the-nation/national-stocks/). The workers have to be supplied by cities and paid by the player. The player starts the construction by placing a building on a tile. He has to pay the money up front. If there is enough steel in one of the player’s stockpiles, a merchant spawns there and transports the steel to the construction site. The construction process starts after all construction costs are paid and the needed steel is delivered. The building starts working after the construction time has passed.

## Technical Implementation of Construction

When the player places a new building on the map, a new construction site actor is added to the game model. A sprite representing the construction site is added to the game view. A construction site needs certain resources and time to complete. After completion, the construction site actor is removed from the game model and his sprite is removed from the game view. The constructed building is added to the game model as well as the respective sprite to the game view.

In an advanced implementation, only if there are enough workers available at a city and the player has enough money to pay the workers available, a builder unit will move to the construction site to build the new building.
