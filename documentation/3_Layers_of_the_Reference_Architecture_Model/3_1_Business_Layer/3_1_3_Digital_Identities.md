### Digital Identities

Establishing trust for data sharing and data exchange is a fundamental
requirement. The IDS-RAM defines two basic types of trust: 1) Static
Trust, based on the certification of operational environment and core technical
components, and 2) Dynamic Trust, based on active monitoring of
operational environment and core technical components. For data sharing and data
exchange in the IDS, some preliminary actions and interactions are
required. These are necessary for every participant, and involve the
Certification Body, Evaluation Facilities, and the Dynamic Attribute
Provisioning Service (DAPS). The figure below
illustrates the roles and interactions required for issuing a digital
identity in the IDS.

![ Interactions required for issuing a digital identity in the
IDS](./media/DigitalIdentities.png)

#### Participant

Certification is required for every participant and the majority of
roles in the IDS, as defined above. Certification refers both to the
organizational capabilities of the participant and the technical
capabilities of the core technical components.

#### Certification

Certification of a operational environment or core component involves the
[Certification Body](#) and an [Evaluation Facility](#).
Evaluation of a operational environment or a core component is executed upon request
of the participant and relies on the contract between the participant
and the Evaluation Facility. In the same way, a Service Provider can
request evaluation of a component. In this process, the Certification
Body is responsible for supervision of the Evaluation Facility involved.

#### Certification Authority

The Certification Authority is responsible for issuing, validating and
revoking [digital certificates](#). A digital certificate
is provided for a participant if both a valid certification for the
operational environment and a valid certification for the core component is
available. This means that the Certificate Authority provides an
IDS-ID for a combination of operational environment and core component. The digital
certificate is valid not exceeding the validity of both certifications,
operational environment certification and the certification of core component used
by the participant. The Certification Authority provides the digital
certificate to the participant upon request.

#### Dynamic Attribute Provisioning Service (DAPS)

The information resulting from the certification process is passed on to
the Dynamic Attribute Provisioning Service (DAPS). This includes master
data and information on [security profiles](#). The CA provides the details on the digital certificate
(public key and IDS-ID). The participant registers at the DAPS after
successfully deploying the digital certificate inside the component.

#### Dynamic Trust Monitoring (DTM)

Continuous monitoring of participants is necessary for classification of
the trustworthiness of all participants in the ecosystem. Dynamic Trust
Monitoring (DTM) implements a monitoring function for every IDS
Component. The DTM shares information with the DAPS to notify each of
the two participant in a data exchange transaction of the current level
of trustworthiness of the other participant.

#### Interactions

The roles described above interact with each other in a structured way.
In the following, a brief description of these interactions is given
(they are described in more detail in the remaining layers and perspectives of the RAM):

1.  **Certification request:** This is a direct interaction between a
    participant and an evaluation facility to trigger an evaluation
    process based on IDS certification criteria.

2.  **Notification of successful certification:** The Certification Body
    notifies the Certificate Authority of the successful certification
    of the Operational Environment and the Core Component. Validity of both
    certifications must be provided.

3.  **Generating the IDS-ID:** The CA generates a unique ID for the pair
    (operational environment and component) and issues a digital certificate.

4.  **Provisioning of X.509 Certificate:** The Certification Authority
    sends a digital certificate (X.509) to the participant in a secure
    and trustworthy way and notifies the DAPS.

5.  **Register:** After the digital certificate (X.509) is deployed
    inside the component, the component registers at the DAPS.

6.  **DTM Interaction**: The DTM and the DAPS exchange information on
    the behavior of the component, e.g. about security issues
    (vulnerabilities) or attempted attacks.
