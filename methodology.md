---
layout: default
title: Methodology
description:
---

## Goal
The primary goal of our project was to combine **Knowledge Graphs** and **Large Language Models** to enrich structured information in the realm of art history in <a href="https://www.wikidata.org/wiki/Wikidata:Main_Page" target="_blank">Wikidata</a>, with a specific focus on two regional painters: <a href="https://www.treccani.it/enciclopedia/marc-antonio-chiarini_%28Dizionario-Biografico%29/" target="_blank">Marcantonio Chiarini</a> <code class="language-plaintext highlighter-rouge">(Q3288556)</code> and <a href="https://www.treccani.it/enciclopedia/francesco-paolo-michetti_%28Dizionario-Biografico%29/" target="_blank">Francesco Paolo Michetti</a> <code class="language-plaintext highlighter-rouge">(Q3081044)</code>. Our subject choice aimed at exploring the effectiveness of Wikidata and LLMs in handling less globally known painters, highlighting potential disparities in data completeness and evaluating the quality and reliability of the outputs suggested by LLMs.

***

## Case study
As a starting point, we selected **Wikidata** as our reference Knowledge Graph and defined a set of crucial biographical and artistic properties that we considered essential for describing a painter. These include: 

* Image depicting the painter <code class="language-plaintext highlighter-rouge">(P18)</code>
* Movement <code class="language-plaintext highlighter-rouge">(P135)</code>
* Country of citizenship <code class="language-plaintext highlighter-rouge">(P27)</code> and Place of birth <code class="language-plaintext highlighter-rouge">(P19)</code>
* Work location <code class="language-plaintext highlighter-rouge">(P937)</code>

We then applied this framework to the two painters in question: Marcantonio Chiarini and Francesco Paolo Michetti. 

***
	
## STEP 1: Crafting SPARQL queries
We used <a href="https://query.wikidata.org/" target="_blank">**Wikidata Query Service**</a> to extract existing data and identify missing information.

We crafted significant **SPARQL** queries using multiple keywords:
<code class="language-plaintext highlighter-rouge">OPTIONAL</code>,<code class="language-plaintext highlighter-rouge">UNION</code>,<code class="language-plaintext highlighter-rouge">DISTINCT</code>,<code class="language-plaintext highlighter-rouge">FILTER</code>,<code class="language-plaintext highlighter-rouge">REGEX</code>,<code class="language-plaintext highlighter-rouge">ORDER BY</code>,<code class="language-plaintext highlighter-rouge">LIMIT</code>,<code class="language-plaintext highlighter-rouge">SERVICE</code>.

Example:
```sparql
SELECT ?painter ?painterLabel ?movementLabel
WHERE {
  VALUES ?painter {
    wd:Q3081044 wd:Q3288556
  }
  OPTIONAL { ?painter wdt:P135 ?movement . }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
}
ORDER BY ?painterLabel
```

This query allowed us to explore how the movement property <code class="language-plaintext highlighter-rouge">P135</code> is linked to both painters and discover the lack of it. By using the keywords <code class="language-plaintext highlighter-rouge">OPTIONAL</code> and <code class="language-plaintext highlighter-rouge">ORDER BY</code>, we aimed to clearly visualize the missing information.

## STEP 2: Prompting LLMS 
We prompted three Large Language Models:
* <a href="https://chatgpt.com/" target="_blank">**ChatGPT**</a>
* <a href="https://gemini.google.com/" target="_blank">**Gemini**</a>
* <a href="https://chat.mistral.ai/chat" target="_blank">**Mistral AI**</a>

to retrieve the missing information using three distinct **prompting techniques**, each tailored to the type of information being requested:

<ol>
  <li><strong>Zero-shot prompting</strong></li> 
  <p>→ direct questions with no prior examples provided.</p>
  <p><pre><code>“Which movement did Marcantonio Chiarini belong to?”</code></pre></p>
  <p>→ typically simple, factual answers requiring no context or reasoning.</p> 
  <li><strong>Few-shot prompting</strong></li>
  <p>→ providing examples to guide the answer toward a significant one.</p>
  <p><pre><code>"If the country of citizenship of Giovanni Battista Tiepolo was the Republic of Venice and the country of citizenship of Caravaggio was the Duchy of Milan, which was the country of citizenship of painter Marcantonio Chiarini?"</code></pre></p>
  <p><pre><code>“If Marcantonio Chiarini belonged to the Baroque movement and Claude Monet belonged to Impressionism, which movement did Francesco Paolo Michetti belong to?”</code></pre></p>
  <p>→ since movements are typically associated with major painters, we encouraged an answer providing examples including both a well known and a less known painter.</p>
  <li><strong>Chain-of-Thought Prompting</strong></li>
  <p>→ encouraging the LLMs to explain their reasoning step by step.</p>
  <p><pre><code>"Which was Michetti’s work location? Let’s think step by step."</code></pre></p>
  <p>→ identifying the painter’s work location may require interpreting his biography and career path to deduce a consistent answer.</p>
</ol>

## STEP 3: Creating RDF triples and manual correction
Once the LLMs provided factual outputs, we asked them to format these pieces of information into Wikidata-compatible RDF triples.
As they provided a starting point, we then compared and evaluated the results. Manual intervention was necessary mainly due to inaccurate Q-IDs. 

## STEP 4: Conclusions
This methodology demonstrated that LLMs can assist in enriching Knowledge Graphs, but cannot yet be trusted for fully automated integration without human validation. 

***

## Tools 

<p>☑️ <strong>Wikidata</strong> → Knowledge Graph</p>
<p>☑️ <strong>Wikidata Query Service</strong> → query the KG to uncover the gaps</p>
<p>☑️ <strong>ChatGPT - Gemini - Mistral AI</strong> → retrieve missing information and generate RDF triples</p>
<p>☑️ <strong>Manual editing</strong> → correct LLMs inaccuracies</p>
<p>☑️ <strong>GitHub - Jekyll - Markdown - HTML</strong> → build the website for the report</p>

***

[← Main Page](./)
