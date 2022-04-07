# Certification Processes

[TODO: add introduction]

## Approval of Evaluation Facilities

In order to ensure the high quality and transparency of the IDS certification process all Evaluation Facilites need to be approved by the impartial [Certification Body](https://github.com/International-Data-Spaces-Association/IDS-G/tree/main/glossary#certification-body) first. 

The approval process is structured in the same way for both types of future Evaluation Facilities (operational environment and components) and includes the following phases:
1. Preparatory Phase
2. Audit Phase
3. Approval Phase

These phases will be described in the following sections. 

### 1. Preparatory Phase:
This phase serves to collect all important documents and information needed for a smooth approval process, but also to discuss the process flow. This phase also offers the opportunity to clarify any questions related to the process within an (optional) inquiry meeting. It begins with the completion of an application form and the signing of a contract between the potential Evaluation Facility and the IDS Certification Body.

### 2. Audit Phase
Each Evaluation Facility is audited in order to ensure that it will conduct evaluations in adherence with the IDS certification scheme. The audit has the aim to check that the requirements for a proper IDS certification are implemented and effective. It consists of collecting evidence in form of documentation and interviews with employees in four different assessments:

1. Quality Management System
2. Security Management System
3. Competence of the Evaluators
4. Testing equipment and its usage (only relevant for Component Certification)

Based on the audit the Certification Body prepares a report including the deviations and potential improvements which will be communicated in a final discussion. Deviations related to the Management System which could affect its effectiveness must be corrected before closing the audit phase within a two-month period at most, with exceptions for critical deviations. If necessary, the correction of the deviations can be verified by an additional audit.

### 3. Approval Phase
On the basis of the audit report, the Certification Body decides on the approval of the applying Evaluation Facility. The decision is made in an objective and comprehensible manner, i.e.  exclusively on the basis of the documented criteria.
In case of a positive decision, the Certification Body issues an approval statement. The approval is valid for a limited time period of two years.
If a negative approval decision is made, the applying Evaluation Facility is informed of the reasons for the rejection before the application is formally rejected.


For quality assurance of the certification process, the approval regularly needs to be renewed. In addition, it is possible to restrict, suspend or withdraw approval in case of major compliance issues.

The full approval scheme can be found [here](./ApprovalScheme)



## Evaluation
[Todo: revise and differentiate assurance levels]
Figure [1](#fig:Certification_process){reference-type="ref"
reference="fig:Certification_process"} outlines the basic structure of
the certification process, together with the roles involved in this
process. The Certification Body and the Evaluation Facility belong to
the "Governance Body" category specified on the Business Layer (see
section 3.1.1). The tasks of these roles with regard to the
certification process are outlined in the following paragraphs. An
in-depth description of their responsibilities can be found in Part 1 of
the White Paper Certification[^2].

It should be noted that all roles described in this section are specific
to the International Data Spaces (i.e. terms such as "Certification
Body" should not be misunderstood to refer to an existing organization
already granting certificates).

![Certification process](./media/image79.png)

The certification process is divided into the following three phases:

1.  Application Phase: The main goal of this stage is the successful
    start of the IDS evaluation and certification process.

2.  Evaluation Phase: The main goal of this stage is the evaluation of
    an applicant or core component based on the defined evaluation
    criteria.

3.  Certification Phase: The main goal of this stage is the examination
    of the evaluation report by the certification body, which issues a
    certificate if the result of the evaluation process is positive.

After a successfully completed evaluation process, the Certification
Body awards an International Data Spaces certificate to the applicant.
This certificate has a limited validity period. In order to renew a
certificate before it expires, re-certification is required, taking into
account any relevant external developments that have happened in the
meantime. Similarly, re-certification is required if changes are made to
the target of certification.

For authentication and authorization, each IDS component must have a
valid X.509 certificate. These technical certificates digitally
represent the evaluation certificate and enable automated trust checks
between partners prior to data transfer within the International Data
Spaces.

A more detailed description of the phases and the issuing of digital
certificates can be found in Part 1 and 4 of the White Paper
Certification[^3].

[^3]: IDSA White Paper Certification -- Framework for the IDS
    Certification Scheme, Version 2.0
    https://www.internationaldataspaces.org/publications/whitepaper-certification/
