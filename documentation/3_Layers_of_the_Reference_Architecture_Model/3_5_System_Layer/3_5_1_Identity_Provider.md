# Identity Provider
To be able to make access control related decisions that are based on reliable identities and properties of Participants, a concept for Identity and Access Management (IAM) is mandatory. To access rosources in the IDS, aspects of identification (i.e., claiming an identity), authentication (i.e., verifying an identity), and authorization (i.e., making access decisions based on an identity) need to be defined.

Several services and components are involved in issuing identities, adding dynamic attributes and enabling trust in the IDS:

The **Certificate Authority (CA)**:

One or multiple CAs issue identity certificates for connector instances by signing Certificate Signing Requests (CSRs) that have been handed in by valid connector instances. They revokes certificates that become invalid and assures private keys are properly stored in hardware modules (such as a TPM or HSM) before signing CSRs (for higher trust levels).

The **Dynamic Attribute Provisioning Service (DAPS)** enriches connector identities by issuing identity claims to enrich IDS Connector identities. It embeds them into a **Dynamic Attribute Token (DAT)** which is handed out to requesting IDS Connector instances. The DAPS verifies the current status/validity of software manifests and descriptions. It delivers dynamic attributes such as device location and serves claims such as valid transport certificates. An identity may have several attributes that dynamically may change over time, which are linked to that identity. A Dynamic Attribute Provisioning Service (DAPS) is used to provide dynamic, up-to-date attribute information about Participants and Connectors.

Using a service to hand out attributes in a dynamic fashion reduces the need for certificate revocation and enables more flexible attribute handling for participants in the International Data Spaces. This allows dynamic assignment of attributes and status flags to Connector instances. Examples of status flags are:

* Withdraw a security status if known vulnerabilities have not been fixed.
* Upgrade the certification status without reissuing a X.509 certificate.
* Assigning membership status to a workflow with contractors.
* Tracking of temporary changes of a Participant’s level of trustworthiness.
* Tracking validity of software manifests.

This concept avoids revocation of certificates in most cases, as it allows to include new attributes if need arises. 

Some services do not provide means for trust establishment, but are purely serving informations that need to be verified in other ways:

The **Participant Information System (ParIS)** serves as an informative service to provide additional information about participants. It does not provide verified information that should be used to build trust upon.

The **Metadata Broker** serves information about IDS connector instances and provides services. It does not provide verified information that should be used to build trust upon and serves only information that is considered public.

Most services run on top of a Connector instance (Clearing House, ParIS, Metadata Broker). The DAPS is used as part of the bootstrapping of trust and thus must be considered as an external service (such as the PKI services). Clearing House and Metadate Broker share functionality with the Connector itself (self-description, identity, audit logging, Usage Control).

## Participant Information Service (ParIS)

The [ParIS](./3_5_1_2_ParIS.md) is a vital part of the Identity Provider. While the CA is responsible to issue and manage technical identity proofs and the DAPS provides time-dependent tokens, the ParIS provides business-related  information of IDS Participants in machine- and human-readable manners.

Further details about trust management can be found in ([Chapter 4.1.2.](/documentation/4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_2_Identity_and_Trust_Management.md)).
