## Onboarding of an IDS Connector and its Operator

The overall 'Onboarding' process requires of two preparational steps required for an organization to act as Data Provider or Data Consumer in the International Data Spaces:
1. Registration and certification of the organization.
2. Acquiring a certified IDS connector.

Based on those prerequisites, an organization can instantiate an arbitrary number of IDS connector instances with the following steps:
1. Provisioning and configuring the connector.
2. Availability setup.

All necessary steps are illustrated in the following figure.

![Onboarding process](./media/onboarding_process.png)
#### _Fig. 3.3.1.1: Onboarding process_

### Preparation: Registration and Certification of the Organization

Any organization that wants to operate an IDS Connector (in order to exchange data in the International Data Spaces) as a Data provider, Data Consumer or provide an additional IDS component needs to pass the Operational Environment Certification (see [Section 4.2.3](../../4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/4_2_3_Operational_Environment_Certification.md)). The Identity Provider is informed that this organization is allowed to operate components in the IDS and request component identity certificates. Additionally, the organization is registered in the Participant Information Service (ParIS). The initial population of a Participant entry is conducted directly after the certification. The Support Organization is informed about the successful steps and provided with the corresponding metadata about the new IDS entity. The provisioning of this information is not part of the IDS interactions and must be managed through communication measures. The Support Organization checks the correctness of the claims, verifies the information, and equips the dedicated ParIS with the new IDS Participant instance. It is further recommended that each Participant also hosts its Self-Description on a publicly accessible endpoint of its choice. Preferably the locator of its Self-Description document, an HTTP URL, is identical with the used Participant URI. This best practice enables the lookup or referencing of the Participant Identifier through every HTTP client and thereby eases the discovery of relevant information. Nevertheless, in case the own supplied Participant Self-Description and the metadata at the ParIS deviate, the latter is more trusted as its claims have been verified through the Support Organization beforehand. Requests to the ParIS itself follow the IDS Message Model and are described, among others, in the IDS-G and the IDS Information Model.

### Preparation: Acquiring a Certified IDS Connector
The organization needs to either request an IDS Connector from a Software Provider, or implement its own one. The IDS Connector is the core technical component for becoming part of the IDS. It must pass the IDS Component Certification (see [Section 4.2.4](../../4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/4_2_4_Component_Certification)) to ensure an adequate level of security and interoperability before it can be instantiated and used in the IDS.

### Connector Configuration and Provisioning
Each IDS Connector that participates in an IDS ecosystem must have a unique identity in the IDS which is issued or confirmed by the IDS Identity Provider.
The required trust anchors for the Identity Provider (e.g. root certificate for CA) must be provisioned onto the connector to enable verification of identity information provided by communication partners.

Additionally, each connector shall provide a Self-Description for other IDS Participants to read. The respective organization needs to create this description at the beginning of the IDS Connector configuration and provisioning process. The IDS Connector Self-Description must contain information about the respective organization, about who maintains the IDS Connector, i.e. the Service Provider, and about the content and type of the data offered or requested. The IDS Information Model defines the mandatory and optional attributes of the Self-Description.
It also requires proof of the certification levels for the organization and the technical component provided in form of signed metadata.

Another mandatory step for the organization is to orchestrate data flows for data retrieval and data provisioning, and to set up system adapters and communication interfaces, the IDS Connector 'endpoints'. Details on the configuration of the IDS Connector are described later on.
Furthermore, a Data Provider or Data Consumer has the option to configure custom access restrictions for bilateral communications. For instance, a Data Provider may want to block certain IDS Participants from accessing their services, as they are competitors in their respective industry or any other reason, or it may require specific access credentials.

If needed, the organization can install and configure Data Apps acquired from an IDS App Store.

###  Availability Setup

An IDS Connector must be made available for other IDS Participants in the data ecosystem. Each Data Provider and Data Consumer can decide whether they want to announce their IDS Connector or the data resources publicly in the data ecosystem. If they do so, they can e.g. select an IDS Metadata Broker from a set of available instances to publish the Self-Description of their IDS Connector. The IDS Metadata Broker provides functions for searching and retrieving registered IDS Connector Self-Descriptions, including data sources, interfaces, security profiles, and current levels of trustworthiness.
