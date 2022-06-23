### Roles in the International Data Spaces

In the following, each role a participant can assume in the
International Data Spaces is described in detail, together with the
basic tasks assigned to it. The majority of roles require certification
of the organization that wants to assume that role, including
certification of the technical, physical, and organizational security
mechanisms the organization employs. Certification of organizations that
want to participate in the International Data Spaces is considered a
fundamental measure to establish trust among all participants
(especially with regard to roles that are crucial for the overall
functioning of the International Data Spaces, such as the Broker Service
Provider, the App Store Provider, the Identity Provider, or the Clearing
House). The Certification Scheme applied in the participant evaluation
process is described in detail in Section 4.2.

There are four categories of roles:

-   Category 1: Core Participant

-   Category 2: Intermediary

-   Category 3: Software / Service Provider

-   Category 4: Governance Body

#### Category 1: Core Participant

Core Participants are involved and required every time data is exchanged
in the International Data Spaces. Roles assigned to this category are
Data Owner, Data Provider, Data Consumer, Data User, and App Provider.
The role of a Core Participant can be assumed by any organization that
owns, wants to provide, and/or wants to consume or use data.

Benefit for participants in the International Data Spaces is created by
these roles as they make data available (Data Owner), provide data (Data
Provider), or consume/use data (Data Consumer, Data User, App Provider).
In addition, Data Providers and Data Consumers may apply business models
(including pricing models) as deemed appropriate.

#### Data Owner

As the legal situation regarding data ownership is very complicated (as
discussed in section 4.3.4), the term 'Data Owner' is not used in a
legal understanding in this document. The Reference Architecture Model
takes an operational data management perspective, defining a Data Owner
as a legal entity or natural person creating data and/or executing
control over it. This enables the Data Owner to define Data Usage
Policies and provide access to its data. Data Ownership includes at
least two major concepts:

-   having the (technical) means and the responsibility to define Usage
    Contracts and Usage Policies, and to provide access to data; and

-   having the (technical) means and the responsibility to define the
    Payment Model, including the model for reuse of data by third
    parties.

Usually, a participant acting as Data Owner automatically assumes the
role of the Data Provider as well. However, there may be cases in which
the Data Provider is not the Data Owner (e.g., if the data is
technically managed by a different entity than the Data Owner, such as
in the case of a company using an external IT service provider for data
management, or if data management activities are handed over to a data
trustee).

In cases in which the Data Owner does not act as the Data Provider at
the same time, the only activity of the Data Owner is to authorize a
Data Provider to make its data available to be used by a Data Consumer.
Any such authorization should be documented by a contract, which should
include data usage policy information for the data provided (see.
Section 4.1.3.6). The contract needs not necessarily be a paper
document, but may be an electronic file as well.

#### Data Provider

The Data Provider makes data available for being exchanged between a
Data Owner and a Data Consumer. As already mentioned above, the Data
Provider is in most cases identical with the Data Owner, but not
necessarily. To submit metadata to a Broker, or exchange data with a
Data Consumer, the Data Provider uses software components that are
compliant with the Reference Architecture Model of the International
Data Spaces.

Providing a Data Consumer with data from a Data Owner is the main
activity of the Data Provider. To facilitate a data request from a Data
Consumer, the Data Provider should provide a Broker Service Provider
(see below) with proper metadata about the data. However, a Broker
Service Provider is not necessarily required for a Data Consumer and a
Data Provider to establish a connection.

Exchanging data with a Data Consumer needs not necessarily be the only
activity of the Data Provider. At the end of a data exchange transaction
completely or partially executed, for example, the Data Provider may log
the details of the successful (or unsuccessful) completion of the
transaction at a Clearing House (see below) to facilitate billing or
resolve a conflict. Furthermore, the Data Provider can use Data Apps to
enrich or transform the data in some way, or to improve its quality.
(Data Apps are specific applications that can be integrated into the
data exchange workflow between two or more participants in the
International Data Spaces.)

If the technical infrastructure for participating in the International
Data Spaces is not deployed by the Data Consumer, a Data Provider may
use a Service Provider (see below) to connect to the International Data
Spaces.

#### Data Consumer

The Data Consumer receives data from a Data Provider. From a business
process modeling perspective, the Data Consumer is the mirror entity of
the Data Provider; the activities performed by the Data Consumer are
therefore similar to the activities performed by the Data Provider.

