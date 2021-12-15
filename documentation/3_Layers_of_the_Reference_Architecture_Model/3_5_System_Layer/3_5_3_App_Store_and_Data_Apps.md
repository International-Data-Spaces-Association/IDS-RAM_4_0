# Data Apps and App Store

As described in section 3.5.1 Connectors can make use of Apps for several purposes. Three types of Data Apps can be distinguished:
- self-developed Data Apps, which are used by the Data Provider’s
own Connector (usually requiring no certification
from the Certification Body),
- third-party Data Apps, which are retrieved from the App
Store (and which may require certification), and
- Data Apps provided by the Connector of the Data Consumer,
which allow the Data Provider to use certain functions
before data is exchanged, e.g., filtering or aggregation of
data (which may also require certification).

In addition, Data Apps can be divided into three categories:
- System Adapters are Data Apps on the Data Provider side,
establishing interfaces to external enterprise information
systems. The main tasks of a Data App belonging to this
category is providing access to enterprise information systems
and, if necessary, transforming from an internal data
model to a data model recommended, or considered as a
standard, for a given application domain, as well as to add
metadata to the data.
- Smart Data Apps (or Data Sink Connectors) are Data Apps
on the Data Consumer side, executing any kind of data
processing, transformation, or storage functionality. Normally,
the data provided by, or sent to, a Smart Data App is
already annotated with metadata (as described in the Information
Layer section).
- Other Apps providing a certain use of the data on Data
Consumer or Data Provider side. Usage Policies can enforce
the processing of the data in a trusted environment,
i.e. a Trusted Connector.

The IDS App Store is a secure platform for distributing Data
Apps; features different search options (e.g. by functional or
non-functional properties, pricing model, certification status,
community ratings, etc.).An IDS App Store consists of a registry
for available Data Apps in this App Store. Therefore an App
Store supports operations for Data App registration, publication,
maintenance, and query, as well as operations for the
provisioning of a Data App to a connector. These basic operations
can be complemented by additional services, e.g. billing
or support activities.