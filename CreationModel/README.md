Creation Model
==============

The objective of this part of the Copyright Ontology is to model the different forms that a creation, the subject matter of copyright, can take along its life cycle.

The resulting model should be capable of modelling complex lifecycles like the one presented in Table 1.

Table 1. Creation lifecycle sample: broadcast of a serial adapted from a literary work

> A creator adapts the original **literary work** Alexandre Dumas’ “The Count of Monte Cristo”, in order to produce a **serial**. 
> The resulting adaptation to a serial is realised as a **script** that is **performed** by some actors, including Gerard Depardieu, and recorded into a **motion picture**. 
> This motion picture is finally **broadcasted** to users who can tune the resulting communication.

The previous lifecycle sample scenario is summarised in Figure 1.

| ![CreationLifecycleSample](http://www.plantuml.com/plantuml/svg/FScn4S8m3030LM01gq-R5YecS1J5rY5RFbawBanFAjh_EtUKs2bCRjLzp0N0yYSLzXfRJ3BKxjGzeJQmobzj_0RKSHgNwbSgj3oT35QZxApzgJi975p2QFxrmGUj9mgzSXj2QKIJ7m00) |
| :--------------------------------------: |
| Figure 1. Overview of the creation lifecycle sample in Table 1 |

### IFLA's FRBR Creation Model

The most used creation model is the one proposed by the International Federation of Library Associations and Institutions (IFLA) called FRBR, Functional Requirements for Bibliographic Records (IFLA Study Group on FRBR, 2013). This standard proposed a set of entities to model creations, which are shown in Figure 2 and detailed next: 

- **Work**: a distinct intellectual or artistic creation. A work is an abstract entity; there is no single material object one can point to as the work. We recognize the work through individual realizations or expressions of the work, but the work itself exists only in the commonality of content between and among the various expressions of the work.
- **Expression**: the intellectual or artistic realization of a Work in the form of alpha-numeric, musical, or choreographic notation, sound, image, object, movement, etc., or any combination of such forms.
- **Manifestation**: the physical embodiment of an Expression of a Work. It encompasses a wide range of materials, including manuscripts, books, periodicals, maps, posters, sound recordings, films, video recordings, CD-ROMs, multimedia kits, etc. It represents all the physical objects that bear the same characteristics, in respect to both intellectual content and physical form.
- **Item**: a single exemplar of a Manifestation that enables us to separately identify individual copies of a Manifestation.

| ![RRD Ontology Creation Model](http://www.plantuml.com/plantuml/svg/LSan3iCW3030hwGF2DuxfbAtBFo04XUi04R6LjIyFbbxwpsenM8RcfGfg_Rn191mk4IQxMC39N9JREeYLv1C9rVQ8NB_2QMiTpBKC1G5Ne91YTlA6nRuKZB10M-_-FclNBTQBW00) |
| :--------------------------------------: |
|      Figure 2. FRBR Creation Model       |

The literary work in Table 1 can be modelled using FRBR Work. Its adaptation to a serial is another Work, though there is no way in FRBR to represent a work as adaptation of another one. 

Then, the script corresponds to an FRBR Expression. However, the performance of the script by the actors is not a FRBR Manifestation because it is not a physical embodiment. In any case, it might be represented as another FRBR Expression though it is no mechanism in FRBR to relate two expressions. Consequently, there is no distinction between scripts and their performances and it is not possible to model that a particular performance depends on a particular script.

The performance recording into a motion picture can be modelled using FRBR Manifestation though its broadcast is not an FRBR Item. In any case, someone recording the broadcast might produce an FRBR Item.

Consequently, FRBR is not suitable to model complex value chains like the one in Table 1. The problem is that complex value chains seem to be the tendency as new ways to generate and distribute content proliferate. It is understandable that FRBR does not make these detailed distinctions as it was originally intended as a conceptual model for bibliographic records. However, most of the available creation models are based on the FRBR model and inherit this limitations.

### LCC's RRM Creation Model

Linked Content Coalition (LCC) Rights Reference Model (RRM) defines the concept Creation that is then particularised into:

* **Work**: A Creation which is a distinct, abstract Creation of the mind whose existence is revealed through one or more Manifestations.
* **Manifestation**: A perceivable Creation.

Moreover, LCC's RRM defines a link between two creations that indicates that one is an **adaptation** of the other.

### RDD Ontology

A more complete formalisation is the RRD ontology for the expression of
intellectual property entities and relations \[[^17]\]. It is not based
on copyright law but on a partial conceptualisation of the creation
model, i.e. the different forms a creation can take along the value
chain. However, this model is not sufficiently detailed as it just
considers Works, Adaptations, Manifestations, Instances and Copies, as
it is shown in Figure 1. There is no distinction between manifestations
as objects or as events, e.g. a script or a performance, neither between
instances as objects or as events, e.g. a recording or a broadcast.

| ![RRD Ontology Creation Model](http://www.plantuml.com/plantuml/svg/LSen3iCW3030hwGF2Dwx9cjKgJ-Wn0KhW96n5JMl3sldkmVLa6r7apmbrTQV0E9F5qcJVQoZ1AwALLtW0fBeua8716u_ePXq84FnNL5W4VHAN3VUCSENeWbsUA_hQwJvJrspacy0) |
| :--------------------------------------: |
|  Figure 3. RRD Ontology Creation Model   |

### OntologyX Creation Model

An alternative to the FRBR creation model is the OntologyX \[[^19]\]
ontology. As it is shown in Figure 2, it does distinguish between
creations as objects, called Manifestations, and as things in time,
called Expressions. However, it does not further detail the different
forms a creation can adopt along the value chain when as object or as
event. Moreover, OntologyX concentrates on the kind of actions that can
be performed on governed content and it does not take into account the
underlying legal framework.

| ![OntologyX Creation Model](http://www.plantuml.com/plantuml/svg/LSen3eCm3030hvG7DDwxCgEkh6amYLKdZXnRYBw-hCnt4xN4lg4hFufP7oy0ZKV8PCK_Fb2JDCDc8Ka5BVIJIbz8qa-bNEn2WHg7eSAi68saBR8XmqxP5GUyhy6Ip_Lvyz2zyXy0) |
| :--------------------------------------: |
|  Figure 4. The OntologyX Creation Model  |

## Proposed Creation Model

The Creation Model conceptualises the different forms a creation can take, which are first classified based on the common distinctions made by general ontologies like SUMO [(Niles & Pease, 2001)](#References) or LKIF [(Hoekstra, Breuker, Bello, & Boer, 2007)](#References) or schema.org ():

- **Abstract**: something that cannot exist at a particular place and time without some physical encoding or embodiment.
  - Examples: *schema:Intangible*, ...

- **Object**: corresponds to the class of ordinary objects and includes digital objects.

  - Examples: *schema:Person*, *schema:Place*, *schema:CreativeWork*, ...

- **Process**: something that happens and has temporal parts or stages.

  - Examples: *schema:Action*, *schema:Event*, ...



In order to facilitate the adoption of the Copyright Ontology, it is rooted on the most used general ontology, schema.org. Consequently, all the proposed concepts for the Creation Model are subconcepts of the corresponding generic ones in schema.org:


- ***schema:Intangile***
  - **Work**: is a distinct intellectual or artistic creation. It includes literary and artistic works, music, pictures and motion pictures, but also computer programs or compilations, like databases.
- ***schema:CreativeWork***: corresponds to the class of ordinary objects and includes digital objects.

    -   **Manifestation**: the materialisation of a work in a concrete medium, a tangible or digital object.

    -   **Fixation**: the materialisation of a performance in a concrete medium, a tangible or digital object.

    -   **Instance**: the reproduction, copy, of a manifestation, a fixation or another instance.
- ***schema:Event***: something that happens and has temporal parts or stages.

    -   **Performance**: the expression in time of a work. Performers or technical methods might be involved in the process.

    -   **Communication**: the transmission of a work among places at a given time. It is a process performed when the public is not present at the place and or time where the communication originates. It includes broadcasts, i.e. one to many, but also communications from a place and at a time individually chosen.

There are many relations among the different forms a creation can take
during its life cycle, see Figure 3, as it evolves from an abstract
idea, i.e. a *Work*, towards something that can be consumed by end
users, e.g. an *Instance*, a *Communication* or a *Performance*. Despite
*Fixations* or *Manifestations* might also be consumed, e.g. a painting.
This creation model constitutes a superset of the ones commented in the
Related Work Section and consequently existing conceptualisations based
on them might be mapped to the Copyright Ontology creation model.

|                                          |
| :--------------------------------------: |
| Figure 5. Copyright Ontology Creation Model |

References
----------

Guha, R. V., Brickley, D., & Macbeth, S. (2016). Schema.org: Evolution of Structured Data on the Web. *Communications of the ACM*, *59*(2), 44–51. https://doi.org/10.1145/2844544

Niles, I., & Pease, A. (2001). Towards a standard upper ontology. 
In C. Welty & B. Smith (Eds.), *FOIS ’01: Proceedings of the international conference on Formal Ontology in Information Systems* (pp. 2-9). New York, NY, USA: ACM Press.

Hoekstra, R., Breuker, J., Bello, M. D., & Boer, A. (2007). The LKIF Core Ontology of Basic Legal Concepts. 
In P. Casanovas, M. A. Biasiotti, E. Francesconi, & M. T. Sagri (Eds.), *Proceedings of the Workshop on Legal Ontologies and Artificial Intelligence Techniques (LOAIT 2007)*.

IFLA Study Group on FRBR (Ed.). (2013). *Functional Requirements for Bibliographic Records, Final Report* (Reprint 2013). Berlin, Boston: De Gruyter Saur. https://doi.org/10.1515/9783110962451


[^17]: Rodríguez, V., Gauvin, M., Delgado, J.: “An Ontology for the Expression of Intellectual Property Entities and Relations”. In M.I. Yagüe & E. Fernández-Medina (eds.) Security in Information Systems, Proceedings of the 5th International Workshop on Security in Information Systems, WOSIS 2007. Madeira, PT: INSTICC Press, 2007, pp. 196-203.

[^19]: Pease, A., Rust, G.: “Formal Ontology for Media Rights Transactions”. In R. García (ed.) “Semantic Web for Business: Cases and Applications”. IGI Global, in press, 2008.

[^26]: \[\] McGuinness, D.L., van Harmelen, F.: “OWL Web Ontology Language Overview”; W3C Recommendation 10 February 2004. http://www.w3.org/TR/owl-features




