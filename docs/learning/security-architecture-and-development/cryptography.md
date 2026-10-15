# Cryptography

## Description

The broader study and application of mathematical techniques for secure communication, including encryption, hashing, digital signatures, and other methods to ensure data integrity, authenticity, and confidentiality. Cryptography underpins most modern security practices, from securing emails to online banking, safeguarding digital interactions from a variety of attacks.

## Why This Matters

Cryptography is essential because it underpins secure communication, protects data integrity, and ensures authenticity across the organization's digital environment. Strong cryptographic practices safeguard information from unauthorized access, tampering, and forgery, enabling trusted operations and interactions. By applying cryptography correctly, it can help maintain a secure and resilient technology ecosystem. Organizations rely on cryptography to protect communications, databases, and digital services. Cryptography helps:

- Ensure secure email, file sharing, and administrative communications.
- Protect sensitive organizational data, including financial and HR records.
- Safeguard systems from cyberattacks, impersonation, and tampering.
- Comply with regulatory, legal, and contractual security obligations.
- Staff implement and maintain cryptographic protocols for system security, secure communications, key management, and authentication services.
- Technical teams use cryptography to protect datasets, validate digital signatures, and securely transmit information within and across organizations.
- End users interact with cryptographic systems when using secure applications, submitting information digitally, and accessing cloud-based resources.

Proper cryptographic practices support operational continuity, protect critical assets, and reinforce trust in organizational systems. Integrating cryptography into everyday activities ensures the confidentiality, integrity, and authenticity of information, supporting a secure, trustworthy, and resilient environment.

## Skill Development

- Research: How does the design of cryptographic protocols ensure secure communication and data integrity across a network?
- Investigate: What are the security design considerations when implementing digital signatures and public key infrastructure (PKI) in a distributed environment?
- Investigate: How does the proper selection of cryptographic algorithms, such as RSA and AES, contribute to a secure system design that resists cryptanalytic attacks?
- Investigate: Cryptography often fails not because the algorithm is weak but because keys are mishandled. What does the full key-management lifecycle involve — generation, secure storage (such as hardware security modules or key vaults), distribution, rotation, revocation, and destruction — and why is key management frequently the hardest part of a cryptographic system to get right?
- Investigate: Why are organizations being urged to prepare now for the quantum threat to cryptography, what does "crypto-agility" mean, and how should an organization inventory the cryptography it uses and plan a migration to the new post-quantum standards (NIST's ML-KEM and ML-DSA)?

## Learning Resources

> **Scope and practice note:** The most reliable rule in applied cryptography is not to invent your own — use standardized algorithms and well-vetted, maintained libraries, and keep algorithm, key-length, and protocol choices aligned with current guidance (which is now shifting toward post-quantum algorithms). Cryptography also fails most often at the edges: weak key management, reused or poorly generated keys, expired or improperly validated certificates, and misconfiguration. Treat keys and private certificates as highly sensitive secrets, and test cryptographic changes carefully, since a mistake can silently weaken protection or break access to encrypted data.

### Reference and further reading

- [O'Reilly: Cryptography](https://www.oreilly.com/search/?q=Cryptography&type=book&rows=100)
- [*Cryptography* (journal)](https://browzine.com/libraries/281/journals/162763/issues/current)
- [McMaster Library: Cryptography (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Cryptography&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Cryptography (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Cryptography&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)

### Foundations and algorithm selection

*Supports: Research — cryptographic protocols and data integrity; Investigate — selecting algorithms such as RSA and AES*

- [Wikipedia: Cryptography](https://en.wikipedia.org/wiki/Cryptography) — an overview of the field: symmetric and asymmetric encryption, hashing, and digital signatures, and how they provide confidentiality, integrity, and authenticity.
- [CCCS: Cryptographic Algorithms for UNCLASSIFIED, PROTECTED A, and PROTECTED B Information (ITSP.40.111)](https://www.cyber.gc.ca/en/guidance/cryptographic-algorithms-unclassified-protected-protected-b-information-itsp40111) — which algorithms (AES, RSA, ECC, SHA-2/3) and key sizes are approved and for what sensitivity levels. The direct reference for the algorithm-selection prompt.
- [NIST SP 800-131A Rev. 2: Transitioning the Use of Cryptographic Algorithms and Key Lengths](https://csrc.nist.gov/pubs/sp/800/131/a/r2/final) — which algorithms and key lengths are acceptable, deprecated, or disallowed over time. (A Revision 3 is in draft, reflecting the move toward post-quantum algorithms.)

### Public key infrastructure and digital signatures

*Supports: Investigate — digital signatures and PKI in a distributed environment*

- [Fortinet: What Is Public Key Infrastructure (PKI)?](https://www.fortinet.com/resources/cyberglossary/public-key-infrastructure) — a vendor-neutral explainer of PKI, certificates, and the chain of trust.
- [Cisco: Public Key Infrastructure (PKI)](https://www.cisco.com/c/en/us/tech/security-vpn/public-key-infrastructure-pki/index.html) — configuring and operating PKI on network infrastructure.
- [Palo Alto Networks: Keys and Certificates](https://docs.paloaltonetworks.com/ngfw/administration/certificate-management/keys-and-certificates) — how keys and certificates are generated, stored, and used on a device.

### Key management

*Supports: Investigate — the key-management lifecycle; secure algorithm and system design*

- [NIST SP 800-57 Part 1 Rev. 5: Recommendation for Key Management](https://csrc.nist.gov/pubs/sp/800/57/pt1/r5/final) — the core reference for the full key lifecycle: generation, protection, crypto-periods, rotation, and destruction. The direct reference for the key-management prompt.
- [CCCS: Guidance on Cloud Service Cryptography (ITSP.50.106)](https://www.cyber.gc.ca/en/guidance/guidance-cloud-service-cryptography-itsp50106) — how encryption and key management (including customer-managed keys) work in cloud services.

### Preparing for the quantum threat

*Supports: Investigate — the quantum threat, crypto-agility, and post-quantum migration*

- [CCCS: Preparing Your Organization for the Quantum Threat to Cryptography (ITSAP.00.017)](https://www.cyber.gc.ca/en/guidance/preparing-your-organization-quantum-threat-cryptography-itsap00017) — why to start now, how to inventory cryptography, and what crypto-agility means. The direct reference for the quantum prompt.
- [NIST Post-Quantum Cryptography project](https://csrc.nist.gov/projects/post-quantum-cryptography) — the standardization effort and the standards finalized in August 2024 — FIPS 203 (ML-KEM), FIPS 204 (ML-DSA), and FIPS 205 (SLH-DSA) — that organizations are migrating toward.
