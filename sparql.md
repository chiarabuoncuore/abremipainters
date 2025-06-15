---
layout: default
title: SPARQL and LLM Prompts 
description: Techniques Used
---
This section presents the **SPARQL queries** and **Large Language Model (LLM) prompts** employed to check, select and enrich <a href="https://www.treccani.it/enciclopedia/marc-antonio-chiarini_%28Dizionario-Biografico%29/" target="_blank"> Marcantonio Chiarini</a> and <a href="https://www.treccani.it/enciclopedia/francesco-paolo-michetti_%28Dizionario-Biografico%29/" target="_blank">Francesco Paolo Michetti</a>'s information on <a href="https://www.wikidata.org/wiki/Wikidata:Main_Page" target="_blank">Wikidata</a>. Our objective was to uncover gaps in Wikidata's coverage of such artists. To achieve this, we used meaningful SPARQL queries to probe Wikidata's existing records, as well as three distinct prompting strategies (<code class="language-plaintext highlighter-rouge">zero-shot prompt</code>, <code class="language-plaintext highlighter-rouge">few-shot prompt</code> and <code class="language-plaintext highlighter-rouge">chain-of-thought prompt</code>. 

## SPARQL Queries

### Query 1: Identifying the painters

The first query allowed us to search for painters whose names included “Chiarini” or “Michetti”.
   
Keywords used: <code class="language-plaintext highlighter-rouge">DISTINCT</code>, <code class="language-plaintext highlighter-rouge">FILTER</code>, <code class="language-plaintext highlighter-rouge">REGEX</code>, <code class="language-plaintext highlighter-rouge">LIMIT</code>.

```sparql
SELECT DISTINCT ?painter ?painterLabel
WHERE {
  ?painter wdt:P106 wd:Q1028181 .
  ?painter rdfs:label ?painterLabel .
  FILTER(LANG(?painterLabel) = "en") .
  FILTER(
    REGEX(?painterLabel, "Chiarini", "i") ||
    REGEX(?painterLabel, "Michetti", "i")
    )
}
LIMIT 10
```

The results displayed by this SPARQL query are the following:

![Image2SPARQLquery](/abremipainters/assets/images/Immagine2.jpg)

This allowed us to identify the Q-IDs associated with Marcantonio Chiarini and Francesco Paolo Michetti. 

### Query 2: Image <code class="language-plaintext highlighter-rouge">(P18)</code>

The following SPARQL query allowed us to identify whether Wikidata features any portraits associated with the painters. 

Keywords used: <code class="language-plaintext highlighter-rouge">DISTINCT</code>, <code class="language-plaintext highlighter-rouge">OPTIONAL</code>, <code class="language-plaintext highlighter-rouge">ORDER BY</code>.

```sparql
     SELECT DISTINCT ?painter ?painterLabel ?image ?imageLabel
WHERE {
  VALUES ?painter {
    wd:Q3081044 wd:Q3288556
  }
  OPTIONAL { ?painter wdt:P18 ?image . }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
}
ORDER BY ?painterLabel
```

The results displayed by this SPARQL query are the following:

![ressparqlquerygap1](/abremipainters/assets/images/resquerygap1.png)

This allowed us to discover that Marcantonio Chiarini's portrait is missing from Wikidata's dataset.

### Query 3: Movement <code class="language-plaintext highlighter-rouge">(P135)</code>

Additionally, we wondered whether the artistic movement the painters belong to was shown in their Wikidata’s page. To find out, we developed the following SPARQL query.

Keywords used: <code class="language-plaintext highlighter-rouge">DISTINCT</code>, <code class="language-plaintext highlighter-rouge">OPTIONAL</code>, <code class="language-plaintext highlighter-rouge">ORDER BY</code>.

```sparql
SELECT DISTINCT ?painter ?painterLabel ?movementLabel
WHERE {
  VALUES ?painter {
    wd:Q3081044 wd:Q3288556
  }
  OPTIONAL { ?painter wdt:P135 ?movement . }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
}
ORDER BY ?painterLabel
```

The results displayed by this SPARQL query are the following:

![ressparqlquerygap2](/abremipainters/assets/images/resquerygap2.png)

This allowed us to discover that information about both painters' artistic movements is missing. 

### Query 4: Place of Birth <code class="language-plaintext highlighter-rouge">(P19)</code> and Country of Citizenship <code class="language-plaintext highlighter-rouge">(P27)</code>

In order to look for the painters' country of citizenship, we also used the adjacent topic of birthplace to be provided with as accurate as possible information. 

Keywords used: <code class="language-plaintext highlighter-rouge">DISTINCT</code>, <code class="language-plaintext highlighter-rouge">UNION</code>, <code class="language-plaintext highlighter-rouge">ORDER BY</code>.

```sparql
SELECT DISTINCT ?painter ?painterLabel ?placeofbirthLabel ?countryofcitizenshipLabel
WHERE {
  VALUES ?painter {
    wd:Q3081044 wd:Q3288556
  }
  {
    ?painter wdt:P19 ?placeofbirth .
  }
  UNION
  {
    ?painter wdt:P27 ?countryofcitizenship .
  }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
}
ORDER BY ?painterLabel
```

