+++
title = "Taxonomy"
weight = 5
pre = "<b>1. </b>"
+++

```sparql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>

SELECT * WHERE {
  ?sub <http://purl.obolibrary.org/obo/TAXRANK_0000004> ?family;
     <http://purl.obolibrary.org/obo/TAXRANK_0000005> ?genus ;
     <http://purl.obolibrary.org/obo/TAXRANK_0000006> ?species.
  SERVICE </api/sparql/taxonomy> {
    
  }
} 
LIMIT 10
```