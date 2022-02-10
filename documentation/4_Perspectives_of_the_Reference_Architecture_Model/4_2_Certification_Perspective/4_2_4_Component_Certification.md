# Component Certification

In order to secure the intended cross-company information exchange, the core components to be used in the IDS must provide the required
functionality and level of security. As such, the certification of core
components focuses on interoperability and security, while aiming to
strengthen the development and maintenance process of these components.

To build this trust in a structured way, the International Data Spaces
has established a well-defined process for core component certification.
An in-depth description of the certification process, and how it applies
to the key elements of the IDS architecture, can be found in Part 3 of
the White Paper Certification[^5]. Access to the core component certification
criteria catalogues for Connectors and Brokers, respectively, can be requested from the IDSA for free[^6].

[todo: revise and describe the different levels <- move here from chapter 4.1 (Security) => done?]  
## Component Assurance Levels:
The depth and rigor of a component evaluation consists of the following three assurance levels:
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

[todo: Add new figure of the matrix here]

## Broker Trust Levels
[todo: description of Broker profiles / levels]

## Outlook
[todo: add how non-connector / broker components are addressed]

[todo: add that/how criteria are applicable for different deployment scenarios]


[^5]: IDSA White Paper Certification -- Framework for the IDS
    Certification Scheme, Version 2.0
    https://www.internationaldataspaces.org/publications/whitepaper-certification/
[^6]: https://internationaldataspaces.org/publications/white-papers/
