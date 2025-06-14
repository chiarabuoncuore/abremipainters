---
layout: default
title: Gap 2 | Movement
---

**Addressing the Gap: The Missing Portrait of Marcantonio Chiarini on Wikidata**

Given that artistic movements are frequently linked to prominent painters whose reputations are widely established and recognized, we questioned whether there might be a lack of information concerning lesser-known artists, such as those included in our analysis.

- **How did we identify the Gap?**

We crafted a SPARQL query to explore how the movement property (P135) is linked to both painters. By using the keywords 'OPTIONAL' and 'ORDER BY', we aimed to clearly visualize any missing information and determine which painter the gap relates to.

![SPARQLQUERY](/abremipainters/assets/images/Immagine5.jpg)


# Results 

The query results revealed a gap in the 'movement' information for both painters, as illustrated in the following scheme/the scheme above.

- **Filling the Gap**

To fill the GAP, we asked this information to the three LLMs at hand: using a zero-shot prompt for Marcantonio Chiarini and a few-shot prompt for Francesco Paolo Michetti so as to get the information while also observing a potential different approach to a similar question posed in a different way.

**A. MARCANTONIO CHIARINI**

We retrieved the information regarding the movement associated with Marcantonio Chiarini by using a zero-shot prompt: “Which movement did the painter Marcantonio Chiarini belong to?”.


*CHAT GPT*

![sparqlchiarini](/abremipainters/assets/images/Immagine8.jpg)

*GEMINI*
   
![sparqlchiarini](/abremipainters/assets/images/Immagine9.jpg)
 
*MISTRAL AI*

![sparqlchiarini](/abremipainters/assets/images/Immagine10.jpg)

The results revealed a slight variation between two broader suggestions of “Baroque” and one more specific reference to “Late Baroque”. To reduce the risk of inaccuracies, we ultimately chose to use the more general and commonly suggested label, associating Marcantonio Chiarini with the Baroque movement. We then prompted the three LLMs to generate relevant RDF triples to add this information to Wikidata and conducted a critical evaluation of their outputs/results.

- **Triple generation**

*CHAT GPT*

![sparqlchiarini](/abremipainters/assets/images/CHIARINI1.png)

*GEMINI*

![sparqlchiarini](/abremipainters/assets/images/CHIARINI2.png)

*MISTRAL AI*

![sparqlchiarini](/abremipainters/assets/images/CHIARINI3.png)

Our analysis showed that all three models returned an incorrect QID for Marcantonio Chiarini, while only Mistral generated an incorrect QID for the Baroque movement. Consequently, we manually corrected the RDF triple:

![sparqlchiarini](/abremipainters/assets/images/CHIARINI4.png) 


**B. FRANCESCO PAOLO MICHETTI**

We retrieved the information regarding the movement associated with Francesco Paolo Michetti by using a few-shot prompt, including in the examples both a widely-known and a lesser-known painter in order to maximise its efficiency: “If Marcantonio Chiarini belonged to the Baroque movement and Claude Monet belonged to Impressionism, which movement did Francesco Paolo Michetti belong to?”.

*CHAT GPT*

![Michetti](/abremipainters/assets/images/Immagine11.jpg)

*GEMINI*

![Michetti](/abremipainters/assets/images/Immagine12.jpg)

*MISTRAL AI*

![Michetti](/abremipainters/assets/images/Immagine13.jpg)

The answers didn’t provide a straightforward or unanimous result, but Realism appeared as the most commonly mentioned movement linked to Francesco Paolo Michetti. Verismo and the Scuola di Resina were suggested as subcategories, while Impressionism and Symbolism came up as possible influences. Based on this, our next step was to ask the language models to generate RDF triples that would add Realism as a movement on Michetti’s Wikidata page.

*CHAT GPT*

![Michetti1](/abremipainters/assets/images/Michetti1.png)

*GEMINI*

![Michetti1](/abremipainters/assets/images/Michetti2.png)

*MISTRAL AI* 

![Michetti1](/abremipainters/assets/images/Michetti3.png)

- **MANUAL CORRECTION**

Our analysis revealed that both ChatGPT and Mistral AI returned incorrect Wikidata QIDs for Francesco Paolo Michetti and the Realism movement. In contrast, the QIDs provided by Gemini were accurate. As a result, we manually refined the RDF triple as follows:

![Michetti1](/abremipainters/assets/images/Michetti4.png)


- **CONCLUSION**

As a result, a SPARQL query confirmed the gap we suspected existed in Wikidata regarding lesser-known painters. LLMs helped us retrieve the missing information and suggested ways to represent it using RDF triples. However, we also identified several inaccuracies in the outputs, which required manual intervention to correct and refine the data. 
This highlights how LLMs can be powerful tools for data enrichment, but still depend on human oversight for accuracy and quality.




[← Main Page](./)
