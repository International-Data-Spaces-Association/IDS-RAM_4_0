# Security Perspective #

## Table of Content ##

[4.1 Security Perspective](./4_1_Security_Perspective.md#security-perspective)

[4.1.1 Security Aspects adressed by the different layers](./4_1_1_Security_Aspects_adressed_by_the_different_layers.md#security-aspects-addressed-by-the-different-layers-of-the-ids-ram)

[4.1.1.1 Business Layer](./4_1_1_Security_Aspects_adressed_by_the_different_layers.md#business-layer)

[4.1.1.2 Functional Layer](./4_1_1_Security_Aspects_adressed_by_the_different_layers.md#functional-layer)

[4.1.1.3 Information Layer](./4_1_1_Security_Aspects_adressed_by_the_different_layers.md#information-layer)

[4.1.1.4 Process Layer](./4_1_1_Security_Aspects_adressed_by_the_different_layers.md#process-layer)

[4.1.1.5 System Layer](./4_1_1_Security_Aspects_adressed_by_the_different_layers.md#system-layer)

[4.1.2 Identity and Trust Management](./4_1_2_Identity_and_Trust_Management.md#identity-and-trust-management)

[4.1.2.1 Identities for Devices](./4_1_2_Identity_and_Trust_Management.md#identities-for-devices)

[4.1.2.1.2 Component Identfier](./4_1_2_Identity_and_Trust_Management.md#component-identifier)

[4.1.2.1.3 Describing Metadata](./4_1_2_Identity_and_Trust_Management.md#describing-metadata)

[4.1.2.1.4 Interactions between IDS Connectors and Identity Components](./4_1_2_Identity_and_Trust_Management.md#interactions-between-ids-connectors-and-identity-components)

[4.1.2.1.5 Component (Identity) Lifecycle](./4_1_2_Identity_and_Trust_Management.md#component-identity-lifecycle)

[4.1.2.2 Identities for Participants](./4_1_2_Identity_and_Trust_Management.md#identities-for-participants)

[4.1.2.3 Trust Bootstrapping and Trust Chains](./4_1_2_Identity_and_Trust_Management.md#trust-bootstrapping-and-trust-chains)

[4.1.3 Securing the Platform](./4_1_3_Securing_the_Platform.md#securing-the-platform)

[4.1.3.1 Deployment Scenarios](./4_1_3_Securing_the_Platform.md#deployment-scenarios)

[4.1.3.2 Hardware Security Features](./4_1_3_Securing_the_Platform.md#hardware-security-features)

[4.1.3.2.1 Hardware Security Module (HSM)](./4_1_3_Securing_the_Platform.md#hardware-security-module-hsm)

[4.1.3.2.2 Trusted Platform Module (TPM)](./4_1_3_Securing_the_Platform.md#trusted-platform-module-tpm)

[4.1.3.2.3 Confidential Computing](./4_1_3_Securing_the_Platform.md#confidential-computing)

[4.1.3.3 Platform Security Requirements](./4_1_3_Securing_the_Platform.md#platform-security-requirements)

[4.1.4 Securing Applications](./4_1_4_Securing_Applications.md#securing-applications)

[4.1.4.1 Security Measures in the Platform](./4_1_4_Securing_Applications.md#security-measures-in-the-platform)

[4.1.4.2 Connector Core Services and Control Apps](./4_1_4_Securing_Applications.md#connector-core-services-and-control-apps)

[4.1.4.3 Adapter and Data Apps](./4_1_4_Securing_Applications.md#adapter-and-data-apps)


[4.1.5 Securing Interaction between IDS Components](./4_1_5_Securing_Interaction_between_IDS_components.md#securing-interaction-between-ids-components)

[4.1.5.1 Preparation of Required Information](./4_1_5_Securing_Interaction_between_IDS_components.md#preparation-of-required-information)

[4.1.5.2 Establishment of a Secure Communication Channel](./4_1_5_Securing_Interaction_between_IDS_components.md#establishment-of-a-secure-communication-channel)

[4.1.5.3 Data Transfer using this Communication Channel](./4_1_5_Securing_Interaction_between_IDS_components.md#data-transfer-using-this-communication-channel)

[4.1.5.4 Dynamic Trust Monitoring](./4_1_5_Securing_Interaction_between_IDS_components.md#dynamic-trust-monitoring)

[4.1.6 Data Usage Control](./4_1_6_Usage_Control.md#data-usage-control)

[4.1.6.1 Introduction](./4_1_6_Usage_Control.md#introduction)

[4.1.6.2 Organizational Rules and Legal Contracts](./4_1_6_Usage_Control.md#organizational-rules-and-legal-contracts)

[4.1.6.3 Roles involved in Usage Control](./4_1_6_Usage_Control.md#roles-involved-in-usage-control)

[4.1.6.3.1 Meta Data Broker](./4_1_6_Usage_Control.md#meta-data-broker)

[4.1.6.3.2 Connector](./4_1_6_Usage_Control.md#connector)

[4.1.6.3.3 Clearing House](./4_1_6_Usage_Control.md#clearing-house)

[4.1.6.3.4 App Store](./4_1_6_Usage_Control.md#app-store)

[4.1.6.3.5 App Provider](./4_1_6_Usage_Control.md#app-provider)

[4.1.6.4 IDS Usage Control Language](./4_1_6_Usage_Control.md#ids-usage-control-language)

[4.1.6.5  IDS Usage Control Policies and Policy Classes ](./4_1_6_Usage_Control.md#ids-usage-control-policies-and-policy-classes)

[4.1.6.6 Management](./4_1_6_Usage_Control.md#management)

[4.1.6.7 Usage Control in a Connector](./4_1_6_Usage_Control.md#usage-control-in-a-connector)

[4.1.6.8 Message Router and Interceptor (Example)](./4_1_6_Usage_Control.md#message-router-and-interceptor-example)

[4.1.6.9 Context Information and Obligation Fulfillment](./4_1_6_Usage_Control.md#context-information-and-obligation-fulfillment)

[4.1.7 Data Provenance Tracking](./4_1_6_Usage_Control.md#data-provenance-tracking)

[4.1.7.1 Operating Principle](./4_1_6_Usage_Control.md#operating-principle)

[4.1.7.2 Architecture](./4_1_6_Usage_Control.md#architecture)

[4.1.7.3 Communication](./4_1_6_Usage_Control.md#communication)

[4.1.7.4 Integration with Distributed Usage Control](./4_1_6_Usage_Control.md#integration-with-distributed-usage-control)

[4.1.8 Data Provenance Tracking addressed by the different Layers](./4_1_6_Usage_Control.md#data-provenance-tracking-addressed-by-the-different-layers)

[4.1.8.1 Business Layer](./4_1_6_Usage_Control.md#business-layer)

[4.1.8.2 Functional Layer](./4_1_6_Usage_Control.md#functional-layer)

[4.1.8.3 Information Layer](./4_1_6_Usage_Control.md#information-layer)

[4.1.8.4 Process Layer](./4_1_6_Usage_Control.md#process-layer)

[4.1.8.5 System Layer](./4_1_6_Usage_Control.md#system-layer)
## Files ##

- [4_1_Security_Perspective.md](./4_1_Security_Perspective.md)
- [4_1_1_Security_Aspects_adressed_by_the_different_layers.md](./4_1_1_Security_Aspects_adressed_by_the_different_layers.md)
- [4_1_2_Identity_and_Trust_Management.md](./4_1_2_Identity_and_Trust_Management.md)
- [4_1_3_Securing_the_Platform.md](./4_1_3_Securing_the_Platform.md)
- [4_1_4_Securing_Applications.md](./4_1_4_Securing_Applications.md)
- [4_1_5_Securing_Interaction_between_IDS_components.md](./4_1_5_Securing_Interaction_between_IDS_components.md)
- [4_1_6_Usage_Control.md](./4_1_6_Usage_Control.md)