### Usage Contracts ###

A legally valid contract is the foundation of any business transaction.
The IDS cannot, and does not intend to, replace legal contracts or
licensing agreements. Instead, the IDS provides a technical framework
for technically enforced agreements in addition to existing, legally
binding contracts. The connection of legally binding contracts and Usage
Contracts is part of the [IDSA Rulebook](https://internationaldataspaces.org/download/19008/).

Many details of a business relationship cannot be modeled in
machine-readable form. Nevertheless, the IDS specifies methods to define
categories of applicable contracts, and it presents patterns to observe
their usage and report validations. For this purpose, the IDS makes use
of the [Information Layer](../3_3_Information_Layer/3_3_InformationLayer.md).

![Technical Enforcement and organizational enforcement of usage
policies](./media/image20_new.png)

A Usage Contract comprises a set of Usage Policies. Each policy
describes a certain permission or obligation of an [IDS Resource](../3_3_Information_Layer/3_3_InformationLayer.md#digital-resource).
Usage Contracts are written in a machine-readable
format (according to the [IDS Usage Policy Language](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_6_Usage_Control.md#ids-usage-control-language)) and must
be interpreted as [defined in the Process Layer](../3_4_Process_Layer/3_4_6_Policy_Enforcement.md). In any
case, a Usage Contract must always be regarded as an extension of an
existing legal agreement between two IDS participants, which can be
overruled by them. As neither the IDS nor any other known technology
stack can sufficiently interpret legal texts, any Usage Contract must
always be in line with the concluded agreements. Each contract between
IDS participants consists of a technical part and a non-technical part.
The technical part focuses on the description of technical interfaces
(Application Programming Interfaces) and the Usage Policy. Negotiation
of the technical part of a contract must be supported by the Information
Layer of the IDS-RAM. The non-technical part focuses on legal aspects of
the intended data exchange. For automatic negotiation of contracts and
conditions standard contracts are necessary (but not yet available
today).
