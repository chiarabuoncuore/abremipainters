---
layout: default
title: Challenges Faced 
description:
---

This KE4H project presented a series of complex challenges that required both technical expertise and problem-solving approaches. In this section, we will explore the key challenges we encountered and outline the solutions we implemented to overcome them, ultimately ensuring the success of the project. 

## 1. Generating accurate SPARQL queries

### Challenge:
Writing **accurate SPARQL queries** for platforms like <a href="https://www.wikidata.org/wiki/Wikidata:Main_Page" target="_blank">Wikidata</a> can be challenging, especially for beginners. The complexity originates from understanding how SPARQL works, learning the meaning and use of the variety of available keywords and the way relationships between entities are modeled. Even simple questions can require nested patterns filtered with keywords like <code class="language-plaintext highlighter-rouge">FILTER</code>, <code class="language-plaintext highlighter-rouge">OPTIONAL</code>, or <code class="language-plaintext highlighter-rouge">UNION</code>. A small error in syntax or logic can lead to no results or incorrect and misleading ones.

### Solution:
In order to identify gaps on Wikidata, we needed to carefully consider which meaningful queries would be most relevant and informative for each specific task. This process helped ensure that we incorporated all the necessary keywords for the project. 

## 2. Q-ID errors in LLM outputs for RDF triples

### Challenge:
A common challenge when using Large Language Models to generate RDF triples for Wikidata is the occurrence of **Q-ID errors**, especially when the model provides incorrect or imprecise entity identifiers (e.g., when filling the "movement" gap for Marcantonio Chiarini, Mistral AI provided the incorrect property <code class="language-plaintext highlighter-rouge">(Q768)</code> for the Baroque movement, instead of the correct <code class="language-plaintext highlighter-rouge">(Q37853)</code>). These mistakes can lead to inaccurate or irrelevant results. 

### Solution:
Since Q-IDs are critical to target the right entities, such errors often require manual verification and correction by cross-checking on Wikidata. While LLMs can accelerate RDF triples generation, human supervision remains essential to ensure factual accuracy.

## 3. Inserting an image 

### Challenge:
Understanding how to add an **image** to the Wikidata entry was definitely challenging, particularly due to concerns around **copyright** and **licensing**. 

### Solution:
Before using the selected image, we had to verify that it was freely available and appropriately licensed for reuse. To address this, we aimed to include an image of Marcantonio Chiarini and identified a suitable <a href="https://upload.wikimedia.org/wikipedia/commons/thumb/9/90/Ritratto_di_Marcantonio_Chiarini_%28bulino%29.jpg/640px-Ritratto_di_Marcantonio_Chiarini_%28bulino%29.jpg" target="_blank">file</a> on <a href="https://commons.wikimedia.org/wiki/Main_Page" target="_blank">**Wikimedia Commons**</a>. To simplify the integration, we asked ChatGPT to generate the corresponding RDF triple code to add the image, which we then included in our proposal as a way to fill this gap efficiently. 

## 4. Developing and structuring the website 

### Challenge:
Since none of us had experience with building websites, neither on <a href="https://github.com/" target="_blank">**GitHub**</a> nor with **Jekyll**, using **Markdown** and **HTML**, the process took a lot of trial and error following thorough documentation. Making sure all the website pages followed a consistent theme and looked cohesive was also tough, for which team effort and support were key to reaching the desired outcome. 

### Solution:
After studying both the GitHub and the Jekyll documentation, we outlined a list of sub-objectives we needed to achieve. After choosing a layout we all liked and enabling the website, we went through the gradual process of adding each page’s content, and finally we concentrated on ensuring navigation ran smoothly, and that the website as a whole looked visually cohesive, so all the content was properly rendered.

## 5. Summary 

<p>☑️ <strong>Generating precise SPARQL queries</strong> → incorporation of relevant keywords and identification of gaps on Wikidata</p>
<p>☑️ <strong>Q-ID errors in LLM outputs for RDF triples</strong> → manual correction by cross-checking on Wikidata</p>
<p>☑️ <strong>Inserting an image</strong> → generation of an RDF triple code to include the image to fill the gap</p>
<p>☑️ <strong>Developing and structuring the website</strong> → study of the GitHub and Jekyll documentation</p>

[← Main Page](./)
