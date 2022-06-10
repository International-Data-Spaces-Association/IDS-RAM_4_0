# Core Component Certification

## Intro
[*TODO: check revision -> Monika*]

To ensure the core values of the International Data Spaces - data 
sovereignty and data security - each IDS component is expected to 
behave in adherence with IDS specifications and to protect the data 
which is transferred and processed by these components. 

This allows for trustful cross-company information exchange, using 
secure components, which meet a list of certification criteria to evaluate 
the compliance with the required functionality, interoperability and level of security. 
This evaluation is conducted in the IDS Core Component Certification.

Each certified component will provide the required functionality and an 
appropriate level of security for specific use cases. As such,
the core component certification is IDS-functionality-, interoperability- and
security-focused, while aiming to strengthen the development and
maintenance process of these components.

A component certification will therefore allow IDS participants to assess the 
possible consequences of secure data sharing and provide transparent 
information about possible guarantees with regards to data sovereignty.

Within the next two subsections, the assurance and trust levels 
for each component type are defined. In the final two subsections, the 
criteria catalogue as well as the reference testbed are outlined.


## Assurance Levels
[*TODO: check update to assurance level 1-3 -> Monika*]
[*TODO: include Verweis auf Test Specifications -> Nadja*]

The depth and rigor of an evaluation consists of the following three
assurance levels as defined by the International Data Spaces certification
scheme:

#### Assurance Level 1: Checklist self-assessment and automated interoperability testing

This level is targeted at developers looking for a low entrance barrier into the IDS.
The effort and costs in this level are therefore very low for the applicant due to the self-assessment approach.
Nevertheless, the core component must fulfill security features (security
requirements, security properties, security functions) as defined by the corresponding criteria catalogue.
The compliance of the implementation with these criteria is confirmed via statements made 
by the developer in a checklist and additionally verified via an automated test 
suite without any involvement of an external evaluation facility.
As seen in the above figure, Assurance Level 1 can only be combined with Trust Level 1, 
as a compliance verification of an evaluation facility is required for the higher trust levels.

#### Assurance Level 2: External concept review including functional and security testing

Starting with Assurance Level 2, external evaluation facilities are tasked with the evaluation, 
to ensure an independent evaluation result.
This external concept review includes the examination of documentation as well as the 
practical testing of the Connector, to ensure the correct implementation of the functional and security requirements.
Level 2 strikes the right balance between an independent review and the corresponding costs.
This level can be combined with all three trust levels.

#### Assurance Level 3: External evaluation including concept review, testing and source code audit

For use cases that require a high evaluation guarantee, such as the exchange of very sensitive data, 
higher efforts and costs will be required to ensure the customers needs in regard to security assurances are met.

As such, the vendor must provide the source code of all security relevant
components, so that an IDS evaluation facility can perform an in-depth source code review, 
in addition to functional and security tests. Furthermore, the development process will be
evaluated, including an audit of the development site.

Assurance Level 3 can only be combined with the Trust Levels 2 and 3.


## Trust Levels and Profiles for Components
[*TODO: pot. image to show the different certification types -> Monika*]
![Overview different component certifications](./media/types_of_component_certification.png)

[*TODO: Is the first part of this statement still correct?  -> Monika*]
Whenever two components establish a communication channel, it's up
to them to decide which information they will send to the
communication partner. Therefore, the identity and certification level
(for both the participant and the component) must be provided by each
component in the form of a digital certificate containing this
information. As with the participant certification, this approach
enables the data owner and data consumer to specify the assurance and trust level 
required by each core component used during data exchange.

For this purpose, the IDS certification scheme defines, in addition to the above assurance 
levels, trust levels for each core component type. These trust levels per component type 
are described in the following subsections.

### Connectors

[*TODO: Is the Connector specification still the correct reference?  -> Monika*]
Being the point of access to the International Data Spaces, the Connector
provides a controlled environment for processing and exchanging
data, ensuring secure transfer of data from the data provider to the
data consumer. As such, the necessary trust in the correct and
complete implementation of the functionality required by the IDS
Reference Architecture Model and the Connector specification can only
be ensured by independent evaluation and certification from an
approved evaluation facility and the certification body of the
IDS.

