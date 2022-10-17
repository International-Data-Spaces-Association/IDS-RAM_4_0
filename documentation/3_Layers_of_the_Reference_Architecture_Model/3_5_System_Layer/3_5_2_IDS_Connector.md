### IDS Connector ###

The International Data Spaces network is constituted by the total of its IDS Connectors. Each IDS Connector allows the exchange of data via the Data Endpoints it exposes. Applying this principle, there is no need for a central instance for data storage. An IDS Connector must be reachable by IDS connectors from other organisations. Due to organizational security policies, this may require changing firewall policies or establishing a demilitarized zone (DMZ). It should be possible to reach an IDS Connector using the standard Internet Protocol (IP), and to operate it in any appropriate environment. A Participant may operate multiple IDS Connectors (e.g., to meet load balancing or data partitioning requirements). IDS Connectors can be operated on-premises or in a cloud environment.

The IDS Connector Architecture uses application container management technology to ensure an isolated and secure environment for individual IDS Apps and IDS Connector functionalities. An IDS App matches an application which offers an API to store, access, or process data. To ensure privacy of sensitive data, its processing should take place as close to the data source as possible. Any data preprocessing (e.g., filtering, anonymization, or analysis) should be performed by the backend services or IDS Apps. Only data intended for being made available to other Participants should be offered by Connectors.

IDS Apps are services for realizing business logic inside the IDS Connector. IDS Apps can be used to process data, connect to external systems, or control the IDS Connector. Therefore, they can be downloaded via the IDS App Store and deployed by the IDS Connector.

