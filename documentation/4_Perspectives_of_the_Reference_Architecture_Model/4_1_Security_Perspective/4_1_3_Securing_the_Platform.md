Issue for this section: https://github.com/International-Data-Spaces-Association/IDS-RAM_4_0/issues/70

Describe how to create and deploy a secure platform as a baseline for the different IDS connector trust levels. Deployment can be monolithic (one connector per machine), shared or distributed.
We need to raise awareness of what security mechanisms can achieve and address limitations of trust mechanisms as well. 


* Deployment scenarios -> Overview illustrations (1:1 1:n m:n)
    * Connector as a single device
    * Multiple connectors per device
    * Distributed deployment (e.g., k8s) 
    * Discussion on-premise and cloud scenarios (cloud is basically on-premise at another site and operator)
    * Deployment scenarios also depend on existing infrastructure and environment (existing modules, services, ...)    
* HW security features, their purpose and limitations (background)
    * HSM
    * TPM
    * Confidential computing / processor based solutions
* Platform security features and requirements
    * Secure boot / measured boot
    * Remote integrity verification (remote attestation)
        * Measurements, Measurement lists, RTM / OS Manifest 
    * Component isolation (e.g., container based isolation)
    * Key handling / provisioning 
    * Integrity protected audit logging
    * Protecting data at rest / in transit
    * Achieving protection from malicious administrators

## HW security features / characteristics
* HSM
    * Cryptographic processor
    * Device to protect external keys from illicit access
    * Provides tamper protection
    * Can be deployed as a network devices, shared by multiple clients
* TPM 
    * Cryptographic module complying to TCG specification 
    * Provides a root of trust, based on a key provisioned by the manufacturer
    * Can securely store measurements of software components
    * Provides interfacing for remote attestation
    * Is attached to a defined device
* Confidential computing
    * Depend on hardware features of the CPU
    * Cryptographically provides confidentiality and integrity protection for process memory
    * Provides measurements for (some of the) software components
    * Current implementations provide remote attestation that verifies the launched software artefact, but no runtime attestation
* For complete fulfillment of certification requirements, a combination of the mentioned techniques might need to be applied. 