For the Connector, three Trust Levels have been defined as part of 
the IDS Certification Scheme. 

#### Trust Level 1: Data space interoperability

Trust Level 1 offers a basic level security profile in order to 
participate in a data space, with only a minimal set of 
agreed cybersecurity requirements to ensure the trustworthiness 
of the ecosystem as a whole. 
The base requirements includes limited isolation of software 
components, secure communication including encryption and
integrity protection, mutual authentication between components, as
well as basic access control and logging. 
However, neither the protection of security related data 
(key material, certificates) nor trust verification are required. 
Persistent data is not encrypted and integrity protection for 
containers is not provided. 

This security profile is therefore meant for communication inside of a 
single security domain. Nevertheless, interoperability with IDS-components 
and compliance to the basic rules of a data space is verified. 

#### Trust Level 2: Feature complete for data usage control
Trust Level 2 provides a common foundation for trusted data exchange 
including the enforcement of Usage Policies in a trusted environment, as well 
as Remote Attestation as a way to prove the integrity of a software stack 
and ensure that the certified software stack is truly deployed.
On top of that, additional cybersecurity requirements are verified during 
the evaluation, including but not limited to strict isolation of software components
(apps/services), secure storage of cryptographic keys in an isolated
environment, secure communication including encryption, authentication 
and integrity protection, access and resource control, usage
control and trusted update mechanisms.

#### Trust Level 3: Additional protection from internal attacks
Trust Level 3 requires additional advanced cybersecurity measures that are not 
commonly required, specifically the support of protection against malicious 
administrators (i.e. protection against internal attacks) an the provision of an 
additional level of trust and verification for the data provider as well as the data consumer.

[*TODO: Is this paragraph still correct for Level 3? If not, delete or move to Level 2?  -> Monika*]
This profile requires hardware based trust anchors (in the form of a
TPM or a hardware-backed isolation environment) and supports remote
integrity verification (i.e., remote attestation). All key material
is stored in dedicated hardware isolated areas.

Similar to the participant certification, a matrix certification
approach as shown in Figure 5 was defined for the Connector certification. 
This ensures on the one hand a low entry
barrier specifically suitable for SMEs and on the other hand a
scalable certification to meet high information security
requirements.

| | **Assurance Level 1** | **Assurance Level 2** | **Assurance Level 3** |
| --- | --- | --- | --- |
|  **Trust Level 1** | :heavy_check_mark: | :heavy_check_mark: | - |
|  **Trust Level 2** | - | :heavy_check_mark: | :heavy_check_mark: |
|  **Trust Level 3** | - | :heavy_check_mark: | :heavy_check_mark: |

Figure 5: Certification Approach for IDS Connectors


#### Connector-based Components (Broker, App Store, ...)
[*TODO: explain how those build on the connector certification levels*]

A Broker service does not have access to primary data, but only to
metadata provided by data providers, which is generally considered
less sensitive. Likewise, Broker services do not assign or enforce
access rights, but merely support data exchange. Nevertheless,
integrity and availability of metadata (i.e., correct and secure
storing and handling of meta- data) is of high importance for the
IDS. Compatibility with the required functionality
as defined by the certification body is therefore evaluated and
certified.

#### Data Apps and Services
[*TODO: revise*]
Data Apps and Services have direct contact with primary data, which
means that a compromised Data App or Service may compromise the integrity of data. However, confidentiality and availability of data is
ensured by the measures defined in the Security Architecture of the
IDS, which strongly limit the potential damage
caused by

Data Apps and Services. Also, Apps and Services will typically use the
security features provided by the Connector. Therefore, not every Data
App or Service to be made available in the IDS
requires a medium or high assurance level certification. However,
the automated test suite mentioned above for the basic security
level will be integrated in the upload process of each IDS App Store.

#### DAPS

#### Certificate Authority
[*TODO: keine zertifizierung für Komponenten, aber Op.Env und Ca-specific certification*]


##  Certification Criteria Catalogue
[*TODO: update -> Nadja*]

The criteria that make up each of the three trust levels for a Connector are defined in such a way that they are specific enough to ensure interoperability with the functional requirements of an IDS Connector, yet general enough, to allow the use of a Connector in different deployment scenarios without having to define different criteria catalogues for each separate use case.

