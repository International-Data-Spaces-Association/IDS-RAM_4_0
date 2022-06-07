# 2. Roles and Responsibilities in IDS Certification

The IDS Certification Framework foresees four entities as depicted in Figure 2.1 which are responsible for defining necessary assets and realizing certification for operational environments and core components.
All certification-related roles described in this section are specific to the Internation Data Spaces, i.e. terms such as "Certification Body" should not be misunderstood to refer to an existing organization already granting certificates. As part of the scheme implementation, the roles defined here will be assigned to actual organizations.

![Role and responsibilities](./media/Certification_scheme_overview.png)
Figure 2.1: International Data Spaces Certification - Roles &
Responsibilities

## International Data Spaces Association

The International Data Spaces Association (IDSA) is an initiative of many international companies and organizations which collaborate to make the vision of the International Data Spaces reality. It defines the framework and reference architecture for setting up data spaces for secure and sovereign data exchange and processing.
With respect to the certification, the IDSA has the following responsibilities:
* Defining and Enhancing the IDS Certification Framework, including
  - Definition of the different types of certification, the utilized Criteria Catalogs, and the Certification Processes to be followed.
  - Monitoring of the current regulatory and legal requirements to evaluate and react to possible influences to the certification scheme.
  - Continuous improvement of the defined certification scheme including the incorporation of the feedback provided by the Certification Body.
* Appointing the IDS Certification Body which governs the implementation of the certification scheme based on the defined framework.
  - Defining the requirements for the Certification Body and verification of the required technical competencies.
  - Monitoring of the Certification Body to ensure a consistent level of quality for the IDS certification of operational environments and core components.
  - Provisioning of recommendations to the Certification Body based on the results of its monito- ring activities.
For the initial phase of implementing certification, it has been decided that the IDSA will take on the role of the Certification Body as described below. When those two roles separate in the future, the IDSA will no longer be actively involved in the conducted operational environment or core component certification and the approval of Evaluation Facilities.

## Certification Body

The IDS Certification Body is appointed by the International Data Spaces Association and among other things regularly aligns with the IDSA to manage the certification process, defines the standardized evaluation procedures and supervises the actions of the Evaluation Facilities. Currently, the IDSA Head Office acts as the Certification Body.

Its responsibilities include:

-   Maintaining the IDS Certification Scheme:
    - The Certification Body and (other) members of the International Data Spaces Association collaborate in the Working Group Certification to formulate and define the IDS Certification Scheme and its utilized criteria catalogues.
    - In particular, the Certification Body in collaboration with the IDSA is responsible for defining the evaluation procedures and operational environment and core component certification approaches based on those criteria catalogues.

-   Offering certification for Assurance Level 1:
    - For Assurance Level 1 for Core Component as well as for Operational Environment Certification, no Evaluation Facility is needed. The Certification Body provides a portal, where Applicants can conduct a self-assessment of their component or operational environment by answering a questionnaire or filling out provided forms for the self-assessment.
    - For components, the Applicant additionally needs to provide information about the results of the automated tests required for Assurance Level 1.
    - The answers will be evaluated by the Certification Body directly.
    - It will make a decision about the award or denial of the desired certification based on the requirements and their acceptance criteria defined the IDS Certification Scheme.

-   Approval of Evaluation Facilites:
    - For the Assurance Level 2 and 3, Evaluation Facilities are needed. They evaluate the components or operational environments in detail and make sure that they fulfill the requirements defined in the IDS Certification Scheme.
    - Before a company may act as an Evaluation Facility, the Certification Body ensures that the company is able to realize the IDS Certification Scheme and take on the role of an Evaluation Facility.
    - Within the approval process, the Certification Body checks legal requirements, existing management processes and the competence of the potential evaluators based on provided documentation.
    - Additionally, the competence of the Evaluation Facility and the usage of adequate tooling is assessed in dedicated workshops with the Certification Body.

-   Supervising evaluations conducted by the Evaluation Facilities:
    - To ensure high quality and comparability of the conducted evaluation, the Certification Body oversees all evaluations and closely observes the performed evaluations on a sample basis.
    - The Certification Body also reminds the Evaluation Facility to get re-approved after two years.
    - Whenever new guidelines are developed and published by the association, the Certification Body informs the Evaluation Facilities.
    -   In case of issues with the work of an Evaluation Facility, the Certification Body decides about the exclusion of Evaluation Facilities from executing IDS evaluations (based on ongoing monitoring and [CRIT-EF]).

- Issuing the certificates for components and operational environments:
    - The Certification Body keeps track of all certifications currently in progress.
    - In the last step of the Certification Process, the Certification Body reviews the information from the Certification Portal for Assurance Level 1 or the evaluation reports received from Evaluation Facilities for Assurance Level 2 or 3.
    -  It makes the final decision about the award or denial of a certificate and only grants the certificate if the Evaluation Facility (for Assurance Level 2 and 3) and the experts of the Certification Body have come to the conclusion that all preconditions are fulfilled.
    - Afterwards, the Certification Body informs the Applicants and the responsible Evaluation Facility of its decision.
    - The Certification Body is responsible for providing the Applicants with the awarded certificates and maintaining a list of all currently valid certificates on its website.

-   Guiding applicants through the certification process.
    - The Certification provides and maintans the list of approved Evaluation Facilites on the IDSA website.
    - By contacting supportoffice@internationaldataspaces.org applicants can reach out for support on the whole certification process.

-   Ongoing monitoring of certification-relevant external developments (e.g. new attack patterns which might circumvent certified security measures).

