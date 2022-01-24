Issue for this section: https://github.com/International-Data-Spaces-Association/IDS-RAM_4_0/issues/70

Describe how to create and deploy a secure platform as a baseline for the different IDS connector trust levels. Deployment can be monolithic (one connector per machine), shared or distributed.
We need to raise awareness of what security mechanisms can achieve and address limitations of trust mechanisms as well. 


* Deployment scenarios
    * Connector as a single device
    * Multiple connectors per device
    * Distributed deployment (e.g., k8s) 
    * Discussion on-premise and cloud scenarios (cloud is basically on-premise at another site and operator)    
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
