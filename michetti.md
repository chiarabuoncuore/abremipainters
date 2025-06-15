---
layout: default
title: Francesco Paolo Michetti
description: Gap 2 | Movement
---

We retrieved the information regarding the movement associated with Francesco Paolo Michetti by using a few-shot prompt, including in the examples both a widely-known and a lesser-known painter in order to maximise its efficiency: “If Marcantonio Chiarini belonged to the Baroque movement and Claude Monet belonged to Impressionism, which movement did Francesco Paolo Michetti belong to?”.

1. *CHAT GPT*

![Michetti](/abremipainters/assets/images/Immagine11.jpg)

2. *GEMINI*

![Michetti](/abremipainters/assets/images/Immagine12.jpg)

3. *MISTRAL AI*

![Michetti](/abremipainters/assets/images/Immagine13.jpg)

The answers didn’t provide a straightforward or unanimous result, but Realism appeared as the most commonly mentioned movement linked to Francesco Paolo Michetti. Verismo and the Scuola di Resina were suggested as subcategories, while Impressionism and Symbolism came up as possible influences. Based on this, our next step was to ask the language models to generate RDF triples that would add Realism as a movement on Michetti’s Wikidata page.

1. *CHAT GPT*

![Michetti1](/abremipainters/assets/images/Michetti1.png)

2. *GEMINI*

![Michetti1](/abremipainters/assets/images/Michetti2.png)

3. *MISTRAL AI* 

![Michetti1](/abremipainters/assets/images/Michetti3.png)

- **MANUAL CORRECTION**

Our analysis revealed that both ChatGPT and Mistral AI returned incorrect Wikidata QIDs for Francesco Paolo Michetti and the Realism movement. In contrast, the QIDs provided by Gemini were accurate. As a result, we manually refined the RDF triple as follows:

![Michetti1](/abremipainters/assets/images/Michetti4.png)


***

[← Gap 2](./gap2.md)

[← Main Page](./)
