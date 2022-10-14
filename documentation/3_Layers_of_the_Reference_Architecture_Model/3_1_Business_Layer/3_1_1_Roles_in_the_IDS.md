### ROLES IN THE INTERNATIONAL DATA SPACES ###

In the following, each role a participant can assume in the
International Data Spaces is described in detail, together with the
tasks assigned to it. The Reference Architecture model distinguishes
four "categories" containing "business roles" that, depending on the
individual business model, can assume one or more of the "basic roles".

#### Basic Roles in the International Data Space ###

The ecosystem of the IDS comprises several basic tasks being carried out
by the various participants. The set of these tasks can be derived from
relevant objects in the IDS and the activities along the respective life
cycle. IDS objects that participants in the IDS have to handle are:

1.  **Connector**: technical core component required for a participant
    to join the International Data Spaces

2.  **Data**: here synonym to Data Asset, i.e. content exposed for
    exchange by the Data Provider

3.  **Vocabulary**: ontologies, reference data models, or metadata
    elements that can be used to annotate and describe datasets, usage
    policies, apps, services data sources etc.

4.  **Identity**: information of and for participants in the IDS

5.  **App**: applications that can be deployed inside the connector.
    Apps facilitate data processing workflows. They may be certified by
    a Certification Body, following the certification procedures defined
    in the [Certification Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/README.md).

6.  **Transaction**: comprises all activities performed in the course of
    a data exchange

7.  **Service**: software running in a connector and provided as a
    service (algorithm and computing time)

For each of these IDS objects, the Reference Architecture Model defines
activities along the life cycle define. The set of activities, or a
subset of it, that describe the life cycle of the objects are:

1.  **Create**: create an object, e.g. software by programming or data
    from reading a sensor

2.  **Own**: own an object or hold the corresponding license or right
    according to local rules and regulations

3.  **Certify/verify**: e.g. certify software according to the IDS
    certification scheme or verify authenticity of data

4.  **Publish**: share meta data on objects such as data, apps, services
    etc.

5.  **Provide**: technically provide the object

6.  **Consume**: technically receive the object

7.  **Use**: make use of an object in a business model that does not
    consist of an intermediary function (see below)

8.  **Delete**: Delete, eliminate or turn object off

Each activity along the life cycle of an IDS object is carried out by a
participant of the IDS. A role that a participant takes to carry out
these activities is called "basic role". As some combinations from an
IDS object and an activity (e.g. "verify data", "delete identity") may
be relevant in other contexts than the IDS RAM or may become relevant in
the future, some potential basic roles are declared as (currently) "out
of IDS RAM scope". The table below shows the basic roles defined in the IDS.

|                 |       **Create**      |       **Own**      | **Certify / Verify** |       **Publish**       |       **Provide**      |      **Consume      |         **Use**         |      **Delete**     |   |   |   |   |   |
|-----------------|:---------------------:|:------------------:|:--------------------:|:-----------------------:|:----------------------:|:-------------------:|:-----------------------:|:-------------------:|:-:|:-:|:-:|:-:|:-:|
| **Connector**   |   Connector Creator   |   Connector Owner  |  Connector Certifier |   Connector Publisher   |   Connector Provider   |  (Out of RAM scope) |      Connector User     |  (Out of RAM scope) |   |   |   |   |   |
| **Data**        |      Data Creator     |     Data Owner     |  (Out of RAM scope)  | Connector / Data Broker |      Data Provider     |    Data Consumer    |        Data User        |     Data Eraser     |   |   |   |   |   |
| **Vocabulary**  |   Vocabulary Creator  |  Vocabulary Owner  |  (Out of RAM scope)  |   Vocabulary Publisher  |   Vocabulary Provider  | Vocabulary Consumer |     Vocabulary User     |  (Out of RAM scope) |   |   |   |   |   |
| **Identity**    |    Identity Creator   |   Identity Owner   | Identity Verificator |   Identitiy Publisher   | Identity Authenticator |  (Out of RAM scope) |      Identity User      | Identity Eliminator |   |   |   |   |   |
| **App**         |      App Creator      |      App Owner     |     App Certifier    |        App Broker       |      App Provider      |     App Consumer    |         App User        |   App Deleter (?)   |   |   |   |   |   |
| **Transaction** | Transaction Initiator | (Out of RAM scope) |  Transaction Clearer |    (Out of RAM scope)   |   (Out of RAM scope)   |  (Out of RAM scope) | Transaction Participant |  (Out of RAM scope) |   |   |   |   |   |
| **Service**     |    Service Creator    |    Service Owner   |   Service Certifier  |      Service Broker     |    Service Provider    |   Service Consumer  |       Service User      |  (Out of RAM scope) |   |   |   |   |   |

