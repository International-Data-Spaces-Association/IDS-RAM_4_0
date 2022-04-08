# Certification Processes

Participants and core components within the IDS ecosystem shall fulfill common requirements to ensure the security of data being processed in the IDS. Therefore, the certification of operational environments (as explained in [Section 4.2.3](../4_2_3_Operational_Environment_Certification.md) and core components (as explained in [Section 4.2.4](../4_2_4_Component_Certification.md) is mandatory. Involved partners are the Applicant, Evaluation Facility and the Certification Body which were introduced in [Section 4.2.2](../4_2_2_Roles.md). ```

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

However, the details for each phase differ slightly between the Assurance Levels as described below and illustrated in the figures.
For Assurance Level 1, the Applicant must apply directly to the Certification Body to trigger the start of the certification process. Once the Certification Body accepts the application, the Applicant is responsible for the Evaluation Phase by conducting a self-assessment and providing the results to the Certification Body. In the Certification Phase, the Certification Body reviews the self-assessment and issues the certificate, if the self-assessment meets the defined requirements.

![image](https://raw.githubusercontent.com/International-Data-Spaces-Association/IDS-RAM_4_0/79589bebf8bcfd15d5f547cb50effa6a16a7e25e/documentation/4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/media/Certification%20assurance%20level%201.png?token=ASQVSNBC5LZ7OC3IWLPKWS3CKBH3O)

Assurance Level 2 and 3 require an independent Evaluation Facility to conduct the evaluation of the component or operational environment. The Applicant must contract an Evaluation Facility which was approved as described in the first section of this chapter. Together, Applicant and Evaluation Facility finalize the application for certification with the Certification Body. Afterwards, the Evaluation Facility is responsible for carrying out the evaluation according to the IDS certification schema. The Evaluation Facility documents their progress and findings in an evaluation report which is passed on to the Certification Body at the end of the Evaluation Phase. In the Certification Phase, the Certification Body examines the evaluation report and issues a certificate, if the evaluation was conducted properly and led to a positive evaluation result.

![image](https://raw.githubusercontent.com/International-Data-Spaces-Association/IDS-RAM_4_0/79589bebf8bcfd15d5f547cb50effa6a16a7e25e/documentation/4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/media/Certification%20assurance%20level%202.png?token=ASQVSNGSBPULZQEXQ4KIWLDCKBH3O)

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