The results displayed by this SPARQL query are the following:

![ressparqlquerygap3](/abremipainters/assets/images/resquerygap3.png)

This allowed us to discover that both painters feature information about their place of birth <code class="language-plaintext highlighter-rouge">(P19)</code>, while Marcantonio Chiarini is missing his country of citizenship <code class="language-plaintext highlighter-rouge">(P27)</code>.

### Query 5: Work Location <code class="language-plaintext highlighter-rouge">(P937)</code>

Finally, we wanted to identify both painters' work locations to understand where they were professionally active, crafting the following SPARQL query.

Keywords used:  <code class="language-plaintext highlighter-rouge">DISTINCT</code>, <code class="language-plaintext highlighter-rouge">OPTIONAL</code>, <code class="language-plaintext highlighter-rouge">ORDER BY</code>.

```sparql
SELECT DISTINCT ?painter ?painterLabel ?worklocationLabel
WHERE {
  VALUES ?painter {
    wd:Q3081044 wd:Q3288556
  }
  OPTIONAL { ?painter wdt:P937 ?worklocation . }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
}
ORDER BY ?painterLabel
```

The results displayed by this SPARQL query are the following:

![ressparqlquerygap4](/abremipainters/assets/images/resquerygap4.png)

This allowed us to discover that Francesco Paolo Michetti is missing information on hiw work location <code class="language-plaintext highlighter-rouge">(937)</code>.

***

## LLM Prompting Techniques

### 1. Zero-shot Prompt
  
<pre><code>"Which movement did the painter Marcantonio Chiarini belong to?"</code></pre>

This prompt proves effective as it clearly identifies the subject, uses precise language to signal the type of answer expected (an artistic movement), and is concise and unambiguous.

### Responses:

### 1. CHATGPT

![Image4](/abremipainters/assets/images/Immagine8.jpg)

### 2. GEMINI

![Image4](/abremipainters/assets/images/Immagine9.jpg)

### 3. MISTRAL

![Image4](/abremipainters/assets/images/Immagine10.jpg)

### Commentary:

While Gemini gives a more direct and concise answer, ChatGPT and Mistral AI provide longer responses with, respectively, more context but excess information on the painter which isn't strictly useful for the original enquiry, and additional context describing the art movement itself. 

### 2. Few-shot Prompt

<pre><code>"If Marcantonio Chiarini belonged to the Baroque movement and Claude Monet belonged to Impressionism, which movement did Francesco Paolo Michetti belong to?"</code></pre>

With this prompt, the LLM is given two clear examples of at the same time a well-known and a lesser-known artist and the corresponding artistic movements. This helps set the pattern <code class="language-plaintext highlighter-rouge">name → movement</code>, teaching the model what kind of answer is expected. It's meant to narrow down ambiguity, encourage analogical reasoning, and improve accuracy and conciseness. 

### Responses:

### 1. CHATGPT

![Image4](/abremipainters/assets/images/Immagine11.jpg)

### 2. GEMINI

![Image4](/abremipainters/assets/images/Immagine12.jpg)

### 3. MISTRAL

![Image4](/abremipainters/assets/images/Immagine13.jpg)

### Commentary:

Once again, where Gemini provides a brief and direct reply, ChatGPT and Mistral AI offer slightly broader answers, exploring on the one hand all the artist's possible connections with artistic movements and motivating them, and on the other hand the characteristics of the movement itself.

It's interesting to note, given that the questions provided as examples feature the same topic (artistic movement), how the two prompting techniques lead to different results: the zero-shot one provided, as seen above, two longer replies, while the few-shot one generated more concise answers, yet still including some excess information, either about the painter or the artistic movement. 

### 3. Chain-of-Thought Prompt

<pre><code>"Which was Francesco Paolo Michetti’s work location? Let’s think step by step."</code></pre>

This kind of prompt encourages the LLM to think step by step before producing a final answer. It proves useful in this context, since establishing the painters' work location may imply a more in-depth research about their biography, such as considering whether they lived, studied or worked abroad, if they traveled much, and more. 

### Responses:

### 1. *CHATGPT*

![chatquestion1](/abremipainters/assets/images/chatworkloc1.jpg)
![chatquestion2](/abremipainters/assets/images/chatworkloc2.jpg)
![chatquestion3](/abremipainters/assets/images/chatworkloc3.jpg)

### 2. _GEMINI_

![geminiquestion](/abremipainters/assets/images/geminiworkloc.png)

### 3. _MISTRAL AI_

![mistralquestion](/abremipainters/assets/images/mistralworkloc.png)

### Commentary:

Once again, where Gemini provides a brief and direct reply, ChatGPT and Mistral AI offer slightly broader answers, exploring on the one hand all the artist's possible connections with artistic movements and motivating them, and on the other hand the characteristics of the movement itself.

***

[← Main Page](./)
