[WIP] Action Model
==================

<!--
| Downloads                                | Documentation                            |
| :--------------------------------------- | :--------------------------------------- |
| [![DownloadTurtle](https://img.shields.io/badge/style-Turtle-orange.svg?style=flat&label=Download)](copyrightonto-actionsnmodel.ttl) [![DownloadRDFXML](https://img.shields.io/badge/style-RDF/XML-orange.svg?style=flat&label=Download)](http://any23-vm2.apache.org/rdfxml/https://raw.githubusercontent.com/rhizomik/copyrightonto/master/CreationModel/copyrightonto-actionsnmodel.ttl) | [![Documentation](https://img.shields.io/badge/style-Ontodocs-blue.svg?style=flat&label=Documentation)](https://rhizomik.github.io/copyrightonto/actionsnmodel/) [![Visualization](https://img.shields.io/badge/style-VOWL-green.svg?style=flat&label=Visualization)](http://visualdataweb.de/webvowl/#iri=http://any23-vm2.apache.org/rdfxml/https://raw.githubusercontent.com/rhizomik/copyrightonto/master/CreationModel/copyrightonto-actionsnmodel.ttl) |
-->

**Table of Contents**

* ...

[TOC]

## Overview

This is the last part of the Copyright Ontology, built on the foundations provided by the other two parts, the [**Creation Model**](../CreationModel) and the [**Rights Model**](../RightsModel). The Action Model captures the dynamic part of the Copyright Ontology, the actions performed by creations value chains' actors. Actions are the main building-block of the Copyright Ontology, in the sense that usually all representations based on this ontology will be built arround one or more actions that connect all the parties and entities participating or involved in them. 

This is an approach, which can be called "Action-Oriented Modelling", followed since early versions of the Copyright Ontology (García, 2010). The importance of Actions for knowledge representation is also highlighted by other initiatives, like schema.org that includes them as part of their proposed vocabulary (Brickley, 2014). This has facilitated the integration of the Copyright Ontology with schema.org, as detailed next.

The most relevant set of actions in the Copyright Ontology includes those that "move" creations along their value chain, based on the stages identified in the [**Creation Model**](../CreationModel). For instance, the ***Manifest*** action makes the abstract idea represented by a *Work* perceivable as a *Manifestation*. Other examples are the ***Perform*** action to generate a *Performance* from a *Manifestation* or the ***Record*** one to fix a *Performance* into a *Recording*. The most relevant actions in this set are presented in Figure 1 as arrows, which link the source and target stage in the value chain and illustrate the connection between the Creation and Action Models.

| ![Actions Model](http://www.plantuml.com/plantuml/svg/JSv12W8n38NX_Pn23s23Mq4SSIsUeTF6DjWsGveeUdgx4Tmz-B_5cxjwKQjbsb8BnIAQb4rMNVi1GFpB9T9iYtMKm4sngGjSGJ9zkD830gzlePHrH8RgkwB0EIXnwrUEME1EoGGxN7xoDkJkdxXr73WzZ_jfnXR7_W80) |
| :--------------------------------------: |
| Figure 1. CopyrightOnto actions in the context of the Creation Model |

These actions are also linked to the rights identified in the [**Rights Model**](../RightsModel) that govern them, as detailed in the following sections. In addition to this set of actions that are modelled to capture what rights or licenses authorise or prohibit (like ***Copy*** or ***Perform***), there are additional actions to manage how the previous actions (or the related rights) are granted (like ***Agree*** or ***Disagree***) or what is asked in return (like ***Attribute*** or ***Pay***). These actions are also presented in the next subsections.

In all cases, actions share a common set of relationships to other entities participating in the action. These relationships, adopted from the linguistics field, are called case roles or semantic roles (Sowa, 1999). Semantic roles in language link the different parts of a sentence to its main component, the verb, which usually represents an action. 

These same roles are also used in other ontologies and vocabularies like [schema.org](http://schema.org) (Guha, Brickley, Macbeth, 2016). In fact, all actions in the Copyright Ontology are particularisations of schema.org's Action and in some cases have direct equivalents in schema.org, as captured in the ontology.

The set of semantic roles is presented in Table 1, organised in sets related to the broad questions that can be made about actions (like Who? What? When?...) and linked to schema.org when the role is reused from that vocabulary.

Table 1. Semantic roles relating actions to the entities participating in them

| Role Kind | Main Role           | Description                              |
| --------- | ------------------- | ---------------------------------------- |
| who       | schema:agent        | The direct performer or driver of the action (animate or inanimate) |
|           | schema:participant  | Other co-agents that participated in the action indirectly, for instance a recipient |
| what      | schema:object       | The object upon which the action is carried out |
|           | schema:result       | The result produced in the action        |
| where     | schema:location     | Where an action takes place              |
|           | schema:fromLocation | The original location of the object or the agent before the action |
|           | schema:toLocation   | The final location of the object or the agent after the action |
| when      | schema:startTime    | When the action started or the time it is expected to start |
|           | schema:endTime      | When the action finished or the time it is expected to end |
|           | pointInTime         | The point in time when the action happens |
|           | duration            | The amount of time the action requires to complete |
| with      | schema:instrument   | The object that helps the agent perform the action |
| why       | aim                 | The reason  or objective of the action   |
| how       | manner              | The way the action is carried out         |
| if        | condition           | Something that must hold or happen before the action starts |
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

Moreover, as in most copyright regimes the creator becomes the holder of all rights on creations just by the mere fact of manifesting them, it is also possible to capture using the Actions Model this fact, as illustrated in Figure 3 through the **consequence** semantic role.

[TODO: Figure 3 and additional explanation]

### Implementation

#### Rules

<!-- If this action brings into existence the first manifestation of a work, the manifest event implies that the creator becomes the holder of all the copyright rights on the creation. All this is modelled by the Manifest-Rule. In order to check that this is the first manifestation of the work, the rule tests if there is not a statement asserting that there is a manifestation of the work yet.

```
RULE:
(∀v:Manifest)
((∃mr:MoralRights)(∃er:EconomicRights)
((∀p:Person)(∀m':Manifestation)(∀w:Work)(∀m:Manifestation)(∀t:Time)
(¬isManifestationOf(m',w)∧agent(v,p)∧theme(v,w)∧result(v,m)∧
pointInTime(v,t)∧location(v,l)
→
agent(mr,p)∧agent(er,p)∧essence(mr,w)∧essence(er,m)∧
start(mr,t)∧start(er,t)∧location(mr,l)∧location(er,l)∧isManifestationOf(m,w)))
```
-->

#### Smart Contracts

## Economic Rights' Actions

Other fundamental actions are those governed by the rights defined in the [**Rights Model**](../RightsModel):

- *Public Performance Right*: controls the ***Perform*** action on a *Manifestation* or a *Recording* but just when it is in public before and audience, like in a club, restaurant or concert.

- *Fixation Right*: governs the **Record** action on a *Performance* or *Communication*. When recording sound the specific right is the *Sound Recording Right*, and *Motion Picture Right* for audiovisual recordings. 

- *Communication Right*: in general, regulates the ***Communicate*** action, specially when the object is a *Manifestation* or *Recording*. This right also includes the ***Retransmit*** action when applied to a *Performance* or a previous *Communication*, e.g. a re-broadcast. 

  Additionally, depending on the intended audience, more specific rights and their corresponding actions can be defined:

  - *Broadcasting Rights*: controls the ***Broadcast*** action, when the communication is simultaneously made to a plurality of people.
  - *Making Available Right*: govens ***Make Available*** action, when the audience individually choses when the communication takes place.



- *Reproduction Right*: regulates the ***Copy*** action.
- *Distribution Right*: includes the ***Distribute*** action, with the more specific actions depending on the kind of distribution: ***Sell***, ***Rent*** and ***Lend***.
- *Transformation Right*: controls the ***Derive*** action, which includes the more specific kinds of derivations of new works from existing ones: ***Adapt***, ***Translate*** or **Synchronise** (a musical composition recording with an audiovisual work).

[TODO: concrete example and Figure 4]

## Related Rights Actions

...

- *Performers Rights*: performers have exclusive Fixation, Communication, Reproduction, Public Performance and Distribution Rights over their performances. The **Perform** action gives rise to this rights of the performer.
- *Producers Rights*: producers have exclusive Reproduction Right over their fixations and exclusive Distribution Right over the resulting copies. These rights are the result of a **Record** action by the producer.
- *Broadcasters Rights*: broadcasters have exclusive Broadcasting, Fixation and Reproduction Rights over their broadcasts, the result of the **Broadcast** action. 

...

## Copyright Exceptions Actions

In addition to the actions connected to the *Economic Rights*, there are other actions related to the copyright exceptions that many copyright legal systems grant to end-users and identified in the [**Rights Model**](../RightsModel). These exceptions are connected to these copyright exceptions as follows:

-   **Quotation Exception**: related to the **Quote** action, which is a **Copy** action but limited to just a portion of the cited work. Moreover, it usually requires the the source is explicitly attributed using the **Attribute** action.

-   **Education Exception**: educational act, any *Copy*, *Communicate* or
    *Perform* action with educational or research purposes.

-   **Reporting Exception**: *inform*, any copyright governed act with
    informative purposes.

-   **Official Act Exception**: official act, any copyright governed act
    that is part of an official act.

-   **Private Copy Exception**: reproduce privately, a *copy* act that
    produces a reproduction solely for private consumption.

-   **Parody Exception**: parody, any copyright governed act with parody or
    caricature purposes.

-   **Temporary Reproduction Exception**: reproduce temporally, a *copy* act
    that produces a temporal reproduction.

...

## Rights Management Actions

Agree / Disagree

Transfer

Attribute

...

<!-- 

This is just the skeleton of the value chain. In order to give a more
detailed model, each step in the value chain should be modelled as an
event with the corresponding action and associated participants linked
through case roles.

However, the objective is not just to model the actual events that
capture the life cycle of a given creation. Prior to these events,
licenses among the involved parties are established in order to govern
the value flux. Consequently, the ontology must be enriched with
permissions, prohibitions and obligations, the modal operators
that make it possible to model things like licenses and contracts.

### Copyright Licenses Modelling

Copyright provides a legal framework that governs creations life cycle
and tries to assure a fair compensation for all the involved parties,
from authors to consumers. Copyright licenses are built on top of this
legal framework and establish the terms for concrete interactions among
these parties.

Licenses should capture the obligations, permissions and prohibitions
that make sense in the copyright domain. The semantics of the license
terms are captured by the ontology described so far, but it lacks the
terms that capture the semantics of obligations, permissions and
prohibitions, the modal part.

In order to produce a more homogeneous and usable conceptualisation, we
have incorporated these concepts in the ontology using the terms that
appear in licenses when expressed using natural language, i.e. using the
corresponding actions and case roles (e.g. Agree for the verb "to agree"
used in licenses in order to model a permission).

However, prior to incorporating modal operators, event patterns should
be introduced as the way to state what is obliged, permitted or
prohibited by a license; they are then referenced from policies that
establish their modality. They are also naturally captured by the
ontology terms described so far. The proposed actions and case roles are
used to model event patterns in the copyright domain.

For instance, Figure 7 shows a pattern for all copy events in a Peer to
Peer network performed by agent “granted” who copies “content01” from
“PeerA” to two peers from the set “PeerB, PeerC, PeerD” at any time
point six months after “2006-01-01”.

[]{#_Ref165698673 .anchor}Figure 7. Pattern for a copy action in a P2P
scenario

Then, there are the terms to state the modality of these event patterns
in copyright licenses. The Copyright Ontology does so in an implicit
way, following the same “action plus case roles” approach used for event
patterns. Additional classes and relations are added in order to attach
modalities to event patterns. The objective is to state that the set of
actions corresponding to the pattern is permitted, obliged or
prohibited, depending to the particular construct that is attached to
the pattern.

Permissions are captured by a new action, *Agree*, and the permitted
pattern is linked using the *theme* case role, whose semantics are to
point to the object of an action. Following with the example in Figure
7, in order to authorise the pattern that it models, an agreement like
the one shown in Figure 8 can be modelled. The agreement between
“granter” and “granted” in the upper part authorises the pattern pointed
by the *theme* case role, the previous P2P copy pattern at the centre of
the figure.

Obligations are captured as event patterns that must be satisfied at
some time point after the event pattern that triggers the obligation is
exercised. They are modelled using the *consequence* case role that
links the triggering pattern to the one that is obliged. For instance,
in the bottom part of Figure 8 it is stated that, if the copy action is
exercised, the consequence is that the “granted” agent must transfer 3
Euros to the “granter” agent before 24 hours from the copy action. There
is also a cardinality constraint that clarifies that just one transfer
is required.

[[]{#_Ref136142793 .anchor}]{#_Ref165698883 .anchor}Figure 8. Agreement
that permits the P2P copy pattern whose consequence is an economic
obligation

Prohibitions are captured by another action, *Disagree*. Like for the
*Agree* action, the *theme* case role is used to link it to the object
of the action, in this case to the pattern that is prohibited. For
instance, in the previous scenario, the contract might also state that
it is forbidden that the “granted” agent changes “content01” using a
*Disagree* pattern with the corresponding *Transform* action pattern as
its *theme*.

Finally, conditions are patterns that must be satisfied in order to
activate the evaluation of another event pattern, thus acting as a
precondition. The *condition* case role is used to model them. It is
applied to the pattern that is conditioned and it links to the pattern
that establishes the condition. The approach is similar to the
obligation case captured by the *consequence* case role but, in this
case, the *condition* case role establishes an a priori condition.

For instance, in the P2P scenario the *Copy* pattern might by
conditioned by a *Transfer* one that requires that the “granted” agent
makes a 1 Euro prepayment to the “granter” agent before the former can
exercise the permitted P2P *Copy* action.

This completes the static part of the Copyright Ontology. For a full
account of the ontology conceptualisation and additional entities reused
from other ontologies in order to make it possible to model related
aspects like the kinds of involved parties or mereological relations,
please refer to \[25\].

Modelling Value Chains Dynamics 
================================

The previous ontology concepts and relations model the static part of
value chains, being the more complex constructs the events that capture
the static ''pictures" that shape, step by step, value chains.
Therefore, it is necessary to incorporate rules and reasoning mechanisms
that make possible to capture the domain dynamics that make value chains
move.

In order to do that, we have followed a hybrid approach that combines
ontology reasoning mechanisms and rules \[16\]. First, there are the
ontology reasoning mechanisms based on Description Logics that implement
license checking and authorise the uses granted by licenses, which are
detailed in Section 4.1. For complex policies and for modelling the rest
of the dynamic aspects, rules are applied as detailed in Section 4.2.

Ontology-based License Checking
-------------------------------

The previous conceptualisation is just an abstraction of the copyright
domain. An implementation is required if we want to use it to build a
computerised copyright management system. The ontology has been
implemented using the Description Logic (DL) variant of the Web Ontology
Language (OWL-DL), which is constrained in order to be managed by DL
reasoners.

The implementation approach, similar to the KAoS one \[15\], it profits
from DL reasoners in order to implement part of the domain dynamics.
They are used to automatically check if actions on copyrighted content
are authorised or not. As it has been shown, licenses are composed of
*Agree* or *Disagree* actions, linked through a *theme* relation to
patterns of actions that are correspondingly authorised or forbidden.

Patterns are implemented as OWL classes made up from the combination of
classes for actions, e.g. *Copy* or *Access*, and a set of OWL
restrictions. Each restriction defines a constraint on how members of
the class, the domain, are related through the specified property to
other ones, the range. The main restrictions in OWL are:

-   **allValuesFrom**: all the values for the range of the restricted
    property must pertain to the given class. For instance, all values
    of the *agent* relation must pertain to the *Publisher Subscribers*
    class or, for the *pointInTime* relation, pertain to the time range
    \[2008/01/01–2008/06/30\]. In order to support the later, custom
    datatypes reasoning is required \[[^36]\].

-   **someValuesFrom**: there is at least one value that pertains to the
    given range class.

-   **hasValue**: the range is limited to a specific individual, not a
    class of them. For instance, the *theme* of a *Copy* action must be
    the individual “doi:10.1032/…”.

-   **cardinality**: this restriction limits the number of individuals
    that can be connected through the restricted property. A maximum,
    minimum or exact cardinality can be defined. For instance, the
    *recipients* of an action can be limited to just two individuals.

Restrictions are combined using the intersection, union and complement
logical operators in order to compose action patterns. For instance,
Figure 9 shows the conceptual model for a license that combines
commercial and open access terms.

[]{#_Ref165562633 .anchor}Figure 9. Agreement on a copy action under
commercial and open access terms

The upper part shows and *Agree* that permits two *Copy* patterns,
connected through the *theme* relation. The one of the left grants
“Publisher Subscribers” to copy some content identified by a DOI at any
time point six months after 2007-01-01. Any attempt to exercise this
action pattern is subject to a commercial condition, a compensation of
3€. On the other hand, the *Copy* pattern on the left grants anyone to
*Copy* the same content, once the period of six months is surpassed, if
the aim is non-commercial.

The constraints on the kinds of actions, their agents, time points, etc.
are then implemented using OWL restrictions, which are combined using
the logical operators in the OWL language. Figure 10 shows the pattern
build up from the combination of such kind of restrictions for the
example presented in Figure 9. For the set of all copy actions on
“doi:10.1032/…”, the light grey area, two subsets are selected and their
union constitutes the licensed actions pattern, the dark grey areas.

[]{#_Ref165562621 .anchor}Figure 10. Building an action pattern as an
intersection of restrictions

As it can be seen in Figure 8, each intersected restriction reduces the
set of actions. For instance, the non-commercial pattern does not
include any restriction on the agent of the action. Consequently, the
licensed actions set includes any non-commercial copy action performed
by anyone later than 2008-07-01. Table 3 shows the DL notation for the
class definition that models the commercial copy pattern.

[]{#_Ref158636702 .anchor}Table 3. OWL-DL Class for the commercial copy
action pattern

-----------------------------------------------------------------
  Pattern ≡ Copy ⊓ (1)

  ∀pointInTime.≥ 2008-01-01T00:00:00, ≤ 2008-06-30T23:59:59 ⊓ (2)

  ∀agent.PublisherSubscribers ⊓ (≥ 1 agent) ⊓ (3)

  ∃theme.{urn:doi.10.1032/…} ⊓ (≤ 1 theme) (4)


Each intersected restriction reduces the initial set of actions, which
corresponds to all the *Copy* actions. First, (1) models the time range
as a restriction on the *pointingTime* case role to a custom datatype.
This case role is a functional property so no additional constraints on
cardinality are required. The last constraints, (2) and (3), restrict
the range of *agent* to one or more instances of the
“PublisherSubscribers” class and *theme* to just the instance
“urn:doi.10.1032/…”.

From this point, the implementation is quite straightforward. DL
reasoners are specially suited for classifying individuals into classes
when the later are based on necessary and sufficient conditions. They
can answer if an individual, considering its relations to other
individuals and attribute values, satisfies all the restrictions of a
class pattern and, thus, can be classified as an instance of that class.

In the context of the Copyright Ontology implementation, this
functionality is used to check if a particular action, modelled as an
individual, is allowed or not by a license. This corresponds to the fact
that the action individual is classified into a class pattern that is
the *theme* of an *Agree*.

However, before the action is authorised, it is also necessary to check
that any existing *condition* is met and that there is not any
disagreement on the action. The DL reasoner is also useful for this
part. It is checked if the precondition pattern is instantiated, so the
precondition is satisfied, and that the checked action is not classified
into a class pattern that is the theme of a *Disagree*.

To sum up, it is checked that there is an agreement on the action and no
disagreement, and that the precondition is satisfied. This behaviour
allows modelling complex licenses, revocation and avoiding the Open
World Assumption inherent to OWL-DL \[27\].

Despite the versatility of the DL based approach to license checking, as
it has been shown in the previous lines, there is an underlying
algorithm that guides what to check using the DL reasoner and how to
interpret its results in the context of the permissions, prohibitions
and obligations that operate on event patterns. As it is detailed in the
next section, this part can be implemented using rules or
programmatically for restricted scenarios.

Rule-based Modelling
--------------------

There are many dynamic aspects of content value chains modelling that
cannot be captured using DL reasoning mechanism. For this part, we have
applied a rule-based approach. This part has not been fully implemented
because it tends to be too scenario specific. In fact, for many
scenarios where the Copyright Ontology has been applied, these part has
been implemented using alternatives like procedural code or SPARQL
queries \[[^37]\] due to its limited scope and complexity.

If the scenario just considers a part of the value chain, especially if
it is the part nearer to consumers, the license checking dynamics
captured by the OWL-DL implementation reduce the remaining behaviours to
be implemented to the interpretation of the modal part that guides DL
reasoning. This has make it easier and more efficient to implement them
procedurally for scenarios like a copyright-aware streaming server or
P2P controlled metadata diffusion \[[^38]\]. In these cases, the range
of actions involved is mainly reduced to *Access* or *Copy* and the
dynamic part to licenses checking. Moreover, it is also possible to use
SPARQL queries in order to implement patterns requiring variables and
closed world assumptions \[[^39]\].

However, for more complex scenarios set of rules have been developed.
The first case is to model the creative process, how authors acquire
rights just as a result of manifesting a new work or by deriving one
from an existing work. For instance, Table 4 presents the
conceptualisation of the rule that, given a manifest event when the
creator materialises a work, assigns the moral and economic rights on
that creation to the creator. There are also rules for other creative
processes but they have just been conceptualised \[25\], there is not
any implementation based on Web rule languages yet.

[]{#_Ref197195800 .anchor}Table 4. The Manifest Rule that assigns rights
to creators

--------------------------------------------------------------------------------
  (∀v:Manifest)\
  ((∃mr:MoralRights)(∃er:EconomicRights)\
  ((∀p:Person)(∀m':Manifestation)(∀w:Work)(∀m:Manifestation)(∀t:Time)\
  (¬isManifestationOf(m',w)∧agent(v,p)∧theme(v,w)∧result(v,m)∧\
  pointInTime(v,t)∧location(v,l)\
  →\
  agent(mr,p)∧agent(er,p)∧essence(mr,w)∧essence(er,m)∧\
  start(mr,t)∧start(er,t)∧location(mr,l)∧location(er,l)∧isManifestationOf(m,w)))

A complete set of rules have been developed and implemented as an
extension[^40] to the Copyright Ontology for a pair of scenarios related
with user rights. These scenarios are private copy and quote \[[^41]\].
The following section provides details about how private copy has been
implemented using rules. This is a particularly important scenario to
take into account as private copy justifies an important revenue channel
for authors through the levies collected by collective societies. Many
DRM systems block this user right and, consequently, this part of the
value chain.

-->

## Summary

Actions defined in the Copyright Ontology (prefixed with "pro:") in the context of the schema.org actions hierarchy (prefixed with "schema:"):

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
  - **cro:Synchronise**
- **cro:Quote**
- **cro:Record**

## Related Work

...

## The Rest of the Copyright Ontology

 [**Creation Model**](../CreationModel) and [**Rights Model**](../RightsModel).

## References

Brickley, D. (2014). *Announcing Schema.org Actions*. Official blog for schema.org. Retrieved from http://blog.schema.org/2014/04/announcing-schemaorg-actions.html

García, R. (2010). *A Semantic Web Approach to Digital Rights Management*. Saarbrücken, Germany: VDM Verlag. Retrieved from http://rhizomik.net/~roberto/thesis

Guha, R. V., Brickley, D., & Macbeth, S. (2016). Schema.org: Evolution of Structured Data on the Web. *Communications of the ACM*, *59*(2), 44–51. https://doi.org/[10.1145/2844544](https://doi.org/10.1145/2844544)

Sowa, J. F. (1999). *Knowledge Representation. Logical, philosophical and computational foundations*. Pacific Grove, CA, USA: Brooks Cole Publishing Co.