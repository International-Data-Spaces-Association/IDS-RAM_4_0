### Securing the Platform ###

Security of data processing in an IDS Component depends on the system security of the utilized software stack consisting of different hardware and software components. Those hardware and software components that are critical for ensuring the confidentiality and integrity of the transmitted and processed data form the Trusted Computing Base (TCB). Different deployment scenarios and their respective TCBs are described in the [first subsection](#deployment-scenarios). The [following subsection](#hardware-security-features) provides some background on hardware security features that might be used for securing the platform. Finally, the [last subsection](#platform-security-requirements) provides an overview of essential security requirements and how to achieve them.

## Deployment Scenarios ##

In general, there are three different possibilities for the combinations of platform and connector service instances:

* A 1:1 mapping with a connector being a single device consisting of one platform instance and one connector service instance
* A 1:n mapping with multiple connectors on one physical device, i.e., a system with one platform instance and multiple connector service instances
* A n:m mapping with multiple devices offering a distributed deployment for multiple connector service instances (e.g. with Kubernetes)

The figure below shows the three options with their respective trusted computing bases:

![Deployment Scenarios](./media/deployment_scenarios.png)

#### _Fig. 4.1.3.1: Deployment Scenarios_

The TCB consists of the following components:

* All **hardware** components with access to unencrypted app data.
* **Firmware / bootloader / UEFI** representing all software components used to bootstrap the system and initialize the hardware before starting the kernel.
* Optionally a **hypervisor** which may be used to isolate multiple connectors on a device by providing a Virtual Machine (VM) for each of them. The impact on the TCB is illustrated for the 1:n mapping in a comparison to a solution with OS-level virtualization, i.e., containers.
* The **kernel** connects user space software to the hardware of the device.
* A (container) **runtime** responsible for starting the execution of applications on the system.
* The **connector core services** taking care of essential connector functionalities as explained in the [System Layer](../../3_Layers_of_the_Reference_Architecture_Model/3_5_System_Layer/3_5_2_IDS_Connector.md).
* An arbitrary number of **apps** as introduced in the [System Layer](../../3_Layers_of_the_Reference_Architecture_Model/3_5_System_Layer/3_5_3_App_Store_and_Data_Apps.md).

Additionally, the TCB may include **external components** in the surrounding infrastructure of a connector which are used for security-relevant tasks, e.g. an authorization server.

It is important to note that from a component security perspective there is no need to address the usage of cloud solutions differently than an on-premise deployment. In both cases, the TCB includes all components that are required to ensure the confidentiality and integrity of the transmitted and processed data and needs to fulfill all requirements defined in the certification criteria catalog. The only differences lie in the responsibility for the different layers of the software stack and ensuring their conformity.

#### Hardware Security Features ####

In the following, we provide a brief overview on three hardware security features that might help fulfilling the requirements introduced in the [subsection below](#platform-security-requirements). For complete fulfillment of certification requirements, a combination of the mentioned techniques might need to be applied.

##### Hardware Security Module (HSM) #####

A Hardware Security Module (HSM) is a physical device containing one or more secure cryptoprocessor(s). It typically provides secure key generation, storage and management and supports using those keys for performing encryption or digital signing. Additionally, most HSMs provide tamper protection, ranging from a notification of detected tampering attempts to deleting the keys upon tamper detection. A HSM can either be directly integrated or attached to the hardware of one device or deployed as a network device which is shared by multiple clients in the network. The components necessary to manage and access the HSM belong to the TCB of the device using the HSM, even if they are deployed on other devices in the network (e.g. in case of a HSM as a network device).

##### Trusted Platform Module (TPM) #####

Trusted Platform Module (TPM) is a specification for secure cryptoprocessors with the newest version being the [TPM 2.0 Specification](https://trustedcomputinggroup.org/resource/tpm-library-specification/) from the Trusted Computing Group. The
TPM API can be implemented in a Secure Element, in the Platform-Firmware, inside a Trusted Execution Environment (TEE), or in form of a pure Software TPM.
A TPM can provide a root of trust for measurement (RTM), reporting and storage based on the Endorsement Key (EK) which was securely provisioned by the TPM manufacturer. It can generate, securely store and mange keys similarly to a HSM but is typically more strongly integrated into one host system only securing the keys for this device. Additionally, a TPM can be used to bind keys to the integrity of the utilized software stack and to securely store measurements of software components. If the TPM measurements include all components of the TCB they can be used as proof of the system's integrity for remote attestation.

##### Confidential Computing #####

Confidential Computing approaches have been introduced with the goal to reduce the size of the TCB in the light of increasingly complex software stacks. They remove processes and components from the TCB by setting up hardware-supported isolated runtime environments, i.e., Trusted Execution Environments (TEE). The CPU utilized in the device must provide the necessary hardware features to support this approach. The hardware cryptographically protects confidentiality and integrity protection for process memory from higher-privileged access. Depending on the utilized CPU, there are different confidential computing approaches offered by the major hardware manufacturers:

* AMD offers a VM-based solution called Secure Encrypted Virtualization ([SEV](https://www.amd.com/en/processors/amd-secure-encrypted-virtualization)) with its newest version being [SEV-SNP](https://www.amd.com/system/files/TechDocs/56860.pdf) (Secure Nested Paging).
* After starting with the process-based Software Guard Extensions ([SGX](https://software.intel.com/content/www/us/en/develop/topics/software-guard-extensions.html)), Intel is now developing a VM-based solution called Trust Domain Extensions ([TDX](https://software.intel.com/content/www/us/en/develop/articles/intel-trust-domain-extensions.html)).
* Likewise, Arm is working on their own VM-based Confidential Computing Architecture ([CCA](https://www.arm.com/why-arm/architecture/security-features/arm-confidential-compute-architecture)).

To prove the correct setup of a TEE, each of the mentioned approaches offers some kind of remote attestation with proof of the integrity of the initial software components required. However, currently available implementations do not offer an attestation for the entire software stack, i.e., the TCB.

#### Platform Security Requirements ####

The Certification Criteria Catalog for Components defines various requirements for interoperability and security of an IDS Connector. It provides three different Trust Levels with an increasing number of requirements as explained in [Section 4.2.4](../4_2_Certification_Perspective/4_2_4_Component_Certification.md).

The following paragraphs provide an overview of important security requirements affecting the platform of an IDS connector and possible approaches for fulfilling them:

* **Integrity and authenticity of the software stack** to prevent undesired behavior of a device: This is typically achieved by utilization of Secure Boot where each component in the boot process verifies the integrity and authenticity of the next component based on an initial root of trust and provided software signatures. Additionally, the (container) runtime may only start applications after verifying their software signatures.
* **Remote integrity verification / remote attestation**, i.e., providing a proof of this integrity to a remote entity: For obtaining the proof of integrity, a device may use not only Secure Boot but also Measured Boot where the results from the integrity verifications (the measurements of all components) are securely stored and provided upon request. The measurements need to be secured from manipulation in later stages of the boot, e.g. by using a TPM with the Platform Configuration Registers (PCRs). These can only be extended, but not reset as long as the device is active. In case a Confidential Computing approach is used for reducing the size of the TCB, the offered remote attestation solution can be used as proof for the utilization of this technology and for proving the integrity of (some parts of) the TCB. The measurements need to be put into context by metadata describing the software behind these measurements as explained in [Section 4.1.2](./4_1_2_Identity_and_Trust_Management.md) and [Section 4.1.5](./4_1_5_Securing_Interaction_between_IDS_components.md).
* **Protecting integrity and confidentiality of data at rest**: Depending on the type of data, integrity and confidentiality of the data needs to be protected. It is typically achieved by encrypting data before persistently storing it, e.g. with disk encryption or by using a database that stores data only in encrypted form. Backups shall always be encrypted to prevent unauthorized access to them.
* **Isolation of processes**: To reduce the attack surface, interactions between different applications on the system shall be kept to a minimum and each application shall only get the privileges it requires. This can be achieved by isolating and restricting applications (containers) using security mechanisms in the Linux kernel such as namespaces, cgroups, AppArmor, SELinux, Linux capabilities and seccomp.
* **Tracking of events**: In case of security incidents, it is important to be able to reconstruct what happened on a connector. This is addressed by an integrity-protected audit log for all security-relevant events on the device. Logging should be performed on all layers: Within the platform up to the container runtime, e.g. by using a logging framework for Linux such as journald, and on the application layer. The latter can be done either by using a defined interface to the platform logging or by using an application-specific solution.
* **Protecting utilized keys**: The cryptographic material (typically keys) used to achieve many of the requirements described above needs to be stored and used in a way that protects its confidentiality (for symmetric or private keys) or integrity (for public keys). Public keys used as root of trust for integrity and authenticity verification are typically provisioned onto the device during a secure initialization phase which is conducted in a secure environment. Private keys used by the device should be generated directly on the device and never directly displayed/provided to users or processes using them. Depending on the chosen Trust Level, the usage of hardware protection mechanisms such as, e.g., a HSM or TPM, is necessary.
* **Achieving protection from malicious administrators**: For Trust Level 3, a connector shall be protected against an internal attacker which has legitimate access to the connector. In order to fulfill all security requirements, this requires a strong reduction of the administration possibilities for a connector. A (single) connector administrator must never get direct control over any layer of the system, but administration of the connector needs to be realized via predefined and restricted management interfaces.
