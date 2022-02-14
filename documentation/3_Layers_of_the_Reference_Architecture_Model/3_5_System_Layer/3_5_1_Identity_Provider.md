# Identity Provider

## DAPS

## ParIS

The Participant Information System role can be implemented in different variations
and implementation patterns. Independent of different design decisions or used
technologies, all ParIS implementations must host an IDS endpoint that hosts a
Self-Description of the ParIS itself as well as functions to query and update
the contained catalog of Participant Self-Descriptions. This endpoint is requried
to allow IDS Conenctors to find the ParIS and interact with it in an IDS compliant
manner. Furthermore, a ParIS should also provide a website with a human-friendly
presentation of its content as well as suitable query and filter capabilities.

Both the webiste and the IDS endpoint might be protected further, by for instance
relating the access permissions to IDS identities. One could, for instance, only
allow registered IDS components to actually retrieve the metadata of other
Participants. That way, the distribution of the Self-Descriptions is limited to
certain data spaces. Nevertheless, as a ParIS is not intended to host or maintain
completely confidential data, a fully implemented access or even Usage Control
regime is usually not necessary. However, the typical requirements of the IDS
communication, for instance encryption or the usage of a DAT, are also relvant
for a ParIS. Consequently, also a ParIS needs an IDS Identity Certificate and
needs to be registered at a DAPS.

In addition to the outside communication, an internally reachable endpoint can be
exposed, only accessible for the operators of the Identity Provider. This endpoint
can be used to enable the provisioning and curation of Participant Self-Descriptions.
The externally reachable endpoints only allow the curation of own Self-Descriptions,
which means that a Participant - or its Connector - can never change another
Participant's Self-Description. Nevertheless, a curation process is needed, which
can be operated using this internal endpoint. Obviously, this curation process
needs to be executed carefully and comply to the IDS Governance rules.

Apart of the endpoints, and the server hosting them,
a ParIS needs either to host an internal database to store and retrieve the
Participant Self-Descriptions or be connected to the general database of its
Identity Provider. Similar to the Metadata Broker, as these Self-Descriptions
are in RDF, a Graph Database or a NoSQL DB with graph capabilities can
be an efficient choice. Additional indexing services can further improve the
repsonse times but are not technically required.
