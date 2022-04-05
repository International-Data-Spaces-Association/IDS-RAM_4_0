# Identity and Trust Management

The International Data Spaces allow participants a cross-company data exchange. In many cases, the participants intending to exchange data do not know enough about the other company and its utilized components to properly assess the consequences of such a data exchange. Thus, the IDS offers mechanisms to gain reliable information which help to establish trust and enable participants to make sovereign and informed decisions.
Identity and trust management is rooted in the components described in ([Chapter 3.5.1](/documentation/3_Layers_of_the_Reference_Architecture_Model/3_3_Process_Layer/3_3_1_Onboarding.md)).

## Identities for Devices

The IDS Connector is the central device to establish trust on a technical level and to ensure a secure data exchange across domain boundaries.
In the IDS, each connector instance possesses it's own identity. Each connector instance is made up of several aspects:
* The platform the IDS Connector instance depends on. A platform consists of hardware, firmware, operating system and (container) runtime environment.
* The Connector Core Services software artefacts that provide management functionality and IDS interoperability.
* The configuration of a IDS Connector (defined data routes, configured Usage Control framework).
* The Data Apps or other services (e.g., Clearing House services) that are bound to this connector instance.

The IDS Connector identity serves to uniquely identify one instance of a service and app bundle on qualified platforms. The identity concept is equally used for all technical components in the IDS.

The service instance for a connector is typically a Service including a core services, usage control framework  and applications (Data Apps).
Other components (Broker, DAPS, ...) are represented by their Service (represented by one or multiple containers) running on a comparable platform.

One component always is characterized by the combination of platform and service instances. As an example, this Connector instance is running several data apps. The identity is comprised of the platform, the Connector Core Services and the deployed Data Apps.

![Components SW Stack](./media/SW_Stack_Components_connector_blueprint.png)


### Component Identifier
The identity of a combination of platform and service instance is bound to an identifier for the service instance.

* Each component gets a UID (Unique Identifier) bound to the service instance.
* This UID is defined by the operator of the component and provided to the CA with a request for an identity certificate.
* The UID is a URL referencing the link at which a self-description of this component instance can be received.
* TODO: Discusscion about UID: Can we define a URL? What about non http schemes? What about connectors not service http?
* Each UID is mapped to a key pair which is typically used for TLS but possibly also data signing and other identity proofs.
* The CA is not required/able to verify that this URL truly offers a valid self-description and utilizes the TLS key for the communication since the URL is typically not yet available as long as the provisioning has not been completed.  See URI verification below.
* Each connector is able to verify the correct mapping of URL and utilized TLS key when querying the self-description.

Each Service Instance needs to be mapped to one platform it utilizes:
* Each platform blueprint gets a unique identifier during the component certification.
* For a component with Trust level 1, the concrete platform instantiation (running version of this blueprint) does NOT get a UID as well as key and certificate for this platform instance. Instead the connector description solely references the (unique) identifier of the certified blueprint (and the operator needs to be trusted to ensure its correct instantiation).
* For components with Trust Level 2 or 3, each platform instantiation needs to be uniquely identified with a UID. This UID is required to provide a mapping from service instance to platform UID.
* Each platform UID is subject of a certificate for the utilized platform key(s) (e.g. AK of a TPM) which enable verification of the platform integrity.
* One platform UID can map to (keys for) 1-n physical devices/protected VMs:
  * If 1 physical device serves as the component platform: 1 UID is mapped to 1 platform key.
  * For distributed platform setups (e.g. with kubernetes): 1 UID for the setup maps to n platform keys for the servers in this distributed platform.
  * If connector is run in one protected VM (e.g. SEV SNP): 1 UID is mapped to 1 key for this SEV-SNP VM.
  * If multiple protected VMs (e.g. SEV SNP) form a distributed platform setup: 1 UID for the setup maps to n platform keys for the VMs which comprise this setup.

![Identity mapping for different scenarios](./media/identity_mapping.png)
(Comment: the platforms in the image may always be either physical devices or protected VMs)

