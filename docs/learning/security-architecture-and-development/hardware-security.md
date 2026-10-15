# Hardware Security

## Description

Protecting physical devices and components, such as CPUs, memory, and IoT devices, from tampering, theft, or malware attacks. Techniques such as hardware-based encryption and secure boot are commonly used. Compromised hardware can bypass software defenses, making it a critical layer to secure for overall system integrity.

## Why This Matters

Hardware security is essential because physical devices and components are foundational to an organization's IT infrastructure. Compromised hardware can bypass software protections, exposing systems and data to theft, tampering, or malware. By securing hardware, staff ensure the integrity, confidentiality, and availability of critical systems across the organization. Enterprise operations depend on hardware for servers, workstations, networking equipment, IoT devices, and other critical systems. Hardware security helps an organization:

- Protect devices from tampering, theft, or unauthorized access.
- Implement hardware-based protections such as encryption and secure boot.
- Ensure system reliability and prevent attacks that bypass software controls.
- Maintain trust in operational infrastructure across departments.

By integrating hardware security into IT architecture, staff can safeguard essential operations and reduce risks posed by physical or low-level attacks. Hardware security influences the daily responsibilities of staff and technical teams:

- Staff implement secure hardware configurations, manage device access, and integrate hardware-based protections such as TPMs (Trusted Platform Modules, which are found in many laptops/desktops) or HSMs (Hardware Security Modules - typically found in datacenters).
- Technical teams ensure computing and specialized devices are physically secured and protected against tampering or unauthorized access.

By embedding hardware security into daily operations, the organization ensures robust defenses at the physical level, supporting secure, reliable, and trustworthy technology use.

## Skill Development

- Investigate: How can hardware-based security mechanisms, such as Trusted Platform Modules (TPMs), be integrated into system architecture to ensure secure boot and data storage?
- Research: What role do hardware security features, such as secure processors, play in the overall security of IT infrastructure?
- Investigate: How can physical security be incorporated into system design to prevent unauthorized physical access to critical hardware?
- Investigate: What is a hardware security module (HSM), how does it differ from a TPM, and why do organizations use HSMs to generate, store, and use cryptographic keys so that the keys never leave tamper-resistant hardware?
- Investigate: Beyond theft and obvious tampering, how can hardware be compromised through physical, side-channel, and supply-chain attacks — power and timing analysis, fault injection, cold-boot memory attacks, exposed debug/JTAG ports, and counterfeit or tampered components introduced before deployment — and what hardware defenses (tamper detection and response, side-channel countermeasures, memory encryption, trusted supply chain, and attestation) address them?

## Learning Resources

> **Scope and safety note:** Hardware is the foundation other controls stand on, so a hardware compromise can quietly defeat software defenses. Many hardware attacks require physical access, specialized equipment, or interception in the supply chain, and testing them (power analysis, fault injection, probing debug ports, opening a device) can destroy equipment or void warranties — do it only on hardware you own or are authorized to assess, never on production or borrowed devices. Treat the secrets inside hardware (keys in a TPM or HSM) as the crown jewels: their value is that they never leave the device, so protect the physical device and its supply chain accordingly.

### Reference and further reading

- [O'Reilly: Hardware security](https://www.oreilly.com/search/?q=Hardware%20Security&type=book&rows=100)
- [McMaster Library: Hardware security (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Hardware%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Hardware security (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Hardware%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)

### Foundations: TPMs, secure boot, and secure processors

*Supports: Investigate — TPMs for secure boot and data storage; Research — secure processors in IT infrastructure*

- [Wikipedia: Hardware security](https://en.wikipedia.org/wiki/Hardware_security) — an overview of the field, including TPMs, secure elements, and hardware roots of trust.
- [Cisco: Trustworthy Technologies (data sheet)](https://www.cisco.com/c/dam/en_us/about/doing_business/trust-center/docs/trustworthy-technologies-datasheet.pdf) — how hardware anchors (secure boot, a hardware root of trust, image signing) build trust into infrastructure devices.
- [Cisco: Security Modules for Security Appliances](https://www.cisco.com/c/en/us/products/interfaces-modules/security-modules-security-appliances/index.html) — examples of dedicated hardware security modules in network infrastructure.
- [CCCS: User Authentication Guidance for IT Systems (ITSP.30.031 V3)](https://www.cyber.gc.ca/en/guidance/user-authentication-guidance-information-technology-systems-itsp30031-v3) — where hardware-backed credentials (TPM-protected keys and FIDO2 security keys) fit into authentication.

### Hardware security modules (HSMs) and key protection

*Supports: Investigate — what an HSM is, HSM vs. TPM, and keeping keys in hardware*

- [Fortinet: What Is a Hardware Security Module (HSM)?](https://www.fortinet.com/resources/cyberglossary/hardware-security-module) — a vendor-neutral explainer of HSMs and how they differ from a TPM. The direct reference for the HSM prompt.
- [Palo Alto Networks: Secure Keys with a Hardware Security Module](https://docs.paloaltonetworks.com/ngfw/administration/certificate-management/secure-keys-with-hardware-security-module) — using an HSM so private keys never leave tamper-resistant hardware.
- [FortiADC HSM Integration](https://help.fortinet.com/fadc/4-8-0/olh/Content/FortiADC/handbook/hsm.htm) and [FortiWeb and Securosys Primus HSM Integration](https://docs.fortinet.com/document/fortiweb/7.6.3/administration-guide/999296/using-securosys-primus-hsm) — concrete examples of integrating an HSM with a device.

### Physical, side-channel, and supply-chain attacks

*Supports: Investigate — physical/side-channel/supply-chain attacks and defenses; Investigate — physical access in system design*

- [NIST Hardware Security (project)](https://csrc.nist.gov/projects/hardware-security) — NIST's program on semiconductor and supply-chain threats, hardware roots of trust, and security measurement.
- [NIST IR 8517: Hardware Security Failure Scenarios — Potential Hardware Weaknesses](https://csrc.nist.gov/pubs/ir/8517/final) — a 2024 catalog of concrete ways hardware can fail or be attacked, directly supporting the hardware-weakness prompt.
- [CCCS: Cyber Security at Home and in the Office — Secure Your Devices, Computers, and Networks (ITSAP.00.007)](https://www.cyber.gc.ca/en/guidance/cyber-security-home-and-office-secure-your-devices-computers-and-networks-itsap00007) — practical physical device-security basics.