The catalogue of certification criteria for the IDS core components
[CRIT-C] was defined as part of the Fraunhofer research project
»Industrial Data Space« and fine-tuned with the members of the WG Certification. The catalogue is split into three thematic sections, i.e.
IDS-specific requirements, functional requirements taken from the
industry standard ISA/ IEC 62443-4-2 [62443-4-2] and best practice
requirements for secure software development.

![criteria Synergy](./media/fig3_criteria.png)
Figure 6: Criteria Synergy

Each criteria section targets a set of evaluation goals:

-   The IDS-specific requirements aim to evaluate the Core
   Component's conformity to the IDS Reference Architecture Model,
   both in regard to functionality (e.g. support of the IDS information
   model) as well as security (e.g. conformance to the IDS security
   architecture).

-   The requirements taken from ISA/IEC 62443-4-2 target the implemented
   functionality and security measures in relation to industry-wide
   accepted requirements for industrial automation and control
   systems, e.g. the capability to obscure feedback of authentication
   information during the authentication process.

-   To round off the catalogue, the best practice requirements for
   secure software development aim to evaluate the security of the
   processes during the development of the component, e.g. design
   documentation, physical security measures and test processes.

To reduce the financial entry barrier not only for IDS participants but 
also for the developers of core components, the
component certification approach is designed to use existing certification 
schemes whenever reasonable. Where such certification
schemes do not exist or aren't widely recognized, e.g., for
IDS-specific aspects, criteria defined within the
International Data Spaces certification scheme will be employed.

The functional and security requirements of the core components to be
evaluated will be defined based on the IDS Reference Architecture
Model, specific component specifications like the Connector Specification as well as widely recognized requirement catalogues like
ISA/IEC 62443-4-2 (e.g. for functional requirements such as data
confidentiality and system integrity).

The evaluation at the various assurance levels can also be supported
and facilitated by requiring appropriate measures used throughout the
lifecycle of the component as defined in ISA/IEC 62443-4-2, such as
using the approach for thorough elicitation of the Security
Requirements, enforcing those Security Requirements at the
Architecture level (e.g., using Security-by-Design) and tracing them
to the

Secure Implementation level, supported by relevant Guidance
Documents, Verification & Validation approaches, as well as a Secure
Defect Management & Secure Update Management.³
³ US Cert: Build Security In: Modeling Tools, 2013

#### Hardware

For certain security profiles as defined in the IDS Reference
Architecture Model, additional hardware security components are
required to achieve an appropriate level of protection for access to
sensitive data. In addition to the core software components of the
IDS, these hardware components must therefore also
be considered in the context of certification. In the interest of
trustworthiness, and to avoid double certification, the use of
third-party certified hardware components will be required (e.g.,
Trusted Platform Modules certified in accordance with the Protection
Profiles BSI- CC-PP-0030-2008 or ANSSI-CC-PP-2015/07). 
Certification activities of the International Data Spaces regarding these
components will be limited to checking the validity of existing base certificates.

##  IDS Reference Testbed
[*TODO: revise -> Sonia*]
The IDS Reference Testbed consists of a set-up with open source IDS components complying to the IDS specifications for establishing connections and communication. The initial basic version of the testbed (as released in December 2021) consists of a Certificate Authority (CA), a Dynamic Attribute Provisioning Service (DAPS), a Meta Data Broker and two Dataspace Connectors. Moreover, an automated test suite is included for testing a conenctor on criteria for interoperability and compliance to the IDS specifications.
![image](https://user-images.githubusercontent.com/77682996/173075490-80c82170-f933-4e67-bd4c-6c94358a31f9.png)

The IDS Reference Testbed is the main tool to prepare for certification, specifically at the component level. The certification of the IDS-components is executed using the IDS Reference Testbed, the same testbed which is publicly available for organizations to test their implementations. This ensures that the technical certification of the IDS components is transparent and that most issues can be resolved by the companies before the actual certification process. Therefore reducing costs and efforts. 
Finally, existing (open-source) implementation of the IDS components can be integrated into the testbed to further help the companies to get familiar with the IDS requirements. In certain cases, companies might use one of the available implementations as basis for their solution. 
