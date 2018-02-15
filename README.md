# CopyrightOnto - Copyright Ontology
_**A Copyright Ontology for Content Rights Management**_

An ontology is a formalization of concepts and relations within a domain. The Copyright Ontology tries to formalise the copyright domain. It is a Web Ontology and thus it is implemented using the World Wide Web Consortium (W3C) standards Resource Description Framework ([RDF](https://de.wikipedia.org/wiki/Resource_Description_Framework)) and Web Ontology Language ([OWL](https://en.wikipedia.org/wiki/Web_Ontology_Language)).

## Approach
The copyright domain is quite complex so the **Copyright Ontology** attempts its **conceptualisation** in **three steps**, which allows facing this process in an incremental way.

First, the objective is the more primitive part, the Creation Model. Second, there is the model for the rights part, the Rights Model, and finally a model for the available actions, the Action Model, which is built on top of the two previous ones:

1. [**Creation Model**](CreationModel) - copyright creations lifecycle.
2. [**Rights Model**](RightsModel) - copyright rights hierarchy.
3. [**Actions Model**](ActionsModel) - copyright actions on creations.

To facilitate the adoption of the Copyright Ontology, it is **built on top of** the generic ontology provided by the [**schema.org**](http://schema.org) vocabulary, one of the best-known and more widely used data vocabularies, promoted by the leading search engines (Google, Yahoo, Bing and Yandex). An RDF version of schema.org has been used, which is automatically generated from the official [RDFa](http://schema.org/docs/schema_org_rdfa.html) version using [pyRdfa](https://www.w3.org/2012/pyRdfa) using:

[https://www.w3.org/2012/pyRdfa/extract?uri=http%3A%2F%2Fschema.org%2Fdocs%2Fschema_org_rdfa.html&format=turtle](https://www.w3.org/2012/pyRdfa/extract?uri=http%3A%2F%2Fschema.org%2Fdocs%2Fschema_org_rdfa.html&format=turtle)
