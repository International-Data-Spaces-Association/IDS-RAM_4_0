# Participant Information Service (ParIS)

From a System Layer view, the architecture and endpoints of a ParIS are very similar to the ones of an IDS Metadata Broker. Both need to receive IDS Self-Descriptions, need to persist them and make them available for other IDS Connectors to query them. 

## Components

A ParIS typicaly consists of the following functional building blocks, which can be implemented using different technology stacks and hosting solutions:

- _Server to host the IDS Endpoints.
- _Database to persist the RDF Self-Descriptions of the registered IDS Participants.
- _Index (optional) to increase the speed for read requests.
- _Website (optional) for human interactions with the ParIS.
- _IAM (optional) for checking the identity claims of clients and to validate their authorization using the IDS DAT. Can be located at the surrounding Identity Provider.

## Endpoints

## Search and Querying

## Life Cycle of Participant's Self-Description


## Data Synchronization inside the Identity Provider
