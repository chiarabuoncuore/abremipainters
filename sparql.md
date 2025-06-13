---
layout: default
title: SPARQL and LLM Prompts 
description: Techniques Used
---
This section presents the SPARQL queries and large language model (LLM) prompts employed to check, select and enrich Charini and Michetti's information on Wikidata. Our objective was to uncover gaps in Wikidata's coverage of such artists. To achieve this, we utilized three distinct prompting strategies (zero-shot prompt, few-shot prompt and chain-of-thought prompt), each designed to probe Wikidata’s existing records and generate supplementary RDF triples where omissions were detected.

**SPARQL QUERIES** 

- *Query painter information by Name*

The first query allowed us to search for regional painters whose names included “Chiarini” or “Michetti”
   
Functions used: **FILTER, REGEX AND UNION, DISTINCT, LIMIT**

![Image1SPARQLquery](/abremipainters/assets/images/Immagine1.jpg)

The results displayed by this SPARQL query are the following:

![Image2SPARQLquery](/abremipainters/assets/images/Immagine2.jpg)



- *Query for Image (P18) identification*

In order to find out if wikidata provides the images of the two italian painters, we asked it to create a SPARQL query, enabling us to discover that Chiarini’s image was missing.

Functions used: **DISTINCT, ORDER BY**

![Image3](/abremipainters/assets/images/Immagine3.jpg)

Results: 

![Image4](/abremipainters/assets/images/Immagine4.jpg)

- *Query for Movement (P135) identification*

Moreover, we wondered whether the artistic movement they belong to was shown in their WikiData’s page. To find it out, we developed the following SPARQL query

Functions used: **OPTIONAL, ORDER BY**


![Image4](/abremipainters/assets/images/Immagine5.jpg)

- *Query for Work Location (P937) identification*

We wanted to find their work locations to understand where each painter was active, crafting the following query, and adding ORDER BY to list the painters’ work locations in a clear and organized way

Functions used: **ORDER BY**

![Image4](/abremipainters/assets/images/Immagine6.jpg)


- *Query for Country of Citizenship (P27) identification*

We used a UNION query to retrieve the country of citizenship for both painters at once. his allows retrieving their respective countries of citizenship efficiently without running separate queries.

Function used: **UNION**

![Image4](/abremipainters/assets/images/Immagine7.jpg)

**LLMs Prompting Techniques**



   
***

[← Main Page](./)
