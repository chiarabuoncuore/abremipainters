---
layout: default
title: Gap 4 | Work Location
---

Another piece of information we examined was the workplaces of the two painters, in order to gain insight into where they received their education and which influences may have shaped their artistic development. 

Considering that: 

*P937: is the label of the work location*

*wd:Q3081044: Francesco Paolo Michetti* 

*wd:Q3288556: Marcantonio Chiarini*

- **We employed a SPARQL query to identify this label on wikidata**

The Wikidata Query Service produced the following results: 

![IMAGE1](abremipainters/assets/images/Immagine6.jpg)

From these results, we learn that Marcantonio Chiarini was active in Vienna, while no information is available regarding the workplace of Francesco Paolo Michetti, reflecting a gap in the data. To address this, we applied the Chain of Thought technique and asked the question — ‘Which was Michetti’s work location? Let’s think step by step’ — to three large language models (ChatGPT, Gemini, and Mistral AI). The following results were obtained:

1. *CHAT GPT*

IMMAGINE 

Based on these results, we generated RDF triples according to the Wikidata ontology: 




- **Manual correction and validation of the codes:**

- *GEMINI*

Based on these results, we generated RDF triples according to the Wikidata ontology and obtained the following: 


IMMAGINE

In this LLM the codes were accurate, and no manual correction was required. 

-*MISTRAL AI*

immagine 

Based on these results, we generated RDF triples according to the Wikidata ontology and obtained the following: 

-**Manual correction and validation of the codes are required**

Immagine 

-**CONCLUSION**

ChatGPT and Mistral provided incorrect codes, whereas Gemini produced the correct ones. By comparing Gemini's results with the codes on Wikidata, we decided to manually correct the codes in ChatGPT and Mistral based on the accurate data from Wikidata. 







