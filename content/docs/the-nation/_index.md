---
title: "The Nation"
weight: 2
geekdocCollapseSection: true
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

The nation is hierarchically organised. At the top is the nation. On the next lower level are provinces. Each province has a central settlement, the market town. Each province also contains population groups and industries.

{{< mermaid class="text-center">}}
graph TD
    N[Nation] --- A["Province A (Market Town/Settlement)"]
    N --- B["Province B (Market Town/Settlement)"]
    N --- C["Province C (Market Town/Settlement)"]
    A --- P1["Population (Farmers, Workers, Aristocrats, ...)"]
    A --- I1["Industries (Mine, Factory, ...)"]
    B --- P2[Population]
    B --- I2[Industries]
    C --- P3[Population]
    C --- I3[Industries]
{{< /mermaid >}}

## Implementation Note

During game initialisation, setup starts at the top level of the national hierarchy and goes through all levels from top to bottom. Lower levels register themselves with their parent level.
