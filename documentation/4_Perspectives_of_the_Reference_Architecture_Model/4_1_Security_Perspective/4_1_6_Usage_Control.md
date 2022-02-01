### **4.1.6 DATA USAGE CONTROL** 
<!-- TOC -->

- [**4.1.6 DATA USAGE CONTROL**](#416-data-usage-control)
  - [**4.1.6.1 INTRODUCTION**](#4161-introduction)
  - [**4.1.6.2 ORGANIZATIONAL RULES AND LEGAL CONTRACTS**](#4162-organizational-rules-and-legal-contracts)
  - [**4.1.6.3 ROLES INVOLVED IN USAGE CONTROL**](#4163-roles-involved-in-usage-control)
    - [**BROKER**](#broker)
    - [**CONNECTOR**](#connector)
    - [**CLEARING HOUSE**](#clearing-house)
    - [**APP STORE**](#app-store)
    - [**APP PROVIDER**](#app-provider)
  - [**4.1.6.4 INFORMATION MODEL**](#4164-information-model)
  - [**4.1.6.5 IDS Policy Language**](#4165-ids-policy-language)
  - [**4.1.6.6 IDS Contract and Usage Policies**](#4166-ids-contract-and-usage-policies)
  - [**4.1.6.7 NEGOTIATION**](#4167-negotiation)
  - [**4.1.6.8 MANAGEMENT**](#4168-management)
  - [**4.1.6.9 USAGE CONTROL IN A CONNECTOR**](#4169-usage-control-in-a-connector)
  - [**4.1.6.10 APACHE CAMEL INTERCEPTOR (EXAMPLE)**](#41610-apache-camel-interceptor-example)
  - [**4.1.6.11 CONTEXT INFORMATION AND OBLIGATION FULLFILLMENT**](#41611-context-information-and-obligation-fullfillment)
  - [**4.1.6.12 DATA PROVENANCE TRACKING**](#41612-data-provenance-tracking)
    - [**OPERATING PRINCIPLE**](#operating-principle)
    - [**ARCHITECTURE**](#architecture)
    - [**COMMUNICATION**](#communication)
    - [**INTEGRATION WITH DISTRIBUTED USAGE CONTROL**](#integration-with-distributed-usage-control)
  - [**4.1.6.13 DATA PROVENANCE TRACKING ADDRESSED BY THE DIFFERENT LAYERS**](#41613-data-provenance-tracking-addressed-by-the-different-layers)
    - [**BUSINESS LAYER**](#business-layer)
    - [**FUNCTIONAL LAYER**](#functional-layer)
    - [**PROCESS LAYER**](#process-layer)
    - [**INFORMATION LAYER**](#information-layer)
    - [**SYSTEM LAYER**](#system-layer)

<!-- /TOC -->

#### **4.1.6.1 INTRODUCTION**

[comment]: <> (1. #### **DATA ACCESS CONTROL**)
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

![image](http://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en_files/image002.gif)

_Figure 4.11: XACML data flow diagram [Source: eXtensible Access Control Markup Language (XACML) Version 3.0 ]_

The actual access control decision has to be made within the Connector and can be implemented using technologies such as XACML or JAAS, depending on the implementation of the Connector. The IDS Security Architecture does not dictate a specific access control enforcement language or implemen- tation.

Alongside with data _access_ control, regulating access to spe- cific digital resources (e.g., a service or a file), the IDS Security Architecture also supports data _usage_ control. In general, the overall goal is to enforce data usage restrictions on the Data Consumer side after access to data has been granted.

[comment]: <> (2. #### **DATA USAGE CONTROL**)

Usage control is an extension of access control ~~(see figure 4.12)~~. It is about the specification and enforcement of re- strictions regulating what may be done with a data asset, and what not. Thus, usage control is concerned with requirements that pertain to data processing (obligations) rather than data access (provisions). Usage control is relevant in the context of intellectual property protection, regulatory compliance, and digital rights management.

![image](4_1_6_images/UC-Definition.drawio.png)

_Figure 4.12: Data usage control – an extension of data access control_

Data usage control in the IDS basically works by attaching data usage policy information to data being exchanged and continuously controlling the way data is processed, aggregat- ed, or forwarded to other endpoints. This data-centric per- spective allows Data Providers to continuously control _data flows_, rather than _accesses to services_. At configuration time, data usage policies support developers and administrators in setting up correct data flows.

At runtime, data usage control enforcement prevents IDS Connectors from handling data in an undesired way (for ex- ample, by forwarding personal data to public endpoints). Thus, data usage control is both a tool for system integrators to ensure they are not building an architecture that violates security requirements, and an audit mechanism providing ev- idence of compliant data usage.

The following examples illustrate security requirements that cannot be achieved by data access control, but require da- ta-centric usage control:

» **SECRECY:** Classified data must not be forwarded to nodes which do not have the respective clearance.

» **INTEGRITY:** Critical data must not be modified by untrust- ed nodes, as otherwise its integrity cannot be guaranteed anymore.

» **TIME TO LIVE:** Data must be deleted from storage after a certain period of time.

» **ANONYMIZATION BY DATA AGGREGATION:** Personal

data may be used only in an aggregated form by untrusted parties. To do so, a sufficient number of distinct data re- cords must be aggregated in order to prevent deano- nymization of individual records.

» **ANONYMIZATION BY DATA SUBSTITUTION**: Data allowing personal identification (e.g., faces in video files) must be replaced by an adequate substitute (e.g., pixelized) in order to guarantee that individuals cannot be deanonymized.

» **SEPARATION OF DUTY**: Two datasets from competitive entities (e.g., two automotive OEMs) must never be aggregated or processed by the same service.

» **USAGE SCOPE:** Data may only serve as input for data pipes within the Connector; it must never leave the Connector and be sent to an external endpoint.

It is important to note that the purpose of data usage control is to allow the specification of such constraints and enforcing them in the respective system. A precondition of data usage control is that the enforcement mechanism itself is trusted; i.e., data usage control itself does not establish trust in an endpoint, but rather builds upon an existing trust relation- ship and facilitates enforcement of legal or technical require- ments, such as service level agreements (SLAs) or data privacy regulations. Thus, users must be aware that data usage con- trol will only provide certain enforcement guarantees if ap- plied on highly trusted platforms, such as Trusted Connectors in the International Data Spaces ~~(see Section 3.2).~~

[comment]: <> (1. ##### **TECHNICAL ENFORCEMENT, ORGANIZATIONAL RULES, AND LEGAL CONTRACTS**)

#### **4.1.6.2 ORGANIZATIONAL RULES AND LEGAL CONTRACTS**

Data usage control can be implemented by means of a ma- chine-readable contract, which is expected to be fulfilled by a party. It is a way to track and trace data as it is used within different systems and to collect evidence of the violation of agreed usage constraints. With that in mind, solutions range from organizational rules or legal contracts to completely technical ways of enforcing usage restrictions. For example, an organizational rule (e.g. a company policy) could state that employees must not use removable storage devices, such as USB sticks. Similarly, a technical form of enforcement, such as group policies specified by the Windows operating system, can prevent employees from using removable storage devic- es. In some scenarios, organizational rules, legal contracts, and technical rules can be used interchangeably. In other scenarios, the three forms can be used to complement each other. In the long run, it can be expected that organization- al rules and legal contracts will increasingly be replaced by technical forms of enforcement (as illustrated in ~~Figure 4.13).~~

Enforcement of data usage restrictions can be characterized and implemented in different forms. Organizational rules or legal contracts can be substituted, or at least accompanied, by technical solutions, which introduce a new level of secu- rity. Vice versa, technical solutions can be accompanied by organizational rules or legal contracts (e.g., to compensate missing capabilities of the technical solution).

Although it is a commonly used solution to address data us- age control restrictions by organizational rules, the IDS-RAM focuses on technical enforcement.
To enforce data usage restrictions, a system’s actions need to be monitored and potentially intercepted by control points (i.e., Policy Enforcement Points, PEPs). These actions must be judged by a decision engine (i.e., a Policy Decision Point, PDP) for requesting permission or denial. In addition to just allowing or denying an action, the decision engine may also require modification of the action. A PEP component encap- sulates the enforcement.

Enforcement relies on a decision. The PDP has the respon- sibility to answer incoming requests (e.g., system actions) from a PEP in the form of a decision (see Figure ~~4.14)~~. De- cision-making based on usage restriction is also called (poli- cy) evaluation. There are several types of evaluation, such as event-based or flow-based approaches.

For event-based systems, data usage transactions are repre- sented as events including attributes to characterize the data usage. Event processing can be differentiated into simple pro- cessing (e.g., event-condition-action paradigm) and stream processing (e.g., sliding window) of events. The terms ”event stream processing” and “complex event processing” are often used interchangeably.

![image](4_1_6_images/Technical_vs_Organizational.drawio.png)

_Figure 4.13: Technical enforcement vs. organizational/legal enforcement_

For example: It is possible to model the transition of data as an event with attributes about the data itself and the recipient. The attributes contain metadata and information on the tar- get system (e.g., supplier management system). The decision engine makes a deny decision if the target system does not correspond to the expected supplier management system.

![image](4_1_6_images/Communication-PEP-and-PDP.drawio.png)

_Figure 4.14: Communication Policy Enforcement Point and Policy Decision Point_

The policy decision may also depend on additional informa- tion that is not present in the intercepted system action it- self. This includes information about the context, such as data flows or the geographical location of an entity. It is also possi- ble to specify pre- or post-conditions that have to hold before (e.g., integrity check of the environment) and after (e.g., data item is deleted after usage) decision-making. In addition, it is possible to define on-conditions that have to hold during us- age (e.g., only during business hours). These conditions usual- ly specify constraints and permissions that have to be fulfilled before, during, and after using data (~~see Figure 4.15)~~.

A Policy Information Point (PIP) provides missing information for decision-making. In addition, such a component can be used to get contextual information for or about the system action intercepted (e.g., data flow information, geolocation of the requesting device).

![image](4_1_6_images/usage-control-conditions.drawio.png)

_Figure 4.15: Usage Control Pre-, On-, and Post-Conditions_

Another important aspect of data usage control is the specification and management of usage restrictions. Data Providers have to express data usage restrictions in a more or less for- mal way. For technical enforcement, the specification must produce a machine-readable output. The Policy Administra- tion Point (PAP) is the entry point for specification of usage policies, often via a user-friendly graphical interface.

#### **4.1.6.3 ROLES INVOLVED IN USAGE CONTROL**

Usage control is a cross-sectional concept and technology, which involves several IDS Roles.

##### **BROKER**

The IDS Broker manages connector self-descriptions that can contain Usage Policies. Therefore the Broker must be able to support Usage Policies. In addition the connector self-de- scription itself may be subject of Usage Policies.

##### **CONNECTOR**

The Connector is the main technical component for imple- menting usage control. Hence, usage control enhanced Con- nectors, such as the Trusted Connector, contain relevant components to perform usage control enforcement as Data Consumer (PEPs, such as the Apache Camel interceptor; PDPs, PMPs). However, PMPs and PDPs need not be part of the Con- nector. In addition, Connectors as Data Providers should pro- vide the technology-dependent policies to the data they pro- vide – for all kinds of systems and enforcement technologies that are part of the ecosystem.

##### **CLEARING HOUSE**

By means of Data Provenance Tracking (as described in the next section), it is possible to track the usage of data and the enforcement of usage restrictions. The Clearing House is able to use this data later on.

##### **APP STORE**

Data Apps can take advantage of usage control technology. The IDS App Store needs to be able to provide information as to whether a Data App implements such technology.

##### **APP PROVIDER**

For Data Apps to take advantage of usage control technology, App Providers need to implement certain components, such as control points (i.e., PEPs), into their application.

#### **4.1.6.4 INFORMATION MODEL**

The IDS Information Model is a modular meta-model (ontol- ogy) describing the capabilities of IDS infrastructure compo- nents, such as the Connector or the Data Endpoints. Descrip- tions of data provided by Data Endpoints are published at dedicated Broker registries, allowing potential Data Consum- ers to search for and identify data that is relevant (semantics) and applicable (quality) for their particular purpose, and to assess in advance data’s affordability (price) and usability (re- strictions).

Extending the Open Digital Rights Language ([ODRL](tps://www.w3.org/community/odrl/model/2.1/)), a W3C standard, the Information Model’s Usage Control module provides machine-readable specifications of usage control policies ~~(see section 3.4.4.1.1)~~. These specify actions that a party is prohibited or permitted to do with regard to given a data asset. In addition, they codify any potentially involved duties. Despite a simple core model, which is depicted in Figure ~~(4.16)~~, ODRL policies are a formal way to declaratively ex- press usage contracts at a specification level. This way, the In- formation Model provides a technology-agnostic, consistent representation of usage control policies across the Interna- tional Data Spaces.

In order to implement and enforce usage policies at a specifi- cation level within individual target environments, it is neces- sary to map organizational and technical measures to the in- dividual target environments. While organizational measures are out of scope here, technical measures involve a variety of additional information sources (PIPs) and tight integra- tion with the host environment (PEPs). Here, the Information Model enhances ODRL constructs via predefined extension “hooks” to support mapping onto lower-level, implementa- tion-oriented policy languages (e.g., IND²UCE XML).

45 M. C. Mont and S. Pearson, “Sticky Policies: An Approach for Managing Privacy across Multiple Parties,” Computer, pp. 60-68, 09 September 2011.

46 R. Iannella, S. Guth, D. Paehler and A. Kasten, “ODRL Version 2.1 Core Model,” 05 03 2015. [Online]. Available: ht[tps://www.w3.org/community/odrl/model/2.1/.](http://www.w3.org/community/odrl/model/2.1/)

![odrl](https://www.w3.org/TR/odrl-model/00Model.png)

_Figure 4.16: ODRL Core Model 2.1 (ODRL Version 2.1 Common Vocabulary Final Specification: 5 March 2015- changed to latest version)_

For example, the ODRL Constraint class expresses logical con- ditions that govern the applicability of a Rule. Here, an Oper- ator _(eq)_ relates the Left Operand (a predicate like _absolute- Position_) to a Right Operand (dynamic or predefined value). On the one side, the Information Model extends the group of [predefined predicates](http://www.w3.org/TR/odrl-vocab/#term-LeftOperand) in order to support decision-making in particular scenarios of the IDS, such as [data residency;](http://www.omg.org/data-residency/) on the other side, it defines a configuration overlay (b) to tie the abstract predicates (a) to an operable programming logic sup- plied by the respective target environment (c), as illustrated by ~~Figure 4.17~~.

![image](4_1_6_images/mapping-of-policy-languages.drawio.png)

_Figure 4.17: Examples of mapping among policy language levels_

#### **4.1.6.5 IDS Policy Language**

&nbsp;

#### **4.1.6.6 IDS Contract and Usage Policies**

&nbsp;

#### **4.1.6.7 NEGOTIATION**

Policy negotiation is also part of policy management. As en- forcement mechanisms can work differently across different systems or technologies, abstract policies may have different instantiations. Hence, usage policies must always be instanti- ated on the target system.

#### **4.1.6.8 MANAGEMENT**

A Policy Management Point (PMP) is responsible for the man- agement of usage policies. Hence, the component is con- cerned with the policy’s lifecycle. This includes instantiation, negotiation, deployment, and revocation of usage restric- tions, as well as conflict detection and resolution.

There are two ways to make usage restriction information available:

1. Usage restriction policy information can be attached to the data that is about to be exchanged. This type of policy is called sticky policy45. Following this approach, data is en- crypted before it is sent to a Data Consumer, and it can only be decrypted if the Data Consumer fully and explicitly accepts the usage restrictions specified.

2. A usage restriction policy can be stored independently of the data it relates to (for instance, in a central component, such as a PMP/PRP). In this case, the management compo- nent has the responsibility to exchange usage restriction information between different systems.

The management of usage policies becomes especially im- portant when data is to be exchanged across system bound- aries. Every time data crosses system boundaries, the target system must be prepared for the protection of incoming data (i.e. it has to deploy the corresponding policy).

#### **4.1.6.9 USAGE CONTROL IN A CONNECTOR**

Usage control only makes sense in an ecosystem where a certain level of trust can be established and maintained for all participants. To enable the establishment of trusted rela- tionships, the central technological components used for data processing and data exchange need to be trustworthy. The IDS Connector is the central component for data exchange and data processing in the International Data Spaces, and thus a central component that needs to be trusted.

The IDS Connector (see previous sections) focuses on security and delivers a trusted platform, incorporating crucial build- ing blocks:

» identity & trust management for authenticating communi- cating parties (e.g., other Connectors) and shaping trusted relationships between partners;

» a trusted platform as a baseline for secure data process- ing;

» trustworthy communication based on authenticated and encrypted connections; and

» access & usage control.

Instances of the Trusted Connector enable remote integrity verification, so the integrity of the deployed software stack can be guaranteed before granting access to data.

The Trusted Connector guarantees a controlled execution environment for data services and supports the creation of trusted relationships. A general constraint is one that remains for all deployed IT systems: As long as physical or logical ac- cess is granted to administrators, protection against data theft by malicious partners is almost impossible to prevent. The International Data Spaces is seen as a network of part- ners that are provided with the technical means to fulfill their obligations and support in deciding what partners to trust and to define reasonable access conditions.

#### **4.1.6.10 APACHE CAMEL INTERCEPTOR (EXAMPLE)**

An IDS Connector may use Apache Camel to coordinate the data flow between different systems and applications. From a technical point of view, the developer does this by using pipelining, which is a dominant paradigm of Apache Camel for connecting different nodes in a route definition. The ba- sic idea of a pipeline is that Apache Camel uses the output of one node as input to the next node. Every node in such a route is a processor, except for the initial endpoint (as shown in ~~Figure 4.18~~).

![image](https://user-images.githubusercontent.com/69632955/150939403-107db526-d0a6-47f4-85d3-30a2b29e4f9b.png)

_Figure 4.18: Apache Camel pipeline (example)_

In order to control the usage of data, one approach can be to intercept the data flow between the services and applica- tions. ~~Figure 4.19~~ shows as example of how developers can do this. Apache Camel offers the possibility to integrate inter- ceptors that it executes every time before and after a proces- sor is working.

As the International Data Spaces provides an Information Model (see ~~Section 3.1~~), additional metadata enhances the data transferred via the route, thereby enabling better usage control enforcement. The Connector attaches the metada- ta to the data package, as explained in ~~section 3.4~~. In addi- tion, a PIP is able to resolve more metadata during the deci- sion-making process if necessary.

![image](https://user-images.githubusercontent.com/69632955/150939429-92add160-5c72-42fa-8b07-6716921caebf.png)

_Figure 4.19: Intercepting Apache Camel data flows_

This paradigm also works across company borders, as data always flows through the IDS Connector and the Apache Cam- el interceptor, respectively (as shown in ~~Figure 4.20~~). When reaching the receiving Connector, the respective policy to protect the data is automatically instantiated.

Depending on the policies available, this way of enforcement is not enough to cover all possible use cases and full usage control.

![image](https://user-images.githubusercontent.com/69632955/150939461-58fc264c-db41-4d40-bad1-e6e73f08d620.png)

_Figure 4.20: Data flow across company borders_

#### **4.1.6.11 CONTEXT INFORMATION AND OBLIGATION FULLFILLMENT**

&nbsp;

#### **4.1.6.12 DATA PROVENANCE TRACKING**

Data provenance tracking is closely related, but also comple- mentary to distributed data usage control. It has its origins in the domain of scientific computing, where it was introduced to trace the lineage of data. Data provenance tracking thereby allows finding out when, how and by whom data was modi- fied, and which other data influenced the process of creating new data items.

This kind of traceability is similar to the data protection re- quirements a data controller is confronted with, so as to be able to fulfill its data subjects’ right to access. It is also closely related to the question of proving compliance with contracts, agreements, or legal regulations. And data provenance track- ing can be used to facilitate clearing in decentralized data eco- systems, since it is capable of aggregating information con- cerning data exchange transactions and data usage.

However, while distributed data usage control is concerned with the enforcement of rights and duties when exchang- ing data across system boundaries, the focus of data prove- nance tracking is on transparency and accountability. In oth- er words: While a Policy Enforcement Point (PEP) serving for distributed data usage control in most cases needs to be able to proactively intercept data usage actions within the control flow (i.e. preventive enforcement), a PEP for data provenance tracking only needs to passively observe, interpret and log data exchange transactions and data usage for retrospective examination (in terms of usage control, this kind of enforce- ment is denoted as “detective enforcement”). Despite this fact, a data provenance tracking infrastructure can be built upon the same PEPs as distributed data usage control. Fur- thermore, data provenance tracking does not require a policy specification language, but rather a specification of how ob- served actions are to be interpreted in terms of data flow or data usage (i.e., a so-called data flow semantics specification). By this, data provenance tracking maintains a data flow mod- el that keeps track of the particular representations of data items. This kind of information can also be leveraged for data usage control enforcement; i.e., the data flow model is imple- mented as a Policy Information Point (PIP).

##### **OPERATING PRINCIPLE**

The operating principle of data provenance tracking is very similar to the operating principle of distributed data usage control. Data provenance tracking relies on passive mon- itoring technology (e.g., PEPs), which deliver events indicat- ing data usage or data flows for being logged. For this, a PEP needs to convey a semantic description of the data usage or data flows its events indicate. The data provenance track- ing infrastructure provides a data flow tracking component, which understands such semantics specifications. The PEP also needs to forward events together with metadata (includ- ing a unique identifier of the data’s content), so that logged transactions can be attributed to data content when data provenance is aggregated or queried.

##### **ARCHITECTURE**

The PEP resides within the message routing component of the Connector (or Data App). It is registered at the data flow track- ing component via a registry component (i.e., a local Policy Management Point, PMP). The same applies for the data flow tracking component. Thereby a PEP can query the local PMP for the communication interface of the local data flow track- ing component, which is then used to deploy semantics spec- ifications for its observed events and to forward actual events during operation.

Data provenance information is queried at a Privacy Dash- board, which is accessible via a Clearing House. The Privacy Dashboard returns a provenance graph for the unique iden- tifier of data content. There are two options for storing data provenance information:

» Centralized architecture (~~see Figure 4.21)~~: A Provenance Storage Point (ProSP) is attached to the Clearing House. After data usage or a data flow has been observed by the data flow tracking component inside the Connector, the transaction is logged at this ProSP.

» Distributed architecture (~~see Figure 4.22~~): Each Connector is equipped with a ProSP, which is directly connected to the data flow tracking component. The Clearing House accom- modates only a stateless Provenance Collection Point (ProCP), which aggregates provenance information com- ing in from the distributed ProSPs whenever a query oc- curs at the Privacy Dashboard.

![image](https://user-images.githubusercontent.com/69632955/150939507-4e3e3678-f129-4995-9b0b-967ad25f96ac.png)

_Figure 4.21: Architecture with centralized component for provenance information storage_

![image](https://user-images.githubusercontent.com/69632955/150939530-5668702a-8c29-4061-9162-28716e144d99.png)

_Figure 4.22: Architecture with distributed component for provenance information storage_

##### **COMMUNICATION**

The local data flow tracking component inside the Connec- tor has to be able to communicate with the centralized data provenance infrastructure (i.e., ProSP or ProCP). For this, a so- called Root-PMP is attached to the Clearing House. Here, the central components register their communication interfaces, and so do the local PMPs of the Connectors. Using these in- terfaces, provenance information is passed on to the central ProSP/ProCP.

Analogous to this hierarchical communication infrastructure, the provenance information of each unit of data content is a tree, a so-called provenance graph. It is either maintained at a central ProSP or at the distributed ProSPs located inside the Connectors. In the latter case, a centralized ProCP at the Clearing House aggregates the various sub-trees for a unique data content identifier from distributed ProSPs (i.e. it consol- idates the provenance information by merging the subtrees).

##### **INTEGRATION WITH DISTRIBUTED USAGE CONTROL**

In complex usage control scenarios, such as establishing data sovereignty for managing globally distributed supply chains, data is passed on from one Data Consumer to another. De- pending on the usage control policy in place, data may be forwarded in its original form, or it may be somehow pro- cessed, aggregated, or anonymized before being forwarded. This indicates the relevance of establishing transparency con- cerning data flows and data usage in compliance with usage control policies, business contracts, or legal regulations. For this purpose, distributed data usage control and data prove- nance tracking complement each other. As explained before, the PEPs used for usage control (detective enforcement) can also serve as a basis for data provenance tracking, whereas in turn data provenance information can be fed back into usage control enforcement (i.e., a usage control PDP can query for all locations of representations of some given data content protected by a usage control policy).

Further synergies can be exploited by employing the same communication infrastructure for distributed data usage control and data provenance tracking. The hierarchical PMP structure (as described in the previous section) can also en- able usage control components to interact across different IDS Connectors (e.g., for shipping policies to other Connectors, deploying and revoking policies, etc.).

#### **4.1.6.13 DATA PROVENANCE TRACKING ADDRESSED BY THE DIFFERENT LAYERS**

&nbsp;

##### **BUSINESS LAYER**

Data provenance tracking primarily supports the work of the Clearing House. It provides the means to establish a central- ized audit log aggregating tracking information concerning data exchange transactions and data usage.

##### **FUNCTIONAL LAYER**

Data provenance tracking does not directly affect the core functionality of the IDS, since it is typically implemented on top of a usage control infrastructure, or based on passive monitoring technology. However, data provenance tracking may enhance the functionality of the IDS by offering func- tions for clearing and accounting, provided tracking is suffi- ciently accurate (e.g., in terms of delivering concrete numbers of data users or a concrete duration of data use). Data Apps might also be considered as content/data the usage of which can be tracked by data provenance technology.

##### **PROCESS LAYER**

Data provenance tracking is integrated in the “Exchange Data” process (or, to be more precise, in the “Query Data” sub-pro- cess). Data provenance tracking components in the Connec- tor of the Data Provider as well as in the Connector of the Data Consumer signal to the data provenance storage com- ponent at the Clearing House that data has been successfully sent or received, respectively. This signaling is implemented based on events intercepted by PEPs for distributed data us- age control.

##### **INFORMATION LAYER**

Data provenance tracking can be orchestrated for different purposes. Regarding the IDS, the most important goals are establishing transparency and being able to prove compli- ance to contracts, agreements, or legal regulations. Reliability of content is a secondary goal of data provenance tracking in the IDS. While making the lineage of data traceable is the original purpose of data provenance tracking, this requires ei- ther specific, data provenance enabled Data Apps or the use of dedicated PEPs for these Data Apps.

##### **SYSTEM LAYER**

Reliability of data provenance information strongly depends on trustworthy Connectors and Data Apps (including their PEPs). It is recommended to integrate data provenance track- ing into Trusted Connectors and to certify Data Apps that are enabled for data provenance tracking and data usage control.
