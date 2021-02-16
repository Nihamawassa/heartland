---
title: Transport Hub
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

The Transport Hub is part of the [Transport System](articles/transport-system). There are three main types of transport hubs:

* **Stables**: place where ox-wagons are stationed for road transport.
* **Train stations**: trains are available at train stations for rail transport.
* **Ports**: barges for river transport on water ways and schooners for coastal transport as well as clippers for ocean-going transport on sea lanes are anchored at ports.

## Features

A Transport Hub is located on a tile.

## Behavior

The Transport Hub spawns a [Transporter](articles/transport-system/transporter) if there is a [Cargo](articles/transport-system/cargo) at the Transport Hub.

## Ports

A port is located on an adjacent tile of a settlement, if

* There is a major river
* There is an estuary
* There is a sea tile

The placement of a port creates a road connection from the settlement to the port. There may also be the need for a ‘loading’ connection from the road to the sea lane.

The placement of a port generates sea lanes from this port to all other already existing and reach-able ports. There is no need to do this from the other ports to the new port as well, because sea lanes are like roads.

### Generation of ports

1. Check adjacent tiles of a settlement for river and sea tiles.
2. Place the port according to the following hierarchy:
    * Place port on a river tile, if the tile is a river mouth to the open sea (estuary)
    * Place the port on a (open) sea tile. Choose cardinal directions (NESW) first. Otherwise choose a random sea tile.
    * Place the port on a river tile. Choose cardinal directions (NESW) first. Otherwise choose a random river tile.
