### Securing Applications ###

A secure platform is needed to guarantee the secure and isolated execution of all applications. This platform provides security mechanisms and enable applications to fulfill their security requirements. Building on a secure platform, all applications deployed on the connector need to integrate into the utilized security mechanisms and fulfill security requirements themselves.

#### Security Measures in the Platform ####

Security measures in the platform are responsible for ensuring a secure deployment of provided applications.
The platform verifies authenticity and integrity of all applications by checking the signatures in the provided App Manifests before starting the applications.
In case the IDS App is supplemented with usage control policies for licensing purposes (e.g., only allowing usage of the software for a certain amount of time or limiting the number of simultaneously running instances), the platform is responsible for enforcing those policies and only starting the application if the defined conditions are met.

Additionally, the platform enforces isolation, communication routes and privileges for all applications based on configuration from the Connector Core Services and/or Control Apps. While some configuration attributes may be set freely, security-critical configuration aspects (which were also assessed during certification) need to be:

* set to fixed values embedded in the utilized software images (not allowing configuring through applications at runtime),
* limited to a pre-defined set of options,
* or validated by certified code (in the Connector Core Services or platform component) before coming into effect.

#### Connector Core Services and Control Apps ####

The Connector Core Services (or respective Core Services for other IDS components) and Control Apps are responsible for offering IDS-specific interfaces, configuring the entire connector stack securely and managing data exchange and processing on the connector.
These applications often have higher privileges on the IDS Connector which are required to use and configure functionalities offered by runtime and kernel of the platform.
The criteria for the certification of an IDS connector apply for these applications and need to be fulfilled by the combination of platform, Connector Core Services and (optionally) Control App.
During certification, the applications must be evaluated as a part of the overall security concept for the connector software stack applications. They need to at least address/cover the following security requirements:

* Authentication and authorization for external interfaces.
* Ensuring integrity and confidentiality for all communication channels and sessions (see also [Section 4.1.5](./4_1_5_Securing_Interaction_between_IDS_components.md)).
* Supporting negotiation and enforcement of usage control policies (see also [Section 4.1.6](./4_1_6_Usage_Control.md)).
* Securely configuring the entire connector stack including the allowed communication routes between apps.
* Logging relevant aspects, e.g., configuration changes, access control decisions, access to data resources.
* For higher Trust Levels: Interacting with responsible kernel/runtime component for using key material protected by hardware mechanisms.

To reduce the attack surface, different functionalities should be split into modular and isolated applications interacting only via defined interfaces. The privileges for the applications should be reduced to those required for the respective functionality in accordance with the principle of least privilege.

#### Adapter and Data Apps ####

In contrast to Connector Core Services and Control Apps, Adapter and Data Apps are unprivileged and isolated containers which cannot modify the connector functionalities but rely on them to provide their app functionality. They need to fulfill specific app requirements, e.g. containing all necessary dependencies to form an independent container, conducting input validation for offered interfaces, and having a description matching the functionality provided by the application.
However, they rely on the certified connector for securing communication channels to the outside world as well as authentication and authorization of users requesting access to provided interfaces.
