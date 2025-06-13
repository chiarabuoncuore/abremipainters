---
layout: default
title: Challenges Faced 
description:
---
## Challenges and Solutions

# 1. Crafting accurate SPARQL Queries
The Challenge of Crafting Accurate SPARQL Queries

Challenge: writing accurate SPARQL queries for platforms like Wikidata can be challenging, especially for beginners. The complexity originates from understanding the structure of RDF data, the variety of prefixes used, and the way relationships between entities are modeled. Even simple questions can require nested patterns filtered with functions like FILTER, OPTIONAL, or UNION. A small error in syntax or logic can result in no results or misleading ones.

Solution: to identify gaps on wikidata, we needed to carefully consider which meaningful queries would be most relevant and informative for each specific task. This process helped ensure that we incorporated all the necessary keywords for the project. 

# 2. Q-ID Errors in LLM Outputs
Challenge: A common challenge when using large language models (LLMs) to generate SPARQL queries for Wikidata is the occurrence of Q-ID errors, especially when the model provides incorrect or imprecise entity identifiers (e.g., when filling the movement gap we obtained Q3288556  instead of the correct Q3786213). These mistakes can lead to inaccurate or irrelevant query results. 

Solution: Since Q-IDs are critical for targeting the right entities, such errors often require manual verification and correction by cross-checking on Wikidata. While LLMs can accelerate query generation, human oversight remains essential to ensure factual accuracy.

# 3. Adding an image 

Challenge: One of the challenges we faced was to understand how to add an image to the Wikidata entry, particularly due to concerns around copyright and licensing. 

Solution: Before using the selected image, we had to verify that it was freely available and appropriately licensed for reuse. To address this, we aimed to include an image of Marcantonio Chiarini and identified a suitable file on Wikimedia Commons: File: Ritratto di Marcantonio Chiarini (bulino).jpg. To simplify the integration, we asked ChatGPT to generate the corresponding RDF triple code for the image, which we then included in our proposal as a way to fill this gap efficiently. 

# 4. Building and structuring the website 

Challenge: As none of us had experience with building websites, neither on GitHub nor with Jekyll, the process took a lot of trial and error following thorough documentation. Making sure all the pages followed a consistent theme and looked cohesive was also tough, for which team effort and support were key to reaching the desired outcome. 


Solution: After studying both the GitHub and the Jekyll documentation, we outlined a list of sub-objectives we needed to achieve. After choosing a layout we all liked and enabling the website, we went through the gradual process of adding each page’s content, and finally we concentrated on ensuring navigation ran smoothly, and that the website as a whole looked visually cohesive, so all the content was properly rendered.

# 5. Summary 

- Generating precise SPARQL Queries → incorporation of relevant keywords and identification of gaps on Wikidata

- Q-ID Errors in LLM Outputs → manual correction by cross-checking on Wikidata

- Inserting an image → generation of a RDF triple code to include the image in the proposal and fill the gap

- Developing and structuring the website → study of the GitHub and Jekyll documentation



[← Main Page](./)
