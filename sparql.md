---
layout: default
title: SPARQL and LLM Prompts 
description: Techniques Used
---
This section presents the **SPARQL queries** and **Large Language Model (LLM) prompts** employed to check, select and enrich <a href="https://www.treccani.it/enciclopedia/marc-antonio-chiarini_%28Dizionario-Biografico%29/" target="_blank">Chiarini</a> and <a href="https://www.treccani.it/enciclopedia/francesco-paolo-michetti_%28Dizionario-Biografico%29/" target="_blank">Michetti</a>'s information on <a href="https://www.wikidata.org/wiki/Wikidata:Main_Page" target="_blank">Wikidata</a>. Our objective was to uncover gaps in Wikidata's coverage of such artists. To achieve this, we utilized three distinct prompting strategies (<code class="language-plaintext highlighter-rouge">zero-shot prompt</code>, <code class="language-plaintext highlighter-rouge">few-shot prompt</code> and <code class="language-plaintext highlighter-rouge">chain-of-thought prompt</code>), each designed to probe Wikidata’s existing records and generate supplementary RDF triples where omissions were detected.

## SPARQL Queries

### Query painter information by Name

The first query allowed us to search for regional painters whose names included “Chiarini” or “Michetti”.
   
Functions used: <code class="language-plaintext highlighter-rouge">FILTER</code>, <code class="language-plaintext highlighter-rouge">REGEX</code>, <code class="language-plaintext highlighter-rouge">UNION</code>, <code class="language-plaintext highlighter-rouge">DISTINCT</code>, <code class="language-plaintext highlighter-rouge">LIMIT</code>.

![Image1SPARQLquery](/abremipainters/assets/images/Immagine1.jpg)

The results displayed by this SPARQL query are the following:

![Image2SPARQLquery](/abremipainters/assets/images/Immagine2.jpg)

### Query for Image <code class="language-plaintext highlighter-rouge">(P18)</code> identification

In order to find out if Wikidata provides the images of the two italian painters, we asked it to create a SPARQL query, enabling us to discover that Chiarini’s image was missing. ?????????????????

Functions used: <code class="language-plaintext highlighter-rouge">DISTINCT</code>, <code class="language-plaintext highlighter-rouge">ORDER BY</code>.

![Image3](/abremipainters/assets/images/Immagine3.jpg)

Results: 

![Image4](/abremipainters/assets/images/Immagine4.jpg)

### Query for Movement <code class="language-plaintext highlighter-rouge">(P135)</code> identification

Additionally, we wondered whether the artistic movement the painters belong to was shown in their Wikidata’s page. To find out, we developed the following SPARQL query.

Functions used: <code class="language-plaintext highlighter-rouge">OPTIONAL</code>, <code class="language-plaintext highlighter-rouge">ORDER BY</code>.

![Image4](/abremipainters/assets/images/Immagine5.jpg)

### Query for Work Location <code class="language-plaintext highlighter-rouge">(P937)</code> identification

We wanted to find their work locations to understand where each painter was active, crafting the following query, and using the keyword <code class="language-plaintext highlighter-rouge">ORDER BY</code> to list the painters’ work locations in a clear and organized way.

Functions used: <code class="language-plaintext highlighter-rouge">ORDER BY</code>

![Image4](/abremipainters/assets/images/Immagine6.jpg)

### Query for Country of Citizenship <code class="language-plaintext highlighter-rouge">(P27)</code> identification

We used the keyword <code class="language-plaintext highlighter-rouge">UNION</code> to retrieve the country of citizenship for both painters at once. This allowed us to retrieve their respective countries of citizenship efficiently without running separate queries.

Function used: <code class="language-plaintext highlighter-rouge">UNION</code>

![Image4](/abremipainters/assets/images/Immagine7.jpg)

***

## LLMs Prompting Techniques

### 1. Zero-shot Prompt
  
<pre><code>"Which movement did the painter Marcantonio Chiarini belong to?"</code></pre>
This prompt proves effective as it clearly identifies the subject, uses precise language to signal the type of answer expected (an artistic movement), and is concise and unambiguous.

### Responses:

1. CHATGPT

![Image4](/abremipainters/assets/images/Immagine8.jpg)

2. GEMINI

![Image4](/abremipainters/assets/images/Immagine9.jpg)

3. MISTRAL

![Image4](/abremipainters/assets/images/Immagine10.jpg)

### 2. Few-shot Prompt

<pre><code>"If Marcantonio Chiarini belonged to the Baroque movement and Claude Monet belonged to Impressionism, which movement did Francesco Paolo Michetti belong to?"</code></pre>
With this prompt, the LLM is given two clear examples of a well-known and lesser-known artist and their corresponding movements. This helps set a pattern: <code class="language-plaintext highlighter-rouge">name → movement</code> which teaches the model what kind of answer is expected. It narrows down ambiguity, encourages analogical reasoning, and improves accuracy.

### Responses:

1. CHATGPT

![Image4](/abremipainters/assets/images/Immagine11.jpg)

2. GEMINI

![Image4](/abremipainters/assets/images/Immagine12.jpg)

3. MISTRAL

![Image4](/abremipainters/assets/images/Immagine13.jpg)

### 3. Chain-of-Thought Prompt

<pre><code>"Which was Michetti’s work location? Let’s think step by step."</code></pre>

This kind of prompt encourages the LLM to think step by step before producing a final answer. It proves useful for reasoning tasks, like math, logic, or multi-step problems.

*Responses*

1. CHATGPT

![Image4](/abremipainters/assets/images/Immagine14.jpg)
![Image4](/abremipainters/assets/images/Immagine15.jpg)

2. GEMINI

![Image4](/abremipainters/assets/images/Immagine16.jpg)

3. MISTRAL

![Image4](/abremipainters/assets/images/Immagine17.jpg)

***

[← Main Page](./)
