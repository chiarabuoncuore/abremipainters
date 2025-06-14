---
layout: default
title: Gap 1 | Image
---

**Identifying the Gap: Missing Marcantonio Chiarini’s Portrait on Wikidata**

- **What is the Gap?**

This project revealed a noticeable deficiency within Wikidata: some entries are missing portrait images (P18). While exploring entries of historical italian regional artists, we found out that Marcantonio Chiarini had no associated portrait image on Wikidata.

- **Why did we choose this Gap?**

Being a relevant person in the artistic field, and more precisely a significant figure in Italian art history, the lack of important information such as the portrait underestimates his importance, and the recognition he deserves.

- **How did we identify the Gap? (Methodology)**

To pinpoint the gap on Wikidata, we utilized a SPARQL query. Specifically, we designed a query to investigate how the image property (P18) is associated with both painters. By incorporating the 'ORDER BY' clause, we were able to effectively highlight any missing data and identify which painter the gap pertains to.

![Image1](/abremipainters/assets/images/Immagine3.jpg) 

Results: 

![Image2](/abremipainters/assets/images/Immagine4.jpg)

From the query, we found out that Marcantonio Chiarini’s image is missing on Wikidata.

Since there is no image associated with Marcantonio Chiarini on Wikidata (P18 property is missing), we performed a manual search on Wikimedia Commons, finding out the following image: 
<a href="https://commons.wikimedia.org/w/index.php?search=MARCANTONIO+CHIARINI&title=Special:MediaSearch&type=image target="_blank">
   Clicca qui per vedere l'immagine
</a>



From the search results, we reviewed multiple images and identified one that appears to be related to Chiarini or his artistic work.

- **RDF Triples Creation to Fill the Gap**

In order to integrate the discovered image into the artist’s Wikidata profile, we created RDF triples that describe the relationship between Marcantonio Chiarini’s Wikidata entity and the image hosted on Wikimedia Commons. These RDF triples are intended to be added to the structured data in Wikidata, using appropriate semantic web standards. At the same time to test the capabilities of different large language models (LLMs) in generating RDF triples from contextual prompts, we provided them with identical tasks. We used the zero-shot prompt in each LLM. 

1. *CHAT GPT*
   
   ![Image3](/abremipainters/assets/images/RDFTRIPLES1.png)
   
2. *GEMINI*
   
    ![Image4](/abremipainters/assets/images/RDFTRIPLES2.jpg)
   
3. *MISTRAL AI*
   
    ![Image5](/abremipainters/assets/images/RDFTRIPLES3.png)

- **Outcome**

As we can see from the comparison of the three LLMs, two of them (CHAT GPT and GEMINI)  gave us the right result, since the Q-IDs for the artist and the image are the same as the ones on Wikidata. While MISTRAL AI produced RDF with incorrect Q-IDs, so we corrected them manually.

- **Q-IDs Manual Correction**
  
 ![Image6](/abremipainters/assets/images/RDFTRIPLES4.png)

- **Conclusion**

A crucial gap in Wikidata concerning Marcantonio Chiarini was identified through a simple SPARQL query. To address this, and in an effort to enrich the dataset, we leveraged three different Large Language Models (LLMs) to generate the necessary RDF triples. While the LLMs provided valuable assistance in retrieving the missing information and suggesting RDF representations, one of their outputs contained inaccuracies, necessitating manual correction.
Subsequent SPARQL queries confirmed the initial suspicion regarding the incompleteness of Wikidata for lesser-known painters. This process demonstrated the potential of LLMs as powerful tools for data enrichment. However, the requirement for manual intervention to correct and refine the generated data also underscored a critical point, in fact, despite their advanced capabilities, LLMs still depend on human expertise for verification and refinement in data management tasks.

[← Main Page](./)





