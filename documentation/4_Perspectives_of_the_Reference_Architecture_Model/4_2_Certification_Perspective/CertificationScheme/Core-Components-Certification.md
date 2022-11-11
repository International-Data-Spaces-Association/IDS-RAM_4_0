**PART 3 --** CORE COMPONENTS CERTIFICATION

To secure the intended cross-industrial and cross-company information
exchange, the Indus- trial Data Space core components must provide the
required functionality and an appropriate level of security. As such,
the core component certification is interoperability- and
security-focused, while aiming to strengthen the development and
maintenance process of these components.

Similar to the participant certification, a matrix certification
approach as shown in Figure 5 was defined for the core components of
the Industrial Data Space. This ensures on the one hand a low entry
barrier specifically suitable for SMEs and on the other hand a
scalable certification to meet high information security
requirements.

| | **Checklist Approach** | **Concept Review** | **High Assurance Evaluation** | 
| --- | --- | --- | --- |
|  **Base Security Profile** | :heavy_check_mark: | :heavy_check_mark: | - |
|  **Trust Security Profile** | - | :heavy_check_mark: | :heavy_check_mark: |
|  **Trust+ Security Profile** | - | :heavy_check_mark: | :heavy_check_mark: |

Figure 5: Certification Approach for core components of the Industrial
Data Space

## Assurance Levels

The depth and rigor of an evaluation consists of the following three
assurance levels as defined by the Industrial Data Space certification
scheme:

#### Checklist Approach

The core component must fulfill security features (security
requirements, security properties, security functions) as defined by
the corresponding checklist. The vendor of the component validates the
claims made about the implementation. Additionally, an automated test
suite will be used to verify the component's security features.

#### Concept Review

Instead of the checklist approach, an in-depth re- view by an
Industrial Data Space evaluation facility is necessary. The review
includes an evaluation of the provided concept as well as practical
functional and security tests.

#### High Assurance Evaluation

For the third level, in addition to the functional and security tests,
the vendor must provide the source code of all security relevant
components and an in- depth source code review will be performed by an
evaluation facility. Furthermore, the development process will be
evaluated, including an audit of the development site.

##  Security Profiles

Whenever two components establish a communication channel, it's up
to them to decide which information they will send to the
communication partner. Therefore, the identity and certification level
(for both the participant and the component) must be provided by each
component in the form of a digital certificate containing this
information. As with the participant certification, this approach
enables the data owner and data consumer to specify the security
profile required for the core components used during data exchange.

For this purpose, the Industrial Data Space certification scheme
defines three security profiles for the core components defined in the
section Component Overview of this paper.

#### Base Security Profile

This profile includes basic security requirements: limited isolation
of software components, secure communication including encryption and
integrity protection, mutual authentication between components, as
well as basic access control and logging. However, neither the
protection of security related data (key material, certificates) nor
trust verification are required. Persistent data is not encrypted and
integrity protection for containers is not provided. This security
profile is therefore meant for communication inside of a single
security domain.

#### Trust Security Profile

This profile includes strict isolation of software components
(apps/services), secure storage of crypto- graphic keys in an isolated
environment, secure communication including encryption, authentication and integrity protection, access and resource control, usage
control and trusted update mechanisms. All data stored on persistent
media or trans- mitted via networks must be encrypted.

#### Trust+ Security Profile

This profile requires hardware based trust anchors (in the form of a
TPM or a hardware-backed isolation environment) and supports remote
integrity verification (i.e., remote attestation). All key material
is stored in dedicated hardware isolated areas.

##  Certification Criteria Catalogue

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

To reduce the financial entry barrier not only for Industrial Data
Space participants but also for the developers of core components, the
component certification approach is designed to use existing certification schemes whenever reasonable. Where such certification
schemes do not exist or aren't widely recognized, e.g., for
Industrial Data Space-specific aspects, criteria defined within the
Industrial Data Space certification scheme will be employed.

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

## Piloting of Certification Criteria

