---
layout: default
title: Gap 1 | Image
---

**Identifying the Gap: Missing Marcantonio Chiarini’s Portrait on Wikidata**

- **What is the Gap?**

This project revealed a noticeable deficiency within Wikidata: some entries are missing portrait images (P18). While exploring entries of historical italian regional artists, we found out that Marcantonio Chiarini had no associated portrait image on Wikidata

- **Why did we choose this Gap?**

Being a relevant person in the artistic field, and more precisely a significant figure in Italian art history, the lack of important information such as the portrait underestimates his importance, and the recognition he deserves

- **How did we identify the Gap? (Methodology)**

To pinpoint the gap on Wikidata, we utilized a SPARQL query. Specifically, we designed a query to investigate how the image property (P18) is associated with both painters. By incorporating the 'ORDER BY' clause, we were able to effectively highlight any missing data and identify which painter the gap pertains to.

![Image1](/abremipainters/assets/images/Immagine1.jpg) 

Results: 

![Image2](/abremipainters/assets/images/Immagine2.jpg)

From the query, we found out that Marcantonio Chiarini’s image is missing on Wikidata

Since there is no image associated with Marcantonio Chiarini on Wikidata (P18 property is missing), we performed a manual search on Wikimedia Commons using the search query:

🔗 Search: “Marcantonio Chiarini” on Commons

From the search results, we reviewed multiple images and identified one that appears to be related to Chiarini or his artistic work

- **RDF Triples Creation to Fill the Gap**

In order to integrate the discovered image into the artist’s Wikidata profile, we created RDF triples that describe the relationship between Marcantonio Chiarini’s Wikidata entity and the image hosted on Wikimedia Commons. These RDF triples are intended to be added to the structured data in Wikidata, using appropriate semantic web standards. At the same time to test the capabilities of different large language models (LLMs) in generating RDF triples from contextual prompts, we provided them with identical tasks. We used the zero-shot prompt in each LLM. 





