# Certification Aspects Addressed by the Different Layers of the IDS-RAM

Certification is an essential mechanism in the IDS which supports the establishment of trust and, thus, an ecosystem which can be used for cross-company data exchange and processing. Therefore, it has relations to the different layers of the IDS RAM as explained below.

## Business Layer

The Certification Body and Evaluation Facilities are in charge of the certification process. Their interactions and responsibilities in this process are described in [Chapter 4.2.2](./4_2_2_Roles.md) and [Chapter 4.2.5](./4_2_5_Processes.md). Both entities belong to the "Governance Body" category specified on the Business Layer (see [Chapter 3.1.1.](../../3_1_1_Roles.md))
Organizations assuming a role under one of the three categories Core Participant, Intermediary, and Software/Service Provider (see [Chapter 3.1.1.](../../3_1_1_Roles.md)) are potential targets of certification, i.e. may act as Applicant for the Certification. The [Certification Scheme](./CertificationScheme) describes for each role what level of certification is required and what the focus of the certification is.

## Functional Layer

The functional requirements of the International Data Spaces are the core requirements expected to be implemented by the technical core components (e.g., the Connector or the Clearing House). Therefore, compatibility of each such implementation with these functional requirements forms the basis of the compliance part of a core component's certification. The security part of the certification focuses on security specific requirements. As for the Security Perspective (see Section 4.1), these security specific requirements are mainly related to the System Layer.

## Process Layer

Whenever relevant for the compliance part of a component's certification, a component is also evaluated in terms of whether it fully supports all processes it is involved in, as defined by the Reference Architecture Model.

## Information Layer

Certification of a core component comprises also its compliance with the Reference Architecture Model regarding functionality, protocols, etc.
Whenever relevant, evaluation of a core component's compliance also refers to its compatibility with the Information Model defined at the Information Layer.

## System Layer

The System Layer defines the possible interactions between the components, detailed requirements for the Connector, and specific types of Connector implementations. The System Layer is the predominant layer regarding the security part of a component's certification.
