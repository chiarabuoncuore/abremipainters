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

```
Which was Francesco Paolo Michetti’s work location? Let’s think step by step.
```

### 1. *CHATGPT*

![chatquestion1](/abremipainters/assets/images/chatworkloc1.jpg)
![chatquestion2](/abremipainters/assets/images/chatworkloc2.jpg)
![chatquestion3](/abremipainters/assets/images/chatworkloc3.jpg)

### 2. _GEMINI_

![geminiquestion](/abremipainters/assets/images/geminiworkloc.png)

### 3. _MISTRAL AI_

![mistralquestion](/abremipainters/assets/images/mistralworkloc.png)

All LLMs, according to the prompting technique used, generated detailed answers providing multiple pieces of information, however the bottom line is visible in the way all three ultimately describe **Francavilla al Mare** as Michetti's primary work location. 

## Filling the gap: creating RDF triples 

We then prompted the three LLMs to generate **RDF triples** based on Wikidata ontology, to represent the missing information.  

### 1. *CHATGPT*

![Imagewl](/abremipainters/assets/images/rdfworllocation1.png)

### 2. _GEMINI_

![Imageine](/abremipainters/assets/images/geminirdfworkloc.png)

### 3. _MISTRAL AI_

![Imagewl](/abremipainters/assets/images/mistralrdfworkloc.png)

## Manual correction

Since the LLMs returned mostly incorrect Q-IDs for Francesco Paolo Michetti <code class="language-plaintext highlighter-rouge">(Q3081044)</code> and Francavilla al Mare <code class="language-plaintext highlighter-rouge">(Q51225)</code>, as well as redundant information in general (ChatGPT), we manually refined the RDF triple as follows:

![Imagewl](/abremipainters/assets/images/correctedrdfworkloc.jpg)

## Conclusion

To conclude, a SPARQL query displayed lack of information in the field of work location for painter Francesco Paolo Michetti. After questioning the LLMs and retrieving such missing information, we also prompted them to provide RDF triples to hypothetically fix the gap on the KG. However, results showed that the chain-of-thought prompting technique increased the incorrectness of LLMs outputs, as not only were some Q-IDs inaccurate, but excess information was also given. This led to the manual correction and refinement of the data, highlighting the limits of LLMs in such field. 

[← Main Page](./)
