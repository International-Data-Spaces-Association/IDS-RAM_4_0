# Data Offering

- BPMN for User interaction (Create Offering [Data Catalog / Resource / Artifact / Representation])

## Data Provider updating Self-Description
- Handful of sentence that the self-description have to be update accordingly
- Not all metadata is made available to everyone. Usage Policy enforcement starts right here and shows everyone who requests the self-description only the data they could access. 

## Metadata Broker interaction
### Data Provider Connector register metadata at Broker
- Sequence diagram for Connector Data Provider register metadata at Broker (optional)

### Data Consumer searching metadata at Broker
To find a Data Provider, the Data Consumer must send a query to a Broker Service Provider. Before that, however, the Data Consumer needs to select a suitable Broker (e.g. based on thematic coverage) and determine the query capabilities (e.g. a graphical search interface or a domain-specific query language). The Broker then returns the query result to the Data Consumer, who needs to interpret the result to find out about the different data sources available in the International Data Spaces for providing the data specified in the query. Each query result must provide information about each IDS Connector capable of providing the desired data, so that the Data Consumer can retrieve each Connector’s self-description
to learn more about how to receive the desired dataset from a technical point of view (e.g., endpoint addresses, protocol). The Data Provider may serve the same data using different
representations or pricing options, so the Data Consumer may select a suitable offer from the Data Provider’s Connector description.

- Sequence diagram for Connector Data Consumer searching metadata at Broker (optional)
- Remember: Filtering of the displayed data according to policy and requester


## Getting Self-Description from Data Provider
- Sequence diagram for getting self description from Data Provider


Alternatively, the Data Consumer may already know a suitable Data Provider. In this case, the Data Consumer can contact the Data Provider directly (i.e. without invoking a broker).


