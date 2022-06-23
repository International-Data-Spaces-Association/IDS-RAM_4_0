## Information Layer

The Information Layer specifies the Information Model, the
domain-agnostic, common language of the International Data Spaces. The
Information Model is an essential agreement shared by the participants
and components of the IDS, facilitating compatibility and
interoperability. The primary purpose of this formal model is to enable
(semi-)automated exchange of digital resources within a trusted
ecosystem of distributed parties, while preserving data sovereignty of
Data Owners. The Information Model therefore supports the description,
publication and identification of data products and reusable data
processing software (both referred to hereinafter as Digital
Resources, or simply Resources). Once the relevant Resources
are identified, they can be exchanged and consumed via 
easily discoverable services. Apart from those core
commodities, the Information Model describes essential constituents of
the International Data Spaces, its participants, its infrastructure
components, and its processes.

The Information Model is evolved and maintained by the IDSA Sub-Working
Group 4.[^1]

### Scope

The Information Model is a generic model, with no commitment to any
particular domain. Domain modeling is delegated to shared vocabularies
and data schemata, as provided, e.g., by domain-specific communities of
the International Data Spaces. The Information Model does not provide a
meta-model for defining custom datatypes comparable to standards such as
OData[^2] or OPC-UA[^3]. Concerns beyond the scope of modeling Digital
Resources and their interchange are considered out of scope. The
Information Model therefore does not deal with the side effects of data
exchange (e.g., in scenarios in which data is used for time-critical
machine operations).

### Model Representations

