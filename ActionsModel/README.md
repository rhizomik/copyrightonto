Action Model
==================

| Downloads                                | Documentation                            |
| :--------------------------------------- | :--------------------------------------- |
| [![DownloadTurtle](https://img.shields.io/badge/style-Turtle-orange.svg?style=flat&label=Download)](copyrightonto-actionsmodel.ttl) | [![Documentation](https://img.shields.io/badge/style-Ontodocs-blue.svg?style=flat&label=Documentation)](https://rhizomik.github.io/copyrightonto/actionsmodel/) [![Visualization](https://img.shields.io/badge/style-VOWL-green.svg?style=flat&label=Visualization)](http://visualdataweb.de/webvowl/#iri=https://raw.githubusercontent.com/rhizomik/copyrightonto/master/ActionsModel/copyrightonto-actionsmodel.ttl) |

**Table of Contents**

* [Overview](#overview)
* [Action Roles](#action-roles)
* [Actions Giving Rise to Rights](#actions-giving-rise-to-rights)
* [Economic Rights Actions](#economic-rights-actions)
* [Copyright Exceptions Actions](#copyright-exceptions-actions)
* [Rights Management Actions](#rights-management-actions)
* [End-User Actions](#end-user-actions)
* [Implementation](#implementation)
* [The Rest of the Copyright Ontology](#the-rest-of-the-copyright-ontology)
* [References](#references)

## Overview

This is the last part of the Copyright Ontology, built on the foundations provided by the other two parts, the [**Creation Model**](../CreationModel) and the [**Rights Model**](../RightsModel). The Action Model captures the dynamic part of the Copyright Ontology, the actions performed by creations value chains' actors. Actions are the main building-block of the Copyright Ontology, in the sense that usually all representations based on this ontology will be built arround one or more actions that connect all the parties and entities participating or involved in them. 

This is an approach, which can be called "Action-Oriented Modelling", followed since early versions of the Copyright Ontology (García, 2010). The importance of Actions for knowledge representation is also highlighted by other initiatives, like schema.org that includes them as part of their proposed vocabulary (Brickley, 2014). This has facilitated the integration of the Copyright Ontology with schema.org, as detailed next.

The most relevant set of actions in the Copyright Ontology includes those that "move" creations along their value chain, based on the stages identified in the [**Creation Model**](../CreationModel). For instance, the ***Manifest*** action makes the abstract idea represented by a *Work* perceivable as a *Manifestation*. Other examples are the ***Perform*** action to generate a *Performance* from a *Manifestation* or the ***Record*** one to fix a *Performance* into a *Recording*. The most relevant actions in this set are presented in Figure 1 as arrows, which link the source and target stage in the value chain and illustrate the connection between the Creation and Action Models.

| ![Actions Model](http://www.plantuml.com/plantuml/svg/JSv12W8n38NX_Pn23s23Mq4SSIsUeTF6DjWsGveeUdgx4Tmz-B_5cxjwKQjbsb8BnIAQb4rMNVi1GFpB9T9iYtMKm4sngGjSGJ9zkD830gzlePHrH8RgkwB0EIXnwrUEME1EoGGxN7xoDkJkdxXr73WzZ_jfnXR7_W80) |
| :--------------------------------------: |
| Figure 1. CopyrightOnto actions in the context of the Creation Model |

These actions are also linked to the rights identified in the [**Rights Model**](../RightsModel) that govern them, as detailed in the following sections. In addition to this set of actions that are modelled to capture what rights or licenses authorise or prohibit (like ***Copy*** or ***Perform***), there are additional actions to manage how the previous actions (or the related rights) are granted (like ***Agree*** or ***Disagree***) or what is asked in return (like ***Attribute*** or ***Pay***). These actions are also presented in the next subsections.

## Action Roles

In all cases, actions share a common set of relationships to other entities participating in the action. These relationships, adopted from the linguistics field, are called case roles or semantic roles (Sowa, 1999). Semantic roles in language link the different parts of a sentence to its main component, the verb, which usually represents an action. 

These same roles are also used in other ontologies and vocabularies like [schema.org](http://schema.org) (Guha, Brickley, Macbeth, 2016). In fact, all actions in the Copyright Ontology are particularisations of schema.org's Action and in some cases have direct equivalents in schema.org, as captured in the ontology.

The set of semantic roles is presented in Table 1, organised in sets related to the broad questions that can be made about actions (like Who? What? When?...) and linked to schema.org when the role is reused from that vocabulary.

Table 1. Semantic roles relating actions to the entities participating in them

| Role Kind | Main Role           | Description                                                  |
| --------- | ------------------- | ------------------------------------------------------------ |
| who       | schema:agent        | The direct performer or driver of the action (animate or inanimate) |
|           | schema:participant  | Other co-agents that participated in the action indirectly, for instance a schema:recipient |
| what      | schema:object       | The object upon which the action is carried out              |
|           | schema:result       | The result produced in the action                            |
| where     | schema:location     | Where an action takes place                                  |
|           | schema:fromLocation | The original location of the object or the agent before the action |
|           | schema:toLocation   | The final location of the object or the agent after the action |
| when      | schema:startDate    | Date and time the action started or is expected to start     |
|           | schema:endDate      | Date and time the action finished or is expected to end      |
|           | pointInTime         | The point in time when the action happens                    |
|           | schema:duration     | The amount of time the action requires to complete           |
| with      | schema:instrument   | The object that helps the agent perform the action           |
| why       | aim                 | The reason  or objective of the action                       |
| how       | manner              | The way the action is carried out                            |
| if        | condition           | Something that must hold or happen before the action starts  |
| then      | consequence         | Something that must hold or happen after the action is completed |

For instance, for a particular performance as the one shown in Figure 2, it is possible to capture the details of the ***Perform*** action using some of the semantic roles presented in Table 1.

| ![Actions Model](http://www.plantuml.com/plantuml/svg/DOun3W8X401xNw4FaEsjpbWRJNm11tkm4LYoxCRewyN2QegPOfQXNjHgsHseXM8HJSe-g_Pn0X3_Seaqsse39N1JREe2Lv1C7wxqXC3zBPIoJibG_L0KE0SbRkFA4Gjib4nmmELVtcPvlADiBFNXQo_e-kzWmHOdlm00) |
| :--------------------------------------: |
| Figure 2. Perform action model using semantic roles |

The following sections present the considered actions for specific contexts, starting from the actions related to the economic and other rights identified in the [**Rights Model**](../RightsModel) and then moving to actions needed to manage them.

## Actions Giving Rise to Rights

Some of the actions operate on creations abstract form, Works, and embody them into Manifestations or Improvisations that can be perceived and thus give rise to Economic Rights on them, usually hold by the creator. This actions are:

* ***Manifest***: when a creator first embodies a *Work* into a tangible object, a *Manifestation* as detailed in the Creation Model.
* ***Improvise***: when the creator directly embodies a *Work* into a *Performance*, without a preceding *Manifestation* of it.

Both actions can be further detailed using the semantic roles listed in Table 1 to identify the creator, the originating Work and the resulting Manifestation or Improvisation. Additional information like the location or the point in time can be also included, as shown in Figure 3. 

Moreover, as in most copyright regimes the creator becomes the holder of all rights on creations just by the mere fact of manifesting them, it is also possible to capture this fact using the Actions Model, as illustrated in Figure 3.

| ![Actions Model](http://www.plantuml.com/plantuml/svg/DOun4W8X301xNw4FaFHMvrZVMFW2X1na1C8aOMxqzM9XjSLkiOkQ5nkr74xKGXaHXvHZDkjw0H2_kqIMntCeIk1csCm5hY2PFbpf1O7xMoXbcvAXUZKKk0OZRhfon08RfI6eSFkNzrcULzzeGxM7hxsWwx-51LkS_080) |
| :--------------------------------------: |
| Figure 3. Example of model of a Manifest action of a derivation of an existing Work |

Through the **consequence** semantic role, the **Manifest** action is linked to a resulting **Agree** action (detailed in following sections) that captures the fact that the copyright regime assigns all **Copyright** on the resulting **Manifestation** to the creator. Note the link between the derived **Work** and the original one. This link is produced by a **Derive** action, also detailed in the following sections.

## Economic Rights Actions

There is a generic action ***Exploit*** which is connected with the *Economic Rights*. Then, in connection with the particular rights connected with exploitation, there are the following more specific actions:

- ***Perform***: to recite, render, play, dance, act,... a *Manifestation* or a *Recording* resulting in a *Performance*. It is not constrained by Copyright unless it is done in public.
  - ***PerformInPublic***:  it is governed by the *Public Performance Right* when it is in public before and audience, like in a club, restaurant or concert.
  - This action, when performed by a performer, gives rise to neighbouring or related rights, concretely the *Performers Rights* described in the [**Rights Model**](../RightsModel).
- ***Record***: to store a *Performance* or *Communication* into a *Recording*. It might be regulated by the *Fixation Right* when the *Recording* is intended for further exploitation. More concretely, when recording sound the specific right is the *Sound Recording Right*, and *Motion Picture Right* for audiovisual recordings.
  - This action, when performed by a producer, gives rise to neighbouring or related rights, concretely the *Producers Rights* described in the [**Rights Model**](../RightsModel).
- ***Communicate***: covers generating a *Communication* to the public in the sense that, contrary to *Perform*, the intended audience is not present at the place where the communication originates. Related in general by the *Communication Right* though, depending on the intended audience, more specific rights and the corresponding actions can be defined.
  - ***Broadcast***: when the communication of a *Manifestation* or *Recording* is simultaneously made to a plurality of people as a  *schema:BroadcastEvent*, regulated by the *Broadcasting Right*.
    - This action, when performed by a broadcaster, gives rise to neighbouring or related rights, concretely the *Broadcasters Rights* described in the [**Rights Model**](../RightsModel).
  - ***Make Available***: offering of on‐demand access to a work to the public, when the audience individually choses when the communication of a from a *Manifestation* or *Recording* takes place as a  *schema:OnDemandEvent*, governed by the *Making Available Right*.
  - ***Retransmit***: takes place when the communication is generated from a *Performance*, thus a *Live Communication*, or from a previous *Communication*.
- ***Copy***: generate replicas of a *schema:CreativeWork*, i.e. a *Manifestation*, *Recording* or *Instance*. The resulting *Instance* might have a physical support or not, like a digital object. Governed by the *Reproduction Right*.
- **Distribute**: to offer a *schema:CreativeWork*, specially *Instance*s, to be enjoyed. The ownership of the physical support or digital object might be permanent or temporal. Related to the *Distribution Right*,  though there are more specific kinds of actions and rights. When the distribution crosses borders, the *Importantion Right* is also relevant.
  - ***Sell***: to permanently transfer the ownership of the physical support or digital object in exchange of an economic compensation, a *schema:PayAction*. Ownership changes can be modelled using *schema:OwnershipInfo*. Depending on the existence of a physical support or not, there might be additional implications like *first sale exhaustion*, which makes just the first sell to be governed by the *Distribution Right*.
  - ***Rent***: to temporarily transfer the physical support or digital object in exchange of an economic compensation. Therefore, this actions has a duration. Governed by the *Rental Right*.
  - ***Lend***: to temporarily transfer the physical support or digital object without requiring a relevant economic compensation.
- ***Derive***: to prepare a derivative work based on one or more preexisting works, governed by the *Transformation Right*. It includes the following more specific kinds of derivations of new works from existing ones.
  - ***Adapt***: when the derivation action aim is to convert a Work from one type of Work to another. For example, to adapt a novel so as to make a motion picture. Governed by the *Adaptation Right*.
  - ***Translate***: when the derived work is in a language other than that of the original version. Controlled by the *Translation Right*.
  - ***Synchronize***: to use a musical composition recording in an audiovisual work. Governed by the *SynchronizationRight*.

[TODO: concrete example and Figure 4]

## Copyright Exceptions Actions

In addition to the actions connected to the *Economic Rights*, there are other actions related to the copyright exceptions that many copyright legal systems grant to end-users as identified in the [**Rights Model**](../RightsModel). These exceptions are connected to these copyright exceptions as follows:

-   *Quotation Exception*: related to the ***Quote*** action, which is a ***Copy*** action but limited to just a portion of the cited work. Moreover, it usually requires the the source is explicitly attributed using the ***Attribute*** action.

-   *Education Exception*: educational act, any ***Copy***, ***Communicate*** or ***Perform*** action with educational or research purposes.
    
-   *Reporting Exception*: related to the ***Inform*** action, any copyright governed action with informative purposes.
    
-   *Official Act Exception*: any copyright governed action that is part of an official act.
    
-   *Private Copy Exception*: to reproduce privately, thus a ***Copy*** action that produces a reproduction solely for private consumption.
    
-   *Parody Exception*: to ***Parody***, any copyright governed action with parody or caricature purposes.
    
-   *Temporary Reproduction Exception*: to reproduce temporally, thus a ***Copy*** action that produces a temporal reproduction required for technical purposes.

## Rights Management Actions

These are actions related to the management of copyright agreements, and their eventual revocation:

- ***Agree***: when there are parties agreeing to a set of constrained actions (as restricted by the associated [Action Roles](#action-roles) like *who*, *what* or *when*) related to the exploitation or use of copyrighted content. The constrained actions are linked to the Agree action trough the *object* action role. Equivalent to *schema:AgreeAction*.
- **Offer**: like *Agree* but when one of the parties is proposing the set of constrained actions to be agreed. Equivalent to *schema:OfferAction*.
- ***Disagree***: used to revoke an existing agreement by referring to the corresponding *Agree* action, which is the *object* of the *Disagree* action. Eequivalent to *schema:DisagreeAction*.

## End-User Actions

* ***Use***: the consumption of copyrighted content by end-users. There are specific kinds of uses:
  * ***Access***: to consume a *schema:OnDemandEvent* resulting from a *MakeAvailable* action.
  * ***Attend***: to consume a *Performance* performed in a *PublicPlace*. The *object* of the action is thus a *Performance* which result from a *Perform* action that is held in the same *PublicPlace*.
  * ***Tune***: to consume a *schema:BroadcastEvent* resulting from a *Broadcast* action.

<!--

## Summary

Actions defined in the Copyright Ontology (prefixed with "cro:") in the context of the schema.org actions hierarchy (prefixed with "schema:"):

schema:Action
- schema:AssessAction
  - schema:ReactAction
    - [schema:AgreeAction](http://schema.org/AgreeAction) = **cro:Agree**
    - [schema:DisagreeAction](http://schema.org/DisagreeAction) = **cro:Disagree**
    - [schema:EndorseAction](http://schema.org/EndorseAction)
    - [schema:WantAction](http://schema.org/WantAction)
- schema:ConsumeAction
  - [schema:ListenAction](http://schema.org/ListenAction)
  - [schema:ReadAction](http://schema.org/ReadAction)
  - schema:UseAction
  - [schema:ViewAction](http://schema.org/ViewAction)
  - [schema:WatchAction](http://schema.org/WatchAction)
- schema:CreateAction = **cro:Manifest**
- schema:OrganizeAction
  - schema:AllocateAction
    - [schema:AcceptAction](http://schema.org/AcceptAction)
    - [schema:AssignAction](http://schema.org/AssignAction)
    - [schema:AuthorizeAction](http://schema.org/AuthorizeAction)
    - [schema:RejectAction](http://schema.org/RejectAction)
- schema:PlayAction
  - [schema:PerformAction](http://schema.org/PerformAction) = **cro:Perform**
- **cro:Distribute**
  - [schema:RentAction](http://schema.org/RentAction) = **cro:Rent**
  - [schema:SellAction](http://schema.org/SellAction) = **cro:Sell**
  - [schema:LendAction](http://schema.org/LendAction) = **cro:Lend**
- schema:Trade
  - [schema:PayAction](http://schema.org/PayAction)
- schema:TransferAction
  - [schema:DownloadAction](http://schema.org/DownloadAction)
- **cro:Attribute**
- **cro:Communicate** (**cro:Retransmit**)
  - **cro:Broadcast**
  - **cro:Make Available**
- **cro:Copy**
- **cro:Derive**
  - **cro:Adapt**
  - **cro:Translate**
  - **cro:Synchronize**
- **cro:Quote**
- **cro:Record**

-->

## Implementation

The **Actions Model** part of the **Copyright Ontology** is implemented using the Resource Description Format ([RDF](https://www.w3.org/RDF/)) and the Web Ontology Language ([OWL](https://www.w3.org/OWL/)). It is available in [Turtle](https://www.w3.org/TR/turtle/) RDF serialization format:

- Copyright Ontology Actions Model: [**copyrightonto-creationmodel.ttl**](copyrightonto-actionsmodel.ttl)

The ontology can be downloaded from the previous link and converted to other RDF/OWL formats using services like Anything To Triples ([Any23](http://any23-vm2.apache.org/))

There is also an ontology documentation generated from the RDF/OWL using [OntoSpy](http://lambdamusic.github.io/Ontospy/):

- Copyright Ontology Creation Model: [**documentation**](https://rhizomik.github.io/copyrightonto/actionsmodel/)

It is also possible to get an overview of the ontology using visualisation services like [WebVOWL](http://vowl.visualdataweb.org/webvowl/):

- Copyright Ontology Creation Model [**overview**](http://visualdataweb.de/webvowl/#iri=https://raw.githubusercontent.com/rhizomik/copyrightonto/master/ActionsModel/copyrightonto-actionsmodel.ttl)

## The Rest of the Copyright Ontology

This is the last part of the **Copyright Ontology**, complementing the [**Creation Model**](../CreationModel) and the [**Rights Model**](../RightsModel).

## References

Brickley, D. (2014). *Announcing Schema.org Actions*. Official blog for schema.org. Retrieved from http://blog.schema.org/2014/04/announcing-schemaorg-actions.html

García, R. (2010). *A Semantic Web Approach to Digital Rights Management*. Saarbrücken, Germany: VDM Verlag. Retrieved from http://rhizomik.net/~roberto/thesis

Guha, R. V., Brickley, D., & Macbeth, S. (2016). Schema.org: Evolution of Structured Data on the Web. *Communications of the ACM*, *59*(2), 44–51. https://doi.org/[10.1145/2844544](https://doi.org/10.1145/2844544)

Sowa, J. F. (1999). *Knowledge Representation. Logical, philosophical and computational foundations*. Pacific Grove, CA, USA: Brooks Cole Publishing Co.