In order to verify the completeness and applicability of the
catalogue of certification criteria for the IDS core component
»Connector« to real-world implementations, as well as the
IDS-readiness of these implementations, piloting workshops with
various IDSA members (e.g. Fraunhofer AISEC, T-Systems, Cybus) were
conducted. The workshops were organized by the WG Certification,
bringing together Fraunhofer IDS certification experts, developers and
product owners. While Fraunhofer had the best knowledge about
certification requirements, the developers and product owners
(consisting at least of the project manager and lead developer)
brought their in-depth knowledge about real-world implementations of
connector components as well as a business/market perspective to the
table.

During these 2-day workshops led by Fraunhofer FOKUS, the Connector
implementation was evaluated by going through the catalogue step by
step and looking into the implemented measures meeting the
requirements as well as the existing developer documentation. This
approach enabled all parties to get a better sense of the status of
the IDS-readiness of the implementation under evaluation. The results
of the workshop were recorded by the evaluation lead and distributed
to the developer. The anonymized results were reported back to the WG
Certification.

In regard to the completeness and applicability of the requirements
themselves, the in-depth discussions during the workshops in some
cases led to an adjustment of the wording of a requirement, the
addition of new requirements or the removal of non-applicable
requirements (either entirely or for a specific Security Profile). As
such, each piloting workshop led to a new version of the requirements
catalogue.

³ US Cert: Build Security In: Modeling Tools, 2013

## Component Overview

This chapter summarizes the Industrial Data Space core components as
assessed in [IDSRA, 4.2] that are targets of the component
certification.

#### Connector

Being the point of access to the Industrial Data Space, the Connector
provides a controlled environment for processing and exchanging
data, ensuring secure transfer of data from the data provider to the
data consumer. As such, the necessary trust in the correct and
complete implementation of the functionality required by the IDS
Reference Architecture Model and the Connector specification can only
be ensured by independent evaluation and certification from an
approved evaluation facility and the certification body of the
Industrial Data Space.

#### Metadata Broker

A Metadata Broker service does not have access to primary data, but only to
metadata provided by data providers, which is generally considered
less sensitive. Likewise, Metadata Broker services do not assign or enforce
access rights, but merely support data exchange. Nevertheless,
integrity and availability of metadata (i.e., correct and secure
storing and handling of meta- data) is of high importance for the
Industrial Data Space. Compatibility with the required functionality
as defined by the certification body is therefore evaluated and
certified.

#### Apps and Services

Data Apps and Services have direct contact with primary data, which
means that a compromised Data App or Service may compromise the integrity of data. However, confidentiality and availability of data is
ensured by the measures defined in the Security Architecture of the
Industrial Data Space, which strongly limit the potential damage
caused by

Data Apps and Services. Also, Apps and Services will typically use the
security features provided by the Connector. Therefore, not every Data
App or Service to be made available in the Industrial Data Space
requires a medium or high assurance level certification. However,
the automated test suite mentioned above for the basic security
level will be integrated in the upload process of each Industrial
Data Space App Store.

#### App Store

While the App Store itself does not have direct contact with primary
data, the Apps and Services they provide do. Compromised security of
the App Store, particularly of the test suite used during app and
service upload, could lead to the circulation of compromised Apps and
Services. Compatibility with the required functionality and security
features is therefore to be evaluated and certified.

#### Hardware

For certain security profiles as defined in the IDS Reference
Architecture Model, additional hardware security components are
required to achieve an appropriate level of protection for access to
sensitive data. In addition to the core software components of the
Industrial Data Space, these hardware components must therefore also
be considered in the context of certification. In the interest of
trust- worthiness, and to avoid double certification, the use of
third-party certified hardware components will be required (e.g.,
Trusted Platform Modules certified in accordance with the Protection
Profiles BSI- CC-PP-0030-2008 or ANSSI-CC-PP-2015/07). Certification activities of the Industrial Data Space regarding these
components will be limited to checking the validity of existing base
certificates.
