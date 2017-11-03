Creation Model
==============

|                                          |                                          |                                          |                                          |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| [![DownloadTurtle](https://img.shields.io/badge/style-Turtle-orange.svg?style=flat&label=Download)](copyrightonto-creationmodel.ttl) | [![DownloadTurtle](https://img.shields.io/badge/style-RDF/XML-orange.svg?style=flat&label=Download)](http://any23.org/rdfxml/https://raw.githubusercontent.com/rhizomik/copyrightonto/master/CreationModel/copyrightonto-creationmodel.ttl) | [![DownloadTurtle](https://img.shields.io/badge/style-Ontodocs-blue.svg?style=flat&label=Documentation)](docs/index.html) | [![DownloadTurtle](https://img.shields.io/badge/style-VOWL-green.svg?style=flat&label=Visualize)](http://visualdataweb.de/webvowl/#iri=http://any23.org/rdfxml/https://raw.githubusercontent.com/rhizomik/copyrightonto/master/CreationModel/copyrightonto-creationmodel.ttl) |



**Table of Contents**

- [Motivation](#motivation)
- [Related Work](#related-work)
  + [IFLA's FRBR Creation Model](#iflas-frbr-creation-model)
  + [LCC's RRM Creation Model](#lccs-rrm-creation-model)
  + [MPEG-21 Media Value Chain Ontology](#mpeg-21-media-value-chain-ontology)
- [Copyright Ontology Creation Model](#copyright-ontology-creation-model)
  + [Implementation](#implementation)
    + [Modelling Sample](#modelling-sample)
- [The Rest of the Copyright Ontology](#the-rest-of-the-copyright-ontology)
- [References](#references)

## Motivation

The objective of this part of the Copyright Ontology is to model the different forms that a creation, the subject matter of copyright, can take along its life cycle.

The resulting model should be capable of modelling complex lifecycles like the one presented in Table 1.

Table 1. Creation lifecycle sample: broadcast of a serial adapted from a literary work

> A creator adapts the original **literary work** Alexandre Dumas’ “The Count of Monte Cristo”, in order to produce a **serial**. 
> The resulting adaptation to a serial is realised as a **script** that is **performed** by some actors, including Gerard Depardieu, and recorded into a **motion picture**. 
> This motion picture is finally **broadcasted** to users who can tune the resulting communication.

An overview of the sample lifecycle in Table 1 is shown in Figure 1.

| ![CreationLifecycleSample](http://www.plantuml.com/plantuml/svg/FScn4S8m3030LM01gq-R5YecS1J5rY5RFbawBanFAjh_EtUKs2bCRjLzp0N0yYSLzXfRJ3BKxjGzeJQmobzj_0RKSHgNwbSgj3oT35QZxApzgJi975p2QFxrmGUj9mgzSXj2QKIJ7m00) |
| :--------------------------------------: |
| Figure 1. Overview of the creation lifecycle sample in Table 1 |

## Related Work

This section outlines existing attempts to model creation highlighting their limitations when trying to model complex scenarios like the one presented in Table 1.

### IFLA's FRBR Creation Model

The most referenced creation model is the one proposed by the International Federation of Library Associations and Institutions (IFLA) called FRBR, Functional Requirements for Bibliographic Records [(IFLA Study Group on FRBR, 2013)](#references). This standard proposed a set of entities to model creations, which are shown in Figure 2 and detailed next: 

- **Work**: a distinct intellectual or artistic creation. A work is an abstract entity; there is no single material object one can point to as the work. We recognize the work through individual realizations or expressions of the work, but the work itself exists only in the commonality of content between and among the various expressions of the work.
- **Expression**: the intellectual or artistic realization of a Work in the form of alpha-numeric, musical, or choreographic notation, sound, image, object, movement, etc., or any combination of such forms.
- **Manifestation**: the physical embodiment of an Expression of a Work. It encompasses a wide range of materials, including manuscripts, books, periodicals, maps, posters, sound recordings, films, video recordings, CD-ROMs, multimedia kits, etc. It represents all the physical objects that bear the same characteristics, in respect to both intellectual content and physical form.
- **Item**: a single exemplar of a Manifestation that enables us to separately identify individual copies of a Manifestation.

| ![RRD Ontology Creation Model](http://www.plantuml.com/plantuml/svg/LSan3iCW3030hwGF2DuxfbAtBFo04XUi04R6LjIyFbbxwpsenM8RcfGfg_Rn191mk4IQxMC39N9JREeYLv1C9rVQ8NB_2QMiTpBKC1G5Ne91YTlA6nRuKZB10M-_-FclNBTQBW00) |
| :--------------------------------------: |
|      Figure 2. FRBR Creation Model       |

The **literary work** introduced in Table 1 can be modelled using *FRBR Work*. Its adaptation to a **serial** is another *FRBR Work*, though there is no way in FRBR to represent a work as an adaptation of another one. 

Then, the **script** corresponds to an *FRBR Expression*. However, the **performance** of the script by the actors is not a *FRBR Manifestation* because it is not a physical embodiment. In any case, it might be represented as another *FRBR Expression* though it is no mechanism in FRBR to relate two expressions. Consequently, there is no distinction between scripts and their performances and it is not possible to model that a particular performance depends on a particular script.

The performance recording into a **motion picture** can be modelled using *FRBR Manifestation* though its **broadcast** is not an *FRBR Item*. In any case, someone recording the broadcast might produce an *FRBR Item*.

Consequently, FRBR is not suitable to model complex value chains like the one in Table 1. The problem is that complex value chains seem to be the tendency as new ways to generate and distribute content proliferate. It is understandable that FRBR does not make these detailed distinctions as it was originally intended as a conceptual model for bibliographic records. However, most of the available creation models are based on the FRBR model and inherit these limitations, as detailed in the next subsections.

### LCC's RRM Creation Model

Another relevant proposal, associated with current initiatives like the Copyright Hub or the Rights Data Integration project, is the Linked Content Coalition (LCC) Rights Reference Model (RRM) [(Rust, 2013)](#references). It defines the concept **Creation** that is then particularised into:

* **Work**: A Creation which is a distinct, abstract Creation of the mind whose existence is revealed through one or more Manifestations.
* **Manifestation**: A perceivable Creation.

Moreover, LCC's RRM defines a link between two creations that indicates that one is an **adaptation** of the other. 

Consequently, it is possible to model the **literary work** and its **serial** adaptation as *LCC Works*. Then, *LCC Manifestation* can model the **script**. However, no further concepts are provided to get into deeper detail when modelling the rest of the creation value chain. The only possibility is to model all (**performance**, **motion picture** and **broadcast**) as *LCC Manifestation* and thus no distinctions can be made.

### MPEG-21 Media Value Chain Ontology

A more detailed formalisation is the one provided by the ISO/IEC standard MPEG-21. One of the parts of this standard, concretely part 19, focuses on modelling media value chains using an ontology, the MPEG-21 Media Value Chain Ontology (MVCO) [(Delgado & Rodriguez-Doncel, 2009)](#references). 

The ontology formalises the following concepts, also shown in Figure 3: 

- **Work**: A creation that retains intellectual or artistic attributes independently of its Manifestations.
- **Adaptation**: A Work that is derived from another Work.
- **Manifestation**: An object or event which is an expression of a Work
- **Instance**: An object or event which is an example of an Identified Manifestation (e.g. a File)
- **Copy**: A mechanical reproduction of analogue or digital representations of a given IP Entity. In the case of digital Copies, the result is virtually identical while in the case of analogue Copies the results can vary considerably in quality.

| ![MVCO Ontology Creation Model](http://www.plantuml.com/plantuml/svg/LSan3iCW3030hoGF2DwpPaRTibDmm2fWP6nLxUlJjRVUIZrMIsXIbw8wvWuWuUqoQR6dJPJ8NR6hYzn02dsvqGiYZuzGBlfBXXQcei0X69IuUqvOuQ9iWXFyUJosltB3Mhq1) |
| :--------------------------------------: |
|  Figure 3. MVCO Ontology Creation Model  |

Though the model is more detailed than the previous ones, its expressivity is also limited in the sense that it makes no distinction between manifestations as objects, like a **script**, and as events, like a **performance**. The same happens with instances as objects or as events, so there is no way to distinguish between a **motion picture** and its **broadcast**.

## Copyright Ontology Creation Model

The Creation Model proposed by the Copyright Ontology aims to overcome the limitations highlighted in the previous subsections. To do so, the starting point is to take into account how general or upper ontologies conceptualise the world around us, which certainly limits the different forms creations can take. Most general ontologies, like SUMO [(Niles & Pease, 2001)](#references) or schema.org [(Guha & Brickley, 2016)](#references), agree on the following basic distinctions about what is there in the world:

- **Abstract**: something that cannot exist at a particular place and time without some physical encoding or embodiment.
  - Examples: SUMO's *Abstract* or schema.org's *Intangible*.

- **Object**: corresponds to the class of ordinary objects and includes digital objects.

  - Examples: SUMO's *Object* or the combination of schema.org's *Person*, *Organization*, *Place* and *CreativeWork*.

- **Process**: something that happens and has temporal parts or stages.

  - Examples: SUMO's *Process* or the combination of schema.org's *Action* and *Event*.


To facilitate the adoption of the Copyright Ontology, it is rooted on the most used general ontology in the Web: schema.org. This is a generic vocabulary founded by Google, Microsoft, Yahoo and Yandex. All the proposed concepts for the Creation Model are subconcepts of the corresponding generic ones in schema.org:


- *schema:Intangible*
  - **Work**: is a distinct intellectual or artistic creation. It includes literary and artistic works, music, pictures and motion pictures, but also computer programs or compilations, like databases.
- *schema:CreativeWork*

    -   **Manifestation**: the materialisation of a work in a concrete medium, a tangible or digital object.
    -   **Recording**: the materialisation of a performance in a concrete medium, a tangible or digital object.
        -   Includes **Sound Recording** and **Audiovisual Recording**.
    -   **Instance**: the reproduction, copy, of a manifestation, a recording or another instance.
- *schema:Event*

    -   **Performance**: the expression in time of a work. Performers or technical methods might be involved in the process.
        -   **Improvisation**: the expression in time of a work that has not been previously materialised in a manifestation.
    -   **Communication**: the transmission of a work among places at a given time. It is a process performed when the public is not present at the place and or time where the communication originates. It includes broadcasts, i.e. one to many, but also communications from a place and at a time individually chosen, like Internet streaming.
        -   Live **Communication**: the direct communication of a performance without a mediating non-ephemeral recording.

The previous concepts are the building blocks of the Copyright Ontology Creation Model. However, in order to capture creation value chains, the model should also include how these different creation forms relate.

Figure 4 presents these relationships that capture the flux from **Work**, towards something that can be consumed by end users, e.g. an **Instance**, a **Communication** or a **Performance**. Despite **Recordings** or **Manifestations** might also be consumed, e.g. a painting.

| ![RRD Ontology Creation Model](http://www.plantuml.com/plantuml/svg/LSen3i8m3030hy03Y7VMpgW3BmYfIQpQSUJOGl1wkZ0mtvsf5uuDm_ZKtCUy0bX-fKhUuX4JhMXtx9wA2bYZZmhjK7IyZMhp0nKaJqU3nJ0xQR_fXWnFgc4uOVdLzQYNltCd6OnfXF0N) |
| :--------------------------------------: |
| Figure 4. Copyright Ontology Creation Model (simplified version) |

This creation model constitutes a superset of the previously introduced ones and thus existing conceptualisations based on them can be mapped to the Copyright Ontology Creation Model. With this model, it is possible to fully model the value chain scenario presented in Table 1, as shown in Figure 5.

| ![CreationLifecycleSample](http://www.plantuml.com/plantuml/svg/DSen3i8m3030hy03Y7SMXgmW1buGKZUnSEB8iONAw-dI-UvCFRClwCgdQZRc5K3JDnIowc-Vg5cwORUGfO5M-acZ3sGPcrAfjgD0IzDG8Iec8-aFMP1XfUAA4-9Hdtkz7ETEAyOjCxvI6unXUEFR7m00) |
| :--------------------------------------: |
| Figure 5. Overview of the creation lifecycle sample in Table 1 |

In case of requiring an even greater level of detail, the whole set of Creation Model concepts can be taken into consideration when defining the relationships among them, thus including **Improvisation** and **Live Communication**, as shown in Figure 6.

| ![RRD Ontology Creation Model](http://www.plantuml.com/plantuml/svg/LSen3i8m3030hz074EzTAx5Ll25DJMBLYIF75eBNjmi3yzr4BR7lwCgtOjR73A3n7J9PySq7Qf9cs2magQ25lbBfW2JzevIBNIXGup1KM1IZaRHLTcHuKNR50SklFgzw_piFPmxTAvy0) |
| :--------------------------------------: |
| Figure 6. Copyright Ontology Creation Model (full version) |

### Implementation

The Creation Model part of the Copyright Ontology is implemented using the Resource Description Format ([RDF](https://www.w3.org/RDF/)) and the Web Ontology Language ([OWL](https://www.w3.org/OWL/)). It is available in [Turtle](https://www.w3.org/TR/turtle/) RDF serialization format:

- Copyright Ontology Creation Model: [**copyrightonto-creationmodel.ttl**](copyrightonto-creationmodel.ttl)

The ontology can be downloaded from the previous link and converted to other RDF/OWL formats using services like Anything To Triples ([Any23](http://any23.org/)), for instance to [**RDF/XML**](http://any23.org/rdfxml/https://raw.githubusercontent.com/rhizomik/copyrightonto/master/CreationModel/copyrightonto-creationmodel.ttl)

<ul> Copyright Ontology Creation Model:
<a href="http://any23.org/rdfxml/https://raw.githubusercontent.com/rhizomik/copyrightonto/master/CreationModel/copyrightonto-creationmodel.ttl" download="copyrightonto-creationmodel.rdf">
   <b>copyrightonto-creationmodel.rdf</b>
</a>
</ul>

There is also an ontology documentation generated from the RDF/OWL using [Ontodocs](https://github.com/lambdamusic/Ontodocs):

- Copyright Ontology Creation Model: [**documentation**](docs/index.html)

It is also possible get an overview of the ontology using visualisation services like [WebVOWL](http://vowl.visualdataweb.org/webvowl/):

- Copyright Ontology Creation Model [**overview**](http://visualdataweb.de/webvowl/#iri=http://any23.org/rdfxml/https://raw.githubusercontent.com/rhizomik/copyrightonto/master/CreationModel/copyrightonto-creationmodel.ttl)

#### Modelling Sample

The Creation Model part of the Copyright Ontology can be then used to model creation value chains like the one presented in Figure 5. 

This is the serialisation of that model using [Turtle](https://www.w3.org/TR/turtle/):

```turtle
@prefix : <http://rhizomik.net/ontologies/copyrightonto/creationmodel-sample.ttl#> .
@prefix copyrightonto: <http://rhizomik.net/ontologies/copyrightonto#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .

:literary_work
  rdf:type copyrightonto:Work ;
.
:serial
  rdf:type copyrightonto:Work ;
  copyrightonto:isDerivationOf :literary_work ;
.
:script
  rdf:type copyrightonto:Manifestation ;
  copyrightonto:hasPerformance :performance ;
  copyrightonto:isManifestationOf :serial ;
.
:performance
  rdf:type copyrightonto:Performance ;
  copyrightonto:hasRecording :motion_picture ;
.
:motion_picture
  rdf:type copyrightonto:AudiovisualRecording ;
  copyrightonto:hasCommunication :broadcast ;
.
:broadcast
  rdf:type copyrightonto:Communication ;
.
```

And this is the same model serialized using [JSON-LD](https://json-ld.org):

```json
{
  "@context": {
    "cro": "http://rhizomik.net/ontologies/copyrightonto#",
    "sample": "http://rhizomik.net/ontologies/copyrightonto/creationmodel-sample.ttl#"
  },
  "@graph": [
    {
      "@id": "sample:literary_work",
      "@type": "cro:Work"
    },
    {
      "@id": "sample:serial",
      "@type": "cro:Work",
      "cro:isDerivationOf": {
        "@id": "sample:literary_work"
      }
    },
    {
      "@id": "sample:script",
      "@type": "cro:Manifestation",
      "cro:isManifestationOf": {
        "@id": "sample:serial"
      },
      "cro:hasPerformance": {
        "@id": "sample:performance"
      }
    },
    {
      "@id": "sample:performance",
      "@type": "cro:Performance",
      "cro:hasRecording": {
        "@id": "sample:motion_picture"
      }
    },
    {
      "@id": "sample:motion_picture",
      "@type": "cro:AudiovisualRecording",
      "cro:hasCommunication": {
        "@id": "sample:broadcast"
      }
    },
    {
      "@id": "sample:broadcast",
      "@type": "cro:Communication"
    }
  ]
}
```

## The Rest of the Copyright Ontology

This part of the Copyright Ontology focuses just on the different forms that creations can take along their lifecycle. The transitions among them are governed by different rights in Copyright, as detailed in the [**Rights Model**](../RightsModel) part of the Copyright Ontology. These rights govern the actions that participants in creation value chains can perform, which are detailed in the [**Actions Model**](../ActionsModel) part of the Copyright Ontology.

References
----------

Delgado, J., & Rodriguez-Doncel, V. (2009). A Media Value Chain Ontology for MPEG-21. *IEEE MultiMedia*, *16*(4), 44–51. https://doi.org/10.1109/MMUL.2009.78

Guha, R. V., Brickley, D., & Macbeth, S. (2016). Schema.org: Evolution of Structured Data on the Web. *Communications of the ACM*, *59*(2), 44–51. https://doi.org/10.1145/2844544

Hoekstra, R., Breuker, J., Bello, M. D., & Boer, A. (2007). The LKIF Core Ontology of Basic Legal Concepts. In P. Casanovas, M. A. Biasiotti, E. Francesconi, & M. T. Sagri (Eds.), *Proceedings of the Workshop on Legal Ontologies and Artificial Intelligence Techniques (LOAIT 2007)*.

IFLA Study Group on FRBR (Ed.). (2013). *Functional Requirements for Bibliographic Records, Final Report* (Reprint 2013). Berlin, Boston: De Gruyter Saur. https://doi.org/10.1515/9783110962451

Rust, G. (2013). *The LCC Rights Reference Model v1.0*. Linked Content Coalition. Retrieved from http://doi.org/10.1000/284

Niles, I., & Pease, A. (2001). Towards a standard upper ontology. In C. Welty & B. Smith (Eds.), *FOIS ’01: Proceedings of the international conference on Formal Ontology in Information Systems* (pp. 2-9). New York, NY, USA: ACM Press.