## Publishing and using Data Apps

Data Apps can be used by IDS Connectors for specific data processing or transformation tasks. They can perform tasks of different complexity, ranging from simple data transformation to complex data analytics. An example of data transformation may be a Data App parsing a single string field with address information and producing a data structure consisting of street name and number, zip code, name of the city, and name of the country.

On a conceptual level, Data Apps can be treated the same way as data offerings in the International Data Spaces. Therefore, just as data is provided by a Data Provider using an IDS Connector and registering this at an IDS Metadata Broker, Data Apps are created by an App Provider and registered at an IDS App Store using the App Provider's IDS Connector as a means to communicate with the IDS App Store. As a consequence, App Providers also need to undergo the onboarding process. Instead of registering their IDS Connector at an IDS Metadata Broker, App Providers register their Data Apps at an IDS App Store.

In order to be published, certain Data Apps require certification from the Certification Body. When it comes to using a Data App that is offered by an IDS App Store, IDS Participants need to execute a process that is very similar to the 'Exchange Data' process.

For each Data App that was successfully certified, the corresponding metadata is stored in the IDS App Store for being retrieved by IDS Participants via a search interface. If an IDS Participant finds a suitable Data App in an IDS App Store, e.g. matching in functionality and compatible with the App Consumer's IDS Connector technical requirements, the Data App can be requested.
