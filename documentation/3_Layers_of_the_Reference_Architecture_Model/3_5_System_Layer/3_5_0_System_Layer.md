# System Layer

The processes defined in the [Process Layer](../3_3_Process_Layer) are summarized in Figure 3.5.0.1 as interactions between the IDS Components. Please note that the Identity Provider is not shown in the figure in order to maintain readability.

![Interaction of technical components](./media/3.5.0.1_interaction_between_technical_components.png)
#### _Fig. 3.5.0.1: Interaction of technical components_

A distributed network like the International Data Spaces relies on the connection of different participants where IDS Connectors or other core components are hosted (an IDS Connector comprising one or more Data Endpoints). The IDS Connector is responsible initiating a data exchange (see [Section 3.3.4](../../3_3_Process_Layer/3_3_4_Exchanging_Data.md)) from and to the internal data resources and enterprise systems of the participating organizations and the International Data Spaces. It provides metadata to the Metadata Broker as specified in the IDS connector self-description, e.g. technical interface description, authentication mechanism, and associated data usage policies. Usage Contracts can be transferred via the IDS Connector to the Clearing House to ensure trust. Also the data transfer can be logged at the Clearing House for trust reasons, or for clearing reasons. Vocabularies can be interpreted by getting more details from the Vocabulary Hub. Additional IDS Apps can be downloaded to the IDS Connector to run operations on the data.

On the System Layer, the roles specified on the Business Layer and the processes defined in the Process Layer are mapped onto a concrete data and service architecture, resulting in what can be considered the technical core of the International Data Spaces.

The IDS consists of the following core components:
- the [Identity Provider](./3_5_1_Identity_Provider.md) (consisting of DAPS and [ParIS](3_5_1_2_ParIS.md)),
- the [IDS Connector](./3_5_2_Connector.md),
- the [App Store and Data Apps](./3_5_3_App_Store_and_Data_Apps.md),
- the [Metadata Broker](./3_5_4_Metadata_Broker.md),
- the [Clearing House](./3_5_5_Clearing_House.md), and
- the [Vocabulary Hub](./3_5_6_Vocabulary_Hub.md).