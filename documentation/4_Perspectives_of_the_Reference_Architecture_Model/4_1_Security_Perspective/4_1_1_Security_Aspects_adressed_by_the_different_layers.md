### SECURITY ASPECTS ADDRESSED BY THE DIFFERENT LAYERS OF THE IDS-RAM ###

Since security generally covers non-functional aspects, security and trust serve as an enabler for functionalities such as data exchange. This results in security being a cross-cutting concern for the layers discussed in the core chapters of the RAM.

#### BUSINESS LAYER ####

Security delivers the means to establish trust in the ecosystem which is the basis for the sovereign data exchange and processing targeted. The roles that are established in [Section 3.1](../../3_Layers_of_the_Reference_Architecture_Model/3_1_Business_Layer/) are either responsible for setting up this trustworthy ecosystem as described in the trust model in [Section 4.1.2](./4_1_2_Identity_and_Trust_Management.md) or for adding services in the IDS that support the establishment of data value chains.

#### FUNCTIONAL LAYER ####

The IDS is intended as a trustworthy ecosystem for sovereign data exchange. This leads to various functional requirements regarding data exchange and data processing which are defined in [Section 3.2](../../3_Layers_of_the_Reference_Architecture_Model/3_2_Functional_Layer/). Security aspects and the trust model used in the IDS [Section 4.1.2](./4_1_2_Identity_and_Trust_Management.md) shape these requirements by enabling or restricting some transactions or operations in the International Data Spaces. Without security, many use cases would not be possible (e.g., offering sensitive data to trusted business partners). The concept of
data usage control described in [Section 4.1.6](./4_1_6_Usage_Control.md) allows Data Providers to attach data usage policy information to their data in order to define how a Data Consumer may use the data.

#### INFORMATION LAYER ####

The Information Layer ([Section 3.4](../../3_Layers_of_the_Reference_Architecture_Model/3_4_Information_Layer/)) provides the means for participants to use a common vocabulary and common semantics to express concepts and relationships between them. In doing so, it is possible to, e.g., describe a connector setup or specify access and usage control policies in a way that these are understood by all participants.

#### PROCESS LAYER ####

To take security aspects into account on the Process Layer([Section 3.3](../../3_Layers_of_the_Reference_Architecture_Model/3_3_Process_Layer/)), it is important that existing processes reflect the defined Trust Model ([Section 4.1.2](./4_1_2_Identity_and_Trust_Management.md)) and are permanently monitored, validated, and redesigned, if need be. For example, to allow trustworthy identification and authentication of components using a public key infrastructure (PKI), the operator of this component must generate a key pair on the component, apply for a public key certificate from the Certificate Authority (CA) and provision this certificate onto the component. For dynamic attribute support, the provider of the Dynamic Attribute Provisioning Service (DAPS) needs to verify the attributes which it will confirm with the Dynamic Attribute Tokens (DATs). The same is true for trustworthy operations of an App Store, for which data must be verified and signed by a trusted entity before it can be uploaded.

#### SYSTEM LAYER ####

The IDS components described in the System Layer ([Section 3.5](../../3_Layers_of_the_Reference_Architecture_Model/3_5_System_Layer/))) form the IDS ecosystems. While the System Layer focuses on the general setup and functionality of these components, the security requirements and concepts for these components are mostly equivalent for the different components which are in essence either IDS connectors or specific types of connectors. The security perspective adds the overall view on the concepts used to ensure trust and security for all these components.
