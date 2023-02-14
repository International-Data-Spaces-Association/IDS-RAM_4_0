### Data Exchange ###

After a successful Onboarding (see Section [3.4.1](./3_4_1_Onboarding.md#onboarding-of-an-ids-connector-and-its-operator)), the operations of a Data Consumer or Data Provider can be assigned to two phases: the Control Phase and the Transfer Phase.
In the Control Phase, both Participants pass multiple processes (Data Offering
(see Section [3.4.2](./3_4_2_Data_Offering.md#data-offering)) and Contract Negotiation (see Section
[3.4.3](./3_4_3_Contract_Negotiation.md)) to prepare the data transfer, using an IDS-specific
communication protocol. The respective protocol bindings are defined in the
[IDS-G](https://github.com/International-Data-Spaces-Association/IDS-G).

In the Transfer Phase, if all aforementioned processes were successfully finished, the Data Consumer
and the Data Provider can start to actually exchange data by invoking a Data Operation (e.g., data
upload or download, data transformation, or data query) via their IDS Connectors. How this can be
done is described in the following.

![Communication Phases](media/communication-phases.png)

##### Figure 3.4.4.1: Communication Phases

The invocation of a Data Operation is part of the Control Phase, as shown in Figure [3.4.4.1](#figure-3441-communication-phases), and
initiated by a Connector that refers to a Contract Agreement. As the subsequent sequence should not
be bound to neither a communication protocol nor to a communication pattern, this can be implemented
differently, as stated in the following. For this to work, a Data Operation request requires
information that enables technical automation (e.g., authentication information, or protocol details).

#### Communication Pattern ####

Communication between the Connectors can be synchronous or asynchronous (i.e., the Data Consumer
does not have to wait for the result to arrive, but will be notified by the Data Provider as soon as
the result is available). On top of that, instead of a pull-request, a push-request can be sent.

In case of a subscription, the Data Consumer may ask for updates regarding the requested data. The
updated data can be provided either after certain events (e.g., after the data has been updated by
the Data Provider) or within certain time intervals (e.g., every five minutes). If a push-request
is made, the Data Consumer repeatedly receives updated query results from the Data Provider. In case
of a pull-request, the Data Consumer can repeat the last part of the process to query data again
(using the same or a different query).

The description of the communication pattern itself is not part of this document, as this is covered
by existing standards (e.g. DIN SPEC 16593-1:2018-04) or as best practices in industry.

#### Communication Protocol ####

To meet various requirements regarding data volume and transfer in real time, the Transfer Process
is not restricted to a specific protocol. This way, technical limitations are bound to those of the
applied systems and not to the Connector component.

##### Data Transfer via the Same Infrastructure and Protocol #####

Either synchronously or asynchronously, the Data Provider's Connector may respond with the Data
Operation result without using a proprietary system or protocol. In the course of this, all
information flows that are shown in Figure [3.4.4.1](#figure-3441-communication-phases)
would run directly between the two Connectors using an IDS protocol.

##### Data Transfer via Another Infrastructure or Protocol #####

Alternatively to the previously described process, after the Data Operation invocation, the Data
Consumer's Connector can take the provided information and establish a connection directly between
the Data Provider’s system acting as a data source, and a system on the consumer-side acting as the
data sink. This offers the possibility for the Connector to establish and leave connections open, or
to switch from data pulling to data pushing easily. The sequence is depicted in Figure [3.4.4.2](#figure-3442-out-of-band-data-exchange).

![Out-of-band Data Exchange](media/data-transfer.png)

##### Figure 3.4.4.2: Out-of-band Data Exchange

#### Semantic Interoperability

Semantic Interoperability is crucial for Data Exchange in Data Spaces (see [section 2.5](../../2_Context_of_the_International_Data_Spaces/2_5_From_Data_To_Information_Do_You_Understand.md)). This starts dhring
Design-time, as described in the [Data Offering process](./3_4_2_Data_Offering.md#data-offering),
and in the process of [publishing](./3_4_2_Data_Offering.md#data-provider-registering-self-descriptions)
and [quering](./3_4_2_Data_Offering.md#data-consumer-searching-for-self-descriptions) self-descriptions.
In the process of Data Exchange the Vocabulary Hub and the Vocabularies are queried and used for semantic
interoperability.

The following steps are followed:

0. During Design Time, the data provider may publish a vocabulary or use an already published vocabulary and reference to it. Details can be found in section[Data Offering](./3_4_2_Data_Offering.md#data-offering)
1. Prior to the invokation of a data operation (in a synchronous or asynchronous way) by the data consumer one or multiple vocabularies are loaded by the data consumers connector.
2. The data consumers connector validates the schema with appropriate measures, depending on the provided schema.
3. Based on the vocabularies the data consumer can implement required interfaces to conduct the
data transfer as described in the sections above.
4. During the data transfer, respectivly after the data was transfered, the data can be validated
against the given vocabularies. In case of invalid data the consumers connector may decline the data
usage.
5. Subsequently to the data transfer the data might require some additonal treatment to make use of
this, like ETL (Extract, Transform, Loading) tooling. During this activity, a connector can make
use of Data Apps, as described in the following section.

![Semantic Interoperability](media/semantic_interop_data-transfer.png)

##### Figure 3.4.4.3: Support of Semantic Interoperability and related activites

#### Usage Control ####

All communication patterns and protocols must ensure that usage control, covering the contents of
the negotiated Contract Agreement, is enforced, and that the involved Connectors are included in the
data transfer, at least by event-based notifications. More details about Policy Enforcement are
described in Section [3.4.6](./3_4_6_Policy_Enforcement.md#policy-enforcement).
