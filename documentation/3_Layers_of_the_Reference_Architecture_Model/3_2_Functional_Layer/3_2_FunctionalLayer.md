## Functional Layer

The Functional Layer defines -- irrespective of existing technologies
and applications -- the functional requirements of the International
Data Spaces, and the features to be implemented resulting thereof.


![ Functional architecture of the International Data
Spaces](./media/image21.png)

The figure above
shows the functional architecture of the International Data Spaces,
subdividing the requirements into six groups of software functionality
to be provided by the IDS. These six groups comply with the strategic
requirements outlined in Section
[Goals of the International Data Spaces](../../1_Introduction1_1_Goals_of_the_International_Data_Spaces.md).

The following subsections give a brief summary of these functional
requirements.

### Trust 

Although requirements related to trust are usually non-functional, they
are addressed by the Functional Layer, since they represent fundamental
features of the International Data Spaces. The Trust group
comprises three main aspects (roles, identity management, and user
certification), which are complemented by governance aspects (see
Section on [Data Governance](../../4_Perspectives_of_the_Reference_Architecture_Model/4_3_Governance_Perspective/4_3_1_Layers.md).

#### Roles

Each role in the International Data Spaces has certain rights and
duties. For example, the Identity Provider is responsible for offering
services to create, maintain, manage, monitor, and validate identity
information of and for participants in the International Data Spaces.
More information about the roles is given in the [Business Layer](#).

#### Identity Management

Every Connector participating in the International Data Spaces must have
a unique identifier and a valid certificate. In addition, each Connector
must be able to verify the identity of other Connectors (with special
conditions being applied here; e.g., security profiles).

#### User Certification

Each participant in the International Data Spaces must undergo
certification in order to establish trust among all participants. More
information about the certification process is given in the [Certification Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/4_2_Certification_Perspective.md).

### Security and Data Sovereignty

Like requirements related to trust, requirements related to security and
data sovereignty are also usually non-functional, but are still
addressed by the Functional Layer, since they represent fundamental
features of the International Data Spaces. The Security and data
sovereignty group contains four major aspects: authentication
authorization; usage policies  usage enforcement; trustworthy
communication  security by design; and technical certification.

#### Authentication & Authorization

Each Connector must have a valid X.509 certificate (or equivalent). With the help of
this certificate, each participant in the International Data Spaces that
operates an endpoint is able to verify the identity of any other
participant. Certain conditions (e.g. security profiles) may also apply
here. More information about authentication is given in the[Security Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_Security_Perspective.md).

The Connector serving as the data source must be able to verify the
receiving Connector's capabilities and security features as well as its
identity. More information about authorization is given in the [Security Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_Security_Perspective.md).

#### Usage Policies & Usage Enforcement

In the IDS, Data Owners and Data Providers can always be sure their data
is handled by a Data Consumer according to the usage policies specified.
Each participant can define usage policies and attach them to outbound
data. Policies might include restrictions, such as disallowing
persistence of data, or disallowing transfer of data to other parties,
for example. More information about usage policies and usage enforcement
is given in the [Security Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_Security_Perspective.md).

#### Trustworthy Communication & Security by Design

Connectors, App Stores, and Brokers can check if the Connector of the
connecting party is running a trusted (i.e. certified) software stack.
Any communication between (external) Connectors can be encrypted and
integrity protected. Each Data Owner and Data Provider must be able to
ensure that their data is handled by the Connector of the Data Consumer
according to the usage policies specified: otherwise the data will not
be sent. To reduce the impact of compromised applications, appropriate
technical measures must be applied (e.g. isolating Data Apps from each
other and from the Connector). Data Providers and Data Consumers can
decide about the level of security to be applied for their respective
Connectors by deploying Connectors supporting the selected security
profile. More information about trustworthy communication and security
by design is given in  the [Security Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_Security_Perspective.md).

#### Technical Certification

The core components of the International Data Spaces, and especially the
Connectors, require certification from the Certification Body in order
to establish trust among all participants. More information about
technical certification is given in the [Certification Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/4_2_Certification_Perspective.md).

### Ecosystem of Data

Being able to describe, find and correctly interpret data is another key
aspect of the International Data Spaces. Therefore, every data source in
the International Data Spaces is described on the Information Layer (see
section 3.4).

The Ecosystem of Data group comprises three major aspects: data
source description, brokering, and vocabularies.

#### Data Source Description

Participants must have the opportunity to describe, publish, maintain
and manage different versions of metadata. Metadata should describe the
syntax and serialization as well as the semantics of data sources.
Furthermore, metadata should describe the application domain of the data
source. The operator of a Connector must be able to define the price,
the pricing model, and the usage policies regarding certain data. More
information about data source description is given in the
[Information Layer](#).

#### Brokering

The operator of a Connector must be able to provide an interface for
data and metadata access. Each Connector must be able to transmit
metadata of its data sources to one or more brokers. Each participant
must be able to browse and search metadata in the metadata repository,
provided the participant has the right to access the metadata.
Furthermore, each participant must be able to browse the list of
participants registered at a broker. More information about brokering is
given in the [Process Layer](#).

#### Vocabularies

To create and structure metadata, the operator of a Connector may use
vocabularies. In doing so, an operator of a Connector can use existing
vocabularies, create own vocabularies, or work with other operators on
new vocabularies provided by vocabulary hubs. Vocabulary hubs are
central servers that store vocabularies and enable collaboration.
Collaboration may comprise search, selection, matching, updating,
requests for changes, version management, deletion, duplicate
identification, and unused vocabularies. Vocabulary hubs need to be
managed. More information about vocabularies is given in the
[Information Layer](#).

### Standardized Interoperability

Standardized data exchange between participants is the fundamental
aspect of the International Data Spaces. The IDS Connector is the main
technical component for this purpose.

#### Operation

Participants should be able to run the Connector software in their own
IT environment. Alternatively, they can run a Connector on mobile or
embedded devices. The operator of the Connector must be able to define
the data workflow inside the Connector. Users of the Connector must be
identifiable and manageable. Passwords and key storage must be
protected. Every action, data access, data transmission, incident, etc.
should be logged. Using this logging data, it should be possible to draw
up statistical evaluations on data usage etc. Notifications about
incidents should be sent automatically.

#### Data Exchange

The Connector must receive data from an enterprise backend system,
either through a push-mechanism or a pull-mechanism. The data can be
provided via an interface or pushed directly to other participants. To
do so, each Connector must be uniquely identifiable. Other Connectors
can subscribe to data sources or pull data from these sources. Data can
be written into the backend system of other participants.

### Value Adding Apps

Before or after the actual data exchange, data may need to be processed
or transformed. For this purpose, the International Data Spaces offers
Data Apps. Each Data App has a lifecycle, spanning its implementation,
provision in the App Store, installation, and support. The App Store
should therefore be clearly visible and recognizable to every
participant.

#### Data Processing and Transformation

A data processing app (which is a subtype of a Data App) should provide
a single, clearly defined processing function to be applied on input
data for producing an expected output. A data transformation app (also a
subtype of a Data App) should be able to transform data from an input
format into a different output format in order to comply with the
requirements of the Data Consumer (without any substantial change made
to the information contained in the data; i.e., loss-less
transformation).

#### Data App Implementation

The developers of Data Apps should be able to annotate the software with
metadata (about functions and interfaces, pricing models, licenses,
etc.). Data Apps must explicitly define their interfaces, dependencies,
and access requirements.

#### Providing Data Apps

Any authorized Data App developer can initiate a software provision
process (App Store publication). Prior to publication in the App Store,
Data Apps must pass an optional evaluation and certification process
controlled by the Certification Body. The App Store should support
authorized users in their search for a suitable application in an
adequate fashion. Access of privileged users (e.g., administrators or
operators) should require strong authentication (e.g., 2-factor
authentication).

#### Installing and Supporting Data Apps

A dedicated Connector service should support authorized users in
(un-)installing Data Apps not originating from an official App Store. In
addition, it should support authorized users in searching, installing,
and managing (e.g., removal or automated updates) Data Apps retrieved
from an App Store.

### Data Markets

Data to be exchanged in the International Data Spaces may have monetary
value. Therefore, the International Data Spaces has to integrate data
market concepts, like clearing and billing, but also governance.

#### Clearing & Billing

The Data Owner can define the pricing model (e.g. pay per transfer, pay
per access, pay per day/month/year), and the price of data. Any
transaction of any participant can be logged. The clearing and billing
process must be simple and standardized.

#### Usage restrictions, and governance

Governance in the International Data Spaces comprises five aspects: data
as an economic good, data ownership, data sovereignty, data quality, and
data provenance. More information about governance is given in [Governance Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_3_Governance_Perspective/4_3_1_Layers.md).

#### Legal aspects

Trading data on a data marketplace requires legal contracts and
conditions that can be negotiated in an automated way. Therefore,
standard contracts for typical data exchange transactions are necessary.
