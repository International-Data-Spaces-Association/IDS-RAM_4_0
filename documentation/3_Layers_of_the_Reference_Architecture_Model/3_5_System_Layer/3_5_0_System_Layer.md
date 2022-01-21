# System Layer

On the System Layer, the roles specified on the Business Layer and the processes defined in the Process Layer are mapped onto a concrete data and service architecture, resulting in what can be considered the technical core of the International Data Spaces.

The IDS consists of the following core components:
- the Identity Provider (consisting of DAPS and ParIS),
- the IDS Connector,
- the App Store,
- the Metadata Broker,
- the Clearing House, and
- the Vocabulary Hub.

How these components interact with each other is depicted
in Figure 3.31.


A distributed network like the International Data Spaces relies on the connection of different member nodes where IDS Connectors or other core components are hosted (an IDS Connector comprising one or more Data Endpoints). The IDS Connector is responsible for the exchange of data or as a proxy in the exchange of data, as it executes the complete data exchange process (see Section 3.3.2) from and to the internal data resources and enterprise systems of the participating organizations and the International Data Spaces. It provides metadata to the Metadata Broker as specified in the IDS connector self-description, e.g. technical interface description, authentication mechanism, exposed data sources, and associated data usage policies. It is important to note that the data is transferred between the IDS Connectors of the Data Provider and the Data Consumer (peer-to-peer network concept).

IDS Connectors  executes the exchange of data between participants of the International Data Spaces. The International Data Spaces network is constituted by the total of its  IDS Connectors. Each IDS Connector provides data via the Data Endpoints it exposes. Applying this principle, there is no need for a central instance for data storage. An IDS Connector is typically operated behind a firewall in a specially secured network segment of a participant (so-called “Demilitarized Zone”, DMZ). It should be possible to reach an IDS Connector using the standard Internet Protocol (IP), and to operate it in any appropriate environment. A participant may operate multiple IDS Connectors (e.g., to meet load balancing or data partitioning requirements). IDS Connectors can be operated on-premises or in a cloud environment. 

There may be different types of implementations of the IDS Connector, based on different technologies and depending on what specific functionality is required regarding the purpose of the Connector. Officially, we distinguish IDS connectors according to their certification level defined in [section 4.2](../../4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/), which indicates, among other things, which security and data sovereignty criteria the connector implements.
