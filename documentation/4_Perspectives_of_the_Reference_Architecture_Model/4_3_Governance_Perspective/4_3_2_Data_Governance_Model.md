### Data Governance ###

#### Key Roles and Correlating Data Governance and Management Activities ####

The following subsections list what data governance / data management
activities central roles in the IDS ecosystem are occupied with, and
what IDS components are involved.

##### Data Owner / Data Provider #####

**DG/DM activities**

- Define usage constraints for data resources
- Publish metadata including usage constraints to Metadata Broker
- Transfer data with usage constraints linked to data
- Receive information about data transaction from Clearing House
- Bill data (if required)
- Monitor policy enforcement
- Manage data quality
- Describe the data source
- Authorize Data Provider, if Data Provider is not the Data Owner

**Enabling/Supporting IDS Component**

- IDS Connector
- Catalogue of rules allowing Data Owners to configure usage conditions related to their own requirements
- Define pricing model and pricing (see [Section 3.3.3](../../3_Layers_of_the_Reference_Architecture_Model/3_3_Information_Layer/3_3_InformationLayer.md#digital-resource))

##### Data Consumer #####

**DG/DM activities**

- Use data in compliance with usage constraints
- Search for existing datasets by making an inquiry at Broker Service Provider
- Nominate Data Users (if needed)
- Receive information about data transaction from Clearing House
- Monitor policy enforcement

**Enabling/Supporting IDS Component:**

- IDS Connector
- Catalogue of rules to act in compliance with usage constraints specified by Data Owner

##### Metadata Broker Service Provider #####

**DG/DM activities**

- Match demand and supply of data
- Provide Data Consumer with metadata

**Enabling/Supporting IDS Component:**

- Metadata Broker Service Provider component
- Core of the metadata model must be specified by the International Data Spaces (by the Information Model)
- Provide registration interface for Data Provider
- Provide query interface for Data Consumer
- Store metadata in internal repository for being queried by Data Consumers

##### Clearing House #####

**Data-related activities**

- Monitor and log data transactions and data value chains
- Monitor policy enforcement
- Provide data accounting platform

**Enabling/Supporting IDS Component:**

- Clearing House component
- Logging data

##### App Store Provider #####

**Data-related activities**

- Offer Data Services (e.g. for data visualization, data quality, data transformation, data governance)
- Provide Data Apps
- Provide metadata and a contract based on the metadata for app user

**Enabling/Supporting IDS Component:**

- App Store Provider component
- Interfaces for publishing and retrieving Data Apps plus corresponding data

#### IDS Data Governance Model ####

The IDS Data Governance Model defines a framework of decision-making
rights and processes with regard to the definition, creation,
processing, and use of data. While governance activities set the overall
directive of the decision-making system, data management comprises three
groups of activities with regard to the creation, processing, and use of
data. In the IDS context, data governance comprises also usage rights of
data shared and exchanged within the IDS ecosystem. The management of
metadata specifies data about data and comprises both syntactic,
semantic and pragmatic information. This is of particular importance in
distributed system environments that do not rely on a central instance
for data storage, but instead allow self-organization of different
heterogeneous databases. Additionally, data lifecycle management is
concerned with the creation and capturing of data, including data
processing, enrichment, storage, distribution, and use.

The following responsibility assignment matrix (RACI matrix) supports
the allocation of these activities to enable a governance mechanism in
the IDS ecosystem. RACI stands for 'responsible' ,
 'accountable' , 'consulted' and 'informed ' . The focus
lies on the 'R' and 'A' of the RACI matrix, supported by the
notation  'S', which stands for supported.

| Activity | Data Owner / Data Provider | Data User / Data Consumer | Metadata Broker | Clearing House|
| :--- | :---: | :---:  | :---:  | :---:  |
| **Management**  | | | | |
| Determine data usage restrictions (execute data ownership rights)| R, A | - | S | - |
| Enforce data usage restrictions   | -     |  R, A   |  -  |  -      |
| Ensure data quality               | R, A  |  -      |  S  |  -      |
|Monitor and log data transactions   | S     |  S      |  -  |  R, A   |  
|Enable data provenance              |  S     |   S |  |  -  | R, A |
|Provide clearing services | S | S |- |R, A|
| **Metadata** | | | | |
| Describe and publish metadata | R, A | - | S | - |
| Look up and retrieve metadata | - | R, A | S | - |
| **Data Lifecycle** | | | | |
| Capture and create data | R, A | - | - | - |
| Store data | R, A | S | - | - |
| Enrich and aggregate data | S  | R, A | S | - |
| Distribute and provide data | R, A  | - | S | - |
| Link data | S | S | R, A | - |

##### Table4.3.2.1: Roles responsible, accountable and supporting in data governance 



The following subsections describe five topics that are addressed by the
Governance Perspective. These topics play an important role when it
comes to the management of data assets.
