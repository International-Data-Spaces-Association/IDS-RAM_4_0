## Blockchain ##

The core purpose of the International Data Spaces is to enable
controlled exchange and sharing of data between organizations --
regardless of the type of data. In many use cases of the International
Data Spaces, this is some form of structured data (e.g. measurement
data, product data, or logistics data). But also other types of
(streaming) data are supported. The IDS Connector allows data owners and
data providers to exchange and share their data with other participants
in the IDS ecosystem, while data sovereignty is ensured at any time.

In the use cases of the International Data Spaces, two basic patterns of
data sharing can be found:

- Data is shared to feed new, data-driven services, such as using the
    data in a new app, smart algorithm, or other digital service in
    which data of different sources/providers is combined.

- Data is shared for some form of business process synchronization,
    such as using the data to execute transactions (e.g. exchange
    orders), enable production (e.g. exchange product data), check
    quality (e.g. monitor the temperature of perishable goods), or
    synchronize processes (e.g. exchange status data).

In many of these cases, this sharing of data enables transactions with
the data itself becoming what one could call a 'shared data asset',
resulting in liability/responsibility for the participating
organizations.

Two examples:

- As perishable goods were exposed to improper ambient temperatures,
    the company ordering the goods refuses acceptance. The temperature
    data thereby becomes a shared data asset that can be stored in a
    shared environment which acts as a trusted record keeper of such
    quality data.

- Several companies want to share their capabilities in order to
    produce a certain type of good. In this case, the capability of each
    company becomes a shared data asset to be stored in shared 'yellow
    pages' accessible for all participants in the ecosystem.

From a functional perspective, it is expected that blockchain technology
will play an important role in maintaining these 'shared data assets' in
an IDS environment. This would complement the existing capabilities of
the IDS architecture to share (potentially large) datasets with the help
of IDS Connectors. For instance, a shared data asset might encompass a
hash code ('fingerprint' of a piece of data) which can be used to verify
a larger file (e.g. a complex product design for which an order was
sent) being shared with the help of an IDS Connector. In terms of the
IDS-RAM, blockchain technology could be used for the Clearing House or
the Metadata Broker, for example (see Business Layer).

In general, the use of Blockchain technology can ensure data consistency
and transparency in combination with the general IDS approach for data
sovereignty and secure data exchange and sharing. In contrast, typical
Data Lakes focus on the integration of data for the purpose of knowledge
extraction (see Figure below).

![ General architectural patterns for data exchange and data
sharing](media/image15.png)
##### Figure 2.9 : General architectural patterns for data exchange and data sharing
