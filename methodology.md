---
layout: default
title: Methodology
description:
---

## Goal
The primary goal of our project was to combine **Knowledge Graphs** and **Large Language Models** to enrich and complete structured information in the realm of art history in Wikidata, with a specific focus on two regional painters: Marcantonio Chiarini and Francesco Paolo Michetti. Our choice aimed at exploring the effectiveness of Wikidata and LLMs in handling less globally known figures, highlighting potential disparities in data completeness and evaluating the quality and reliability of the outputs suggested by LLMs.

## Case study
As a starting point, we selected **Wikidata** as our reference Knowledge Graph and defined a set of crucial biographical and artistic properties that we considered essential for describing a painter. These include:
* Artistic movement <code class="language-plaintext highlighter-rouge">(P135)</code>
* Image depicting the painter <code class="language-plaintext highlighter-rouge">(P18)</code>
* Work location <code class="language-plaintext highlighter-rouge">(P937)</code>
* Country of citizenship <code class="language-plaintext highlighter-rouge">(P27)</code>
We then applied this framework to the two painters in question: Marcantonio Chiarini and Francesco Paolo Michetti. 
	
### STEP 1: Crafting SPARQL queries
We used **Wikidata Query Service** to extract existing data and identify missing information.
We crafted significant **SPARQL** queries using multiple keywords:
<code class="language-plaintext highlighter-rouge">UNION</code>,<code class="language-plaintext highlighter-rouge">OPTIONAL</code>,<code class="language-plaintext highlighter-rouge">UNION</code>,<code class="language-plaintext highlighter-rouge">DISTINCT</code>,<code class="language-plaintext highlighter-rouge">FILTER</code>,<code class="language-plaintext highlighter-rouge">REGEX</code>,<code class="language-plaintext highlighter-rouge">ORDER BY</code>,<code class="language-plaintext highlighter-rouge">LIMIT</code>,<code class="language-plaintext highlighter-rouge">SERVICE</code>.

Example:


***

[← Main Page](./)
