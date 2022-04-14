Issue for this section: https://github.com/International-Data-Spaces-Association/IDS-RAM_4_0/issues/72
# Securing Applications

Building on a secure platform, all applications deployed on the connector need to integrate into the utilized security mechanisms and fulfill security requirements themselves.
In the following, we separately address the connector core services and control apps which typically have higher privileges and can be used to configure the platform, and the adapter and data apps which can be deployed on the connector to process data.

## Securing Connector Core Services and Control Apps
The Connector Core Services (or respective Core Services for other IDS components) and Control Apps are responsible for offering IDS-specific interfaces, configuring the entire connector stack securely and managing data exchange and processing on the connector.
These applications often have higher privileges on the connector required to use and configure functionalities offered by the Kernel in the connector platform.
To reduce the attack surface, different functionalities should be split into modular and isolated applications interacting only via defined interfaces. The privileges for the applications should be reduced to those required for the respective functionality in accordance with the principle of least privilege.
It is important that the privileged applications are considered as a part of the overall security concept for the connector software stack applications in order to fulfill all security requirements for the IDS Component Certification. At least the following aspects should be addressed within the application (as well):
* Use of (external) interfaces shall be limited to a list of authorized users following the principle of least privilege.
* The applications need to check identification, authentication and authorization before allowing an user to interact with these external interfaces.
* Communication channels and sessions need to be secured following common best practices for ensuring integrity and confidentiality of communication. Securing the communication between connectors is further described in [Section 4.1.5](./4_1_5_Securing_Interaction_between_IDS_components.md).
* The Connector Core Services (and possibly control apps) need to support the negotiation and enforcement of (agreed) usage control policies. More details can be found in [Section 4.1.6](./4_1_6_Usage_Control.md)
* Configuration of the connector consists of configuring the connector core services and control apps themselves, and interacting with components in the platform responsible for configuring components in the kernel or runtime as well as for defining privileges and allowed communication routes between applications. While some aspects may be configured freely, security-critical configuration aspects (which were also assessed during certification) must be set to fixed values embedded in the utilized software images, limited to a pre-defined set of options or validated by certified code before coming into effect.
* Decisions or actions taken by the applications which are relevant for a latter re-construction of events and achieving non-repudiation, e.g., configuration changes or decisions on data access,  need to be logged. This can be achieved by a specific logging container or by integrating into the logging framework utilized by the platform. In both cases, the integrity of the audit logs needs to be ensured.
* For higher Trust Levels, the key material utilized for fulfilling the aforementioned requirements needs to be protected by hardware mechanisms and used through the respective kernel or runtime applications.

## Secure Usage of Adapter and Data Apps


## App Store and Distribution of Apps

### Apps in the IDS
Apps necessary for processing data, isolated from each other

What are apps used for?
* convert data between formats
* compute results from input data
* persistent storing of data →  different storing options possible for connectors:
  * either storage within the connector with attached UC restrictions or
  * external - only in encrypted version without access to plain data
  => Database is part of core connector services, data app should not store data persistently but uses this Database

Possible reasonable use cases for Usage Control in the context of apps:
* NDA with PDFs/files in data base
  * Usage Control Policy: Delete Files after certain amount of time/date
  * Enforcement depends on compliance of the person viewing the files: we can technically only enforce deletion from data in the database, not that a user copies/notes down data from the viewed files (the latter needs to be covered by legal means)
* Use apps which do not display/provide the input data directly but only provide computation results
  * Examples:
    * Video stream from parking lot with Data App that derives how many places are free
    * Status information from machines which are monitored and processed in data app → only predictive maintenance instructions or warnings leave the app
  * Enforcement is done by ensuring that the app does not provide the input data (Certification of Apps) and making sure that input data is only stored in the connector and only processed by the respective (certified) app

### App Store
* App = Container image (executable on Linux kernel, independent (brings all dependencies)) -> from developer
* Metadata (Description) in App manifest including measurements and signatures used for integrity protection -> from developer, possibly from evaluator
* App License - similar to usage control policies for other types of data -> from developer
  * Pay once and use on own connectors -> no policy to be attached to app
  * Usage on a specific connector instance
  * Usage for a certain amount of time (e.g. usage on own conectors for a year)
  * Processing of amount x of data (Anzahl Datenpakete, Menge der Daten in Größe)
  * Free version of apps

App Store offers the following interfaces:
* one for uploading apps:
  * input: app, manifest (pre-evaluated apps contain the respective information already), license
  * App store triggers test service (automated test suite):
    * more details?
    * test service adds signature, if tests are successfully passed
  * after successful response from app store, the apps are added to the app store database
* one for searching apps in the app store (GUI and search engines from FIT)
* one for downloading apps
  * input: identifier for the app to be downloaded
  * app store takes care of money transaction
  * provides app parts for download

![App Store Interactions](./media/app_store_interaction.png)

### Apps on a connector
![App Interactions](./media/app_interaction.png)

Securing the app in the connector:
* Container run-time responsible for ensuring the following aspects:
  * Integrity and authenticity of apps -> verified before start of app
  * Validation of license aspects (e.g. usage for time frame, ...)
* Routing responsible for controlling data flows between apps
  * Essential question: which data flows are allowed/how to decide which flows are allowed
  * First approach: data provider receives an overview of the data flows in the connector and what happens with their data in case of a transfer -> then they can decide whether they want to share or not
  * Open point: which interfaces do the apps require → Suggestion:
    * store this data
    * give me this data
    * transfer this information to app X (on connector Y)
