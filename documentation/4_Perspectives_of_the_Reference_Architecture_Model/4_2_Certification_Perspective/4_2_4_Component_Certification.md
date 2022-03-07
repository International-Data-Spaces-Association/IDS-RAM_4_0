# Component Certification

In order to secure the intended cross-company information exchange, the 
core components to be used in the IDS must provide the required
functionality and level of security. As such, the certification of core
components focuses on interoperability and security, while aiming to
strengthen the development and maintenance process of these components.

To build this trust in a structured way, the International Data Spaces
has established a well-defined process for core component certification.
An in-depth description of the certification process, and how it applies
to the key elements of the IDS architecture, can be found in Part 3 of
the White Paper Certification[^5]. Access to the core component certification
criteria catalogues for Connectors and Brokers, respectively, can be requested from the IDSA for free[^6].

Within the next two subchapters, three different levels of assurance and trust for the certification of components are defined.
This matrix approach allows the component developer to select both the assurance and trust level for the certification of their component, that best correspond with the use cases, that their specific component was developed for. On the one hand, this ensures a low entry barrier specifically suitable for SMEs. On the other
hand, a scalable certification to meet high information security requirements becomes possible.

## Component Assurance Levels:
The depth and rigor of a component evaluation consists of the following three assurance levels, 
independent on the type of component that is being certified (e.g. Connector, Broker, etc.):
* Assurance Level 1: Checklist self-assessment and automated interoperability testing
	* This level is therefore targeted at developers looking for a low entrance barrier into the IDS. 
	* The effort and costs in this level are very low for the applicant due to the self-assessment approach. 
	* The interoperability is verified via statements made by the developer in a checklist and an automated test suite without any involvement of an external evaluation facility.
* Assurance Level 2: External concept review including functional and security testing
	* Starting in level 2, external evaluation facilities are tasked with the evaluation, to ensure an independent evaluation result.
	* Level 2 is the right balance between an independent review and the corresponding costs. 
	* The external concept review includes the examination of documentation as well as the testing the Connector, to ensure the correct implementation of the functional and security requirements. 
* Assurance Level 3: External evaluation including concept review, testing and source code audit
	* For use cases that require a high evaluation guarantee, such as the exchange of very sensitive data, higher efforts and costs will be required to ensure the customers needs in regard to security assurances are met.
	* As such, level 3 includes an in-depth source code review as well as a review of the development process (including an audit of the development site) in addition to the evaluation performed for level 2.

## Connector Trust Levels
The criteria that make up each of the three trust levels for a Connector are defined in such a way that they are specific enough to ensure interoperability with the functional requirements of an IDS Connector, yet general enough, to allow the use of a Connector in different deployment scenarios without having to define different critera catalogues for each separate use case.

The following three trust levels are defined for the certification of a Connector:
* Trust Level 1: Data space interoperability
	* basic level security profile to participate in a data space
    * minimal agreed cybersecurity requirements to ensure the trustworthiness of the ecosystem as a whole 
	* verified interoperability with IDS-components and compliance to the basic rules of a data space
* Trust Level 2: Feature complete for data usage control
	* provision of a common foundation for trusted data exchange including the enforcement of Usage Policies in a trusted environment
	* remote attestation
	* additional cybersecurity requirements are verified
* Trust Level 3: Additional protection from internal attacks
	* addition of advanced cybersecurity measures that are not commonly required
	* support of protection against malicious administrators (internal attacks)
	* provision of an additional level of trust and verification for the data provider as well as the data consumer

The following figure illustrates all possible combinations of assurance and trust level, that an applicant can choose from. The combinations not marked with a tick, e.g. Assurance Level 1 and Trust Level 3 can not be selected, due to incompatible purposes. 
![Bild-Titel](./media/2022_Component_Certification_Matrix.png)

## Certification of other components
As the Broker, App Store, Clearing House, ParIS and Vocabulary Provider components are at their core also a Connector, the general certification process and assurance levels apply to them as well, in addition to component specific funtional profiles. As an example for these profiles, the criteria catalogue "Components-Broker" can be requested from the IDSA for free[^6].

[^5]: IDSA White Paper Certification -- Framework for the IDS
    Certification Scheme 
    https://internationaldataspaces.org/publications/white-papers/
[^6]: https://internationaldataspaces.org/publications/white-papers/
