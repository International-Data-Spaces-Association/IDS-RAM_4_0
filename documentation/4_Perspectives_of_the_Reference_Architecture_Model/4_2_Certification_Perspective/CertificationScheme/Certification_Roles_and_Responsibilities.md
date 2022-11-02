# 2. Roles and Responsibilities in IDS Certification

The IDS Certification Framework foresees four entities as depicted in Figure 2.1 which are responsible for defining necessary assets and involved in certification for operational environments and core components.
All certification-related roles described in this section are specific to the International Data Spaces, i.e. terms such as "Certification Body" should not be misunderstood to refer to an existing organization already granting certificates. As part of the scheme implementation, the roles defined here will be assigned to actual organizations.

![Role and responsibilities](./media/Certification_scheme_overview.png)
Figure 2.1: International Data Spaces Certification - Roles & Responsibilities

## International Data Spaces Association

The International Data Spaces Association (IDSA) is an initiative of many international companies and organizations which collaborate to make the vision of the International Data Spaces reality. It defines the framework and reference architecture for setting up data spaces for secure and sovereign data exchange and processing.
With respect to the certification, the IDSA and its Working Group Certification have the following responsibilities:

* Defining and Enhancing the IDS Certification Framework:
  - Definition of the different types of certification, the utilized Criteria Catalogs, and the Certification Processes to be followed.
  - Analyzing existing "base" certificates (e.g. for organizations or for software and hardware security components) to determine their validity and sufficiency, and deciding about their acceptance within the IDS certification scheme.
  - Monitoring of the current regulatory and legal requirements to evaluate and react to possible influences to the certification scheme.
  - Continuous improvement of the defined certification scheme including the incorporation of the feedback provided by the Certification Body.

* Appointing and Supervising the IDS Certification Body which governs the implementation of the certification scheme based on the defined framework:
  - Defining the requirements for the Certification Body and verification of the required technical competencies.
  - Monitoring of the Certification Body to ensure a consistent level of quality for the IDS certification of operational environments and core components.
  - Provisioning of recommendations to the Certification Body based on the results of its monitoring activities.
For the initial phase of implementing certification, it has been decided that the IDSA will take on the role of the Certification Body as described below. When those two roles separate in the future, the IDSA will no longer be actively involved in the conducted operational environment or core component certification and the approval of Evaluation Facilities.

## Certification Body

The IDS Certification Body is appointed by the International Data Spaces Association and among other things regularly aligns with the IDSA to manage the certification process, defines the standardized evaluation procedures and supervises the actions of the Evaluation Facilities. Currently, the IDSA Head Office acts as the Certification Body.

Its responsibilities include:

* Offering certification for Assurance Level 1 (where no Evaluation Facility is needed):
  - Providing a Certification Portal where Applicants can conduct a self-assessment of their component or operational environment by answering a questionnaire or filling out provided forms for the self-assessment.
  - For components, providing means for the applicant to transfer information about the results of the automated tests required for Assurance Level 1.
  - Evaluating the answers and test results provided by the applicant.
  - Making a decision about the award or denial of the desired certification based on the requirements and their acceptance criteria defined the IDS Certification Scheme.

* Approval of Evaluation Facilities (required for Assurance Level 2 and 3, further defined in the [Approval Scheme](../ApprovalScheme/README.md)):
  - Ensuring that the company is able to realize the IDS Certification Scheme and take on the role of an Evaluation Facility before allowing it to act as such.
  - Conducting the approval by checking legal requirements, existing management processes and the competence of the potential evaluators based on provided documentation.
  - Conducting workshops with the Evaluation Facilities to assess their competence and the usage of adequate tooling (for component certification)
  - Making a decision about the approval of an Company as an Evaluation Facility (possibly after defined corrective measures have been implemented).
  - Informing Evaluation Facilities about changes in the IDS Certification Scheme and aligned relevant documents and conducting an Ad Hoc Approval if necessary.
  - Reminding Evaluation Facilities of the necessary re-approval after two years and conducting this Re-Approval.

* Supervising and monitoring evaluations conducted by the Evaluation Facilities (Assurance Level 2 and 3):
  - Overseeing all evaluations to ensure high quality and comparability of the conducted evaluations.
  - Supporting Evaluation Facilities with decisions on the focus of the evaluations and arising questions.
  - Reviewing the final evaluation reports from the Evaluation Facilities, providing feedback to the Evaluation Facilities and making a decision about the award or denial of the desired certification based on the requirements and their acceptance criteria defined the IDS Certification Scheme.
  - Conducting Ad Hoc Approvals and deciding about the exclusion of an Evaluation Facilities from executing IDS evaluations in case of quality or compliance issues with the work of the Evaluation Facility (based on ongoing monitoring and the requirements defined in the [Approval Scheme](../ApprovalScheme/README.md)).

* Issuing the certificates for components and operational environments:
  - Informing applicants (and for Assurance Level 2 and 3 the responsible Evaluation Facilities) about the decision regarding the award or denial of a certificate.
  - Issuing a paper and a machine-readable version of the certificate and providing it to the applicant.
  - Informing the Identity Provider to ensure up-to-date information being used there.

