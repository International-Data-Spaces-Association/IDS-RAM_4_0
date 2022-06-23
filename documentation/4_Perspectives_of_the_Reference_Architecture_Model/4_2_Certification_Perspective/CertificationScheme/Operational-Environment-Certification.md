**PART 2 -** OPERATIONAL ENVIRONMENT CERTIFICATION

One of the Industrial Data Space goals is to evolve to- wards a global
de-facto standard for cross-industrial and cross-company information
exchange. There- fore, a low financial and procedural barrier to join
the Industrial Data Space is inevitable. It must there- fore be
ensured that participants of the Industrial Data Space fulfill a
certain level of security in order to comply with the security
requirements set by the Industrial Data Space.

The participants of the Industrial Data Space will collaborate by
sharing their valuable information and data. Trust between the
involved participants is necessary for such a collaboration.
Furthermore it is essential for the Industrial Data Space and its
reputation that the participants are trustworthy. This trust can be
achieved by evaluating participants regarding their fulfilment of the
defined levels of security, including infrastructure reliability and
process compliance. To build this trust in a structured and ongoing
way the Industrial Data Space established a well-defined process for
participant certification.

This participant certification is based on established certification
standards and methods, as described in the following chapter
Certification Criteria Catalogue. Therefore the certification of one
participant demonstrates a level of security regarding availability,
confidentiality and integrity to all other participants and
stakeholder. So the process for participant certification as
described below is building the necessary trust in the participants of
the Industrial Data Space.

To ensure on the one hand a low entry barrier specifically suitable
for SMEs and on the other hand a scalable certification to meet high
information security requirements, the matrix certification approach
as shown in Figure 4 was defined for the certification of
participants.

The participant certification approach is displayed by two dimensions.
The horizontal dimension is the Evaluation Depth, describing the level
of detail at which an evaluation is performed. The vertical dimension
is the increasing extent of the Security Requirements that need to be
fulfilled.

## Evaluation Depth

The horizontal dimension Evaluation Depth consists of the following
three layers, with only the second and third layer containing actual
evaluation tasks:

#### Self-Assessment

A Self-Assessment is a mere self-declaration by the prospective
participant in order to clarify the participant's identity and the
provisioning of information about the participant's systems. No
evaluator is involved in performing a self-assessment and no
information of contained in a self-assessment is validated by an
evaluation facility.

Due to the fact that no evaluator is involved in the Self-Assessment,
no fully-qualified Industrial Data Space certificate is handed out to
the participant. The Self-Assessment leads only to a digital X.509
certificate in order to facilitate participation in the Industrial
Data Space. Nevertheless, it is a possibility for a prospective
participant to explore and test the features of the Industrial Data
Space in selected use cases. Another scenario for this layer is the
use of a managed connector. It is operated by a fully evaluated
service provider and the Self-Assessment would be only a low entry
barrier for an end-user of such a managed connector.

#### Management System

The evaluation of the participant's Management System is the next
layer of evaluation depth. This evaluation is performed by an
independent evaluation facility and involves analyzing whether the
applicant has defined a management system and whether the applicant is
actively working according to the defined management system. This
layer of evaluation depth usually involves interviews, site audits and
exemplary review of information and evidence at a certain point in
time.

#### Control Framework

The deepest layer of evaluation is the analysis of the Control
Framework. This evaluation contains not only the review of the
management system but also the evaluation of the operational
effectiveness of the management system and the controls defined within
the control framework of the applicant. This usually involves
interviews, site audits and evidence gathering activities based on
randomized sampling

to demonstrate that controls were performed over a certain period of
time. As with a Management System evaluation, the results are then
approved by the Certification Body.

## Security Requirement Extent

The extent of the Security Requirements consists of the following
three levels and all levels are built on one another containing
requirements derived from ISO/IEC 27001¹.

#### Entry Level

The entry level covers only the basic security requirements that
every participant of the Industrial Data Space needs to fulfill. The
entry level serves as a low barrier for companies (especially SMEs)
interested in trying out Industrial Data Space participation,
without facing considerable up-front investments. With that in mind,
this level is only combined with the low-cost self-assessment and an
evaluation of the participant's Management System.

#### Member Level

The member level additionally covers all relevant security
requirements ensuring an advanced level of security, suitable for most
of the core participants as defined in the Business Layer of the IDS
Reference Architecture Model [IDSRA, 3.1]: Data Owner, Data
Provider, Data Consumer, Broker Service Provider, App Store Provider,
Vocabulary Provider, Service Provider. The member level is sufficient
for most use cases involving the exchange of sensitive data.

#### Central Level

Finally, the central level includes special requirements that are
necessary for Industrial Data Space participants intending to perform
key functionalities and roles within the Industrial Data Space. These
requirements are appropriate since these roles have special
responsibilities so any security breaches would risk affecting the
Industrial Data Space as a whole, or substantial parts of it.
Concretely, this applies to the following roles defined in the
Business

