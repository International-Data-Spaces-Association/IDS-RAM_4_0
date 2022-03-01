# Certification Processes

Participants and core components within the IDS ecosystem shall fulfill common requirements to ensure the security of data being processed in the IDS. Therefore, the certification of operational environments (as explained in [Chapter 4.2.3](../4_2_3_Operational_Environment_Certification.md) and core components (as explained in [Chapter 4.2.4](../4_2_4_Component_Certification.md) is mandatory. Involved partners are the Applicant, Evaluation Facility and the Certification Body which were introduced in [Chapter 4.2.2](../4_2_2_Roles.md). ```

## Approval of Evaluation Facilities
[TODO: Add chapter on approval of evaluation facilities ]

## Certification Process for Operational Environments and Core Components

Figures 1 and 2 outline the basic structure of
the certification process, according to the different assurance levels, together with the roles involved in this
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

The certification follows the same process for all certification profiles in Operational Environment and Component Certification. It consists of the following three phases:

1.  Application Phase: The main goal of this stage is the successful
    start of the IDS evaluation and certification process.

2.  Evaluation Phase: The main goal of this stage is the evaluation of
    an applicant or core component based on the defined evaluation
    criteria.

3.  Certification Phase: The main goal of this stage is the examination
    of the evaluation report by the certification body, which issues a
    certificate if the result of the evaluation process is positive.

For Assurance Level 1, the Applicant must apply directly to the Certification Body to trigger the start of the certification process. Once the Certification Body accepts the application, the Applicant is responsible for the Evaluation Phase by conducting a self-assessment and providing the results to the Certification Body. In the Certification Phase, the Certification Body reviews the self-assessment and issues the certificate, if the self-assessment meets the defined requirements.

![image](https://user-images.githubusercontent.com/77682996/155738445-479e9507-7415-4e16-b0dd-6d159d3d8528.png)

The second and third assurance level certification require an Evaluation Facility to conduct the evaluation of the component or operational environment. The applicant must apply for certification to an approved evaluation facility to carry out the evaluation according to the IDS certification schema. Provided the Evaluation Facility accepts the application, the evaluation will be conducted and an evaluation report will be generated. The Certification Body will examine the evaluation report and, if the result is possitive, issue a certificate.

![image](https://user-images.githubusercontent.com/77682996/155738509-f4477f71-aeb8-4de2-bbf1-53373ae919c5.png)
After a successfully completed evaluation process, the Certification
Body awards an International Data Spaces certificate to the Applicant.
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