### Describing Metadata
The IDS targets not only a secure exchange of data but also a trustworthy environment for data processing honoring the defined usage control policies. To achieve this goal, it is not sufficient to only know the identity of another IDS component, but additional information about the company operating the component and the utilized software stack is required.
This information is provided in form of the following describing artifacts:
* A **Company Description** for each company operating an IDS component which contains verified information about the company as well as information about its Operational Environment Certification (explained in [Chapter 4.2.3](../4_2_Certification_Perspective/4_2_3_Operational_Environment_Certification.md)).
* **Software Manifests** for the utilized software components which have been evaluated in the Component Certification explained in [Chapter 4.2.4](../4_2_Certification_Perspective/4_2_4_Component_Certification.md)). In addition to the awarded certification levels, the manifests contain verified measurements which can be used to validate that the described software is truly running on the device. To support re-usability of components, the description of each software stack consists of three types of Software Manifests used for describing different layers:
  * A **Root of Trust for Measurement (RTM) Manifest** for components of the boot stage,
  * an **Operating System (OS) Manifest** for utilized kernel and user space components, including the container run time enabling the execution of different isolated containers/apps, and
  * an arbitrary number of **App Manifests** per component identifying the utilized containers/apps.
Signatures are utilized to represent the passed stages of the certification process (described in [Chapter 4.2.5](../4_2_Certification_Perspective/4_2_5_Processes.md)) and allow a validation of the correctness of the describing artifacts.
In addition to these static artifacts, the connector operator may add additional attributes to the component's description or have them validated and registered at the DAPS.

### Interactions between IDS Connectors and Identity Components

To establish a trusted connection, each connector needs the identity information of the corresponding connector to perform access and usage control decisions. The interactions can be depicted as follows:

![Interaction between IDS Connectors and Identity Components](./media/IdM_Interactions.png)

1. Each IDS Connector acquires a valid identity from the IDS Device CA.
2. Each IDS Connector requests a current Dynamic Attibute Token from DAPS.
3. When establishing communication, the DAT of both IDS Connector instances is exchanged. This is also matched with the used TLS certificate.

To avoid the possibility of abusing a DAT by an attacker, these DATs must be treated as confidential information. to further protect from attacks performed with leaked DATs, each Connector has to validate the presented certificate by matching it to the connectors identifier.
Two cases must be evaluated:

