---
layout: default
title: SPARQL and LLM Prompts 
description: Techniques Used
---
This section presents the SPARQL queries and large language model (LLM) prompts employed to check, select and enrich Charini and Michetti's information on Wikidata. Our objective was to uncover gaps in Wikidata's coverage of such artists. To achieve this, we utilized three distinct prompting strategies (zero-shot prompt, few-shot prompt and chain-of-thought prompt), each designed to probe Wikidata’s existing records and generate supplementary RDF triples where omissions were detected.

**SPARQL QUERIES** 

1. *Query painter information by Name*

The first query allowed us to search for regional painters whose names included “Chiarini” or “Michetti”
   
Functions used: **FILTER, REGEX AND UNION, DISTINCT, LIMIT**

![Image1SPARQLquery](/abremipainters/assets/images/Immagine1.jpg)

The results displayed by this SPARQL query are the following:

![Image2SPARQLquery](/abremipainters/assets/images/Immagine2.jpg)

2. *Query for Image(P18) identification)*

In order to find out if wikidata provides the images of the two italian painters, we asked it to create a SPARQL query, enabling us to discover that Chiarini’s image was missing.

Functions used: **DISTINCT, ORDER BY**







   
***

[← Main Page](./)