The [IDS App Store](./3_5_3_App_Store_and_Data_Apps.md#app-store-and-ids-apps), [Metadata Broker](./3_5_4_Metadata_Broker.md#metadata-broker), and [Clearing House](./3_5_5_Clearing_House.md) are based on the IDS Connector architecture (which is described in detail in the following section) in order to support secure and trusted data exchange with these services.

#### IDS Connector Architecture ####

The Connector consists of one or more computers/virtual machines, operating systems running on them, an Application Container Management, and the Connector Core Service(s) built on top of it.

![Connector Architecture](media/3.5.2.1_connector_architecture.png)
##### Figure 3.5.2.1: Connector Architecture

The individual elements of the deployment are shown in Figure 3.5.2.1 and described below:

- _Application Container Management_: In most cases, the deployment of the Connector Core Service(s) and selected IDS Apps is based on application containers. See Section [3.5.2.3](#special-connectors) for specialized IDS Connectors. IDS Apps are isolated from each other by containers in order to prevent unintended interdependencies. Using Application Container Management, extended control of IDS Apps and containers can be enforced. During development, and in case of systems with limited resources, Application Container Management can be omitted.  
- A _Certified Core Container_ contains one _Connector Core Service_ which provides components like Data Management, Metadata Management, Contract and Policy Management, IDS App Management, IDS Protocols Authentication, and many more. Detailed explanations to the IDS Connector's functionalities are given in the following Section [3.5.2.2](#ids-connector-functionalities).
- An _Certified App Container_ is a certified container downloaded from the App Store, providing a specific IDS App to the IDS Connector.
- A _Custom Container_ provides a self-developed Custom App. Custom containers usually require no certification. 
- An _IDS App_ defines a public API, which is invoked from the IDS Connector. This API is formally specified in a meta-description that is imported during the deployment phase of an IDS App. The tasks to be executed by IDS Apps may vary. IDS Apps can be implemented in any programming language and target different runtime environments. Existing components can be reused to simplify a migration from other integration platforms. A detailed description of how to use IDS Apps can be found in Section [3.4.5](../3_4_Process_Layer/3_4_5_Publishing_and_using_Data_Apps.md#publishing-and-using-ids-apps), the deployment of IDS Apps is explained in Section [3.5.3](./3_5_3_App_Store_and_Data_Apps.md#app-store-and-ids-apps).
- The _Runtime_ of a Custom/Certified App/Certified Core Container depends on the selected technology and programming language. The Runtime, along with the application, constitutes the main part of a container. Different containers may use different runtimes. What runtimes are available depends only on the base operating system of the host computer. From the runtimes available, a service architect may select the one deemed most suitable.

#### IDS Connector Functionalities ####

The IDS Connector must include some essential functionality in its _Connector Core Service(s)_. The functionalities can be implemented in individual micro services or as a single comprehensive software block. In addition, the services do not have to be deployed in the same infrastructure.

![Connector Functional View](media/3.5.2.2_connector_functional_view.png)
##### Figure 3.5.2.2: Connector Functional View

The individual functionalities of the _Connector Core Service(s)_ are shown in Figure 3.5.2.2 as an [UML deployment diagram](https://www.omg.org/spec/UML/2.5.1/) that depicts each functionality as one component. The figure intentionally does specify the external interfaces of components but not the internal ones as these vary from implementation to implementation. Also, the image does not include all the interactions between the components for the sake of clarity.

The components are described below:

- The _Authentication Service_ holds the necessary information to authenticate the IDS Connector from/to other backend systems and/or authorize the system access from/to the IDS Connector from other IDS participants. For security reasons, a clear separation of the internal and external access credentials is recommended. 
The _Authentication Service_ provides interfaces for configuration and to connect custom authentication services. In order to authorize incoming and outgoing connections it holds

- the Key/Trust Store for the _IDS Protocol(s)_,
- the credentials for the access of the _Data Management_ and _Data Exchange_ to external systems, and
- the information for the access control of the _Data Exchange_ and _Data Management_ to the IDS.

This is shown via the solid line inside the IDS Connector. 

- The _Data Exchange_ component provides or requires interfaces to exchange data with other IDS Participants (providers/consumers). It can be deployed on another infrastructure than the IDS Protocol(s) component and it is possible to have more then one Data Exchange component to support multiple protocol bindings. The _Data Exchange_ component does not support IDS-specific interfaces nor does it interpret the IDS Information Model.
- The _IDS Protocol(s)_ component supports at least one IDS specific interface defined in [IDS-G](https://github.com/International-Data-Spaces-Association/IDS-G) to realize the processes defined in the Section [3.4](../3_4_Process_Layer/3_4_Process_Layer.md). All components interact with the IDS Protocol component as shown by the dashed lines.
- The _Remote Attestation_ component is used to increase the trust between the participating components. It can be used to detect whether the software has been modified at the other party's end (see Section [4.1](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_Security_Perspective.md) for more information). The component is needed for certification level 2 or higher (see Section [4.2.4](../../4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/4_2_4_Component_Certification.md#component-certification)).
- The _(Audit) Logging Service_ is responsible for the logging of all relevant information during the operation of the component. For example, changes to settings, error messages, data accesses, and policy implementations should be logged. The information can also be passed on to corresponding systems that take over the (auditable) logging. Therefore, the component provides or requires an interface to this systems. 
- The _Monitoring Service_ is used to monitor the status of the component. It can be used to check, e.g., if the IDS Connector is running, remains in an error state, or is offline.
- The _Data App Management_ component supports the download, deployment, and integration of IDS Apps in the IDS Connector.
- The _Policy Engine_ summarizes all components used for enforcing the IDS Usage Control Policies (part of an IDS Contract). These cover the Policy Administration Point (PAP), the Policy Enforcement Point (PEP), the Policy Information Point (PIP), the Policy Execution Point (PXP), the Policy Management Point (PMP), and the Policy Decision Point (PDP). All are described in detail in Section [4.1.6](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_6_Usage_Control.md#usage-control-in-a-connector).
- The _Contract Management_ component is responsible for managing the contract negotiation between Participants (see Section [3.4.3](../3_4_Process_Layer/3_4_3_Contract_Negotiation.md#contract-negotiation)) and storing the IDS Contract Agreements afterwards. Contract management can be seen as part of _Metadata Management. However, it is visualized as a separate component due to the importance of Usage Control in IDS.
- The _Metadata Management_ component holds the metadata of provided and consumed data assets. The metadata is mainly defined by the IDS Information Model, however, it can be further enriched with additional information. The metadata is coupled with the contracts from the Contract Management component and the data from the Data Management component.
- The _Data Management_ component holds the data assets itself or holds a link to the data sources, data sinks, or IDS Apps to get or send the data assets to their interface dynamically. 
- The _Configuration Management_ component contains the configuration parameters for the IDS Protocols and all components in general.
- The _User Management_ component is responsible for providing user authentication for every interface of the components. Therefore, the User Management can use external Identity Services or provide this service by itself. It also can be configured via an interface.

There may be different types of implementations of an IDS Connector, based on different technologies and depending on what specific functionality is required regarding the purpose of the Connector. IDS Connectors are distinguish according to their certification level defined in Section [4.2](../../4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/4_2_Certification_Perspective.md#certification-perspective), which indicates, among other things, which security and data sovereignty criteria the IDS Connector implements.

#### Special Connectors ####

What type of IDS Connector is to be implemented may depend on various aspects, such as the execution environment given or the current developmental stage regarding used Data Services or applyed Data Flows. In the following, three exemplary scenarios are outlined:

- _Developer Connector:_
As is the case, for the development of any software, developing IDS Apps or configuring Data Flows comprises several phases (specification, implementation, debugging, testing, profiling, etc.). For reasons of simplification, it may be useful to run Connectors without application container management. In doing so, the development process can be accelerated, as packing and starting the container can be omitted, and debugging can be done in the development environment. After successfully passing all tests, the configurations can be used to deploy a productive (live) Connector. Upon deployment in the live environment, the Connector is ready for being used.
- _Mobile Connector:_
Mobile operating systems (e.g., Android, iOS, or Windows Mobile) use platforms with limited hardware resources. In such environments, application container management is not necessarily required. The same applies for operating systems which do not support application containers, or systems without any operating system (e.g., microcontrollers). In such environments, IDS Apps (and the Connector Core Service(s)) can be started directly on the host system, without requiring any virtualization. The differences between Connectors with containers and Connectors without containers can be met by different Connector Core Service(s).
- _Embedded Connector:_
Another way of IDS Connector miniaturization offers the Embedded Connector. Embedded Connectors have the same design as Mobile Connectors, and do not necessarily require application container management either. Steps for IDS Connector miniaturization may include the use of a common runtime for all components, or simplified versions of IDS Connector Core Service(s). If data is to be sent to a fixed recipient only, a simple IDS protocol library may be sufficient. Similarly, it may be sufficient to hard-code a single, fixed connection instead of using a configurable component. To save communication overhead, simple API calls inside the common runtime could be used.
