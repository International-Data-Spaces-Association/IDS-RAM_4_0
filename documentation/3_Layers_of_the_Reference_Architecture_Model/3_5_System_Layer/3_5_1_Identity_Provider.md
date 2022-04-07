# Identity Provider
To be able to make access control related decisions that are based on reliable identities and properties of Participants, a concept for Identity and Access Management (IAM) is mandatory. To access ressources in the IDS, aspects of identification (i.e., claiming an identity), authentication (i.e., verifying an identity), and authorization (i.e., making access decisions based on an identity) need to be defined.
The Identity Provider in the IDS consists of three complementary components: Certificate Authorities (CAs) are responsible for issue and manage technical identity claims, the Dynamic Attribute Provisioning Service (DAPS) provides short-lived tokens with up-to-date information about connectors, and the Participant Information Service (ParIS) provides business-related information of IDS Participants in machine- and human-readable manners. Further details about trust management can be found in ([Chapter 4.1.2.](/documentation/4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_2_Identity_and_Trust_Management.md)).

## Certificate Authorities (CAs)

One or multiple CAs issue identity certificates for connector instances by signing Certificate Signing Requests (CSRs) that have been handed in by valid connector instances. They revoke certificates that become invalid and, for higher trust levels, assure that private keys are properly stored in hardware modules (such as a TPM or HSM). They are essential trust building entities responsible for ensuring that only registered organizations may operate components in the IDS.

## Dynamic Attribute Provisioning Service (DAPS)
A DAPS enriches connector identities by issuing up-to-date information in form of signed claims. It embeds them into **Dynamic Attribute Tokens (DATs)** which are handed out to requesting IDS Connector instances. The DAPS verifies the current status/validity of Software Manifests and Company Descriptions which contain metadata regarding passed IDS certifications (see [4.1.2](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_2_Identity_and_Trust_Management.md#describing-metadata). Simultaneously it delivers dynamic attributes, such as device location or currently supported transport certificates, which may dynamically change over time and are linked to the connector identity based on the DAT. Thus, a Dynamic Attribute Provisioning Service (DAPS) is used to provide dynamic, up-to-date attribute information about Participants and Connectors.

Using a service to hand out attributes in a dynamic fashion reduces the need for certificate revocation and enables more flexible attribute handling for participants in the International Data Spaces. This allows dynamic assignment of attributes and status flags to Connector instances. Exemplary use cases are:

* Tracking of temporary changes of a Participant’s level of trustworthiness.
* Assigning membership status to a workflow with contractors.
* Information about known vulnerabilities in utilized software stacks.
* Information about available newer versions of software components.
* Revocation of issued certification for components or operational environments.

This concept avoids revocation of Connector identity certificates in most cases, as it allows to include or change attributes if need arises. 
The DAPS is used as part of the bootstrapping of trust and is not a connector itself but an external service (such as the PKI services). 

## Participant Information Service (ParIS)

The ParIS is a vital part of the Identity Provider. It provides business-related information about participants in the IDS that have been checked by the Support Organization.