These basic roles are suitable to define technical tasks in the IDS and
roles of the participants in detail. As this quite large number is,
however, bulky especially for early discussions, grouping basic roles to
business roles is advisable. The basic roles are explained in a suitable
context of the business roles.

#### Business Roles in the International Data Space ####

On the level of the business layer, depending on the use case, it might
not be crucial to distinguish between basic roles. E.g. if an industrial
company intends to provide quality check data to a supply chain partner,
the distinction between data owner and data creator is unnecessary.
Hence, business roles are introduced. Business roles comprise one or
more basic role. Their exact scope of comprised basic roles depends on
the individual business model of the participant as individual business
models (including pricing models) may be applied as deemed appropriate.
E.g. a data intermediary (see details below) operating a data hub may
store data as a trustee, act as a broker or do both -- depending on the
business model. Therefore, as the assignment of basic roles to a
business role may vary, the assignment is marked with the following
symbols:

-   **T** (typical): basic role typically taken by a business role

-   **M** (mandatory): required role from a technical perspective

There are four categories of roles:

» Category 1: Core Participant

» Category 2: Intermediary

» Category 3: Software Developer

» Category 4: Governance Body

#### CATEGORY 1: CORE PARTICIPANT ####

Core Participants are involved and required every time data is exchanged
in the International Data Spaces. Roles assigned to this category are
Data Supplier and Data Customer. The role of a Core Participant can be
assumed by any organization that owns, wants to provide, and/or wants to
consume or use data.

Benefit for participants in the International Data Spaces is created by
these roles as they create, potentially own and possibly provide data as
well as receive, process and most likely at some point in time delete
data.

##### DATA SUPPLIER ####

The Data Supplier is a role that induces data into the IDS ecosystem.
Depending on the individual business and technical operation model, the
business role Data Supplier typically assumes the basic roles Data
Creator, Data Owner, and/or Data Provider.

The **Data Creator** creates data, e.g. by generating data such as from
a sensor or accessing data in backend IT systems.

