Issue for this section: https://github.com/International-Data-Spaces-Association/IDS-RAM_4_0/issues/72

# Securing applications

Apps necessary for processing data, isolated from each other,

App Store:
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
  * App store triggers test service (automated test suite) -> test service adds signature, if tests are successfully passed
  * after successful response from app store, the apps are added to the app store database
* one for searching apps in the app store (GUI and search engines from FIT)
* one for downloading apps
  * input: identifier for the app to be downloaded
  * app store takes care of money transaction
  * provides app parts for download

Enforcing of the licenses defined for the app:
* legal agreements
* validation of policies in container runtime before starting the apps
* central monitoring based on remote attestation (see where apps are running)

Running App Instance:
* configuration from operator
* state with data (file system)


Container runtime:
* responsible for ensuring integrity of components by verifying integrity (measurements)
* enforces "usage control for apps" -> checks license before starting an app



* Deployment and decommissioning of software artifacts

## Role of the App Store
* Context discussion of app store (app store has no security responsibilities)

## Data app interaction
    * Securing data app interaction / defining allowed data flows
    * Defining access control for data apps
    * Sketching the connection to usage control (later section)
