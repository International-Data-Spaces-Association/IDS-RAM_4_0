### Securing Interaction between IDS Components ###

Data transfer in the IDS needs be secured by protecting the communication between IDS components, i.e. enabling identification, authentication, and authorization for components as well as providing confidentiality and integrity protection for the transferred data. This chapter explains the following aspects about establishing and using a secure communication channel between IDS components:

* Ensuring availability of [all required information](#preparation-of-required-information) on the component,
* [Establishing of a secure communication channel](#establishment-of-a-secure-communication-channel), and
* Using the communication channel for [data transfer](#data-transfer-using-this-communication-channel)
Additionally, we address the topic of [Dynamic Trust Monitoring](#dynamic-trust-monitoring) which may be used to continuously track the current status of IDS components.

#### Preparation of Required Information ####

In preparation for the establishment of a secure communication channel, an IDS component needs to be have a set of information available as shown in the image below.
![Overview Required Information](./media/information_for_communication_channel.png)

##### Figure 4.1.5.1: Overview Required Information

Most of the information is provisioned onto the component when it is initially taken into service and only updated occasionally when things change:

* A private key called **Identity Key** is used to identify the component ([Chapter 4.1.2.](./4_1_2_Identity_and_Trust_Management.md)). The key needs to be protected on the device and shall be only known to this specific component.
* The **Device Identity Certificate** maps the public key (corresponding to the private key) to a UID and the responsible company (operator) as described in [Chapter 4.1.2.](./4_1_2_Identity_and_Trust_Management.md).
* The **Company Description** contains metadata concerning the responsible company (as described in [Chapter 4.1.2.](./4_1_2_Identity_and_Trust_Management.md)), in particular its certification level from the Operational Environment Certification ([Chapter 4.2.3](../4_2_Certification_Perspective/4_2_3_Operational_Environment_Certification.md)).
* **Software Manifests** for all utilized software components contain metadata describing the deployed software (as described in [Chapter 4.1.2.](./4_1_2_Identity_and_Trust_Management.md)), in particular the expected measurements and information about the certification level based on the Component Certification ([Chapter 4.2.4.](../4_2_Certification_Perspective/4_2_4_Component_Certification.md)).
* The **CA Trust List** contains information about all Certificate Authorities (CAs) used in the IDS which issue identity certificates for devices and users as described in [Chapter 4.1.2.](./4_1_2_Identity_and_Trust_Management.md). It is used as a trust anchor for validating signatures based on the utilized certificate and certificate chain.

Additionally, the IDS component requires two artifacts for the establishment of a secure communication channel that need to be requested regularly during connector operation:

* The **Dynamic Attribute Token (DAT)** contains up-to-date revocation information about the utilized Company Descriptions and Software Manifests as well as dynamic attributes for the component. It is only valid for a short amount of time and the component regularly needs to request it from the Dynamic Attribute Provisioning Server (DAPS) to be able to prove current attributes and the up-to-dateness of the utilized software stack.
* The integrity of the software stack can only be proven (as requested for Trust Level 2 and 3) with **Measurements** collected during a measured boot as described in [Chapter 4.1.3](./4_1_3_Securing_the_Platform.md). Those measurements are stored in an integrity protected way and get provided upon request (with a Nonce for freshness) by the hardware trust anchor with a signature proving their correctness.

#### Establishment of a Secure Communication Channel ####

The establishment of a secure communication channel requires five essential steps which use the information described above. The image below shows the necessary information for the different validation steps separately to show the logic behind the validations. However, in an implementation of the protocol, necessary information may be transferred in a combined Attestation Report.

![Communication Channel Establishment](./media/communication_channel_establishment.png)
#####  Fig. 4.1.5.2: Establishing a Secure Communication Channel

1. **TLS Handshake**: The communication channel builds on an existing standard to achieve communication security: Transport Layer Security (TLS, currently in
[Version 3](https://datatracker.ietf.org/doc/html/rfc8446)). The TLS handshake protocol is used to set up an authenticated, confidential and integrity-protected communication channel based on the Identity Device Certificates (before transferring all other information using the TLS record protocol).
2. **Requesting Attestation**: Each component requests the information required for a remote attestation from its communication partner. The request includes a random nonce which can be used to prove freshness of the provided attestation information.
3. **Identity Validation**: Each component validates the identity of its communication partner based on the utilized identity certificate (mapping of key to UID and company) and the company description with the certification level from Operational Environment Certification ([Chapter 4.2.3](../4_2_Certification_Perspective/4_2_3_Operational_Environment_Certification.md)).
4. **Integrity Validation**: Current measurements of the utilized software stack in combination with metadata about the functionalities and certification level of the used software artifacts allow an assessment of IDS component and possible consequences of a data exchange. While the validation of actual measurements is only possible/required for component of Trust Level 2 or 3, the software manifests may also be transferred for components of Trust Level 1 to provide some transparency.
5. **Validation of Up-to-dateness and Dynamic Attributes**: The Dynamic Attribute Token issued from the DAPS allows revocation of issued certification (incl. information about newer software versions or found vulnerabilities) and supplements the long-living information in Company Description and Software Manifests with confirmed dynamic attributes as described in [Chapter 4.1.2.](./4_1_2_Identity_and_Trust_Management.md). The establishment of a communication channel requires the validation of this current information in order to fully assess the trustworthiness of the other component.

Based on these steps, each component has transparent information about their communication partner and can sovereignly decide about (the terms for) data sharing.

#### Data Transfer using this Communication Channel ####

After establishing the secure communication channel, it can be used to transfer arbitrary data with the desired protocols on the application layer.
As long as the communication remains bound to this communication channel, the transferred (attestation) information can be used to assess the consequences of the data transfer. It is in general possible to change from this channel to another way of communication for the further data exchange. In such a case, it is essential to ensure that the new communication channel is bound to the exact same communication partner as during this communication channel establishment. In case this is not the case, the involved parties should be aware that the security guarantees offered by the successful remote attestation may not hold for the new data communication or exchange channel.

#### Dynamic Trust Monitoring ####

The information provided during the establishment of a secure communication channel may be used by a Dynamic Trust Monitoring service which provides an overview of deployed components in the data space. The attestation report and DAT can provide status information about the utilized software (versions) and possible security issues. As an alternative or addition, the Dynamic Trust Monitoring may provide black box testing of components such as checking of used communication protocol versions or port scans.  For the collection of more in-depth information about the monitored components, it is possibly to deploy monitoring clients on the different connectors which continously provide the Dynamic Trust Monitoring with relevant status information.