As the legal situation regarding data ownership is very complicated (as
discussed in the [Governance Perspective](#)), the term '**Data Owner'** is not used in a
legal understanding in this document. The Reference Architecture Model
takes an operational data management perspective, defining a Data Owner
as a legal entity or natural person executing control over data. This
enables the Data Owner to define Data Usage Policies and provide access
to its data. Data Ownership includes at least two major concepts:

» having the (technical) means and the responsibility to define Usage
Contracts and Usage Policies, and to provide access to data; and

» having the (technical) means and the responsibility to define the
Payment Model, including the model for reuse of data by third parties.

The **Data Provider** makes data technically available in the IDS for
being transmitted to a Data Customer on behalf of the Data Owner. To
submit metadata to a Broker, or exchange data with a Data Consumer, the
Data Provider uses software components that are compliant with the
Reference Architecture Model of the International Data Spaces. Compliant
software is available from Software Developers and App Developers.

Usually, a participant acting as a Data Creator automatically assumes
the role of the Data Owner. However, if rights or licenses on data are
given to different participant, the same assumes the role of the Data
Owner. In this case, Data Owner and Data Creator would be different
participants.

Initially, a participant acting as a Data Creator automatically assumes
the role of the Data Provider as well. However, there may be cases in
which the Data Provider is not the Data Creator, e.g. if the data is
technically managed by a different entity than the Data Creator. This
can be the case of a company using an external IT service provider for
data management, or if data management activities are handed over to a
Data Intermediary (cf. below) as a data trustee.

In cases in which the Data Owner does not act as the Data Provider at
the same time, the only activity of the Data Owner is to authorize a
Data Provider to make its data available to be used by a Data Consumer.
Any such authorization should be documented by a contract, which should
include data usage policy information for the data provided (see
[Usage Control in IDS](#)). The contract needs not necessarily be a paper
document, but may be an electronic file as well.

At the end of a complete or partial data transaction, for example, the
Data Provider may log the details of the successful (or unsuccessful)
completion of the transaction at a Clearing House (see below) to
facilitate billing or resolve a conflict. Furthermore, the Data Provider
can use Apps in the IDS connector to enrich or transform the data in
some way, or to improve its quality. Data Apps are specific applications
that can be loaded into the IDS connector and, thus, linked into the
data exchange workflow.

##### DATA CUSTOMER #####

The **Data Consumer** receives data from a Data Provider. From a
business process modeling perspective, the Data Consumer is the mirror
entity of the Data Provider; the activities performed by the Data
Consumer are therefore similar to the activities performed by the Data
Provider.

If data is processed by a Service Provider (see below), the Data
Customer takes the role of a **Service Consumer**. This constellation my
occur, e.g. when the Data Owner/Provider attaches usage policies to the
data that require data being processed by a third-party service (i.e.
Service Provider) before being handed to the consumer. Then, the Data
Customer is both Data Consumer and Service Consumer.

Similar to the Data Owner being the legal entity that has the legal
control over its data, the **Data User** is the legal entity that has
the legal right to use the data of a Data Owner as specified by the
usage policy. The Data User can be identical with the Data Consumer.
However, there may be scenarios in which these roles are assumed by
different participants. For example, a patient could use a web-based
software system to manage their personal health data and grant access to
this data to a health coach. The data could be received from a hospital.
In this case, the health coach would be the Data User and the provider
of the web-based software system would be the Data Consumer.

In existing, mostly quite static relations, the Data Customer and Data
Supplier already know each other and intend to exchange specific data
sets (e.g. capacity information for a particular part to be produced).
In these cases, the Data Consumer directly requests data (and the
corresponding metadata) from the Data Provider or the Data Provider
pushes data directly to the Data Consumer.

If the Data Customer searches for a type of data that is provided by
many suppliers, .e.g. weather data, the Data Consumer can search for
existing datasets by making an inquiry at a Data Intermediary that
assumes the basic role of a Data Broker (cf. according section below).
The Data Intermediary (Data Broker) then provides the required metadata
for the Data Consumer to connect to a Data Provider.

Like a Data Provider, the Data Consumer may log the details of a
successful (or unsuccessful) data exchange transaction at a Clearing
House, use Apps to enrich, transform, etc. the data received, or use a
Data Broker to retrieve data sources.

#### CATEGORY 2: INTERMEDIARY #####

Intermediaries act as trusted entities and are commonly considered as
"platforms". They assume a rather central role compared to the great
number of data suppliers and customers, though multiple, especially
competitive platforms of the same role may and shall exist. Business
Roles assigned to this category are Data Intermediary, Services
Intermediary, App Store, Vocabulary Intermediary, Clearing House, and
Identity Authority. Most likely, the business models of intermediaries
will lead to a combination of some of the business roles, e.g. act as
both Data and Service Intermediary.

The Intermediary roles may be assumed only by trusted organizations.
They create benefit for participants in the IDS by establishing trust,
providing metadata, and creating a business model around their services.

##### Data Intermediary #####

The Data Intermediary is a platform operator that assumes mainly the
data-related basic roles Data Provider/Data Consumer and Data Broker.

Assuming the basic role of a **Data Provider** or **Data Consumer**, the
Data Intermediary is responsible for the execution of the data exchange
on behalf of the Data Owner or User respectively. Providing a Data
Consumer with data is, hence, the main activity of the Data Provider.

To facilitate a data request from a Data Consumer, the Data Intermediary
would provide a **Data Broker** with proper metadata about the data.
Acting as a Data Broker, the Data Intermediary stores and manages
information about the data sources available in the International Data
Spaces. An organization offering data brokering in the International
Data Spaces may assume other intermediary basic roles at the same time
(e.g. Service Broker, Clearing House or Identity Authority, see below).
Assuming further basic roles consequently means additional tasks a
participant has to execute.

The activities of the Data Broker mainly focus on receiving and
providing metadata. The Data Broker must provide an interface for Data
Creators to send their metadata. The metadata should be stored in an
internal repository for being queried by Data Consumers in a structured
manner. While the core of the metadata model must be specified by the
International Data Spaces (i.e. by the Information Model, see
  [Information Layer](#)), a Data Broker may extend the metadata model to manage additional
metadata elements.

After the Data Broker has provided the Data Consumer with the metadata
about a certain Data Provider, it is not involved in the subsequent data
exchange process.

##### Service Intermediary #####

A service offers e.g. data analysis, data integration, data cleansing,
or semantic enrichment to improve the quality of the data exchanged in
the International Data Spaces. Analogously to the Data Intermediary, the
Service Intermediary is a platform operator providing metadata on
services, the services itself (i.e. app including computing time as a
trustee), or both. Hence, the Service Intermediary typically assumes
mainly the service-related basic roles of the Service Provider and/or
Service Broker.

A **Service Provider** receives data from a Data Provider (or another
Service Provider) and either returns the calculation result to the same
or directs it to an indicated Data Consumer (which then is a Service
Consumer at the same time). The participant who receives processed data
from a Service Intermediary could be again a Service Intermediary as
data can be routed through an arbitrary number of instances of services
in the IDS.

In order to provide the service, the Service Provider installs apps in
its IDS connector that can be developed by the participant himself or
from a third-party App Provider. The Service Intermediary is then an App
Consumer. Just like in the case of data, the Service Owner might be a
different organization than the Service Provider. The Service Provider
then operates the service on behalf of the owner.

To allow other participants in the IDS to retrieve available services,
Service Intermediaries may also assume the role of the **Service
Broker**. The Service Broker provides metadata on present services in
the IDS analogously to the Data Broker.

##### APP STORE #####

The business role of the App Store is responsible to distribute data
apps. In contrary to the Service Provider, the algorithm is not executed
in the platform of the App Store, but provided for download to the IDS
connector of the App Consumer. App Consumer and App Owner may be
different, if the owner acquires (purchases) an app, but lets it be
distributed to Service Provider. The App Store role typically comprises
the basic roles of the App Broker and App Provider. Apps are programmed
by the App Creator that can, but does not have to be identical to the
App Owner (cf. Data Owner/Creator above).

The App Store is first responsible for managing information about apps.
This is the **Data Broker** role. The App Store should provide
interfaces for publishing and retrieving apps plus corresponding
metadata. In most cases, the App Store will, secondly, also assume the
basic role of the **App Provider** as it is common for mobile phone app
stores. The App Store then technically provides the app on behalf of the
App Owner. However, not only data, but also apps may be sensitive and,
therefore, shall be stored in the sphere of the App Owner. In this case,
the App Broker and App Provider roles would be taken be different
participants.

Depending on the business model, an App Store could also comprise the
**App Owner** role as the store may own the license for particular apps.
As the App Store might take responsibility for the validity and
functionality of the apps provided, the App Store could also act as an
**App Certifier**.

##### VOCABULARY Intermediary #####

The Vocabulary Intermediary technically manages and offers vocabularies
(i.e. ontologies, reference data models, or metadata elements). The
Vocabulary Intermediary typically assumes the basis roles of the
Vocabulary Publisher and Vocabulary Provider. Vocabularies are owned and
governed by the according Standardization Organization (cf. category 4).

Vocabularies can be used to annotate and describe data assets. These
data assets may comprise at least:

-   **Information Model** of the International Data Spaces, which is the
    basis for the description of data sources (see [Information Layer](#)). There
    is only one information model in the IDS governed by the IDSA.

-   **Domain-specific vocabularies**: They are essential for the
    scalability and success of the IDS. Domains are e.g. represented in
    the very common set of linked open data (LOD). For example, "gene
    ontology" is a unified vocabulary for parts of life sciences, "GAO"
    for the automotive industry, etc.

-   **Legal terms**: To describe usage policies and to enable smart
    contracting, legal terms must be coded in a machine-readable and
    -understandable manner. The IDS Information Model defines the Open
    Digital Rights Language (ODRL) to describe usage policies. Still,
    IDS communities such as a (closed) supply chain network or a
    domain-specific IDS initiative could define additional
    (complementary or alternative) vocabularies, e.g. depict the
    International Commercial Terms (Incoterms) as an ontology or
    reference to the iShare Scheme.

There is no dedicated or exclusive role that creates vocabularies.
Usually, standardization organizations such as ISO, EN, IEEE etc., but
also industrial associations define standards that can be formulated as
a vocabulary (Vocabulary Creators and Owners). Except the IDS
information model, there can be multiple vocabularies describing the
same context (e.g. different types of smart contracts or usage policy
descriptions). A single vocabulary for the same context support
standardization and, thus, compatibility efforts. Multiple vocabularies
provide flexibility and competitiveness.

To find the right and latest vocabulary, they must be retrievable with
the help of a **Vocabulary Publisher**. This is a repository of
vocabulary metadata. In most cases, as vocabularies are usually (for the
sake of their purpose) open, the Vocabulary Intermediary will also act
as a **Vocabulary Provider**, i.e. providing the vocabulary technically
for download.

Vocabulary Users are all instances using vocabularies, e.g. Data
Suppliers, Data Customers, Service Intermediaries, Data Intermediaries,
App Stores, etc. Also the Vocabulary Intermediary possibly may use a
vocabulary to describe the vocabulary repository.

##### CLEARING HOUSE #####

The Clearing House is an intermediary that provides clearing and
settlement services for all financial and data exchange transactions. In
the International Data Spaces, clearing activities are separated from
broker services, since these activities are technically different from
maintaining a metadata repository. As already stated above, it might
still be possible that the role Clearing House and other intermediary
roles are assumed by the same organization, as both roles require acting
as a trusted intermediary between the Data Supplier and the Data
Customer.

The Clearing House logs all activities performed in the course of a data
exchange, thus, assuming the role of the **Transaction Clearer**. After
a data exchange, or parts of it, has been completed, both the Data
Supplier and the Data Customer confirm the data transfer by logging the
details of the transaction at the Clearing House, e.g. by means of
distributed ledger technologies. Based on this logging information, the
transaction can then be billed. The logging information can also be used
to resolve conflicts (e.g., to clarify whether a data package has been
received by the Data Customer or not). The Clearing House also provides
reports on the performed (logged) transactions for billing, conflict
resolution, etc.

##### Identity Authority #####

The Identity Authority should offer a service to create, maintain,
manage, monitor, and validate identity information of and for
participants in the International Data Spaces. This is imperative for
secure operation of the International Data Spaces and to avoid
unauthorized access to data. Hence, every participant in the IDS
inevitably owns an identity (describing the respective participant) and
uses an identity for authentication.

The Identity Authority consist of a Certification Authority (managing
digital certificates for the participants of the International Data
Spaces), a Dynamic Attribute Provisioning Service (DAPS, managing the
dynamic attributes of the participants), and a service named Dynamic
Trust Monitoring (DTM, for continuous monitoring of the security and
behavior of the network. More details about identity management can be
found in the [security perspective](#).

Typically, identities are created by the Identity Authority, then acting
as an **Identity Creator**. In the sense of a directory, the authority
would also publish the identity if desired by the owner and especially
provide certificates, DAPS etc. for authentication purposes. These are
the basic roles **Identity Publisher** and **Identity Authenticator**.

#### CATEGORY 3: SOFTWARE DEVELOPER ####

This category comprises IT companies providing software to the
participants of the International Data Spaces. Roles subsumed under this
category are the business roles App Developer and Connector Developer.

Benefit is created by these roles by providing software to the
participants of the International Data Spaces. Please note that the
process of providing software to be used for establishing the endpoints
of a data exchange transaction (e.g. Enterprise Systems like ERP or MES,
or other platforms) is not part of the International Data Spaces, as it
takes place before an organization joins the IDS.

##### App Developer #####

App Developers develop data apps to be used in an IDS Connector. Thus,
the App Developer typically covers the basic roles **App Creator** and,
as long as the data app is not created on behalf, **App Owner**.

To be deployable, a data app has to be compliant with the system
architecture of the International Data Spaces (see [system layer](#)). In
addition, data Apps can be certified by a Certification Body in order to
increase trust in these applications (especially with regard to Data
Apps processing sensitive information).

Data apps are published and most likely provided in the App Store to
Data Customers, Data Suppliers, or Intermediaries. App Developers should
describe each Data App using metadata (in compliance with a metadata
model) with regard to its semantics, functionality, interfaces, etc.

##### Connector Developer #####

A Connector Developer provides software for implementing the
functionality required by the International Data Spaces (i.e., through
software components, as described in the [system layer](#)). Unlike Data Apps,
software is not provided by the App Store, but delivered over the
Connector Developer's usual distribution channels, and used on the basis
of individual agreements between the Connector Developer and the user
(e.g., a Data Customer, a Data Supplier, or an Intermediary). This
procedure implies that the agreements (e.g. licenses) for deployment and
software usage remain outside the scope of the International Data
Spaces.

The Connector Developer typically assumes the basic roles **Connector
Creator**, **Connector Owner**, and -- considering the way of software
distribution described above -- **Connector Provider**.

#### CATEGORY 4: GOVERNANCE BODY #####

Governance Bodies in the IDS have the authority and task to set and
enforce guidelines to standardize data exchange, to create trust and, in
the end, to enable sustainable operation of the IDS. The Certification
Body, Evaluation Facilities, Standardization Organizations, and the
International Data Spaces Association are the business roles in the
category of Governance Bodies.

##### CERTIFICATION BODY AND EVALUATION FACILITIES #####

The participants in the International Data Spaces benefit from the
Certification Body and the Evaluation Facilities as these roles take
care of the certification process and issue certificates (both with
regard to organizations that want to participate and with regard to
software components that are to be used).

The Certification Body, together with selected Evaluation Facilities, is
in charge of the certification of the participants and the core
technical components in the International Data Spaces. These Governance
Bodies make sure that only compliant organizations are granted access to
the trusted business ecosystem. In this process, the Certification Body
supervises the actions and decisions of the Evaluation Facilities.

Thus, from the technical perspective, the basic roles **Connector
Certifier**, **App Certifier** and **Service Certifier**.

The Certification Scheme applied in the process is described in the [Certification Perspective](#).

##### Standardization Organization #####

Standardization Organizations govern standards that are typically
describe as an ontology or vocabulary. In general, there is neither a
claim for exclusiveness of a standard nor an obligation apply it. One
example could be the International Commercial Terms (Incoterms) that are
a common legal foundation in logistics, but does have to be applied. A
domain-specific Standardization Organization is, e.g., Odette, a
European organization setting data standards for the automotive
industry.

The business role Standardization Organization, therefore, comprises the
basic roles **Vocabulary Creator** and **Vocabulary Owner**.

Among the standardization organizations, the IDSA assumes a special
role, as it is exclusively entitled to govern the IDS Reference
Architecture Model and the Information Model.

##### INTERNATIONAL DATA SPACES ASSOCIATION (IDSA) #####

The International Data Spaces Association (IDSA) is a non-profit
organization promoting the continuous development of the International
Data Spaces. More specifically, it supports and governs the continuous
development of the Reference Architecture Model and the participant
certification process. The International Data Spaces Association is
currently organized across several working groups, each one addressing a
specific topic (e.g., architecture, use cases and requirements, or
certification). Members of the Association are primarily large
industrial enterprises, IT companies, SMEs, research institutions, and
industry associations.

As the International Data Spaces Association is not directly involved in
the data exchange activities of the International Data Spaces, its role
will not be further addressed in the sections on the other Layers.
