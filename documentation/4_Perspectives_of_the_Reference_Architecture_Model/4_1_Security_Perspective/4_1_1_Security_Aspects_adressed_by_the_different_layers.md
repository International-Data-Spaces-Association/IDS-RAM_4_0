# SECURITY ASPECTS ADDRESSED BY THE DIFFERENT LAYERS OF THE IDS-RAM


## BUSINESS LAYER
Data spaces create value by interconnecting entities and exchanging data and services. To protect these value-driven business models, a sound security foundation is needed. Security aspects are crucial for the definition of roles and interaction patterns in the International Data Spaces and thus have indirect impact on the business layer. 

## PROCESS LAYER
To take security aspects into account on the Process Layer, it
is important that existing processes are permanently moni-
tored, validated, and redesigned, if need be. For example, to
allow trustworthy identification and authentication of Partic-
ipants using a central public key infrastructure (PKI), a Par-
ticipant must apply for a public key certificate that is regis-
tered in a central PKI and deployed inside its Connector. For
dynamic attribute support, an identity management server
needs to verify attributes before issuing access tokens. The
same is true for trustworthy operations of an App Store, for
which data must be verified and signed by a trusted entity be-
fore it can be uploaded. Security requirements directly shape the process layer. 

## INFORMATION LAYER
The Information Layer provides the means for Participants to
use a common vocabulary and common semantics to express
concepts and relationships between them. In doing so, it is
possible to specify access and usage control policies in a way
that these are understood by all Participants. The same is true
for access control requirements defining minimum security
profiles, which must be met before access is granted.

## SYSTEM LAYER
As the IDS Connector is the central technical component on the
System Layer, it is predominantly this gateway where the
security features of the International Data Spaces are imple-
mented. Presenting itself as the implementation of one of the security profiles,
it takes up all relevant security specifications and
requirements, and serves as the technological baseline for use
case implementations.

## FUNCTIONAL LAYER
Security requirements may restrict certain transactions or
operations in the International Data Spaces, or even prevent
them. However, security is also an enabling factor. Without
security, many use cases would not be possible (e.g., offering
sensitive data to trusted business partners). The concept of
data usage control allows Data Providers to attach data usage
policy information to their data in order to define how a Data
Consumer may use the data.
