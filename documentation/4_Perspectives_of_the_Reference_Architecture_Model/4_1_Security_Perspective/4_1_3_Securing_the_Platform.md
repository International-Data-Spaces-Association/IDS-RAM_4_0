# Securing the Platform

Security of data processing in an IDS component depends on the system security of the utilized component. The hardware and software components that are critical to ensure the confidentiality and integrity of the transmitted and processed data form the Trusted Computing Base (TCB). Different deployment scenarios and their respective TCBs are described in the [first subsection](#deployment-scenarios). The [following subsection](#hardware-security-features) provides some background on hardware security features that might be used for securing the platform. Finally, the [last subsection](#platform-security-requirements) provides an overview of essential security requirements and how to achieve them.

TODO: Overall goal: Describe how to create and deploy a secure platform as a baseline for the different IDS connector trust levels. Deployment can be monolithic (one connector per machine), shared or distributed. We need to raise awareness of what security mechanisms can achieve and address limitations of trust mechanisms as well.

## Deployment Scenarios
TODO: Deployment scenarios -> Overview illustrations (1:1 1:n m:n)
* Connector as a single device
* Multiple connectors per device
* Distributed deployment (e.g., k8s)
* Discussion on-premise and cloud scenarios (cloud is basically on-premise at another site and operator)
* Deployment scenarios also depend on existing infrastructure and environment (existing modules, services, ...)

## Hardware Security Features

In the following, we provide a brief overview on three hardware security features that might help securing the TCB of an device. For complete fulfillment of certification requirements, a combination of the mentioned techniques might need to be applied.

### Hardware Security Module (HSM)
A Hardware Security Module (HSM) is a physical device containing one or more secure cryptoprocessor. It typically provides secure key generation, storage and management and supports using those keys for performing encryption or digital signing. Additionally, most HSMs provide tamper protection, ranging from a notification of detected tampering attempts to deleting the keys upon tamper detection. A HSM can either be directly integrated or attached to the hardware of one device or deployed as a network device which is shared by multiple clients in the network. The components necessary to manage and access the HSM belong to the TCB of the device using the HSM, even if they are deployed on other devices in the network (e.g. in case of a HSM as a network device).

### Trusted Platform Module (TPM)
Trusted Platform Module (TPM) is a specification for secure cryptoprocessors with the newest version being the [TPM 2.0 Specification](https://trustedcomputinggroup.org/resource/tpm-library-specification/) from the Trusted Computing Group. The
TPM API can be implemented in a Secure Element, in the Platform-Firmware, inside a Trusted Execution Environment (TEE), or in form of a pure Software TPM.
A TPM can provide a root of trust for measurement (RTM), reporting and storage based on the Endorsement Key (EK) which was securely provisioned by the TPM manufacturer. It can generate, securely store and mange keys similarly to a HSM but is typically more strongly integrated into one host system only securing the keys for this device. Additionally, a TPM can be used to bind keys to the integrity of the utilized software stack and to securely store measurements of software components. If the TPM measurements include all components of the TCB they can be used as proof of the system's integrity for remote attestation.

### Confidential Computing
Confidential Computing approaches have been introduced with the goal to reduce the size of the TCB in the light of increasingly complex software stacks. They remove processes and components from the TCB by setting up hardware-supported isolated runtime environments, i.e., Trusted Execution Environments (TEE). The CPU utilized in the device must provide the necessary hardware features to support this approach. The hardware cryptographically protects confidentiality and integrity protection for process memory from higher-privileged access. Depending on the utilized CPU, there are different confidential computing approaches offered by the major hardware manufacturers:
* AMD offers a VM-based solution called Secure Encrypted Virtualization ([SEV](https://www.amd.com/en/processors/amd-secure-encrypted-virtualization) with its newest version being [SEV-SNP](https://www.amd.com/system/files/TechDocs/56860.pdf) (Secure Nested Paging).
* After starting with the process-based Software Guard Extensions ([SGX](https://software.intel.com/content/www/us/en/develop/topics/software-guard-extensions.html)), Intel is now developing a VM-based solution called [Trust Domain Extensions ([TDX](https://software.intel.com/content/www/us/en/develop/articles/intel-trust-domain-extensions.html)).
 * Likewise, Arm is working on their own VM-based Confidential Computing Architecture ([CCA](https://www.arm.com/why-
arm/architecture/security-features/arm-confidential-compute-architecture)).

To prove the correct setup of a TEE, each of the mentioned approaches offers some kind of remote attestation with proof of the integrity of the initial software components required. However, currently available implementations do not offer an attestation for the entire software stack, i.e., the TCB.

## Platform Security Requirements
TODO: Platform security features and requirements
* Secure boot / measured boot
* Remote integrity verification (remote attestation)
    * Measurements, Measurement lists, RTM / OS Manifest
* Component isolation (e.g., container based isolation)
* Key handling / provisioning
* Integrity protected audit logging
* Protecting data at rest / in transit
* Achieving protection from malicious administrators