* Providing information and guidance for the IDS certification process:
    - Providing and maintaining the list of approved Evaluation Facilities on a website.
    - Providing and maintaining a list of all awarded IDS certificates on a website.
    - Provide support for the entire certification process (currently under supportoffice@internationaldataspaces.org)

* Maintaining the IDS Certification Scheme:
  - Defining the evaluation procedures and operational environment and core component certification approaches based on those criteria catalogs (taking into consideration feedback from the IDSA and its Working Group Certification).
  - Ongoing monitoring of certification-relevant external developments (e.g. new attack patterns which might circumvent certified security measures).
  - Ensuring continuous adherence to the IDS certification scheme following up on changes and updates received from the IDSA.
  - Providing input based on the practical quality assurance experiences to future updates of the IDS certification scheme to the International Data Spaces Association.

## Evaluation Facility

There are two types of Evaluation Facilities: One for IDS components and one for the operational environment. An organization usually performs only one type, but it is possible to have both functions. Any organization may become an evaluation facility if it passes the approval process for the respective Trust and Assurance Levels.
Once an Evaluation Facility is approved it can be contracted by an Applicant and is as such responsible for carrying out the detailed technical and/or organizational evaluation work during the certification process for either the IDS component or the operational environment in its assurance level scope. After the process, the Evaluation Facility issues an evaluation report listing details regarding the performed evaluation actions as well as information regarding the confirmed security level.
The depth and scope of the performed evaluation actions depend on the desired level of security. These security levels are specified in more detail in Section 3 and 4 of this document.

The responsibilities of the Evaluation Facility include:

* Obtaining approval by the Certification Body to perform evaluations, based on an approval process with criteria defining personnel competencies and organizational requirements (see section above):
  - Applying for approval as an Evaluation Facility for all desired types of certification and Trust and Assurance.
  - Providing all necessary information for the Assessment of the organizations suitability and participating in the audit conducted by the Certification Body.
  - Clarifying legal and framework conditions with the Certification Body.

* Conducting evaluations for components or evaluation facilities:
  - Ensuring that an Applicant is aware of the expectations and the process required for IDS certification.
  - Registering planned evaluations at the Certification Body before starting an evaluation for an Applicant.
  - Organizing and conducting the evaluations independently and with direct communication with the applicant directly. The Evaluation Facility is responsible for the evaluation whereby the Certification Body has the function of a supervisor.
  - Keeping the Certification Body informed about the progress and arising problems during the evaluation.
  - Applying the criteria specified in the IDS certification scheme according to generally accepted standards and best practices as well as provided test specifications, if applicable (including the execution of any necessary tests and on-site checks).
  - Documenting the results in an evaluation report.
  - Providing the evaluation report to the Certification Body.

The term Evaluation Facility is used throughout the document to refer both to authorized auditors for management system evaluations (i.e., operational environment certifications), as well as approved evaluators for product evaluations (i.e., core component certifications). Hence, multiple approved Evaluation Facilities will exist in the IDS certification scheme, but in each evaluation only one Evaluation Facility will be involved.

The flexibility of the certification approaches defined in Part 3 and 4 of this document allows for a wide range of evaluation experts to participate in the IDS certification scheme, such as software penetration testers, common criteria specialists, ISO 27001 auditors and accounting firms. As such, it is expected that all certification levels defined in this document and therefore the needs of startup companies and SMEs as well as those of large corporations will be sufficiently addressed.

## Applicant
Applicants are the entities that request certification for an operational environment or core component. Typically, for core components they are organizations or individuals that develop software components intended to be deployed within the International Data Spaces, whereas for operational environments they are organizations that intend to operate components in the IDS. They trigger the process actively by submitting an application to the Certification Body (for Assurance Level 1) or one of the approved IDS Evaluation Facilities (for Assurance Level 2 or 3) and play an active part in the certification process.

As such, the responsibilities of the respective organization include:

* Actively triggering the certification process
  - For certification with Assurance Level 1: Registering at the offered IDS Certification Portal to start the certification directly
  - For certification with Assurance Level 2 or 3: Contracting one of the approved IDS Evaluation Facilities (freely chosen upon the applicant's demands) to conduct the evaluation.

* Conducting a self-assessment for Assurance Level 1:
  - Filling out the questionnaire or self-assessment document truthfully which is used to assess the conformity of the component or organization with the requirements.
  - Clarifying open questions and doubts about a fulfillment of any of the requirements before submitting the final documents.
  - For core component certification: Running the automated tests as described in the provided documentation and uploading the results achieved.

* Providing all necessary material needed for the evaluation and certification of its component or organization for Assurance Level 2 or 3:
  - Providing the Evaluation Facility with documentation, source code and other material required to assess the fulfillment of the criteria for the intended Trust Level.
  - Communicating swiftly with and providing all necessary information and evidence to the Evaluation Facility and the Certification Body.
  - Reacting adequately to findings occurring during the course of the evaluation.
