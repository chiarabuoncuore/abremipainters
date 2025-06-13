---
layout: default
title: SPARQL and Prompts 
description: Techniques Used
---
This section presents the SPARQL queries and large language model (LLM) prompts employed to identify "regional" painters whose names contain either "Chiarini" or "Michetti." Our objective was to uncover gaps in Wikidata's coverage of such artists. To achieve this, we utilized three distinct prompting strategies (zero-shot prompt, few-shot prompt and chain-of-thought prompt), each designed to probe Wikidata’s existing records and generate supplementary RDF triples where omissions were detected.

1. The first query allowed us to search for “regional” painters whose names included “Chiarini” or “Michetti”
Functions used: FILTER, REGEX AND UNION, DISTINCT, LIMIT

![Image1SPARQLquery](/abremipainters/assets/images/Immagine1.jpg)
   
***

[← Main Page](./)
