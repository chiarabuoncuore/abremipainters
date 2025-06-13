---
layout: default
title: Final Report
description:
---


The objective of this project was to explore the Knowledge Graph Wikidata using SPARQL queries, in order to find relevant missing information that had to be added. The research on two almost unknown painters - Marcantonio Chiarini and Francesco Paolo Michetti - provided the starting point for our project, as we found that their Wikidata pages presented several gaps that could have been filled in. 

First of all, we queried Wikidata for knowledge gaps using SPARQL and we uncovered missing data concerning their artistic movement, country of citizenship, portraits and work location.Then, we employed three Large Language Models (ChatGPT, Gemini, Mistral AI) to generate RDF triples to cover these gaps, and we prompted them using three prompting techniques: zero-shot, few-shot, chain of thought. As a result, we often obtained triples that presented errors related to the entity IDs or the property IDs. We manually corrected them according to Wikidata ontology. 

In conclusion, we observed that LLMs can facilitate the enrichment of a Knowledge Graph, especially regarding the creation of RDF triples. However, human work still proves essential for checking LLM’s answers for possible errors.


***

[← Main Page](./)
