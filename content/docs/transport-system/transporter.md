---
title: Transporter
weight: 1
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

The Transporter is part of the [Transport System](articles/transport-system). It is located at its [Transport Hub](articles/transport-system/transport-hub) waiting for Cargo. After loading [Cargo](articles/transport-system/cargo), the Transporter transports the Cargo to its target Transport Hub.

## Components

* [TransporterComponent](classes/characterizing-classes/TransporterComponent/) - the [characterizing class](classes/characterizing-classes/) of the Transporter
* SelectableComponent
* MovingObject

## Behavior

* The Transporter moves from its Transport Hub to another Transport Hub.
* The Transporter "loads" the initial Cargo:
  * `void LoadCargo(List<Cargo>)`
* If there is more Cargo at the Transport Hub that has the target Transport Hub also in its transport path, the Transporter "loads" it as well.
* When the Transporter arrives at its target Transport Hub, it unloads all Cargo:
  * `List<Cargo> UnloadCargo()`

## Finite State Machine

The behavior of the Transporter is controlled by a finite state machine.

States:

* **Idle:** the Transporter is at its Transport Hub waiting for Cargo. As soon as Cargo is loaded to the Transporter, it switches to the Moving state.
* **Moving:** the Transporter moves to the Cargo's target Transport Hub. As soon as the target is reached, the Transporter unloads the Cargo, is set back to its Transport Hub, and switches to the Idle state.
