# Rights Model

| Downloads                                                    | Documentation                                                |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [![DownloadTurtle](https://img.shields.io/badge/style-Turtle-orange.svg?style=flat&label=Download)](copyrightonto-rightsmodel.ttl) | [![Documentation](https://img.shields.io/badge/style-Ontodocs-blue.svg?style=flat&label=Documentation)](https://rhizomik.github.io/copyrightonto/rightsmodel/) [![Visualization](https://img.shields.io/badge/style-VOWL-green.svg?style=flat&label=Visualization)](http://visualdataweb.de/webvowl/#iri=https://raw.githubusercontent.com/rhizomik/copyrightonto/master/RightsModel/copyrightonto-rightsmodel.ttl) |

**Table of Contents**

- [Overview](#overview)
- [WIPO Rights Model](#wipo-rights-model)
  - [Economic Rights](#economic-rights)
  - [Other Rights](#other-rights)
    - [Moral Rights](#moral-rights)
    - [Related Rights](#related-rights)
    - [Copyright Exceptions](#copyright-exceptions)
- [US Music Industry Rights Model](#us-music-industry-rights-model)
- [US Film Industry Rights Model](#us-film-industry-rights-model)
- [Implementations](#implementation)
- [Related Work](#related-work)
- [The Rest of the Copyright Ontology](#the-rest-of-the-copyright-ontology)
- [References](#references)

## Overview

Once we have established the [**Creation Model**](../CreationModel), it is time to capture how it is regulated. This is done by the **Rights Models** part of the Copyright Ontology described in this document, which capture the copyright legal aspects.

There are many legal systems worldwide and the objective of the Copyright Ontology is to provide the mechanisms to model them. As part of this effort, and to test and illustrate the capabilities of the Rights Model, we have also generated some **Rights Models for specific legal frameworks**. 

The most relevant one, as it helps testing the scope of the whole Copyright Ontology, is the legal framework proposed by the **World Intellectual Property Organisation** [(WIPO, 2004)](#references) described in the next section. 

The idea is to also be capable of modelling **country specific** legal systems or even the rights governing **particular industries**. For instance the music or the film industries in the USA. This is possible thanks to the last part of the Copyright Ontology, the [**Actions Model**](../ActionsModel), which establishes a common foundation based on actions involving copyrighted content. These actions intend to be generic and the target of the restrictions defined through rights.

## WIPO Rights Model

Though there is not a global copyright framework that uniformly applies worldwide, the World Intellectual Property Organisation (WIPO) has arranged [many treaties](http://www.wipo.int/treaties/en/) to harmonise the plethora of country-level regulations into a unified system that facilitates copyright protection and management across borders. For instance, the [Berne Convention for the Protection of Literary and Artistic Works](http://www.wipo.int/treaties/en/ip/berne/) (1886) or the [Beijing Treaty on Audiovisual Performances](http://www.wipo.int/treaties/en/ip/beijing/) (2012)

The Copyright Ontology captures this overarching set of rights in its WIPO Rights Model. It includes **economic** and **related rights**, plus **moral rights** when applicable,  as shown in Figure 1.

| ![Copyright Ontology Rights Model](http://www.plantuml.com/plantuml/svg/JSez3i8m343Xgy01Y7TMPbIfDoYfcrWaSUGV8JXzqm6fwtlVbLeilg9BkMIphdS0MJuXaML_kQ94ReRDGkGAakd7bTuGkN-5KhOn6UgYXWBp4VJ9AnROABcWmkCFfm5l9n6wrx83) |
| :--------------------------------------: |
| Figure 1. The Rights Model in the Copyright Ontology |

### Economic Rights

These are the most relevant rights in the context of copyright value chains. They are related to the exploitation of copyright:

-   **Reproduction Right**: regulates actions that produce replicas of a given object, i.e. *Instances* as defined in the [Creation Model](../CreationModel). Examples of reproduction are the mass production of CD copies from an audio recording master, to scan a book to produce a digitalisation of it or to download a digital file into the local hard disk.
-   **Distribution Right**: governs actions geared towards distributing previously made copies incorporated into tangible products. The ownership of the corresponding physical support can be transferred permanently, i.e. the distribution act is a sale, or just temporally, i.e. a rent if there is a significant economic compensation or a loan if not.
-   **Public Performance Right**: controls *Performances* of works, as defined in the [Creation Model](../CreationModel), when they are made in public, i.e. before an audience.
-   **Fixation Right**: regulates the materialisation of a *Performance* into an object that constitutes a *Recording*, also defined in the [Creation Model](../CreationModel). Common fixations are motion pictures and sound recordings, which are governed by the corresponding **Sound Recording Right** and **Motion Picture Right**.
-   **Communication Right**: regulates the realisation of *Communications* of works, as defined in the [Creation Model](../CreationModel), including wire or wireless means and those realised from a place and at a time individually selected. This right is concretised into **Broadcasting Right**, when the communication is simultaneously made to a plurality of people, and **Making Available Right**, when the communication is individually chosen.
-   **Transformation Right**: controls actions that generate new works from previously existing ones. The results of this kind of actions are considered new works, and not mere reproductions because they contribute something new. This right is concretised into the **Adaptation Right**,  the **Translation Right** and the **Synchronization Right**. The former creates a new work of a different type than the original one, e.g. a film from a novel. The latter generates a work of the same type but in a different language.

These rights are conceded to the author or promoter of the creation by the mere act of bringing the work into existence. Consequently, whenever an author generates a new creation, the author **automatically** gets all Economic Rights, and also the Moral Rights as detailed next. This fact can also be captured using the Copyright Ontology as detailed in the [Actions Model](../ActionsModel). From this initial situation, it is possible to transfer, or at least license, the Economic Rights to third parties giving rise to content value chains, as also detailed in the [Actions Model](../ActionsModel).

### Other Rights

In addition to the Economic Rights, many jurisdictions recognise additional rights. Many of them are also being harmonised worldwide through different treaties. For instance, the Berne Convention requires member countries to grant to authors the Attribution and Integrity moral rights. There are also treaties for the protection of related rights, like those of performers, producers or broadcasters as detailed next.

#### Moral Rights

Moral rights are always held by the creator and cannot be commercially exploited. They are not present in all legal systems. However, WIPO treaties are promoting some of them to improve worldwide copyright law harmonisation:

-   **Attribution Right**: the right to claim authorship of the work.
-   **Integrity Right**: the right to object to any distortion, mutilation or other modification of, or other derogatory action to the work which would be prejudicial to the author's honour or reputation.
-   **Disclosure Right**: exclusive right to reveal the work, making it available.
-   **Withdrawal Right**: exclusive right to withdraw the work from the market.

#### Related Rights

In addition to authors' rights, other parties also involved in the exploitation of works enjoy their own rights. Performers, producers and broadcasters make a significant contribution to make works reach end-users. Their contribution entails the **Related Rights**, also known as **Neighbouring Rights**:

-   **Performers Rights**: performers have exclusive Fixation, Communication, Reproduction, Public Performance and Distribution Rights over their performances. These rights, when the performance is of a copyrighted work, will be in addition to the rights of copyright owners with respect to the performance and subsequent exploitation of the performance.
-   **Producers Rights**: producers have exclusive Reproduction Right over their fixations and exclusive Distribution Right over the resulting copies. As before, these rights will be in addition to the rights of copyright owners.
-   **Broadcasters Rights**: broadcasters have exclusive Broadcasting, Fixation and Reproduction Rights over their broadcasts. Here broadcasting of a broadcast is understood as re-broadcasting. Re-broadcasting is either simultaneous transmission of a broadcast of a program being received from another source or a new deferred broadcast of a formerly recorded program transmitted or received earlier. These rights must be considered in addition to the rights of copyright owners when applicable.

#### Copyright Exceptions

End-users do not hold any rights to the creations they consume. They need to comply with copyright to legally access works. This means that they access and consume works under the author or the copyright holder authorisation or license, sticking to their terms and conditions. 

For instance, a license for a film states that the user can only view it a fixed number of times and thus is cheaper than a DVD copy. This kind of conditions are not regulated by copyright, they are established by the usage agreements among end-users and content providers. Other uses not explicitly authorised are forbidden, like making copies that are not kept private.  

This kind of agreements are the kind of expressions captured by rights expression languages that can be modelled using the last part of the Copyright Ontology, the [**Actions Model**](../ActionsModel). The Copyright Ontology is general enough to be able to model copyright-related actions and also end-users actions like those established in content provision agreements.

However, there are some aspects of end-users' activity that are regulated by copyright. End-users have some special permissions that grant them the possibility to perform some actions otherwise forbidden by copyright. These exceptions to copyright are limitations to authors' rights and, although they are often presented as end-user privileges, they are not end-users' rights, though they are commonly referred to like that, e.g. the "right" to quote.

The following copyright exceptions included in the Copyright Ontology are just a generalisation of the full range of exceptions considered in jurisdictions worldwide:

- **Quotation Exception**: the making of quotations from a protected work, provided that the source is mentioned and that the extent of the quotation is compatible with fair practice.
- **Education Exception**: illustration for teaching and research, uses for reproduction and communication to the public in educational institutions, libraries and archives.
- **Reporting Exception**: uses by the press to report about current events.
- **Official Act Exception**: use for certain administrative, judicial or security proceedings and religious or official ceremonies.
- **Private Copy Exception**: the reproduction of a work exclusively for the personal and private use of the person who makes the reproduction, e.g. a backup.
- **Parody Exception**: use for parody and caricature.
- **Temporary Reproduction Exception**: ephemeral reproductions required for facilitating some technological processes geared towards work usage, e.g. internet caches.

## US Music Industry Rights Model

Work in progress.

## US Film Industry Rights Model

Work in progress.

## Implementation

The **Rights Model** part of the **Copyright Ontology** is implemented using the Resource Description Format ([RDF](https://www.w3.org/RDF/)) and the Web Ontology Language ([OWL](https://www.w3.org/OWL/)). It is available in [Turtle](https://www.w3.org/TR/turtle/) RDF serialization format:

- Copyright Ontology Rights Model: [**copyrightonto-rightsmodel.ttl**](copyrightonto-rightsmodel.ttl)

The ontology can be downloaded from the previous link and converted to other RDF/OWL formats using services like Anything To Triples ([Any23](http://any23-vm2.apache.org/))

There is also an ontology documentation generated from the RDF/OWL using [OntoSpy](http://lambdamusic.github.io/Ontospy/):

- Copyright Ontology Rights Model: [**documentation**](https://rhizomik.github.io/copyrightonto/rightsmodel/)

It is also possible to get an overview of the ontology using visualisation services like [WebVOWL](http://vowl.visualdataweb.org/webvowl/):

- Copyright Ontology Rights Model [**overview**](http://visualdataweb.de/webvowl/#iri=https://raw.githubusercontent.com/rhizomik/copyrightonto/master/RightsModel/copyrightonto-rightsmodel.ttl)

## Related Work

Other attempts to formalise copyright and rights expression, like MPEG-21 ontologies or Rights Expression Languages schemas, generally ignore the underlying legal framework. They go straight into modelling the actions that are permitted or prohibited and avoid the extra layer provided by the legal concepts that shape these actions, who can perform them or the entities they operate on.

Though this might be seen as a simplification that facilitates the definition and adoption of these proposals, our view is that this is, in fact, a lost opportunity.  Considering the underlying legal framework helps to formalise the underlying concepts better and benefits from the international harmonisation attempts that provide more robust grounds for Internet-wide copyright management.

## The Rest of the Copyright Ontology

Like the rest of rights expression languages, the Copyright Ontology also tries to formalise the concrete actions that are governed by the previous rights, which are permitted or prohibited to model licenses or agreements. They are detailed in the last part of the Copyright Ontology, the [**Actions Model**](../ActionsModel), which together with the [**Creation Model**](../CreationModel) and this **Rights Model** constitute the whole **Copyright Ontology**.

## References

WIPO. (2004). *WIPO Intellectual Property Handbook: Policy, Law and Use*. WIPO Publications. Retrieved from http://www.wipo.int/about-ip/en/iprm
