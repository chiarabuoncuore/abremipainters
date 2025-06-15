---
layout: default
title: Marcantonio Chiarini
description: Gap 2 | Movement
---

## Identifying the gap:

We retrieved the information regarding the movement associated with Marcantonio Chiarini by using a <code class="language-plaintext highlighter-rouge">zero-shot prompt</code>:
<pre><code>“Which movement did the painter Marcantonio Chiarini belong to?”</code></pre>

### 1. *CHAT GPT*

![chatchiarinimov](/abremipainters/assets/images/Immagine8.jpg)

### 2. *GEMINI*
   
![geminichiarinimov](/abremipainters/assets/images/Immagine9.jpg)
 
### 3. *MISTRAL AI*

![mistralchiarinimov](/abremipainters/assets/images/Immagine10.jpg)

The results revealed a slight variation between two broader suggestions of “Baroque” and one more specific reference to “Late Baroque”. To reduce the risk of inaccuracies, we ultimately chose to use the more general and commonly suggested label, associating Marcantonio Chiarini with the **Baroque** movement.

## Filling the gap: creating RDF triples

We then prompted the three LLMs to generate relevant **RDF triples** to hypothetically add this information to Wikidata and conducted a critical evaluation of the generated outputs.

### 1. *CHAT GPT*

![rdfchiarinimovchat](/abremipainters/assets/images/CHIARINI1.png)

### 2. *GEMINI*

![rdfchiarinimovgemini](/abremipainters/assets/images/CHIARINI2.png)

### 3. *MISTRAL AI*

![rdfchiarinimovmistral](/abremipainters/assets/images/CHIARINI3.png)

## Manual correction:

Our analysis showed that all three LLMs returned an incorrect Q-ID for Marcantonio Chiarini, while only Mistral generated an incorrect Q-ID for the Baroque movement. Consequently, we manually corrected the RDF triple:

![correctrdfchiarinimov](/abremipainters/assets/images/CHIARINI4.png) CAMBIA 

***

[← Gap](./gap2.md) 

[← Main Page](./)
