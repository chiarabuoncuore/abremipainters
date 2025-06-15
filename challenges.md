---
layout: default
title: Challenges Faced 
description:
---

This KE4H project presented a series of complex challenges that required both technical expertise and problem-solving approaches. In this section, we will explore the key challenges we encountered and outline the solutions we implemented to overcome them, ultimately ensuring the success of the project. 

## 1. Generating accurate SPARQL Queries

### Challenge:
Writing **accurate SPARQL queries** for platforms like <a href="https://www.wikidata.org/wiki/Wikidata:Main_Page" target="_blank">Wikidata</a> can be challenging, especially for beginners. The complexity originates from understanding the structure of RDF data, knowing the variety of prefixes used and the way relationships between entities are modeled. Even simple questions can require nested patterns filtered with functions like <code class="language-plaintext highlighter-rouge">FILTER</code>, <code class="language-plaintext highlighter-rouge">OPTIONAL</code>, or <code class="language-plaintext highlighter-rouge">UNION</code>. A small error in syntax or logic can result in no results or incorrect and misleading ones.

### Solution:
In order to identify gaps on Wikidata, we needed to carefully consider which meaningful queries would be most relevant and informative for each specific task. This process helped ensure that we incorporated all the necessary keywords for the project. 

## 2. Q-ID Errors in LLM Outputs

### Challenge:
A common challenge when using Large Language Models to generate SPARQL queries for Wikidata is the occurrence of **Q-ID errors**, especially when the model provides incorrect or imprecise entity identifiers (e.g., when filling the movement gap we obtained <code class="language-plaintext highlighter-rouge">Q3288556</code>  instead of the correct <code class="language-plaintext highlighter-rouge">Q3786213</code>). These mistakes can lead to inaccurate or irrelevant query results. 

### Solution:
Since Q-IDs are critical for targeting the right entities, such errors often require manual verification and correction by cross-checking on Wikidata. While LLMs can accelerate query generation, human oversight remains essential to ensure factual accuracy.

## 3. Inserting an image 

### Challenge:
Understand how to add an **image** to the Wikidata entry was definitely challenging, particularly due to concerns around **copyright** and **licensing**. 

### Solution:
Before using the selected image, we had to verify that it was freely available and appropriately licensed for reuse. To address this, we aimed to include an image of Marcantonio Chiarini and identified a suitable file on <a href="https://commons.wikimedia.org/wiki/Main_Page" target="_blank">**Wikimedia Commons**</a>: File: Ritratto di Marcantonio Chiarini (bulino).jpg. To simplify the integration, we asked <a href="https://chatgpt.com/" target="_blank">ChatGPT</a> to generate the corresponding RDF triple code for the image, which we then included in our proposal as a way to fill this gap efficiently. 

## 4. Developing and structuring the website 

### Challenge:
As none of us had experience with building websites, neither on <a href="https://github.com/" target="_blank">**GitHub**</a> nor with **Jekyll**, the process took a lot of trial and error following thorough documentation. Making sure all the website pages followed a consistent theme and looked cohesive was also tough, for which team effort and support were key to reaching the desired outcome. 

### Solution:
After studying both the GitHub and the Jekyll documentation, we outlined a list of sub-objectives we needed to achieve. After choosing a layout we all liked and enabling the website, we went through the gradual process of adding each page’s content, and finally we concentrated on ensuring navigation ran smoothly, and that the website as a whole looked visually cohesive, so all the content was properly rendered.

## 5. Summary 

<p>☑️  Generating precise SPARQL Queries → incorporation of relevant keywords and identification of gaps on Wikidata</p>
<p>☑️  Q-ID Errors in LLM Outputs → manual correction by cross-checking on Wikidata</p>
<p>☑️  Inserting an image → generation of an RDF triple code to include the image in the proposal and fill the gap</p>
<p>☑️  Developing and structuring the website → study of the GitHub and Jekyll documentation</p>

[← Main Page](./)
