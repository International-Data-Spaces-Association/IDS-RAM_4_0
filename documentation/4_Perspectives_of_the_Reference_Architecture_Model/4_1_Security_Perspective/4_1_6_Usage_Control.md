### **4.1.6**
1. #### **DATA ACCESS CONTROL**
In information security, access control restricts access to re- sources. Authorization is the process of granting permission to resources. There are several models of access control, such as Discretionary Access Control (DAC), Mandatory Ac- cess Control (MAC), Role-Based Access Control (RBAC), Attri- bute-Based Access Control (ABAC), etc. RBAC and ABAC are the most frequently used models.

The [XACML](http://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en.html) (eXtensible Access Control Markup Language) standard is used to introduce commonly used terms in the field of access control. XACML is a policy language to express ABAC rules. The main building blocks of the language are sub- ject, action, resource, and environment:

» The subject describes who is accessing a data asset (e.g., a user).

» The action describes what the subject wants to do with the data asset (e.g., read, write).

» The resource describes the data asset.

» The environment specifies the context of the action (e.g., time, location).

Figure ~~(4.11)~~ illustrates the XACML data flow diagram and the main actors or components to implement it: the Policy En- forcement Point (PEP), the Policy Decision Point (PDP), the Policy Information Point (PIP), and the Policy Administration Point (PAP).

» In general, attributes can describe anything or anyone. Nevertheless, they can be divided into four major catego- ries:

» Subject attributes, describing the user by e.g. their age, role, or clearance;

» Action attributes, describing the intended action (e.g. read, write, or delete);

» Resource (or object) attributes, describing the resource it- self (e.g. object type, location, or classification);

» Context (or environment) attributes, addressing time, lo- cation, or other dynamic aspects.

In the IDS, access control is a resource-centric regulation of ac- cess requests from subjects (i.e., IDS participants) to resourc- es (i.e., Data Services). Data Owners define attribute-based access control policies for their endpoints. In addition, they define the attribute values a subject must attest in order to grant access to the resource. These attributes may include:

» Specific identity of Connector(s) (only access requests from one or more specific Connectors will be granted);

» Connector attributes (only access requests from a Connec- tor that possesses specific attributes will be granted);

» Security profile requirements (only access requests from a Connector that meets specific security requirements will be granted; e.g., having a TPM >= 1.2 and doing application isolation).


![](Aspose.Words.e1c6ccdc-0aea-4ca5-b10d-f01d0ae154a3.004.png)

*Figure 4.11: XACML data flow diagram [Source: eXtensible Access Control Markup Language (XACML) Version 3.0 ]*

The actual access control decision has to be made within the Connector and can be implemented using technologies such as XACML or JAAS, depending on the implementation of the Connector. The IDS Security Architecture does not dictate a specific access control enforcement language or implemen- tation.

Alongside with data *access* control, regulating access to spe- cific digital resources (e.g., a service or a file), the IDS Security Architecture also supports data *usage* control. In general, the overall goal is to enforce data usage restrictions on the Data Consumer side after access to data has been granted.

2. #### **DATA ACCESS CONTROL**

Usage control is an extension of access control ~~(see figure 4.12)~~. It is about the specification and enforcement of re- strictions regulating what may be done with a data asset, and what not. Thus, usage control is concerned with requirements that pertain to data processing (obligations) rather than data access (provisions). Usage control is relevant in the context of intellectual property protection, regulatory compliance, and digital rights management.

*Figure 4.12: Data usage control – an extension of data access control*

Data usage control in the IDS basically works by attaching data usage policy information to data being exchanged and continuously controlling the way data is processed, aggregat- ed, or forwarded to other endpoints. This data-centric per- spective allows Data Providers to continuously control *data flows*, rather than *accesses to services*. At configuration time, data usage policies support developers and administrators in setting up correct data flows.

At runtime, data usage control enforcement prevents IDS Connectors from handling data in an undesired way (for ex- ample, by forwarding personal data to public endpoints). Thus, data usage control is both a tool for system integrators to ensure they are not building an architecture that violates security requirements, and an audit mechanism providing ev- idence of compliant data usage.

The following examples illustrate security requirements that cannot be achieved by data access control, but require da- ta-centric usage control:

» **SECRECY:** Classified data must not be forwarded to nodes which do not have the respective clearance.

» **INTEGRITY:** Critical data must not be modified by untrust- ed nodes, as otherwise its integrity cannot be guaranteed anymore.

» **TIME TO LIVE:** Data must be deleted from storage after a certain period of time.

»  **ANONYMIZATION BY DATA AGGREGATION:** Personal

data may be used only in an aggregated form by untrusted parties. To do so, a sufficient number of distinct data re- cords must be aggregated in order to prevent deano- nymization of individual records.

»   **ANONYMIZATION BY DATA SUBSTITUTION**: Data allowing personal identification (e.g., faces in video files) must be replaced by an adequate substitute (e.g., pixelized) in order to guarantee that individuals cannot be deanonymized.

» **SEPARATION OF DUTY**: Two datasets from competitive entities (e.g., two automotive OEMs) must never be aggregated or processed by the same service.

» **USAGE SCOPE:** Data may only serve as input for data pipes within the Connector; it must never leave the Connector and be sent to an external endpoint.

It is important to note that the purpose of data usage control is to allow the specification of such constraints and enforcing them in the respective system. A precondition of data usage control is that the enforcement mechanism itself is trusted; i.e., data usage control itself does not establish trust in an endpoint, but rather builds upon an existing trust relation- ship and facilitates enforcement of legal or technical require- ments, such as service level agreements (SLAs) or data privacy regulations. Thus, users must be aware that data usage con- trol will only provide certain enforcement guarantees if ap- plied on highly trusted platforms, such as Trusted Connectors in the International Data Spaces ~~(see Section 3.2).~~











#### **2**
1. ##### **TECHNICAL ENFORCEMENT, ORGANIZATIONAL RULES, AND LEGAL CONTRACTS**
Data usage control can be implemented by means of a ma- chine-readable contract, which is expected to be fulfilled by a party. It is a way to track and trace data as it is used within different systems and to collect evidence of the violation of agreed usage constraints. With that in mind, solutions range from organizational rules or legal contracts to completely technical ways of enforcing usage restrictions. For example, an organizational rule (e.g. a company policy) could state that employees must not use removable storage devices, such as USB sticks. Similarly, a technical form of enforcement, such as group policies specified by the Windows operating system, can prevent employees from using removable storage devic- es. In some scenarios, organizational rules, legal contracts, and technical rules can be used interchangeably. In other scenarios, the three forms can be used to complement each other. In the long run, it can be expected that organization- al rules and legal contracts will increasingly be replaced by technical forms of enforcement (as illustrated in ~~Figure 4.13).~~

Enforcement of data usage restrictions can be characterized and implemented in different forms. Organizational rules or legal contracts can be substituted, or at least accompanied, by technical solutions, which introduce a new level of secu- rity. Vice versa, technical solutions can be accompanied by organizational rules or legal contracts (e.g., to compensate missing capabilities of the technical solution).

Although it is a commonly used solution to address data us- age control restrictions by organizational rules, the IDS-RAM focuses on technical enforcement.
To enforce data usage restrictions, a system’s actions need to be monitored and potentially intercepted by control points (i.e., Policy Enforcement Points, PEPs). These actions must be judged by a decision engine (i.e., a Policy Decision Point, PDP) for requesting permission or denial. In addition to just allowing or denying an action, the decision engine may also require modification of the action. A PEP component encap- sulates the enforcement.

Enforcement relies on a decision. The PDP has the respon- sibility to answer incoming requests (e.g., system actions) from a PEP in the form of a decision (see Figure ~~4.14)~~. De- cision-making based on usage restriction is also called (poli- cy) evaluation. There are several types of evaluation, such as event-based or flow-based approaches.

For event-based systems, data usage transactions are repre- sented as events including attributes to characterize the data usage. Event processing can be differentiated into simple pro- cessing (e.g., event-condition-action paradigm) and stream processing (e.g., sliding window) of events. The terms ”event stream processing” and “complex event processing” are often used interchangeably.


![](Aspose.Words.e1c6ccdc-0aea-4ca5-b10d-f01d0ae154a3.014.png)

*Figure 4.13: Technical enforcement vs. organizational/legal enforcement*

For example: It is possible to model the transition of data as an event with attributes about the data itself and the recipient. The attributes contain metadata and information on the tar- get system (e.g., supplier management system). The decision engine makes a deny decision if the target system does not correspond to the expected supplier management system.
![](Aspose.Words.e1c6ccdc-0aea-4ca5-b10d-f01d0ae154a3.018.png)
*Figure 4.14: Communication Policy Enforcement Point and Policy Decision Point*

The policy decision may also depend on additional informa- tion that is not present in the intercepted system action it- self. This includes information about the context, such as data flows or the geographical location of an entity. It is also possi- ble to specify pre- or post-conditions that have to hold before (e.g., integrity check of the environment) and after (e.g., data item is deleted after usage) decision-making. In addition, it is possible to define on-conditions that have to hold during us- age (e.g., only during business hours). These conditions usual- ly specify constraints and permissions that have to be fulfilled before, during, and after using data (~~see Figure 4.15)~~.

A Policy Information Point (PIP) provides missing information for decision-making. In addition, such a component can be used to get contextual information for or about the system action intercepted (e.g., data flow information, geolocation of the requesting device).


![](Aspose.Words.e1c6ccdc-0aea-4ca5-b10d-f01d0ae154a3.019.png)

*Figure 4.15: Usage Control Pre-, On-, and Post-Conditions*

2. ##### **SPECIFICATION, MANAGEMENT, AND NEGOTIATION**
Another important aspect of data usage control is the specifi- cation and management of usage restrictions. Data Providers have to express data usage restrictions in a more or less for- mal way. For technical enforcement, the specification must produce a machine-readable output. The Policy Administra- tion Point (PAP) is the entry point for specification of usage policies, often via a user-friendly graphical interface.

A Policy Management Point (PMP) is responsible for the man- agement of usage policies. Hence, the component is con- cerned with the policy’s lifecycle. This includes instantiation, negotiation, deployment, and revocation of usage restric- tions, as well as conflict detection and resolution.

There are two ways to make usage restriction information available:

1. Usage restriction policy information can be attached to the data that is about to be exchanged. This type of policy is called sticky policy45. Following this approach, data is en- crypted before it is sent to a Data Consumer, and it can only be decrypted if the Data Consumer fully and explicitly accepts the usage restrictions specified.

1. A usage restriction policy can be stored independently of the data it relates to (for instance, in a central component, such as a PMP/PRP). In this case, the management compo- nent has the responsibility to exchange usage restriction information between different systems.

The management of usage policies becomes especially im- portant when data is to be exchanged across system bound- aries. Every time data crosses system boundaries, the target system must be prepared for the protection of incoming data (i.e. it has to deploy the corresponding policy).

Policy negotiation is also part of policy management. As en- forcement mechanisms can work differently across different systems or technologies, abstract policies may have different instantiations. Hence, usage policies must always be instanti- ated on the target system.

3. ##### **USAGE CONTROL BUILDING BLOCKS**
This section outlines which components the International Data Spaces uses to integrate data usage control technolo- gies. The first subsection deals with the IDS Information Mod- el and its modules addressing data usage control. The sub- sequent sections are about the Trusted Connector and the Apache Camel interceptor.

4. ##### **INFORMATION MODEL**
The IDS Information Model is a modular meta-model (ontol- ogy) describing the capabilities of IDS infrastructure compo- nents, such as the Connector or the Data Endpoints. Descrip- tions of data provided by Data Endpoints are published at dedicated Broker registries, allowing potential Data Consum- ers to search for and identify data that is relevant (semantics) and applicable (quality) for their particular purpose, and to assess in advance data’s affordability (price) and usability (re- strictions).

Extending the Open Digital Rights Language ([ODRL](tps://www.w3.org/community/odrl/model/2.1/)), a W3C standard, the Information Model’s Usage Control module provides machine-readable specifications of usage control policies ~~(see section 3.4.4.1.1)~~. These specify actions that a party is prohibited or permitted to do with regard to given a data asset. In addition, they codify any potentially involved duties. Despite a simple core model, which is depicted in Figure ~~(4.16)~~, ODRL policies are a formal way to declaratively ex- press usage contracts at a specification level. This way, the In- formation Model provides a technology-agnostic, consistent representation of usage control policies across the Interna- tional Data Spaces.

In order to implement and enforce usage policies at a specifi- cation level within individual target environments, it is neces- sary to map organizational and technical measures to the in- dividual target environments. While organizational measures are out of scope here, technical measures involve a variety of additional information sources (PIPs) and tight integra- tion with the host environment (PEPs). Here, the Information Model enhances ODRL constructs via predefined extension “hooks” to support mapping onto lower-level, implementa- tion-oriented policy languages (e.g., IND²UCE XML).


45 M. C. Mont and S. Pearson, “Sticky Policies: An Approach for Managing Privacy across Multiple Parties,” Computer, pp. 60-68, 09 September 2011.

46 R. Iannella, S. Guth, D. Paehler and A. Kasten, “ODRL Version 2.1 Core Model,” 05 03 2015. [Online]. Available: ht[tps://www.w3.org/community/odrl/model/2.1/.](http://www.w3.org/community/odrl/model/2.1/)


![](Aspose.Words.e1c6ccdc-0aea-4ca5-b10d-f01d0ae154a3.024.png)
*Figure 4.16: ODRL Core Model 2.1 (ODRL Version 2.1 Common Vocabulary Final Specification: 5 March 2015)*

For example, the ODRL Constraint class expresses logical con- ditions that govern the applicability of a Rule. Here, an Oper- ator *(eq)* relates the Left Operand (a predicate like *absolute- Position*) to a Right Operand (dynamic or predefined value). On the one side, the Information Model extends the group of [predefined predicates](http://www.w3.org/TR/odrl-vocab/#term-LeftOperand) in order to support decision-making in particular scenarios of the IDS, such as [data residency;](http://www.omg.org/data-residency/) on the other side, it defines a configuration overlay (b) to tie the abstract predicates (a) to an operable programming logic sup- plied by the respective target environment (c), as illustrated by ~~Figure 4.17~~.


![](Aspose.Words.e1c6ccdc-0aea-4ca5-b10d-f01d0ae154a3.027.png)

*Figure 4.17: Examples of mapping among policy language levels*
