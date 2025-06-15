---
layout: default
title: Gap 2 | Movement
description: Which artistic movement do the painters belong to? 
---

## Choosing the property

Given that artistic movements are frequently linked to prominent painters whose reputations are widely established and recognized, we questioned whether there might be a lack of information concerning lesser-known artists, such as those included in our analysis.

## Identifying the gap

We crafted a **SPARQL query** to explore how the movement property <code class="language-plaintext highlighter-rouge">(P135)</code> is linked to both painters. By using the keywords <code class="language-plaintext highlighter-rouge">OPTIONAL</code> and <code class="language-plaintext highlighter-rouge">ORDER BY</code>, we aimed to clearly visualize any missing information and determine which painter the gap relates to.

```sparql
SELECT DISTINCT ?painter ?painterLabel ?movementLabel
WHERE {
  VALUES ?painter {
    wd:Q3081044 wd:Q3288556
  }
  OPTIONAL { ?painter wdt:P135 ?movement . }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
}
ORDER BY ?painterLabel
```

### Results:

The query results revealed a gap in the "movement" <code class="language-plaintext highlighter-rouge">(P135)</code> information for both painters, as illustrated below.

![resquerygap2](/abremipainters/assets/images/resquerygap2.png)

## Retrieving the information

To fill the gap, we asked this information to the three LLMs at hand: using a <code class="language-plaintext highlighter-rouge">zero-shot prompt</code> for **Marcantonio Chiarini** <code class="language-plaintext highlighter-rouge">(Q3288556)</code> and a <code class="language-plaintext highlighter-rouge">few-shot prompt</code> for **Francesco Paolo Michetti** <code class="language-plaintext highlighter-rouge">(Q3081044)</code> so as to get the information while also observing a potential different approach to a similar question posed in a different way.

### [Marcantonio Chiarini](./chiarini.md) 

### [Francesco Paolo Michetti](./michetti.md) 

## Conclusion 

To conclude, a SPARQL query confirmed the gap we suspected existed in Wikidata regarding lesser-known painters. LLMs helped us retrieve the missing information and suggested ways to represent it using RDF triples. However, we also identified several inaccuracies in the outputs, which required manual intervention to correct and refine the data. 
This highlights how LLMs can be powerful tools for data enrichment, but still depend on human oversight for accuracy and quality.

[← Main Page](./)
