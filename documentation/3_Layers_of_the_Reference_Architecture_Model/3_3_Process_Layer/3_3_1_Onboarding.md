## Onboarding

The overall 'Onboarding' process consists of several sub-processes. The first step for an organization to join the International Data Spaces as a Data Provider or Data Consumer is to acquire an identity to be used in the IDS.  <!-- old: This identity, which forms the basis for establishing trusted communication in the IDS, is provided by the Certification Body and an Evaluation Facility in the form of a certificate issued by an Identity Provider. -->
This identity, which forms the basis for establishing trusted communication in the IDS, is provided by an IDS Identity Provider in the form of a certificate issued by an accredited Certification Authority (CA).
In a second step, the organization needs to either request an IDS Connector from a Software or Service Provider, or create its own one. The IDS Connector, being the core technical component for becoming part of the IDS, must then set up. After that, it is provisioned with digital proof of its IDS identity, an X.509 certificate. The digital certificate is based on the organizational certification of the Participant and the technical certification of the IDS Connector (see section 3.1 and section 4.2). (**//TODO** insert link to the Business Layer and Certification Perspective) In a third step, the IDS Connector needs to be configured for internal use and prepared for secure communication ([Security Setup](#security-setup)). In the final step, the IDS Connector needs to be made available for other participants in the IDS.

The overall 'Onboarding' process is illustrated in the following figure.

![Onboarding process](../../media/image22.png)

The following paragraphs describe each step of the 'Onboarding' process in more detail.

### Acquire Identity

Any organization that wants to operate an IDS Connector in order to exchange data in the International Data Spaces as a Data provider, Data Consumer or provide an additional IDS component needs to acquire a unique identity in the form of a certificate issued by a accredited Certificate Authority (TODO: need to define participant identity further). This certificate enables to establish trusted connections to other IDS Participants (see section 3.1).

Please note that this IDS identity certificate is by default not the same as the one necessary to encrypt the communication channel itself, e.g. for using HTTPS. Even though both may use the same standards, the purposes are different and therefore different certificate files can be used. It might be best practice to distinguish them to reduce the risk of identity theft.

**//TODO** insert link to  Business Layer, add link to connector identity

<!-- // Any organization that wants to operate an IDS Connector in order to exchange data in the International Data Spaces as a Data provider or Data Consumer needs to acquire a unique identity in the form of a digital certificate. This certificate enables them to establish secure and trusted connections to other IDS participants (see section 3.1). -->


### Participant Information Service

The initial population of a Participant entry is conducted directly after the certification and identity creation process is finished. The Support Organization is informed about the successful steps and provided with the corresponding metadata about the new IDS entity. The provisioning of this information is not part of the IDS interactions and must be managed through communication measures. The Support Organization checks the correctness of the claims, verifies the information, and equips the dedicated ParIS with the new IDS Participant instance. It is further recommended that each Participant also hosts its Self-Description on a publicly accessible endpoint of its choice. Preferably the locator of its Self-Description document, an HTTP URL, is identical with the used Participant URI. This best practice enables the lookup or referencing of the Participant Identifier through every HTTP client and thereby eases the discovery of relevant information. Nevertheless, in case the own supplied Participant Self-Description and the metadata at the ParIS deviate, the latter is more trusted as its claims have been verified through the Support Organization beforehand. Requests to the ParIS itself follow the IDS Message Model and are described, among others, in the IDS-G and the IDS Information Model.

### Connector configuration and provisioning

Each IDS Connector that participates in an IDS ecosystem must provide a Self-Description for other IDS Participants to read. The respective organization needs to create this description at the beginning of the IDS Connector configuration and provisioning process. The IDS Connector Self-Description must contain information about the respective organization, about who maintains the IDS Connector, i.e. the Service Provider, and about the content and type of the data offered or requested. The IDS Information Model (**//TODO** insert link to the IM section) defines the mandatory and optional attributes of the Self-Description.

Another mandatory step for the organization is to orchestrate data flows for data retrieval and data provisioning, and to set up system adapters and communication interfaces, the IDS Connector 'endpoints'. (Details on the configuration of the IDS Connector are described in section 3.5.1.1). **//TODO** insert link to  System Layer/Connector Configuration Model

If needed, the organization can install and configure Data Apps acquired from an IDS App Store or register Self-Descriptions at IDS Metadata Brokers.

### Security setup

To enable secure communication, a Certification Authority issues a certificate to the new IDS Participant, which can be different from the issued identity certificate for identification of the IDS participant in combination with the Dynamic Attribute Token (IDS DAT). This certificate for secure communication is deployed to enable Transport Layer Security (TLS). On top of that for communication with other IDS Participants a Dynamic Attribute Token has to be requested from the Identity Provider (section 4.1). The token is a signed attestation that the security-critical information that the Connector states about itself has been verified. The token is presented by each outgoing communication message of the IDS Connector, so that also the communicating IDS Connectors have a means to verify the trustfulness of their communication partners. Important to understand is that the DAT only supports the claims that are actually contained in the token itself. Additional attributes or descriptions that are only part of the Self-Descriptions, for instance Contract Offers, licenses, or endpoint descriptions, are not verified by any IDS Identity Provider.

Furthermore, an organization that wants to assume the role of Data Provider or Data Consumer has the option to configure custom access restrictions for bilateral communications. For instance, a Data Provider may want to block certain IDS Participants from accessing their services, as they are competitors in their respective industry or any other reason, or it may require specific access credentials. These configurations may be set up in the last step of the Security Setup process (see section 4.1). **//TODO** insert link to  Business Layer

### Availability setup

After local IDS Connector deployment and Security Setup, an IDS Connector must be made available for other IDS Participants in the data ecosystem. Each Data Provider and Data Consumer can decide whether they want to announce their IDS Connector or the data resources publicly in the data ecosystem. If they do so, they can select an IDS Metadata Broker from a
set of available instances to publish the Self-Description of their IDS Connector. The IDS Metadata Broker provides functions for searching and retrieving registered IDS Connector Self-Descriptions (see section 3.5.2), including data sources, interfaces, security profiles, and current levels of trustworthiness.
