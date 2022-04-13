Issue for this section: https://github.com/International-Data-Spaces-Association/IDS-RAM_4_0/issues/72
# Securing Applications

Building on a secure platform, all applications deployed on the connector need to integrate into the utilized security mechanisms and fulfill security requirements themselves.
In the following, we separately address the connector core services and control apps which typically have higher privileges and can be used to configure the platform, and the adapter and data apps which can be deployed on the connector to process data.

## Securing Connector Core Services and Control Apps
* which security requirements affect the application layer of the connector:
  * Securing communication - see 4.1.5 for IDS communication and remote attestation
  * Realization/Support for usage control - see 4.1.6.
  * Proper securing of interfaces: User Identity and Access Management
  * possibly secure configuration of platform
  * Logging of relevant aspects (Data access, ...)
  * Trust 2&3: using keys protected by hardware mechanisms (requires interaction with platform)


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