-   Analyzing existing "base" certificates (e.g. for organizations or for software and hardware security components) to determine their validity and sufficiency, and deciding about their acceptance within the Industrial Data Space certification scheme.

-   Ensuring continuous adherence to the IDS certification scheme following up on changes und updates received from the Certification Body and the IDS Association.

-   Providing input based on the practical quality assurance experiences to future updates of the IDS certification scheme to the International Data Spaces Association.


## Evaluation Facility

There are two types of Evaluation Facilites: One for IDS components and one for the operational environment. An organization usually performs only one type, but it is possible to have both functions. As written in the previouse section an approval process needs to be conducted to become an official IDS Evaluation Facility. Further, the Organization is beeing approved to perform evaluations for specific assurance levels of the IDS certification. This means, that an Evaluation Facility that is approved to conduct evaluations for instance for assurance level 2 is only allowed to evaluate components or operational environment for the assurance level 2.
Once an Evaluation Facility is approved it can be contracted by an Applicant and is as such responsible for carrying out the detailed technical and/or organizational evaluation work during the certification process for either the IDS component or the operational environment in its assurance level scope. After the process, the Evaluation Facility issues an evaluation report listing details regarding the performed evaluation actions as well as information regarding the confirmed security level.
The depth and scope of the performed evaluation actions depend on the desired level of security. These security levels are specified in more detail in Part 2 and 3 of this document.

The responsibilities of the Evaluation Facility include:

-   Obtaining approval by the Certification Body to perform evaluations, based on an approval process with criteria defining personnel competencies and organizational requirements (see section above).

-   Applying the criteria specified in the IDS certification scheme according to generally accepted standards and best practices (including the execution of any necessary tests and on-site checks).

-   Organizes and conducts the evaluations independently and communicates with the applicant directly. The Evaluation Facility is therefore responsible for the evaluation whereby the Certification Body has the function of a supervisior.

-   Documenting the results in an evaluation report.

-   Providing the evaluation report to the Certification Body.

The term Evaluation Facility is used throughout the document to refer both to authorized auditors for management system evaluations (i.e., participant certifications), as well as approved evaluators for product evaluations (i.e., core component certifications). Hence, multiple approved Evaluation Facilities will exist in the Industrial Data Space certification scheme, but in each evaluation only one Evaluation Facility will be involved.

The flexibility of the certification approaches defined in Part 2 and 3 of this document allows for a wide range of evaluation experts to participate in the Industrial Data Space certification scheme, such as software penetration testers, common criteria specialists, ISO 27001 auditors and accounting firms. As such, it is fully expected that all certification levels defined in this document and therefore the needs of startup companies and SMEs as well as those of large corporations will be sufficiently addressed (PLEASE CHECK).


## Applicant
The Applicant plays an active part in the certification process. He or she triggers the process actively by submitting an application to the Certification Body (for Assurance Level 1) or one of the approved IDS Evaluation Facilities (for Assurance Level 2 oder 3). This applies to organizations/individuals that develop software components intended to be deployed within the International Data Spaces (i.e., prospective Software Providers) and to organizations that intend to operate components in the IDS.

As such, the responsibilities of the respective organization include:

-   Actively triggering the certification process
    -   for a certification at Assurance Level 1: applying at the Certification Body directly. the applicant can choose the self-assessment approach, where no Evaluation Facility is required. The applicant needs to visit the IDSA Website (Link Here) to registeres to the "IDS Certification Portal" for triggering the start of the certification for IDS components with the Assurance Level 1. By filling out a questionnaire with true/false and open questions the applicant assures the IDS conformity of the component. The IDS Certification Body is responsible for checking and assessing the answers given by the applicant. In case of a positive outcome, the Certification Body provides the certificate directly to the applicant.

    -   for a certification at Assurance Level 2 or 3: applying at one of the approved IDS Evaluation Facilites. The Applicant can choose the Evaluation Facility upon his demands. The certification process will be then organized mainly by the chosen Evaluation Facility whereas the Certification Body will be informed only of the process led by the Evaluation Facility. After the evaluation of the components took place, the Evaluation Facility provides the report to the Certification Body that assesses the report and decides if the certificate can be issued to the applicant or not.

-   Providing all necessary material needed for the evaluation and certification of its component or organization and supports with questions or issues arising.

-   Communicate swiftly with and provide all necessary information and evidence to the Evaluation Facility and the Certification Body.

-   React adequately to findings occurring during the course of the evaluation.

## Issuance of Certificates

![Issuance of Certificates](media/fig2_.png)
Figure 2: International Data Spaces Certification -- Issuance of Certificates

After a successfully completed evaluation, the Certification Body awards an Industrial Data Space evaluation certificate to the applicant. These certificates will have a limited validity period.
In order to renew a certificate before it expires, a re-certification is required, taking into account any relevant external developments that have happened in the meantime. Similarly, re-certification is required if changes are made to the target of certification; in case of minor changes, "lightweight", low-cost re-certification may be sufficient. The definition of major and minor changes will follow the definition used within widely accepted certification standards such as ISO 27001.

For authentication and authorization, each IDS component must have a valid X.509 certificate, in order to verify the identity of other participants. These technical certificates digitally represent the evaluation certificate and enable automated trust checks between partners prior to data transfer within the Industrial Data Space. Upon a successful certification of an organization, such a technical certificate is issued to the organization to confirm certain attributes like organizational name, certification status, etc. This technical certificate can be used to trigger processes such as applying for X.509 connector certificates.
