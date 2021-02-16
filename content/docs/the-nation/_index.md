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
    Nation --> Province A
    Nation --> Province B
    Nation --> Province C
{{< /mermaid >}}

## Implementation Note

During game initialisation, setup starts at the top level of the national hierarchy and goes through all levels from top to bottom. Lower levels register themselves with their parent level.
