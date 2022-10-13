### Identity Provider ###

To be able to make access control related decisions that are based on reliable identities and properties of Participants, a concept for Identity and Access Management (IAM) is mandatory. To access ressources in the IDS, aspects of identification (i.e., claiming an identity), authentication (i.e., verifying an identity), and authorization (i.e., making access decisions based on an identity) need to be defined.
The Identity Provider in the IDS consists of three complementary components: Certificate Authorities (CAs) are responsible for issue and manage technical identity claims, the Dynamic Attribute Provisioning Service (DAPS) provides short-lived tokens with up-to-date information about connectors, and the Participant Information Service (ParIS) provides business-related information of IDS Participants in machine- and human-readable manners. Further details about trust management can be found in ([Chapter 4.1.2.](/documentation/4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_2_Identity_and_Trust_Management.md)).

#### Certificate Authorities (CAs) ####

One or multiple CAs issue identity certificates for connector instances by signing Certificate Signing Requests (CSRs) that have been handed in by valid connector instances. They revoke certificates that become invalid and, for higher trust levels, assure that private keys are properly stored in hardware modules (such as a TPM or HSM). They are essential trust building entities responsible for ensuring that only registered organizations may operate components in the IDS.

#### Dynamic Attribute Provisioning Service (DAPS) ####

A DAPS enriches connector identities by issuing up-to-date information in form of signed claims. It embeds them into **Dynamic Attribute Tokens (DATs)** which are handed out to requesting IDS Connector instances. The DAPS verifies the current status/validity of Software Manifests and Company Descriptions which contain metadata regarding passed IDS certifications (see [4.1.2](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_2_Identity_and_Trust_Management.md#describing-metadata). Simultaneously it delivers dynamic attributes, such as device location or currently supported transport certificates, which may dynamically change over time and are linked to the connector identity based on the DAT. Thus, a Dynamic Attribute Provisioning Service (DAPS) is used to provide dynamic, up-to-date attribute information about Participants and Connectors.

Using a service to hand out attributes in a dynamic fashion reduces the need for certificate revocation and enables more flexible attribute handling for participants in the International Data Spaces. This allows dynamic assignment of attributes and status flags to Connector instances. Exemplary use cases are:

* Tracking of temporary changes of a Participant’s level of trustworthiness.
* Assigning membership status to a workflow with contractors.
* Information about known vulnerabilities in utilized software stacks.
* Information about available newer versions of software components.
* Revocation of issued certification for components or operational environments.

This concept avoids revocation of Connector identity certificates in most cases, as it allows to include or change attributes if need arises.
The DAPS is used as part of the bootstrapping of trust and is not a connector itself but an external service (such as the PKI services).

#### Participant Information Service (ParIS) ####

The ParIS is a vital part of the Identity Provider. It provides business-related information about participants in the IDS that have been checked by the Support Organization.

From a System Layer view, the internal architecture components and endpoints of a ParIS are very similar to the ones of an IDS Metadata Broker. Both need to receive, persist, and make IDS Self-Descriptions available for other IDS Connectors to query them. The main difference is the type of Self-Description they manage - Connectors and Resources by the Metadata Brokers and Participants by the ParIS.

##### Components #####

A ParIS typically consists of the following functional building blocks, which can be implemented using different technology stacks and hosting solutions:

* _Server_ to host the IDS Endpoints.
* _Database_ to persist the RDF Self-Descriptions of the registered IDS Participants.
* _IAM_ for checking the identity claims of clients and to validate their authorization using the IDS DAT. Can be located at the surrounding Identity Provider.
* _Index_ (optional) to increase the speed for read requests.
* _Website_ (optional) for human interactions with the ParIS.

##### Endpoints #####

The interactions with a ParIS can be distinguished into two main categories. The first one is related to the initial provisioning of Participant information during their onboarding in an IDS as well as the according updates through the operators of the general Identity Provider. As this workflow is completely component-internal, proprietary or custom patterns might be used. The necessity for this internal endpoint is due to the required higher trust in the Participant metadata. For instance, an incorrect VAT-ID or jurisdiction has direct and concrete legal consequences, therefore a certain validation workflow at the Identity Provider operator must be enabled.

In addition, an IDS compliant endpoint must be exposed for the communications with IDS Connectors. While this endpoint could also - given proper authentication and authorization procedures - serve for the purpose described above, its main concern is the provisioning of querying capabilities and to allow individual Participants to adjust their own Self-Description.

##### Search and Querying #####

Each ParIS instance must provide IDS compliant functions to dereference Participant identifiers. A dereferencation function accepts the Participant identifier, an IRI according to the IDS Information Model, and returns the related Self-Description document. In addition, a ParIS may provide further search capabilities, like full-text search, attribute-based or facet search, or even expose expressive query language like SPARQL. In any case, the respective capabilities must be outlined in the Self-Description of the ParIS itself, to make them discoverable for IDS Connectors.

##### Life Cycle of Participant's Self-Description #####

Similar to Connector and Resource Self-Descriptions, also Participant Self-Descriptions (SD) pass different lifecycle stages. The initial version is provided by the Participant itself, either directly as an IDS Information Model instance or as a filled form during the onboarding process. This SD is then, after the IDS identity of the new Participant has been created, populated at the according ParIS.

In case mistakes in this SD are noticed or attributes of the Participant change, both the operator of the Identity Provider as well as the Participant itself have the technical means to adjust the Self-Description. Note that the operator of the Identity Provider could also prohibit direct updates due to otherwise skipped validation workflows.

In case a Participant temporarily or completely leaves an IDS, the according Self-Description can also be made unavailable. An unavailable SD is not exposed to the regular search and query functionalities anymore. Nevertheless, the ParIS should still keep the SD or at least its identifier, to enable potential later reactivations and especially prevent identity hijacking attempts. In such an attack, a newly onboarded Participant could try to use an identifier of another Participant that has left the IDS already, and thereby claim the access and usage permissions of the latter.

##### Data Synchronization between ParIS instances #####

The core attributes of an IDS Participant, e.g., its identifier, need to be maintained comprehensively between different components. Apart from that, no further synchronization between different ParIS instances are enforced.
