# Contract Negotiation

While a Connector Self-Description basically contains descriptive information about available 
datasets, these also include Usage Control information in form of a Contract Offer. A Contract Offer
describes under what conditions the Data Provider is willing to make its data available to the Data 
Consumer. This can range from simple access restrictions to complex pre- and post-duties. See more
details in Section x. // TODO Link to information layer explaining a contract offer.
<!-- Source: https://github.com/International-Data-Spaces-Association/IDS-G-pre/tree/usage-control-terms/UsageControl/contract -->

In a (semi-)automated negotiation process performed by the Usage Control frameworks of the 
participating IDS Connectors, the Data Consumer and the Data Provider need to agree on a Data Usage
Contract, respectively Contract Agreement. 

<!-- Sequence diagram -->
<!-- Integrate Clearing House workflow during Contract Negotiation -->
<!-- Source: https://github.com/International-Data-Spaces-Association/IDS-G-pre/tree/main/Communication/sequence-diagrams/data-connector-to-data-connector -->

Figure x shows this process in detail. ...

As soon as a Contract Agreement has been reached, this is instantiated and deployed inside both IDS 
Connectors. This means it needs to be persisted in an immutable way on both sides. Next, the 
consuming IDS Connector can be configured to process further data received by the Data Provider 
as defined by the contract. How this Policy Enforcement will be ensured is explained in Section 
3.3.6. <!-- Link to Policy Enforcement Section -->
