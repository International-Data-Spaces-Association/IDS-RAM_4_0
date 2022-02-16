# SECURITY ASPECTS ADDRESSED BY THE DIFFERENT LAYERS OF THE IDS-RAM

Since security generally covers non-functional aspects, security and trust serve as an enabler for functionalities such as data exchange. This results in security being a cross-cutting concern for the layers discussed in the core chapters of the RAM. 

## BUSINESS LAYER
Security delivers the means to create trust in the ecosystem and allows to create data value chains. The roles that are established in chapter [Chapter 3.1](../../3_Layers_of_the_Reference_Architecture_Model/3_1_Business_Layer/README.md) are used to establish these data value chains. 

## PROCESS LAYER
To take security aspects into account on the Process Layer, it is important that existing processes are permanently monitored, validated, and redesigned, if need be. For example, to allow trustworthy identification and authentication of Participants using a central public key infrastructure (PKI), a Participant must apply for a public key certificate that is registered in a central PKI and deployed inside its Connector. For dynamic attribute support, an identity management server needs to verify attributes before issuing access tokens. The same is true for trustworthy operations of an App Store, for which data must be verified and signed by a trusted entity before it can be uploaded.

## INFORMATION LAYER
The Information Layer provides the means for Participants to use a common vocabulary and common semantics to express concepts and relationships between them. In doing so, it is possible to specify access and usage control policies in a way that these are understood by all Participants. The same is true for access control requirements defining minimum security profiles, which must be met before access is granted.

## SYSTEM LAYER
As the Connector is the central technical component on the System Layer, it is predominantly the Connector where the
security features of the International Data Spaces are implemented. Being an extension of the Base Connector, the Trusted Connector takes up all relevant security specifications and requirements, and serves as the technological basis for use case implementations.

## FUNCTIONAL LAYER
Security requirements may restrict certain transactions or operations in the International Data Spaces, or even prevent them. However, security is also an enabling factor. Without security, many use cases would not be possible (e.g., offering sensitive data to trusted business partners). The concept of
data usage control allows Data Providers to attach data usage policy information to their data in order to define how a Data Consumer may use the data.
