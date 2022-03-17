# Metadata Broker

The IDS Metadata Broker consists of an IDS Connector (see section [3.5.2.0](./3_5_2_0_Connector.md)<!--//**TODO** add correct link-->), an endpoint for the registration, publication, maintenance and query of Self-Descriptions. Therefore, for any interaction with the IDS Metadata Broker the processes defined on the Process Layer, the descriptions defined on the Information Layer and descriptions defined on the System Layer can be applied. The Information Layer describes the message types for registration and query. An IDS Metadata Broker may provide additional services that in term must be described by using terms from the IDS Information Model in the respective Metadata Broker's Self-Description document.

**Note:  Even though the name might indicate a different purpose, an IDS Metadata Broker is *not* a message broker or provides any similar functions to distribute data assets actively by itself.**

As a direct consequence of the IDS Connector-nature of the Metadata Broker, each instance must be compliant to the Connector Certification criteria and in particular provide the functionalities and endpoints of general Connectors. For instance, a Metadata Broker must provide a Self-Description that provides further information about itself for other IDS components. A Metadata Broker must also have a valid IDS Identity and use a valid DAT in its communication.

In addition to these requirements for each IDS Connector, the Metadata Broker provides further functionalities for a data space. It's main purpose is the persistence and storing of Self-Description documents and offering efficient access and search functions on their content. It therefore requires a reliable and scalable internal database. As the Self-Description documents are encoded in RDF, usually JSON-LD, a graph-oriented database like a triple store or a property graph database might be used. Nevertheless also traditional SQL or NoSQL databases may be applied, which may not have the same native query support but still can be sufficient. In any case the internal architecture of a Metadata Broker must be flexible enough to cope with extensions of the data scheme. The IDS Information Model can always be enriched with further attributes, so a Metadata Broker must also allow the persistence and querying of information which was not yet known at its deployment time. Furthermore, Metadata Brokers operated for certain domains or dedicated data spaces might also enforce the existence of attributes that are not covered by the core IDS Information Model or part of the IDS namespace. That implies that a certain Metadata Broker instances require Self-Descriptions which information content goes beyond the IDS Information Model. In such cases, the additional requirements are outlined in the Metadata Broker Self-Description as well as in the content of the return messages, in case a Connector has not set such attributes yet.

Furthermore, a Metadata Broker implementation might add indexing or caching modules to reduce the query evaluation time. It can be generally expected that the amount of READ requests is significantly higher than the overall number of remote WRITE activities so a READ-optimized architecture can lead to better user experiences. Such design decisions however are in the responsibility of the operator.

Additionally, most use cases for Metadata Brokers require a human-oriented interface to the Self-Descriptions. A website with fulltext and facet search capabilities is therefore usually provided. The website might further provide the creation and management of the locally stored Self-Descriptions. However, as the registration and updating process at the Metadata Broker is centered around Connectors, the authority of the human website user and the asset-hosting Connector must be ensured.

## Endpoints

Metadata Brokers must provide remote endpoints to their own Self-Description (read-only) as well as to the locally persisted Self-Description graph (read/write for the hosting Connectors, read-only for the others). The server hosting these endpoints translates incoming requests, performs the necessary IDS identity and validity checks, and translates them into operations to the database.

A Metadata Broker might support endpoints for different IDS protocol bindings. In any case, the content of the responses are protocol-independent. That means a successful read operation using one binding must also be successful through any other if targeting the same Self-Description. A Metadata Broker may however discriminate based on the identity of the requester, providing responses to one Connector while rejecting another due to IDS Usage Control configurations.


## Search and Querying

The main purpose of a Metadata Broker is the provisioning of remote search functionalities. This can be done in a resource-oriented manner if the identifiers of the targeted Self-Descriptions are already known in advance. Alternatively, full-text or complex queries might be used. A complex query in this  sense is any query that combines filters, aggregations or traverses the Self-Description graph to search for information. Which query language is supported by which Metadata Broker instance is outlined in its own Self-Description.

The IDS Information Model provides the scheme for the searches. The knowledge of the Information Model can be used by querying Connectors to formulate their inquiries. Metadata Brokers may also provide additional templates or preformulated queries to support the Connectors.


## Self-Description Life Cycle

Self-Descriptions go through a life cycle. Created Self-Descriptions are in the `active` state as long as they are not put to `unavailable` by its sovereign. It's important to note that the later state is different to a deletion. It is important to track the usage of Self-Descriptions, in particular their unique identifier, to avoid name clashes or false flag attacks. A Connector therefore can ask to not publicly provide a Self-Description anymore by setting it to `unavailable` but it cannot force the Metadata Broker or any other Connector to completely delete the information from its internal databases.

A Self-Description can be made `active` at any time again by the respective Connector. In addition, it can overwrite already active Self-Descriptions with a new one. The update of a previously `unavailable` Self-Description however will set it back to `active` automatically. Furthermore, new Self-Descriptions must not use the identifier of already existing ones.

## Data Synchronization

The Metadata Broker is an optional component in a data space. That of course means that there can be data spaces that completely operate without any Metadata Broker. There can be however also data spaces where several Metadata Broker instances are provided. In such use cases, the synchronization between these instances becomes a topic, in particular to avoid redundant or conflicting information.

At the current state, the IDS does not specify or recommend any technical synchronization mechanism or process. Data space operators may implement such processes, via peer-to-peer architectures, declaring a leading instance, or relying on Distributed Ledger approaches. As a consequence, a Connector communicating with several Metadata Brokers at the same time must not - without having additional information - assume that the Self-Descriptions of the various Metadata Brokers are aligned.
