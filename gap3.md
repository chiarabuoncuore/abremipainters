---
layout: default
title: Gap 3 | Country of citizenship
---
An artist's nationality often influences their styles and themes, therefore finding out the “country of citizenship” of painters like Marcantonio Chairini and Francesco Paolo Michetti is essential, since it provides the context for interpreting their work and to better understand the environment that shaped their artistic identity. For this reason, our goal is to update this property in their respective WikiData’s pages.

**1st step: IDENTIFYING THE GAP**
 
 We created the following SPARQL query using Union operator in order to find out Chiarini and Michetti’s country of citizenship.


**GAP IDENTIFIED:** thanks to this SPARQL query, we discovered that Chiarini’s page did not indicate his country of citizenship.

![Sparql query](/abremipainters/assets/images/chiarinicountryofcitizenship/SPARQLQUERYCHIARINICOUNTRYOFCITIZENSHIP.jpg)

**2nd STEP: REQUEST THE MISSING INFORMATION TO 3 DIFFERENT LANGUAGE MODELS**

 after having detected the gap, we asked, through a “zero-shot prompting technique”, which was Chiarini’s country of citizenship to 3 different LLMs: Chat GPT, Gemini and Mistral.

- **CHATGPT**
  
![question to ChatGPT](/abremipainters/assets/images/chiarinicountryofcitizenship/CHATGPTQUESTION.jpg)


- **GEMINI**
  
![question to Gemini](/abremipainters/assets/images/chiarinicountryofcitizenship/GEMINIQUESTION.jpg)


- **MISTRAL**
  
![question to Mistral](/abremipainters/assets/images/chiarinicountryofcitizenship/MISTRALQUESTION.png)


**INFORMATION ACQUIRED:** Since all the 3 LLMs provided us with the same answer, we took for granted that Chiarini’s country of citizenship is: Italy.


**3rd step: CREATION OF RDF TRIPLES USING WIKIDATA ONTOLOGY**
 
 Having discovered Italy (Q38) is Chiarini’s country of citizenship, we asked the 3 LLMs to create an RDF triples basing on WikiData ontology.

- **CHATGPT:**
  
![RDF triple created by ChatGPT](/abremipainters/assets/images/chiarinicountryofcitizenship/GEMINIINCORRECTRDF.jpg)


- **GEMINI:**
  
![RDF triple created by Gemini](/abremipainters/assets/images/chiarinicountryofcitizenship/CHATGPTRDFTRIPLE.jpg)


 Since Chiarini’s code was incorrect, we manually refined it:
 

 ![RDF triple created by Gemini, manually fixed](/abremipainters/assets/images/chiarinicountryofcitizenship/GEMINICORRECTRDF.jpg)
 

- **MISTRAL:**
  
![RDF triple created by Mistral](/abremipainters/assets/images/chiarinicountryofcitizenship/MISTRALINCORRECTRDF.jpg)

Mistral provided us only with an example of a RDF triple, so we fixed it manually:

![RDF triple created by Mistral, manually refined](/abremipainters/assets/images/chiarinicountryofcitizenship/MISTRALCORRECTRDF.jpg)


After having verified every prefix, here’s the final and correct RDF triple:

![Final RDF](/abremipainters/assets/images/chiarinicountryofcitizenship/FINALRDF.jpg)

**4th step: SUMMARY**

Firstly, thanks to the manual creation of a SPARQL query using “UNION” as a command, we were able to find a piece of missing information: Chiarini’s country of citizenship. Then we had the possibility to obtain this information by asking ChatGPT, Gemini and Mistral. Subsequently, we asked these LLMs to provide us with RDF triples regarding the painter’s country of citizenship. Both Gemini and Mistral’s RDF triple had to be manually refined.


[← Main Page](./)
