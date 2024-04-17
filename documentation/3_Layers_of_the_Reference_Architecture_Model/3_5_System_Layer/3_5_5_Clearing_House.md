### Clearing House ###

The IDS Clearing House consists of an IDS Connector (see section [3.5.2](./3_5_2_IDS_Connector.md#ids-connector)) and bases all its functions on a logging service that records information relevant for clearing and billing as well as usage control. The information sent to the Clearing House is defined in the Process Layer.

![Clearing House Architecture](media/clearing_house_architecture.png)
##### Figure 3.5.5.1: Clearing House Architecture

The Clearing House uses this information to provide a Clearing and Settlement Service on the basis of usage contracts and helps with the automization of payments between Data Provider and Data Consumer. It can also use this information to provide a Billing Service to allow the Data Space Operator the billing of the participants. The UC Claim Validation service uses the logged usage control data to allow the validation of usage claims on resources.
