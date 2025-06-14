---
layout: default
title: Gap 2 | Movement
---

**Addressing the Gap: The Missing Portrait of Marcantonio Chiarini on Wikidata**

Given that artistic movements are frequently linked to prominent painters whose reputations are widely established and recognized, we questioned whether there might be a lack of information concerning lesser-known artists, such as those included in our analysis

- **How did we identify the Gap?**

We crafted a SPARQL query to explore how the movement property (P135) is linked to both painters. By using the keywords 'OPTIONAL' and 'ORDER BY', we aimed to clearly visualize any missing information and determine which painter the gap relates to

![SPARQLQUERY](/abremipainters/assets/images/Immagine5.jpg)


Results 

The query results revealed a gap in the 'movement' information for both painters, as illustrated in the following scheme/the scheme above

- **Filling the Gap**

To fill the GAP, we asked this information to the three LLMs at hand: using a zero-shot prompt for Marcantonio Chiarini and a few-shot prompt for Francesco Paolo Michetti so as to get the information while also observing a potential different approach to a similar question posed in a different way.

**A. MARCANTONIO CHIARINI**

We retrieved the information regarding the movement associated with Marcantonio Chiarini by using a zero-shot prompt: “Which movement did the painter Marcantonio Chiarini belong to?”.


1. *CHAT GPT*

![sparqlchiarini](/abremipainters/assets/images/Immagine8.jpg)

2. *GEMINI*
   
![sparqlchiarini](/abremipainters/assets/images/Immagine9.jpg)
 
3. *MISTRAL AI*

![sparqlchiarini](/abremipainters/assets/images/Immagine10.jpg)

The results revealed a slight variation between two broader suggestions of “Baroque” and one more specific reference to “Late Baroque”. To reduce the risk of inaccuracies, we ultimately chose to use the more general and commonly suggested label, associating Marcantonio Chiarini with the Baroque movement. We then prompted the three LLMs to generate relevant RDF triples to add this information to Wikidata and conducted a critical evaluation of their outputs/results.

[← Main Page](./)