1. The connector uses its identity certificate for TLS connections. In this case, the corresponding IDS connector must assure the identifier in the DAT matches the presented certificate.
2. The connector uses a separate certificate for TLS connectors (e.g., issued by a CA such as Let's Encrypt). In this casem the corresponding IDS Connector must assure the certificate fingerprint matches the one that is embedded in the DAT.


### Component Lifecycle -> potentially move to process layer

| Phase | When does it happen | How is the component identity affected | What about the data? |
| --- | --- | --- | --- |
| **Provisioning** | New component becomes available when an operator provisions a new instance of the blueprint (on a new device, a new service-instance in the cluster, ...) | A component identity is issued by a Certificate Authority (CA) which issues an x509 identity certificate (or something comparable) | No Data is available on a newly provisioned component, but arbitrary data can be added afterwards. |
| **Maintaining** | New versions of utilized software are distributed, configuration of the component changes (slightly) | As long as the trust level of the SW stack AND the operator remains unchanged, the identity does NOT change. | Data already stored on the connector MUST adhere to the defined UC policies so update or migration strategies need to ensure their fulfillment by deleting/removing/making data inaccessible. |
| **Out of service (Decommissioning)** | Component is sold/transferred to another operator, SW change that affects the overall trust level, component is not offered/available any longer | The component identity needs to be decommissioned, certificate(s) of the component(s) is(are) revoked. | All data currently on/in the connector needs to be removed (if necessary transfer them to other connectors beforehand). |


### Technical Possibilities for Realizing the Concepts - beide

The UID scheme is defined by the respective operating company. 
* für Component UID legt der IDS im IDS-G ein Schema fest - genaue Umsetzung fürs Konzept irrelevant.
* Nachweis über die Identität (Schlüssel - UID mapping & company Mapping) muss von CA ausgestellt werden - üblicherweise bisher als x509 Zertifikat, aber auch andere Ansätze denkbar
* Metadaten (Software/Unternehmen - zertifizierte Eigenschaften Mapping ) in einer "signierten Datei" z.B. JWS, VCs, ... -> signierte Info mit langer Laufzeit -> technischen Standards im IDS-G festlegen
* DAT-Token: OAuth-Token, VC, ... (Aktualität und ggf. weitere geprüfte EIgenschaften)-> signierte Info mit kurzer Laufzeit -> technischen Standards im IDS-G festlegen

## Identities for Participants (enterprises/organizations or Human Users) - Monika
Diskussion über Identitäten für Teilnehmer eines Datenraums.
Wofür bräuchte/will man das?
-> Verantwortlichkeit für das Verhalten eines Konnektors
-> Verantwortlichkeit für Daten (Qualität, Inhalt der Daten und andererseits für Freigabeprozesse, Managen vorhandener Datensätze) -> Verantwortlichkeit und Berechtigungsmanagement

Kann man prinzipiell auf Unternehmes- oder Personenebene machen
-> Unternehmen ist beständiger als Personen
-> aber: Unternehmen wird immer durch Personen geprägt und "das Unternehmen" kann keine Handlungen vornehmen

Für Unterschriften im "Namen des Unternehmens" - mit einem key Pair für "das Unternehmen" müsste das Unternehmen intern Berechtigungsmanagement und Zugriff auf den Schlüssel kontrollieren, damit niemand falsch was signieren Kann
-> prinzipiell umsetzbar, aber recht kompliziert und fehleranfällig

deshalb state-of-the-art: einzelne Personen im Unternehmen bekommen Identitäten und Schlüssel und können damit "Dinge unterschreiben"

Konkret für den IDS wäre das Konzept:
Abbildung des Zertifizierungskonzept und Trust-Management:
* Personenzertifikate mit 4 Rollen:
  * Developer (Entwickler sowei Zuständiger für die Komponentenzertifizierung)
  * Evaluator
  * Certifier
  * Operator (umfasst sowohl den Vertreter des Unternehmens für die Zertifizierung als auch den Provisionierer/Admin der Konnektoren)
* eine oder mehrere USer CAs im IDS stellen jeweils einer Person ein Identitätszertifikat aus. Nur die zuständige Person bekommt Zugriff auf die privaten Schlüssel
Prinzipiell sind weitere Rollen möglich, müssen halt IDS-weit anerkannt und vereinbart sein.
Rollen sollten hier immer in Bezug auf den IDS ausgestellt werden - ein Abbilden von Unternehmensinternen Rollen ist bisher im IDS nicht vorgesehen aufgrund der Vielfalt in der Unternehmensstruktur.

### Technical Possibilities for Realizing the Concepts
* Nachweis über die Identität (Key gehört zu Person) und Rolle (Person übt Rolle aus) -> beide Infos müssen dann von User CA verifizierbar zur Verfügung gestellt werden, klassisch als x509 Zertifikat, aber auch andere Ansätze denkbar
* Sicheres Generieren und Speichern von Private Key für Personen, der verwendet wird: Soft-Token, Smartcard, eID, ...
* Wichtig: Details in RuleBook und IDS-G festlegen, sollte mit eIDAS aligned sein

## Trust Bootstrapping and Trust Chains
Each component requires two certificates and keys:
1. Platform Key: for the platform used
2. TLS Key: for the service instance running

We have 2-3 parties involved in the trust bootstrapping and different guarantees for the different trust levels:
* Connectors with Trust Level 1 (prev. Base Connectors):
  * Certificate confirms that the key belongs to a TLS key under control of the operator specified in the organization attributes of the certificate
  * Trust Anchors Provisionierung Gerät:
    * CA ensures that the request for the certificate was issued/approved by the operator specified in the organizations attributes and that the operator has a currently valid operational environment certification;
    * Operator is responsible for ensuring that only this service instance has access to the private key (ensured by processes assessed in the operational environment certification)
  * Trust Anchors Certification Process: User CA only issues certs for people truly fulfilling those roles; involved people only sign manifests and company descriptions following the standard procedure and if they are convinced everything in the description artifact is correct
    * Operator that the software described is truly running (no measurements) -> description of SW stack as part of self-description, not mandatory part of each communication

* Connectors with Trust Level 2/3 (prev. Trust(+) Connectors)) - exemplary for a TPM:
  * Certificate confirms that the key belongs to a platform/TLS key under control of the operator specified in the organization attributes of the certificate AND keys are protected by hardware mechanisms (inside the TPM):
  * Trust Anchors  Provisionierung Gerät:
    * TPM Manufacturer confirms that an Endorsement Key is placed in a TPM.
    * CA ensures that the platform key (attestation key - AK)/TLS key are truly protected by the TPM: for the AK by ensuring that the AK belongs to a valid EK, for TLS key by verifying signature from AK.
    * Additionally, the CA ensures that the request for the certificate was issued/approved by the operator specified in the organizations attributes;
    * Operator is responsible for only requesting certificates for TPMs under their control (ensured by processes assessed in the operational environment certification).
  * Trust Anchors Certification Process: User CA only issues certs for people truly fulfilling those roles; involved people only sign manifests and company descriptions following the standard procedure and if they are convinced everything in the description artifact is correct
