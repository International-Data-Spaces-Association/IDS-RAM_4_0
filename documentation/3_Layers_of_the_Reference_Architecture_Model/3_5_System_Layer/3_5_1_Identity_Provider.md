# Identity Provider
To be able to make access control related decisions that are based on reliable identities and properties of Participants, a concept for Identity and Access Management (IAM) is mandatory. To access rosources in the IDS, aspects of identification (i.e., claiming an identity), authentication (i.e., verifying an identity), and authorization (i.e., making access decisions based on an identity) need to be defined.

Identity provisioning is rooted in a PKI infrastructure, detailed in ([Chapter 4.1.2.](./4_1_2_Identity_and_Trust_Management.md)). 

The **Certificate Authority (CA)** issues certificates for all entities. These certificates are used for authentication and encryption between Connectors.

To support dynamic identity claims, we define the **Dynamic Attribute Provisioning Service (DAPS)**. 

## Dynamic Attribute Provisioning Service (DAPS)
An identity may have several attributes, which are linked to that identity. A Dynamic Attribute Provisioning Service (DAPS) is used to provide dynamic, up-to-date attribute information about Participants and Connectors.

Using a service to hand out attributes in a dynamic fashion reduces the need for certificate revocation and enables more flexible attribute handling for participants in the International Data Spaces. This allows dynamic assignment of attributes and status flags to Connector instances. Examples of status flags are:

* Withdraw a security status if known vulnerabilities have not been fixed.
* Upgrade the certification status without reissuing a X.509 certificate.
* Assigning membership status to a workflow with contractors.
* Tracking of temporary changes of a Participant’s level of trustworthiness.
* Tracking validity of software manifests.

This concept avoids revocation of certificates in most cases, as it allows to include new attributes if need arises. Details of the concept and interaction patterns can be found in ([Chapter 4.1.2.](./4_1_2_Identity_and_Trust_Management.md)).

## Participant Information Service (ParIS)

The [ParIS](./3_5_1_2_ParIS.md) is a vital part of the Identity Provider. While the CA is responsible to issue and manage technical identity proofs and the DAPS provides time-dependent tokens, the ParIS provides business-related  information of IDS Participants in machine- and human-readable manners.
