### Privacy consequences ###

Enterprises are advised well enough to start early on with good privacy practices. One of the activities that every
Company can do is the proper data classification and separation of data. The following is a list of more advanced privacy
enhancing technologies that currently exists, but experts in any of these technologies are rare and hard to find.

#### PET (Privacy Enhancing Technologies) ####

Please also refer to [the publication of the European Union Agency for Cybersecurity](https://www.enisa.europa.eu/publications/data-protection-engineering).

##### Divide and conquer #####

One of the things that every company can do: Data records are not stored together, but rather divided up into several chunks.
correlation of data is then ensured by special pseudonymization/anonymization techniques. Even if one data set is lost, an
attacker cannot draw further conclusions and the user/employee record stays protected.

##### Obfuscation #####

Adding random data or noise data to existing records in order to disturb certain kind of computations or to distract an potential
attacker. Obfuscation is not a strong privacy-preserving technique, but allows to „cloak“ data with a certain degree of uncertainty.
E.g. hashing content effectively hides that data content, but as soon as the initial data is known, hashing can be repeated and looses
it’s protective power.

##### TLS / E2E encryption #####

Although TLS does protect data in transit in an efficient and widely accepted way, it is not the best measure in terms of
privacy protection. E.g. scinetist were able to identify Google search queries from the size of data TLS protected data packets
in the internet due to the still available metadata. The need for End2End encryption arises out of the privacy risks mentioned above.
As Intermediate broker / provider are able to see customer data, it is only prudent to encrypt the data in a way that allows
the use for the primary purpose only.

##### Transport Layer Privacy / Source Anonymitiy #####

helps to achieve untracability, without loosing the access to the data itself. Protocol metadata is one important source to draw
conclusion and to correlate data, transport layer privacy or source anonymity is another important aspect to consider. For highly
confidential data it is therefore required to hide/obfuscate source information from the data set. Although there can be no data
exchange to the right destination without metadata, there are existing technologies that do obfuscate and therefore limit the
ability of each company to draw conclusions that may impact privacy.

##### Secure Multiparty Computation #####

A set of algorithm that allows to compute e.g. the mean of a dataset, without exposing each single record. Multiparty computations
exists for a variety of problems, but do not protect single records or entities.

##### Pseudonymization #####

Replaces the information about a user with a random identitfier to prevent correlation of data and to discourage an attacker.
Pseudonyms can be placed either on groups or on individual records.

##### PPRL (Privacy preserving record linkage) / Enhanced Privacy ID (EPID) #####

PPRL links allow to create an identifier which resembles a data record. This PPRL link can then be shared to link data records
during analytics, but it is not possible to link back to the initial data record. In a similar way

##### Zero-Knowledge Proof #####

Prove to another party that you are who you are, without revealing the information (the "proof“), but rather the fact that you certainly know the information.

##### (Fully-) homomorphic encryption #####

As set of encryption algorithms that allows a limited set of computations on the encrypted data without destroying the encryption.

##### Functional encryption #####

A more general term for any advanced encryption scheme. The required key size is usually larger, the possible applications
have to be choosen from the variety of possible algorithms. e.g. proxy re-encryption allows to send a message to an intermediate
broker, but the message can be re-encrypted to a final recipient at a later point in time.

#### Minimum required risk mitigations ####

While the above „hard“ privacy technologies are means that need to be tailored towards a specific use case, enterprise are
advised to not rely on these technologies only, but rather look out to strengthen their organization capabilities.

As already mentioned, applying a data classification scheme that is aligned with the business goal helps. Companies have started to
assign the role of the Chief Information Security Officer (CISO) as a response to the increasing need to protect their company from
cybersecurity attacks and fraud. In addition, companies should think about assigning the role of a Chief Privacy Officer (CPO)
to reflect on the increasing need to address risks in relation with privacy laws and regulations.

When looking at the current state of technology, then companies should at least be familiar with the guidelines and rules that have been set
out by the [OWASP TopTen privacy risks]((https://owasp.org/www-project-top-10-privacy-risks/)). Addressing these TopTen is certainly a good step into the right direction:

| 2021   | Title / Description                              | F   | R   | T
| ------- |  ----------------------------------------------- | --- | --- | ---
| P1      | Web Application Vulnerabilities      | H   | VH  | T
|         | Apply SDLC principles and use external pentesters to boost application security |   |   |
| P2      | Operator-sided Data Leakage                      | H   |  VH   | O+T
|         | Audit the operator on a regular basis / encrypt data |   |   |
| P3      | Insufficient Data Breach Response                | H  | VH | O+T
|         | create, maintain and test the incident response plan |   |   |
| P4      | Consent on Everything                            | VH | H  | O+T
|         | consent should be voluntarily, collect for each purpose |   |   |
| P5      | Non-transparent Policies, Terms and Conditions   | VH  |  H   |  O
|         | lack of transparency leads to distrust and a deep sense of insecurity | | |
| P6      | Insufficient Deletion of User Data               | H | H | O+T
|         | Deletion of data after use                       |   |   |
| P7      | Insufficient Data Quality                | M | H |  O+T
|         | provide update forms / ask the user              |   |   |
| P8      | Missing or Insufficient Session Expiration       | M | VH | T
|         | automatically log our after x-hours / user education |   |   |
| P9      | Inability of Users to Access and Modify Data     | H | VH | O+T
|         | provide easy to use ways to access / change or delete data / data structure model |   |   |
| P10     | Collection of Data Not Required for the User-Consented Purpose | H | H | O
|         | define purpose and and collect / use only data needed / data minimization |   |   |

**Legend**

F = Frequency /
T = Technical Measure /
O = Organizational Measure /
L = Low is considered as an limited and calculated risks /
M = Medium risk/ frequency , impact is causing serious problems /
H = High risks / frequency is likely to happen, and the impact is devastating
VH = Very high risk / frequency almost certain to happen, impact is devastating
