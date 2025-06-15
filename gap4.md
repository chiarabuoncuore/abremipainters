---
layout: default
title: Gap 4 | Work Location
description: Where were the painters active? 
---

## Choosing the property

Another piece of information we examined was the work location of the two painters, in order to gain insight into not only where they were professionally active, but also where they received their education and which influences may have shaped their artistic development. 

## Identifying the gap

To pinpoint the gap on Wikidata, we created a **SPARQL query** to investigate the work location <code class="language-plaintext highlighter-rouge">(P937)</code>
associated with both painters. By using the <code class="language-plaintext highlighter-rouge">OPTIONAL</code> keyword, we asked the KG to provide us with pieces of information for both painters at the same time, and ensuring the return of a blank space if such information is missing without rejecting the solution. 

```sparql
SELECT DISTINCT ?painter ?painterLabel ?worklocationLabel
WHERE {
  VALUES ?painter {
    wd:Q3081044 wd:Q3288556
  }
  OPTIONAL { ?painter wdt:P937 ?worklocation . }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
}
ORDER BY ?painterLabel
```

### Results: 

![resultsguerygap4](/abremipainters/assets/images/resquerygap4.png)

From these results, we learn that Marcantonio Chiarini was active in Vienna, while no information is available regarding the workplace of Francesco Paolo Michetti, reflecting a gap in the data.

## Retrieving the information

To address the missing data, we asked the three LLMs with the <code class="language-plaintext highlighter-rouge">chain-of-thought prompt</code> the following question: 

Which was Francesco Paolo Michetti’s work location? Let’s think step by step. 

## Filling the gap: creating RDF triples 

## Manual correction

## Conclusion


Considering that: 

*P937: is the label of the work location*

*wd:Q3081044: Francesco Paolo Michetti* 

*wd:Q3288556: Marcantonio Chiarini*



- **We employed a SPARQL query to identify this label on wikidata**

The Wikidata Query Service produced the following results: 

![IMAGE1](/abremipainters/assets/images/Immagine6.jpg)

From these results, we learn that Marcantonio Chiarini was active in Vienna, while no information is available regarding the workplace of Francesco Paolo Michetti, reflecting a gap in the data. To address this, we applied the Chain of Thought prompting technique and asked the question — ‘Which was Michetti’s work location? Let’s think step by step’ — to three large language models (ChatGPT, Gemini, and Mistral AI). The following results were obtained:

*CHAT GPT*

![IMAGE1](/abremipainters/assets/images/Immagine14.jpg)

![IMAGE1](/abremipainters/assets/images/Immagine15.jpg)

- **RDF Triples Creation**

Based on these results, we generated RDF triples according to the Wikidata ontology: 

![Imagewl](/abremipainters/assets/images/rdfworllocation1.png)

![Imagewl](/abremipainters/assets/images/rdfworllocation2.png)


- **Manual correction and validation of the codes:**

![Imagewl](/abremipainters/assets/images/rdfworklocatrion3.png)


*GEMINI*

![Imagewl](/abremipainters/assets/images/Immagine16.jpg)

Based on these results, we generated RDF triples according to the Wikidata ontology and obtained the following: 

![Imageine](/abremipainters/assets/images/WORKLOCATION.png)


In this LLM the codes were accurate, and no manual correction was required. 

*MISTRAL AI*

![Imagewl](/abremipainters/assets/images/Immagine17.jpg)


Based on these results, we generated RDF triples according to the Wikidata ontology and obtained the following:

![Imagewl](/abremipainters/assets/images/rdftripleserratimistral.png)


- **Manual correction and validation of the codes are required**

![Imagewl](/abremipainters/assets/images/gap4ultimaimmagine.png)
 
- **CONCLUSION**

ChatGPT and Mistral provided incorrect codes, whereas Gemini produced the correct ones. By comparing Gemini's results with the codes on Wikidata, we decided to manually correct the codes in ChatGPT and Mistral based on the accurate data from Wikidata. 

[← Main Page](./)





