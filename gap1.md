---
layout: default
title: Gap 1 | Image
description: What do the painters look like?
---

## Choosing the property

Being a relevant person in the artistic field, and more precisely a significant figure in Italian art history, the lack of important information such as the portrait underestimates his importance, and the recognition he deserves.

## Identifying the gap

To pinpoint the gap on Wikidata, we designed a **SPARQL query** to investigate how the image property <code class="language-plaintext highlighter-rouge">(P18)</code> is associated with both painters. By incorporating the <code class="language-plaintext highlighter-rouge">ORDER BY</code> keyword, we were able to effectively identify which painter the gap pertains to.

```sparql
SELECT DISTINCT ?painter ?painterLabel ?image ?imageLabel
WHERE {
  VALUES ?painter {
    wd:Q3081044 wd:Q3288556
  }
  ?painter wdt:P18 ?image .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
}
ORDER BY ?painterLabel
```

### Results: 

![Results](/abremipainters/assets/images/resquerygap1.png)

The query showed the lack of Marcantonio Chiarini's <code class="language-plaintext highlighter-rouge">(Q3288556)</code> image on Wikidata. Therefore, we performed a manual search on <a href="https://commons.wikimedia.org/w/index.php?search=MARCANTONIO+CHIARINI&title=Special%3AMediaSearch&type=image" target="_blank">Wikimedia Commons</a>. From the search results, we reviewed multiple images and identified <a href="https://upload.wikimedia.org/wikipedia/commons/thumb/9/90/Ritratto_di_Marcantonio_Chiarini_%28bulino%29.jpg/640px-Ritratto_di_Marcantonio_Chiarini_%28bulino%29.jpg">one</a> that appears to be related to Chiarini or his artistic work.

## Filling the gap: creating RDF triples

In order to integrate the discovered image into the artist’s Wikidata profile, we asked all three LLMs with the <code class="language-plaintext highlighter-rouge">zero-shot prompt</code> to generate **RDF triples** describing the relationship between Marcantonio Chiarini’s Wikidata entity and the image hosted on Wikimedia Commons. These RDF triples are intended to be added to the structured data in Wikidata, using appropriate semantic web standards.

### 1. *CHAT GPT*

![Chat](/abremipainters/assets/images/RDFTRIPLES1.png)
   
### 2. *GEMINI*
   
![Gemini](/abremipainters/assets/images/RDFTRIPLES2.jpg) 
   
### 3. *MISTRAL AI*

![Mistral](/abremipainters/assets/images/RDFTRIPLES3.png)

## Manual correction

As we can see from the comparison of the three LLMs, two of them (CHAT GPT and GEMINI) gave us the right result, since the **Q-IDs** for the artist and the image are the same as the ones on Wikidata. Conversely, MISTRAL AI produced an RDF triple with incorrect Q-IDs, so we corrected it manually.

![Mistralcorrect](/abremipainters/assets/images/RDFTRIPLES4.png)

## Conclusion

A crucial gap in Wikidata concerning Marcantonio Chiarini was identified through a simple SPARQL query. To address this, and in an effort to enrich the dataset, we leveraged three different Large Language Models (LLMs) to generate the necessary RDF triples. While the LLMs provided valuable assistance in retrieving the missing information and suggesting RDF representations, one of their outputs contained inaccuracies, necessitating manual correction.
Subsequent SPARQL queries confirmed the initial suspicion regarding the incompleteness of Wikidata for lesser-known painters. This process demonstrated the potential of LLMs as powerful tools for data enrichment. However, the requirement for manual intervention to correct and refine the generated data also underscored a critical point: in fact, despite their advanced capabilities, LLMs still depend on human expertise for verification and refinement in data management tasks.

[← Main Page](./)
