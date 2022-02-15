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

[todo: add statement that different levels were created for different use cases as lead-in to the next two sub-chapters]
[todo: add statement that the criteria are defined in a rather general way, to allow the use of a component in different deployment scenarios, without having to define different critera catalogues for different use cases]

## Component Assurance Levels:
[todo add rationale per assurance level and add the current sub-bullet points there to avoid obvious duplicates between title and description]
The depth and rigor of a component evaluation consists of the following three assurance levels, 
independent on the type of component that is being certified (e.g. Connector, Broker, etc.):
* Assurance Level 1: Checklist self-assessment and automated interoperability testing
	* checklist self-assessment 
	* automated test suite
* Assurance Level 2: External concept review including functional and security testing
	* correct implementation of functional and security requirements verified through external experts
* Assurance Level 3: External evaluation including concept review, testing and source code audit
	* in-depth source code review 
	* evaluation of the development process, including an audit of the development site

## Connector Trust Levels
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

![Bild-Titel](./media/2022_Component_Certification_Matrix.png)

## Certification of other components
[todo: add how non-connector are addressed - As the components Broker, AppStore, Clearing House, Vocabulary Provider, PARIS are at their core also a Connector ... the general process and assurance levels also apply to them in addition to component specific funtional profiles]

[^5]: IDSA White Paper Certification -- Framework for the IDS
    Certification Scheme 
    https://internationaldataspaces.org/publications/white-papers/
[^6]: https://internationaldataspaces.org/publications/white-papers/
