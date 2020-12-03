+++
title = "Import into the triple-store"
weight = 5
pre = "<b>1. </b>"
+++

We have several tools to import data inside PHO-KB.

## importer.MainKt

This tool imports the data from LOTUS and Napralert inside a new Triple-store: data/pho_processed.

Currently with regard to bioactivities, it imports only pain related evidences from Napralert for demonstration purpose.


{{<mermaid align="left">}}
graph LR;
LOTUS[LOTUS] --> TI[[Taxonomy Importer]]
N[NAPRALERT] --> TI
TI -->|Aligns with| GNFinder
TI -->|Harmonized taxonomical data| TS[(Triple Store<br/>RDF4J)]

subgraph Types Importer
RI[[Results Types Importer]]
AI[[Activities Types Importer]]
ETI[[Evidences Types Importer]]
end

N --> RI
RI --> TS

N --> AI
AI --> TS

N --> ETI
ETI --> TS

N --> PI[[Pain Evidences Importer]]
PI --> TS


style TS  fill:#f9f,stroke:#333,stroke-width:0.5px

{{< /mermaid >}}
