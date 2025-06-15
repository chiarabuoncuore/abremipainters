---
layout: default
title: Gap 3 | Country of citizenship
description: Where do these painters come from? 
---

## Choosing the property

An artist's nationality often influences their styles and themes, therefore finding out the country of citizenship of painters like Marcantonio Chairini and Francesco Paolo Michetti is essential, since it provides the context to interpret their work and to better understand the environment that shaped their artistic identity.

## Identifying the gap

To pinpoint the gap on Wikidata, we created a **SPARQL query** to investigate how the place of birth <code class="language-plaintext highlighter-rouge">(P19)</code> and country of citizenship <code class="language-plaintext highlighter-rouge">(P27)</code> properties are associated with both painters. We chose the former as a correlated element to "country of citizenship" since they are usually closely linked. By using the <code class="language-plaintext highlighter-rouge">UNION</code> keyword, we asked the KG to provide us either with the painters' place of birth or country of citizenship.

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

### Results:

![resultsparqlcoc](/abremipainters/assets/images/resquerygap3.png)

Thanks to this SPARQL query, we discovered that Chiarini’s page did not indicate his country of citizenship, but rather only his place of birth.

## Retrieving the information

After detecting the gap, we asked the chosen LLMs to indicate Chiarini’s country of citizenship using a <code class="language-plaintext highlighter-rouge">few-shot prompt</code>:

```
If the country of citizenship of Giovanni Battista Tiepolo was the Republic of Venice and the country of citizenship of Caravaggio was the Duchy of Milan, which was the country of citizenship of painter Marcantonio Chiarini?
```

### 1. *CHATGPT*
  
![question to ChatGPT](/abremipainters/assets/images/chatcoc.jpg)

### 2. *GEMINI*
  
![question to Gemini](/abremipainters/assets/images/geminicoc.jpg)

### 3. *MISTRAL AI*
  
![question to Mistral](/abremipainters/assets/images/mistralcoc.png)

As can be seen, LLMS ChatGPT and Gemini provided the generally and historically correct answer "Papal States", while Mistral AI returned false information ("Republic of Venice"). Upon confirming that Marcantonio Chiarini was in fact born in <a href="https://www.treccani.it/enciclopedia/marc-antonio-chiarini_%28Dizionario-Biografico%29/" target="_blank">Bologna</a>, and that Bologna was part of the <a href="https://it.wikipedia.org/wiki/Bologna#Storia" target="_blank">Papal States</a> during that period, we discarded Mistral AI's response. We therefore associated Marcantonio Chiarini's country of citizenship with the **Papal States**.

## Filling the gap: creating RDF triples

We then prompted the three LLMs to generate meaningful **RDF triples** containing the discovered information. 

### 1. *CHATGPT*
  
![question to ChatGPT](/abremipainters/assets/images/chatrdfcoc.jpg)

### 2. *GEMINI*
  
![question to Gemini](/abremipainters/assets/images/geminirdfcoc.png)

### 3. *MISTRAL AI*
  
![question to Mistral](/abremipainters/assets/images/mistralrdfcoc.png)

## Manual correction

Since all three LLMs returned incorrect Q-IDs for Marcantonio Chiarini <code class="language-plaintext highlighter-rouge">(Q3288556)</code> while Gemini was the only one to return the correct Q-ID for Papal States <code class="language-plaintext highlighter-rouge">(Q170174)</code>, we refined the RDF triple manually as follows: 

![question to Mistral](/abremipainters/assets/images/correctedrdfcoc.jpg)

## Conclusion

Firstly, through a SPARQL query using the <code class="language-plaintext highlighter-rouge">UNION</code> keyword, we were able to find a piece of missing information regarding Chiarini’s country of citizenship. Subsequently we prompted the chosen LLMs ChatGPT, Gemini and Mistral AI to obtain such missing information. We then asked the LLMs to provide us with RDF triples regarding the painter’s country of citizenship, and manually corrected the given output, as they were all incorrect. It's important to note that Mistral AI provided us with completely incorrect information, which led us to outright ignore its input in this section of our project.

[← Main Page](./)