Before the connection to a Data Provider can be established, the Data
Consumer can search for existing datasets by making an inquiry at a
Broker Service Provider. The Broker Service Provider then provides the
required metadata for the Data Consumer to connect to a Data Provider.
Alternatively, the Data Consumer can establish a connection with a Data
Provider directly (i.e., without involving a Broker Service Provider).
In cases in which the information to connect with the Data Provider is
already known to the Data Consumer, the Data Consumer may request the
data (and the corresponding metadata) directly from the Data Provider.

Like a Data Provider, the Data Consumer may log the details of a
successful (or unsuccessful) data exchange transaction at a Clearing
House, use Data Apps to enrich, transform, etc. the data received, or
use a Service Provider to connect to the International Data Spaces (if
it does not deploy the technical infrastructure for participation
itself).

#### Data User

Similar to the Data Owner being the legal entity that has the legal
control over its data, the Data User is the legal entity that has the
legal right to use the data of a Data Owner as specified by the usage
policy. In most cases, the Data User is identical with the Data
Consumer. However, there may be scenarios in which these roles are
assumed by different participants. For example, a patient could use a
web-based software system to manage their personal health data and grant
access to this data to a health coach. The data could be received from a
hospital. In this case, the health coach would be the Data User and the
provider of the web-based software system would be the Data Consumer.

#### App Provider

App Providers develop Data Apps to be used in the International Data
Spaces. To be deployable, a Data App has to be compliant with the system
architecture of the International Data Spaces (see Section 3.5). In
addition, Data Apps can be certified by a Certification Body in order to
increase trust in these applications (especially with regard to Data
Apps processing sensitive information). Each Data App must be published
in the App Store for being accessed and used by Data Consumers and Data
Providers. App Providers should describe each Data App using metadata
(in compliance with a metadata model) with regard to its semantics,
functionality, interfaces, etc.).

#### Category 2: Intermediary

Intermediaries act as trusted entities. Roles assigned to this category
are Broker Service Provider, Clearing House, Identity Provider, App
Store Provider, and Vocabulary Provider. These roles may be assumed only
by trusted organizations.

Benefit for participants in the International Data Spaces is created by
these roles by establishing trust, providing metadata, and creating a
business model around their services.

#### Broker Service Provider

The Broker Service Provider is an intermediary that stores and manages
information about the data sources available in the International Data
Spaces. As the role of the Broker Service Provider is central but
non-exclusive, multiple Broker Service Providers may be around at the
same time (e.g., for different application domains). An organization
offering broker services in the International Data Spaces may assume
other intermediary roles at the same time (e.g., Clearing House or
Identity Provider, see below). Nevertheless, it is important to
distinguish organizations and roles (e.g., assuming the role of a Broker
Service Provider means that an organization deals only with metadata
management; at the same time, the same organization may assume the role
of a Clearing House, for which completely different tasks are defined).

The activities of the Broker Service Provider mainly focus on receiving
and providing metadata. The Broker Service Provider must provide an
interface for Data Providers to send their metadata. The metadata should
be stored in an internal repository for being queried by Data Consumers
in a structured manner. While the core of the metadata model must be
specified by the International Data Spaces (i.e., by the Information
Model, see Section 3.4), a Broker Service Provider may extend the
metadata model to manage additional metadata elements.

After the Broker Service Provider has provided the Data Consumer with
the metadata about a certain Data Provider, its job is done (i.e., it is
not involved in the subsequent data exchange process).

#### Clearing House

The Clearing House is an intermediary that provides clearing and
settlement services for all financial and data exchange transactions. In
the International Data Spaces, clearing activities are separated from
broker services, since these activities are technically different from
maintaining a metadata repository. As already stated above, it might
still be possible that the two roles Clearing House and
Broker Service Provider are assumed by the same organization, as
both roles require acting as a trusted intermediary between the Data
Provider and the Data Consumer.

The Clearing House logs all activities performed in the course of a data
exchange. After a data exchange, or parts of it, has been completed,
both the Data Provider and the Data Consumer confirm the data transfer
by logging the details of the transaction at the Clearing House. Based
on this logging information, the transaction can then be billed. The
logging information can also be used to resolve conflicts (e.g., to
clarify whether a data package has been received by the Data Consumer or
not). The Clearing House also provides reports on the performed (logged)
transactions for billing, conflict resolution, etc.

