### Certification Aspects Addressed by the Different Layers of the IDS-RAM ###

Certification is an essential mechanism in the IDS which supports the establishment of trust and, thus, an ecosystem which can be used for cross-company data exchange and processing. Therefore, it has relations to the different layers of the IDS RAM as explained below.

#### Business Layer ####

The Certification Body and Evaluation Facilities are in charge of the certification process. Their interactions and responsibilities in this process are described in [Section 4.2.2](./4_2_2_Roles.md) and [Section 4.2.5](./4_2_5_Processes.md). Both entities belong to the "Governance Body" category specified on the Business Layer (see [Section 3.1.1.](../../3_Layers_of_the_Reference_Architecture_Model/3_1_Business_Layer/3_1_1_Roles.md))
Organizations assuming a role under one of the three categories "Core Participant", "Intermediary", and "Software/Service Provider" (see [Section 3.1.1.](../../3_Layers_of_the_Reference_Architecture_Model/3_1_Business_Layer/3_1_1_Roles_in_the_IDS.md)) are potential targets of certification, i.e. may act as Applicant for the Certification. The [Certification Scheme](./CertificationScheme/README.md) describes for each role what level of certification is required and what the focus of the certification is.

#### Functional Layer ####

The functional requirements of the International Data Spaces defined in [Section 3.2](../../3_Layers_of_the_Reference_Architecture_Model/3_2_Functional_Layer/3_2_FunctionalLayer.md#functional-layer) are the core requirements expected to be implemented by the technical core components (e.g., the Connector or the Clearing House). Therefore, compatibility of each such implementation with these functional requirements forms the basis of the compliance part of a core component's certification. The security part of the certification focuses on security specific requirements. The security requirements are mainly related to the System Layer and the Security Perspective provided in [Section 4.1](../4_1_Security_Perspective/4_1_Security_Perspective.md#security-perspective).

#### Information Layer ####

Certification of a core component comprises also its compliance with the Reference Architecture Model regarding functionality, protocols, etc.
Whenever relevant, evaluation of a core component's compliance also refers to its compatibility with the Information Model defined in the Information Layer ([Section 3.3.](../../3_Layers_of_the_Reference_Architecture_Model/3_3_Information_Layer/3_3_InformationLayer.md#information-layer)).

#### Process Layer ####

The Process Layer ([Section 3.4.](../../3_Layers_of_the_Reference_Architecture_Model/3_4_Process_Layer/3_4_Process_Layer.md#process-layer)) defines relevant processes for onboarding and using components in the IDS. Where those processes are relevant for the compliance of a component or organization, they are also evaluated during certification with regards to the adherence with those processes.

#### System Layer ####

The System Layer ([Section 3.5.](../../3_Layers_of_the_Reference_Architecture_Model/3_5_System_Layer/3_5_0_System_Layer.md#system-layer)) defines the possible interactions between the components, detailed requirements for the Connector, and specific types of Connector implementations. The System Layer is the predominant layer regarding the security requirements with the Component Certification.
