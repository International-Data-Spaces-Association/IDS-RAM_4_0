## Purpose and Structure of the Reference Architecture ##

Focusing on the generalization of concepts, functionality, and overall
processes involved in the creation of a secure 'network of trusted
data' , the IDS-RAM resides at a higher abstraction level than common
architecture models of concrete software solutions do. The document
provides an overview supplemented by dedicated architecture
specifications defining the individual components of the International
Data Spaces (Connector, Broker, App Store, etc.) in detail.

In compliance with common system architecture models and standards
(e.g., ISO 42010, 4+1 view model), the Reference Architecture Model uses
a five-layer structure expressing various stakeholders' concerns and
viewpoints at different levels of granularity.

The general structure of the Reference Architecture Model is illustrated
in the figure below. The model is made up of five layers:

The *Business Layer* specifies and
categorizes the different roles which the participants of the
International Data Spaces can assume, and it specifies the main
activities and interactions connected with each of these roles.

The *Functional Layer* defines the functional requirements of the
International Data Spaces, plus the concrete features to be derived from
these.

The *Process Layer* specifies the interactions taking place
between the different components of the International Data Spaces; using
the BPMN notation, it provides a dynamic view of the Reference
Architecture Model.

The *Information Layer* defines a conceptual model
which makes use of linked-data principles for describing both the static
and the dynamic aspects of the International Data Space's constituents.

The *System Layer* is concerned with the decomposition of the logical
software components, considering aspects such as integration,
configuration, deployment, and extensibility of these components.

In addition, the Reference Architecture Model comprises three
*perspectives* that need to be implemented across all five layers:

- *Security*,
- *Certification*, and
- *Governance*.

![ General structure of Reference Architecture
Model](../media/image11.png)
#### Figure 1.2: General structure of the IDS Reference Architecture Model