The Information Model has been specified at three levels of
formalization. Each level corresponds to a digital representation,
ranging from this high-level, conceptual document down to the level of
operational code, as depicted in Figure
[3.4.1](#_fig-341-representations-of-the-information-model_). Every
representation depicts the complete Information Model in its particular
way. Among the different representations, the Declarative Representation
(IDS Vocabulary) is the only normative specification of the Information
Model. As such, it is accompanied by a set of auxiliary resources (e.g.,
guidance documents, reference examples, validation tools, and editing
tools intended to support a competent, appropriate, and consistent usage
of the IDS Vocabulary).

#### Conceptual Representation

The Conceptual Representation of the Information Model presents a
high-level overview of the main, largely invariant concepts, with no
commitment to a particular technology or domain. It targets a general
audience, management boards, and media, as it provides basic information
and promotes a shared understanding of the concepts by means of a
textual document and a plausible visual notation. Where available,
references to related elements of the Declarative Representation and a
Programmatic Representation are provided, encouraging the reader to take
a look at these alternative implementations.

#### Declarative Representation

The Declarative Representation (IDS Vocabulary) provides a normative
view of the Information Model of the International Data Spaces.[^4] It
has been developed along the analysis, findings, and requirements of the
Conceptual Representation. Based on a stack of W3C Semantic Web
technology standards[^5] and standard modeling vocabularies (the Data Catalog Vocabulary DCAT[^6],
the Open Digital Rights Language ODRL[^7], the Simple Knowledge Organization System SKOS[^8], etc.), it provides a formal, machine-interpretable
specification of concepts envisaged by the Conceptual Representation,
residing at the persistent namespace URI <https://w3id.org/idsa/core/> according to best practices for publishing linked data[^bp-ld].
Furthermore, it details and formally defines entities of the
International Data Spaces in order to be able to share, search for, and
reason upon the structured metadata describing these entities. The IDS Vocabulary is defined using RDF Schema[^rdfs] and the OWL Web Ontology Language[^owl]; additionally, descriptions of Digital Resources can be validated against SHACL shapes[^shacl] that express syntactic and semantic conditions. Queries against, e.g., Data Resources listed in the Data Catalogue of a Connector or Broker, or against Software Resources available from an App Store, can be formulated in query languages such as SPARQL[^sparql].  Thus, the
Declarative Representation comprises a complete referential model allowing the derivation of a
number of Programmatic Representations. The IDS Vocabulary is typically
used and instantiated by knowledge engineers, ontology experts, or
information architects. It defines a fairly minimal, domain-agnostic
core model and relies on third-party standard and custom
vocabularies in order to express domain-specific facts. According to the
common practice, existing domain vocabularies and standards are reused
where possible, fostering acceptance and interoperability.

#### Programmatic Representation

The Programmatic Representation of the Information Model targets
Software Providers by supporting seamless integration of the Information
Model with a development infrastructure software developers are familiar
with. It comprises a programming language data model (e.g., Java,
Python, C++) shipped as a set of documented software libraries (e.g.,
JAR files).[^9] The Programmatic Representation provides a best-effort
mapping of the IDS Vocabulary onto native structures of a target
programming language. This approach supports type-safe development,
well-established unit testing, and quality assurance processes. It
allows developers to easily create instances of the Information Model
that are compliant with the IDS Vocabulary, relieving them from the
intricacies of ontology processing.


![Representations of the Information Model](./media/image31.png)

#### _Fig. 3.4.1: Representations of the Information Model_

### Conceptual Representation of a Digital Resource in the IDS

In the following, the pivotal concept of a Digital Resource is
introduced, segregated into modules in accordance with the
separation of concerns principle (SoC principle). To do so, a
set of six broad concerns (“concern hexagon”) is provided.

#### Version Note

Since version 3.0 of the IDS-RAM, this section of the document has
been reduced to the same high level of abstraction as the other sections.
Full versioning
information is available from the repository that hosts the source code of the
normative Declarative Representation as well as documentation covering further details on the Conceptual Representation.[^10]
The remaining text has been edited to better present the Information Layer in the context of the other layers, and to provide up-to-date pointers to external standards reused.

#### (Digital) Resource

A (Digital) Resource in the context of the International Data Spaces is
a uniquely identifiable, valuable, digital (i.e., non-physical) commodity
that can be traded and exchanged between remote participants using the
IDS infrastructure. Following the web resource paradigm[^11], the
abstract content of a Resource may be provided in a variety of
representations. Examples of Resources include documents, time series of
sensor values, messages, image file archives, or media streams.
Resources are subject to forwarding, processing, and/or consumption,
with a particular demand for modeling related, complementary aspects
(i.e., content, provenance, provisioning etc.). These are analyzed and
specified here by applying the separation of concerns (SoC)
paradigm[^12].

#### Separation of Concerns (SoC)

Following the separation of concerns design principle, only one
dimension of a subject matter is considered at a time, for the sake of
clarity and consistency. Similar to the principle a microscope works,
each concern follows a particular, analytical point of view, while other
concerns can temporarily be disregarded. This principle can be applied
to information modeling, aiming at a thorough understanding of the
domain and fostering modularity and re-usability of the resulting (sub-)models. Accordingly designed, these models may evolve independently of
each other and can be updated by different agents at different times. As
any modification of a single element of the overall model does not
require a change in other, logically unrelated parts, the development
and maintenance of models can be substantially simplified.


![Outline of the Concern-Basic concern hexagon](./media/image32.png)

#### _Fig. 3.4.2: Outline of the Concern-Basic concern hexagon_

#### Concern Hexagon

To illustrate the main modeling [c]{.underline}oncerns of Digital
Resources in a way easy to memorize, the mnemonic hexagonal arrangement
of [c]{.underline}arbon atoms can be used (“C-Hexagon”), as shown in
Figure [3.4.2](#_fig-342-outline-of-the-concern-basic-concern-hexagon_).

As a
Resource's content is its most essential aspect, *C*ontent is located at
the top of the hexagon. The *Content* concern deals with 
1. the description of a Resource's abstract substance, 
2. its serialization as a representation in a machine-interpretable format, and 
3. the materializations of these representations at certain points in time as one or more instances (e.g., values or artifacts).

Content is interpretable by references to a
shared, formally defined *C*oncept, which may cover the meaning, annotation and interpretation of entities by, e.g., 
1. natural language keywords, 
2. terms defined in curated sources such as controlled vocabularies, or
3. types defined in type systems or ontologies.

On the other hand, links to a particular
*C*ontext (in terms of, e.g.,
* time, 
* place, or 
* real-world entities)
make the
Content potentially relevant for certain Data Consumers.

Thus, the upper
part of the C-Hexagon deals with the “what” aspects, independently of
Data Exchange, Data Sharing or Data Utilization. The lower part relates
to the “how” aspects; i.e., how the content is exchanged
(*C*ommunication) and under which conditions (*C*ommodity). 

The *Communication* concern deals with means to communicate a Resource's Content in one of the Representations
available, e.g., 
* by sending messages in some communication protocol
* to a resource or service endpoint or to an IDS Connector
* in order to perform an operation.

The *Commodity* concern helps to address the value and utility of a Resource in terms of, e.g.,
* its provenance,
* its quality, and
* the (usage) policies attached to it, e.g., the obligation to pay a certain price for its consumption.

The 
*C*ommunity of Trust concern refers to the distinctive feature of the
International Data Spaces being an ecosystem of certified participants
operating certified components, such as Connectors. Using such components, Participants exchange and share Digital Resources in a secure and trusted way in accordance
with contracts composed of usage policies, thus ensuring data sovereignty.

![Detailed Concern Hexagon](./media/image53.png)

#### _Fig. 3.4.3: Detailed Concern Hexagon_


The level of detail differs across the individual concerns. The
selection of their constituting aspects may change in light of new
requirements and insights; Fig. [3.4.3](#_fig-343-detailed-concern-hexagon_) suggests one such expansion of the C-Hexagon to one more level of detail.

Modeling concerns may inform, but do not
necessarily correspond to any physical organization of the model (e.g.,
modules or directories).

[^1]: IDSA members may find further information at
    https://industrialdataspace.jiveon.com/community/workinggroups/architecture/swg4-information-model/.

[^2]: https://www.odata.org/

[^3]: https://opcfoundation.org/

[^4]: https://github.com/International-Data-Spaces-Association/InformationModel

[^5]: https://www.w3.org/standards/semanticweb/

[^6]: Data Catalog Vocabulary (DCAT) - Version 2. W3C Recommendation 04 February 2020. https://www.w3.org/TR/vocab-dcat-2/

[^7]: ODRL Information Model 2.2. W3C Recommendation 15 February 2018. https://www.w3.org/TR/odrl-model/

[^8]: SKOS Simple Knowledge Organization System Reference. W3C Recommendation 18 August 2009. https://www.w3.org/TR/skos-reference/

[^rdfs]: RDF Schema 1.1. W3C Recommendation 25 February 2014. https://www.w3.org/TR/rdf-schema/

[^owl]: OWL 2 Web Ontology Language Document Overview (Second Edition). W3C Recommendation 11 December 2012. https://www.w3.org/TR/owl2-overview/

[^shacl]: Shapes Constraint Language (SHACL). W3C Recommendation 20 July 2017. https://www.w3.org/TR/shacl/

[^sparql]: SPARQL 1.1 Query Language. W3C Recommendation 21 March 2013. https://www.w3.org/TR/sparql11-query/

[^bp-ld]: Best Practices for Publishing Linked Data. W3C Working Group Note 09 January 2014. http://www.w3.org/TR/ld-bp/

[^9]: Known implementations are listed at https://github.com/International-Data-Spaces-Association/InformationModel/.

[^10]: In the repository referenced in section 3.4.2.2, see the
    top-level file *CHANGELOG.md*.

[^11]: R. Fielding. \"Architectural Styles and the Design of
    Network-based Software Architectures,\" 2000. PhD thesis. Table 5-1
    \"REST Data Elements\". Available: https://www.ics.uci.edu/$\sim$
    fielding/pubs/dissertation/rest_arch_style.htm$\#$ tab_5\_1

[^12]: E. W. Dijkstra. \"On the role of scientific thought,\" EWD 447,
    2000. Available:
    http://www.cs.utexas.edu/users/EWD/ewd04xx/EWD447.PDF
