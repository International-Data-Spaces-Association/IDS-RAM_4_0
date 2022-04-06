# Identity Provider
To be able to make access control related decisions that are based on reliable identities and properties of Participants, a concept for Identity and Access Management (IAM) is mandatory. To access ressources in the IDS, aspects of identification (i.e., claiming an identity), authentication (i.e., verifying an identity), and authorization (i.e., making access decisions based on an identity) need to be defined.

Several services and components are involved in issuing identities, adding dynamic attributes and enabling trust in the IDS:

One or multiple **Certificate Authorities (CAs)** issue identity certificates for connector instances by signing Certificate Signing Requests (CSRs) that have been handed in by valid connector instances. They revoke certificates that become invalid and, for higher trust levels, assure that private keys are properly stored in hardware modules (such as a TPM or HSM).

A **Dynamic Attribute Provisioning Service (DAPS)** enriches connector identities by issuing up-to-date information in form of signed claims. It embeds them into **Dynamic Attribute Tokens (DATs)** which are handed out to requesting IDS Connector instances. The DAPS verifies the current status/validity of Software Manifests and Company Descriptions which contain metadata regarding passed IDS certifications (see [4.1.2](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_2_Identity_and_Trust_Management.md#describing-metadata). Simultaneously it delivers dynamic attributes, such as device location or currently supported transport certificates, which may dynamically change over time and are linked to the connector identity based on the DAT. Thus, a Dynamic Attribute Provisioning Service (DAPS) is used to provide dynamic, up-to-date attribute information about Participants and Connectors.

Using a service to hand out attributes in a dynamic fashion reduces the need for certificate revocation and enables more flexible attribute handling for participants in the International Data Spaces. This allows dynamic assignment of attributes and status flags to Connector instances. Exemplary use cases are:

* Tracking of temporary changes of a Participant’s level of trustworthiness.
* Assigning membership status to a workflow with contractors.
* Information about known vulnerabilities in utilized software stacks.
* Information about available newer versions of software components.
* Revocation of issued certification for components or operational environments.

This concept avoids revocation of Connector identity certificates in most cases, as it allows to include or change attributes if need arises. 

Additional, there are some services offering information which do not provide means for trust establishment, resulting in the need to verify information in other ways if necessary:

The **Participant Information System (ParIS)** serves as an informative service to provide additional information about participants. It does not provide verified information that should be used to build trust upon.

The **Metadata Broker** serves information about IDS connector instances and provides services for finding possible communication/business partners. It does not provide verified information that should be used to build trust upon and serves only information that is considered public.

Most services run on top of a Connector instance (Clearing House, ParIS, Metadata Broker). The DAPS is used as part of the bootstrapping of trust and, thus, must be considered as an external service (such as the PKI services). Clearing House and Metadata Broker share functionality with the Connector itself (self-description, identity, audit logging, Usage Control).

## Participant Information Service (ParIS)

The [ParIS](./3_5_1_2_ParIS.md) is a vital part of the Identity Provider. While the CA is responsible to issue and manage technical identity proofs and the DAPS provides time-dependent tokens, the ParIS provides business-related  information of IDS Participants in machine- and human-readable manners.

Further details about trust management can be found in ([Chapter 4.1.2.](/documentation/4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_2_Identity_and_Trust_Management.md)).
