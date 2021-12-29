# Data Offering

- **//TODO** BPMN for User interaction (Create Offering [Data Catalog / Resource / Artifact / Representation])

A Participant who wants to offer data artifacts in a data space needs to conduct several steps to make it available to potential Data Consumers. In the most simplistic way, the Data Provider knows his Consumer at the beginning and directly informs him about available data assets, the selected endpoints, and the access mechanisms. This bidirectional data exchange bypasses most of the IDS infrastructure components and keeps the additional efforts to a minimum.

However, in typical data spaces use cases, a Data Provider does not know which other Participant is interested into his data offering, or even doesn't know about the existence of the later Data Consumer at the time when the data set is published. In such cases, the proper description and advertisement at the right locations is critical to enable a business transaction.

The IDS defines manners to tackle these challenges by specifying a technology-agnostic language for data Self-Descriptions as well as the necessary infrastructure components to host and search through these Self-Descriptions. In all cases, the original Data Provider stays the sovereign origin of any information, and any involved component acts on behalf of it. Therefore, it is in general not allowed for any intermediate player to change or manipulate the content of the received Self-Descriptions, apart of obviously wrong data or to protect the operability of the data space as a whole. Examples might be phishing attempts or other malicious content, the duty to follow legislative regulations like copyright protections, or less severe issues like unintentional syntactic or semantic errors.
**//TODO** Respective explanations in the Governance Section, then link to it here

Apart of such edge cases, the Data Provider has the interest to correctly and comprehensively describe its data assets to maximize the amount of interested Data Consumers. It further wants to stick to commonly accepted and understood standards to simplify its discovery for potential business partners. The [IDS Information Model](../3_4_Information_Layer) provides the schema for the Self-Descriptions themselves and their basic building blocks, like for instance Usage Contracts, endpoint descriptions, or the internal structure of data assets.

The first step in a typical data publication process is therefore the proper creation of a data asset Self-Description in JSON-LD. Usually, Connectors provide the technical manners to create and maintain them through suitable GUIs. In any way, the created Self-Descriptions are then deployed at the Connector that also hosts the related data assets. This Connector is also the only applicable source of truth for metadata about the data assets. Copied or otherwise differently located Self-Descriptions might be outdated or misleading, therefore a potential Data Consumer may want to double-check the correctness of a found Self-Description by also requesting a version directly from the original Connector.

After reaching a syntactically and semantically correct Self-Description, the Data Provider may want to announce it in a data space. To do so, it sends the Self-Description to the responsible IDS infrastructure component, an IDS Metadata Broker. The location of available Metadata Broker instances as well as the selection of the appropriate ones is in the responsibility of each data space Participant and not - for now - generally specified. The Metadata Broker then stores the received Self-Descriptions and makes them available for search requests for other Connectors. Potential Data Consumers can search through the stored Self-Descriptions, filter for relevant offers, and then in the third step of the process negotiate and request a data asset directly at the hosting Connector.

## Data Provider updating a Self-Description
- **//TODO** Handful of sentences that the self-description have to be update accordingly
- **//TODO** Not all metadata is made available to everyone. Usage Policy enforcement starts right here and shows everyone who requests the self-description only the data they could access.

## Interactions with IDS Metadata Brokers

### Data Provider Connector register metadata at Broker
- Sequence diagram for Connector Data Provider register metadata at Broker (optional)


![Publish Self-Description](../../media/image25_register-at-broker.png)


### Data Consumer searching for Self-Descriptions

To find a Data Provider, the Data Consumer may search in the catalogs of a Metadata Broker Service Provider. Before that, however, the Data Consumer needs to select a suitable Broker (e.g. based on thematic coverage) and determine the query capabilities (e.g. a graphical search interface or a domain-specific query language). The Broker then returns the query result to the Data Consumer, who needs to interpret the result to find out about the different data sources available in the International Data Spaces for providing the data specified in the query. Each query result must provide information about each IDS Connector capable of providing the desired data, so that the Data Consumer can retrieve each Connector’s self-description
to learn more about how to receive the desired dataset from a technical point of view (e.g., endpoint addresses, protocol). The Data Provider may serve the same data using different
representations or pricing options, so the Data Consumer may select a suitable offer from the Data Provider’s Connector description.

- Sequence diagram for Connector Data Consumer searching metadata at Broker (optional)
- Remember: Filtering of the displayed data according to policy and requester

![Query Self-Descriptions](../../media/image27_query-at-broker.png)


## Getting Self-Description from Data Provider
- Sequence diagram for getting self description from Data Provider


Alternatively, the Data Consumer may already know a suitable Data Provider. In this case, the Data Consumer can contact the Data Provider directly (i.e. without invoking a broker).