¹For more information see
[https://www.iso.org/isoiec-27001-](http://www.iso.org/isoiec-27001-)
information-security.html

Layer of the IDS Reference Architecture Model [IDS- RA, 3.1]:
Clearing House and Identity Provider.

This distinction of the full qualified Industrial Data Space
participants in a member level and a central level have been designed
in order to have lower financial and procedural accession criteria.

These two dimensions form a matrix with nine fields as shown in Figure
4, and each field represents a combination of Evaluation Depth and the
extent of the Security Requirements. This matrix is used by the data
owner to define the degree of security that needs to be provided by
other participating organizations in order for them to be allowed to
obtain and process the owner's data. Due to this flexible
certification approach, the data owner is enabled to

specifically tailor their certification based on their business'
requirements and capabilities. In addition, other participants
benefit from using the matrix. For example, a new participant
benefits from a low entry barrier by getting a certificate for entry
level and self-assessment. After this, the participant can
continuously develop in any direction of the matrix in order to
facilitate a cooperation with other participants. This flexibility is
especially helpful for start-ups and SMEs. On the other hand, the matrix enables certificates with a rate of security high enough to be
sufficient even for large companies or those with strict security
requirements. Each participant is therefore enabled to decide the
required rate of security for the exchange of data, e.g. entry level
for weather data, but member level coupled with Management System for
sensitive business data.

| |  **Entry Level** | **Member Level* | **Central Level** |
|---|---|---|---|  
|  **Data Owner** | Required | Recommended | Optional |
|  **Data Provider** | Required | Recommended | Optional |
|  **Data Consumer** | Required | Recommended | Optional |
|  **Broker Service Provider** | - | Required | Optional |
|  **App Store Provider** | - | Required | Optional |
|  **Vocabulary Provider** | - | Required | Optional |
|  **Service Provider** | - | Required | Optional |
|  **Clearing House** | - | - | Required |
|  **Identity Provider** | - | - | Required |

Figure 3: Mapping of the roles in the Industrial Data Space to the
levels of certification

| | **Self-Assessment** | **Management System** | **Control Framework** |
| --- | --- | --- | --- |
| **Entry Level** | :heavy_check_mark: | :heavy_check_mark: | - |
|  **Member Level**  | - | :heavy_check_mark: | :heavy_check_mark: |
|  **Central Level** | - | :heavy_check_mark: | :heavy_check_mark: |

Figure 4: Certification Approach for participants of the Industrial
Data Space

## Certification Criteria Catalogue

To further reduce the financial entry barrier for Industrial Data
Space applicants, the participant certification approach is designed
to allow the re- use of existing certificates obtained through compliance with other certification schemes, standards, and norms. Depending
on the desired level and depth of the evaluation, this could for
example imply that certain control testing can be inherited from an
ISAE3000 certification framework.

In order to enable the participants to reuse their existing
certificates, the participant certification criteria catalogue
[CRIT-\] has been developed on the basis of established security
standards. Due to the nature of the Industrial Data Space and its
inter- national approach the standards ISO/ IEC 27001 and BSI C5²
(Bundesamt für Sicherheit in der Informationstechnologie (engl.
Federal Office for Information Security) Cloud Computing Compliance
Controls Catalogue) have been chosen. The standard ISO/ IEC 27001 has
been chosen due to its international distribution and its reputation
for information security. The standard BSI C5 is a standard for
information security and developed for modern IT environments like
cloud computing.

² For more information see
ht[tps://www.bsi.bund.de/DE/](http://www.bsi.bund.de/DE/)
Themen/DigitaleGesellschaft/CloudComputing/Anforderungs-
katalog/Anforderungskatalog_node.html

Out of both standards the requirements relevant for the Industrial
Data Space have been selected for their applicability regarding the
different levels. These requirements have been grouped in 16 sections with a different number of requirements for each level. Due to
the incremental approach of the level all requirements of the entry
level are also relevant for the member and central level and all
requirements of the member level are also relevant for the central
level.

## Piloting of Certification Criteria

In order to verify the completeness, applicability, feasibility and
relevance of the catalogue of certification criteria for the IDS
participant certification, as well as the certification process for
participants, piloting workshops with various IDSA members (e.g.
GESIS, Komsa, Thyssenkrupp) were conducted. The workshops were
organized by the WG Certification, bringing together experts in
participant certification from the Working Group with the security
officer and / or the compliance officer from the companies. In addition to the
audit readiness, this validation gave valuable feedback for the list
of certification requirements and the associated questionnaire.

These 1-day workshops led by the expert from the Working Group were
organized as a health check. The certification expert explained the
certification process in detail. In a second phase the audit readiness was evaluated by going through the catalogue step by step. No
documented evidence was required, only verbal information was
collected. This approach enabled all parties to get a better sense of
the status of the IDS-readiness for the participant, as well as the
significance of each criteria. The results of the workshop were
recorded by the evaluation lead and distributed to the company. The
anonymized results were reported back to the WG Certification.

In regard to the completeness and applicability of the criteria
themselves, the in-depth discussion during the workshops in some cases
led to an adjustment of the wording of a criterion. In addition the
feedback of the piloting led to a new entry in the dimension matrix of
Evaluation Depth and the Extent of the Security Requirements for
participant certification (Member Level, Management System).

## Participants Overview

This chapter summarizes the description of the architectural roles of
the Industrial Data Space participants as defined in [IDSRA, 3.1]
and how the participant certification applies to them.

#### Core Participants

The Data Provider is responsible for the integrity, confidentiality,
and availability of the data it publishes and provides. Evaluation
and certification of the security mechanisms employed by the data
provider shall provide a sufficient degree of security against the
risk of relevant security requirements (such as data integrity,
confidentiality, or availability) being undermined by attacks.

Data Owners are assumed to often act as a data provider at the same
time. In the case of the data owner and the data provider being
different entities (i.e., the data owner does not publish the data
itself but hands over this task to a data provider), both the data
owner and the data provider are responsible for integrity and
confidentiality of the data. Responsibility for the availability of
the data, however, rests solely with the data provider in this case,
provided

the data owner has handed over the data to the data provider.

For a data owner not acting as a data provider, evaluation and
certification of the technical, physical, and organizational
security mechanisms employed provide a sufficient degree of security
against the risk of data integrity or confidentiality being undermined
by attacks.

As an organization that has access to data provided by a data owner,
the Data Consumer also assumes responsibility for the confidentiality
and integrity of that data (i.e., in terms of making sure the data
can- not leave the Industrial Data Space in an uncontrol- led manner
and cannot be corrupted before being used). Furthermore, the data
consumer has to make sure the data cannot be used for purposes other
than permitted. Against all these risks, evaluation and certification
of the technical, physical, and organizational security mechanisms
employed by the data consumer provide a sufficient degree of security.

#### Intermediaries

Since preventing sensitive data from ending up in the wrong hands is a
central goal of the Industrial Data Space initiative, it is highly
critical to eliminate all risks involving manipulation of
identities. The integrity and availability of identity-related
information processed by the Identity Provider is therefore of utmost
importance. Only evaluation and certification of the security
mechanisms employed by the respective organization (in combination
with technical security measures in relation with the software
components used for processing identity-related information) is able
to provide a sufficient degree of security against these risks.

Broker Service Providers, providers of Clearing House services, the
App Store Provider, and the Vocabulary Provider deal only with
metadata, transactions, or apps (i.e., they do not work with the
sensitive payload data which the Industrial Data Space is designed to
protect). The risk associated with possible breaches of
confidentiality, integrity, and availability of metadata is lower
(with the exception of clearing house transaction data, which,
however, lies beyond the scope of the Industrial Data Space).
Nevertheless, an attacker succeeding in exfiltrating or corrupting
metadata, or impeding

the availability of metadata, would be able to cause considerable
damage to the Industrial Data Space or targeted participants --
especially if such successful attacks would remain undetected over
extended periods of time. Therefore, evaluation and certification
tailored to the specific risk profiles of and security mechanisms
employed by broker service providers, providers of clearing house
services, app store providers, and vocabulary providers is pro- posed
in order to ensure a sufficient degree of security against the risks
mentioned. As far as the app store provider is concerned, there is an
additional risk in terms of an attacker successfully substituting
legitimate apps with modified versions, thereby threatening the
payload data indirectly. However, technical measures in the app store
implementation (e.g., only apps cryptographically signed by the app
developer are accepted and distributed) seem more effective for
reducing this risk than organizational measures on the part of the app
store provider.

####  Software / Service Providers

Providers of compliant software usually have no contact with sensitive
data, but execute tests with appropriate, non-sensitive test data.
Therefore, in most cases no certification of the organizational
security is required. If access to actual data of the Industrial Data
Space is necessary, the Software Provider assumes the role of data
consumer or data provider for as long as such access is needed. In
that case, the certification requirements of the corresponding roles
apply.

If a participant does not deploy the technical infra- structure
required to participate in the Industrial Data Space itself, it can
outsource certain tasks, like publishing their data in the Industrial
Data Space to a Service Provider hosting the required infrastructure.
If this is the case, this Service Provider assumes the role of a Data
Provider, Data Consumer, Broker Ser- vice Provider, etc. and performs
the corresponding activities. They inherit the original role's
responsibilities and risks, and shall therefore be subject to the
corresponding requirements regarding certification.