#### Identity Provider

The Identity Provider should offer a service to create, maintain,
manage, monitor, and validate identity information of and for
participants in the International Data Spaces*.* This is imperative for
secure operation of the International Data Spaces and to avoid
unauthorized access to data.

The Identity Provider consist of a Certification Authority (managing
digital certificates for the participants of the International Data
Spaces), a Dynamic Attribute Provisioning Service (DAPS, managing the
dynamic attributes of the participants), and a service named Dynamic
Trust Monitoring (DTM, for continuous monitoring of the security and
behavior of the network. More details about identity management can be
found in section 4.1.

#### App Store Provider

The App Store provides Data Apps. These are applications that can be
deployed inside the Connector, the core technical component required for
a participant to join the International Data Spaces. Data Apps
facilitate data processing workflows. They may be certified by a
Certification Body, following the certification procedures defined in
Section 4.2.

The App Store is responsible for managing information about Data Apps
offered by App Providers (see below). The App Store should provide
interfaces for publishing and retrieving Data Apps plus corresponding
metadata.

#### Vocabulary Provider

The Vocabulary Provider manages and offers vocabularies (i.e.,
ontologies, reference data models, or metadata elements) that can be
used to annotate and describe datasets. In particular, the Vocabulary
Provider provides the Information Model of the International Data
Spaces, which is the basis for the description of data sources (see
Section 3.4). In addition, other domain specific vocabularies can be
provided.

#### Category 3: Software / Service Provider

This category comprises IT companies providing software and/or services
(e.g., based on a software-as-a-service model) to the participants of
the International Data Spaces. Roles subsumed under this category are
Service Provider and Software Provider.

Benefit is created by these roles by providing software and services to
the participants of the International Data Spaces.

It should be noted that the process of providing software to be used for
establishing the endpoints of a data exchange transaction (e.g.
Enterprise Systems like ERP or MES, or other platforms) is not part of
the International Data Spaces, as it takes place before an organization
joins the IDS.

#### Service Provider

If a participant does not deploy the technical infrastructure required
for participation in the International Data Spaces itself, it may
transfer the data to be made available in the International Data Spaces
to a Service Provider hosting the required infrastructure for other
organizations.

This role includes also providers offering additional data services
(e.g., for data analysis, data integration, data cleansing, or semantic
enrichment) to improve the quality of the data exchanged in the
International Data Spaces. From a technical point of view, such a
Service Provider can be considered a Data Provider and a Data Consumer
at the same time (e.g., as a Data Consumer, it receives data from a Data
Provider, then provides its specific service, and then turns into a Data
Provider itself and offers the data in the International Data Spaces).

Unlike the services provided by a Service Provider, Data Apps can be
installed in the IT environment of a Data Consumer or Data Provider for
implementing additional data processing functionality. To use the
functionality of a Data App, the data therefore does not have to be
transferred to an external Service Provider.

#### Software Provider

A Software Provider provides software for implementing the functionality
required by the International Data Spaces (i.e., through software
components, as described in Section 3.5). Unlike Data Apps, software is
not provided by the App Store, but delivered over the Software
Providers' usual distribution channels, and used on the basis of
individual agreements between the Software Provider and the user (e.g.,
a Data Consumer, a Data Provider, or a Broker Service Provider). This
procedure implies that the agreements between Software Providers and
Data Consumers, Data Providers, etc. remain outside the scope of the
International Data Spaces.

#### Category 4: Governance Body

The Certification Body, Evaluation Facilities, and the International
Data Spaces Association are the Governance Bodies of the International
Data Spaces.

Benefit for participants in the International Data Spaces is created by
the Certification Body and the Evaluation Facilities by taking care of
the certification process and issuing certificates (both with regard to
organizations that want to participate and with regard to software
components that are to be used).

#### Certification Body and Evaluation Facilities

The Certification Body, together with selected Evaluation Facilities, is
in charge of the certification of the participants and the core
technical components in the International Data Spaces. These Governance
Bodies make sure that only compliant organizations are granted access to
the trusted business ecosystem. In this process, the Certification Body
supervises the actions and decisions of the Evaluation Facilities.

The Certification Scheme applied in the process is described in Section
4.2.

#### International Data Spaces Association (IDSA)

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
