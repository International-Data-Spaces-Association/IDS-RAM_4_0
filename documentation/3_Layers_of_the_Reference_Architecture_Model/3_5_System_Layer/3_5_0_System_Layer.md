# System Layer

On the System Layer, the roles specified on the Business Layer are mapped onto a concrete data and service architecture
in order to meet the requirements specified on the Functional Layer, resulting in what can be considered the technical core
of the International Data Spaces.

From the requirements identified on the Functional Layer, three major technical components result that require further specifications on the System Layer:
- the Connector,
- the App Store,
- the Metadata Broker,
- the Clearing House,
- the Vocabulary Hub, and
- the ParIS.

How these components interact with each other is depicted
in Figure 3.31.

The Connector, the Metadata Broker, and the App Store are supported
by four additional components (which are not specific to the
International Data Spaces, but specified for the International
Data Spaces):

- the Identity Provider as defined in the Security
Perspective,
- the Vocabulary Hub currently as defined outside the IDS,
- the Update Repository (i.e. the source for updates of deployed Connectors) depending on the connectors technology, and <!--//**TODO**: 'Update Repository' is new at this location (by Sebastian Bader) --> 
- the Trust Repository (i.e. the source for trustworthy software stacks and fingerprints as well as remote attestation checks) as discussed in the Security Perspective.

A distributed network like the International Data Spaces relies on the connection of different member nodes where Connectors or other core components are hosted (a Connector comprising one or more Data Endpoints). The Connector is responsible for the exchange of data or as a proxy in the exchange of data, as it executes the complete data exchange process (see Section 3.3.2) from and to the internal data resources and enterprise systems of the participating organizations and the International Data Spaces. It provides metadata to the Broker as specified in the connector self-description, e.g. technical interface description, authentication mechanism, exposed data sources, and associated data usage policies. It is important to note that the data is transferred between the Connectors of the Data Provider and the Data Consumer (peer-to-peer network concept).

There may be different types of implementations of the Connector, based on different technologies and depending on what specific functionality is required regarding the purpose of the Connector. Two fundamental variants are the Base Connector and the Trusted Connector (see Section 4.1) as they differ in the capabilities regarding security and data sovereignty.

Connectors can be further distinguished into External Connectors and Internal Connectors:
- An External Connector executes the exchange of data between participants of the International Data Spaces. The
International Data Spaces network is constituted by the total of its External Connectors. Each External Connector
provides data via the Data Endpoints it exposes. Applying this principle, there is no need for a central instance for
data storage. An External Connector is typically operated behind a firewall in a specially secured network segment
of a participant (so-called “Demilitarized Zone”, DMZ). From a DMZ, direct access to internal systems is not possible.
It should be possible to reach an External Connector using the standard Internet Protocol (IP), and to operate it
in any appropriate environment. A participant may operate multiple External Connectors (e.g., to meet load balancing
or data partitioning requirements). External Connectors can be operated on-premises or in a cloud environment.
- An Internal Connector is typically operated in an internal company network (i.e., a network which is not accessible
from outside). Implementations of Internal Connectors and External Connectors may be identical, as only the purpose
and configuration differ. The main task of an Internal Connector is to facilitate access to internal data sources in
order to provide data to External Connectors.
