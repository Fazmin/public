# Encryption

## Description

Encryption converts data into a secure format, ensuring that only authorized parties can access it. Common techniques include AES, RSA, and TLS for securing communications and stored data from unauthorized access.

## Why This Matters

Encryption is essential because it protects sensitive data, communications, and digital assets from unauthorized access. Strong encryption ensures confidentiality, preserves data integrity, and supports trust across the organization's IT systems. By implementing effective encryption practices, staff help safeguard information critical to business and operational activities. Enterprise operations rely on encrypted systems to protect financial transactions, employee records, administrative databases, and cloud-based services. Encryption helps the organization and users:

- Maintain confidentiality of sensitive organizational and personal data.
- Ensure secure transmission of information across networks.
- Protect critical systems from unauthorized access and data breaches.
- Comply with legal, regulatory, and contractual requirements.
- Staff add confidentiality measures to databases, email, backups, and network communications, manage keys securely, and ensure proper cryptographic protocols are followed.
- Technical teams use secure storage and communications for sensitive datasets, maintain secure key-handling practices, and follow guidelines for protecting collaborative projects.
- End users interact confidentially with systems through secure applications, email, and cloud storage, adhering to policies that protect their own and others' information.

## Skill Development

- Research: How does encryption design impact the confidentiality and integrity of data, and what factors must be considered when selecting an encryption algorithm?
- Investigate: How can symmetric and asymmetric encryption be utilized in the design of secure systems for data protection at rest and in transit?
- Investigate: How does encryption key management factor into overall system design, and what practices ensure secure key distribution and rotation?
- Investigate: For data at rest, what is the difference between full-disk encryption, file or folder encryption, and database or application-level encryption (such as transparent data encryption)? Why does encryption at rest defend against some threats (a lost or stolen disk) but not others (a compromised, running application that already holds the key)?
- Reflect: Encryption is reversible with the right key, whereas hashing is a one-way function. Why is it inaccurate to say that well-managed passwords are "encrypted," and how should a designer decide when data should be encrypted (and later decrypted) versus hashed?

## Learning Resources

> **Scope and key-management note:** Encryption only protects against specific threats — an intercepted transmission or a stolen disk — not a compromised running system, a careless user, or a mishandled key. The key is the real secret, so how keys are generated, stored, rotated, backed up, and destroyed usually determines whether encryption succeeds; losing a key can also mean losing the data permanently, so plan for recovery. Use standardized algorithms and well-vetted libraries rather than inventing your own, and keep algorithm and key-length choices current as guidance shifts toward quantum-resistant options.

### Reference and further reading

- [O'Reilly: Encryption](https://www.oreilly.com/search/?q=Encryption&type=book&rows=100)
- [McMaster Library: Encryption (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Encryption&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)
  
### Foundations and algorithm selection

*Supports: Research — encryption design and algorithm selection; Reflect — encryption versus hashing*

- [Wikipedia: Encryption](https://en.wikipedia.org/wiki/Encryption) — what encryption is, the difference between symmetric and asymmetric schemes, and how it differs from one-way hashing (useful for the encryption-vs-hashing prompt).
- [CCCS: Cryptographic Algorithms for UNCLASSIFIED, PROTECTED A, and PROTECTED B Information (ITSP.40.111)](https://www.cyber.gc.ca/en/guidance/cryptographic-algorithms-unclassified-protected-protected-b-information-itsp40111) — which algorithms (AES, RSA, ECC, SHA-2/3) and key sizes are approved and for what sensitivity levels. The direct reference for algorithm selection.
- [CCCS: Preparing Your Organization for the Quantum Threat to Cryptography (ITSAP.00.017)](https://www.cyber.gc.ca/en/guidance/preparing-your-organization-quantum-threat-cryptography-itsap00017) — why algorithm selection must now consider quantum resistance and crypto-agility.
- [Cisco: What Is Encryption?](https://www.cisco.com/site/us/en/learn/topics/security/what-is-encryption.html) and [Palo Alto Networks: What Is Data Encryption?](https://www.paloaltonetworks.com/cyberpedia/data-encryption) 

### Symmetric, asymmetric, and protecting data at rest and in transit

*Supports: Investigate — symmetric vs. asymmetric for data at rest and in transit; Investigate — layers and limits of at-rest encryption*

- [CCCS: Using Encryption to Keep Your Sensitive Data Secure (ITSAP.40.016)](https://www.cyber.gc.ca/en/guidance/using-encryption-keep-your-sensitive-data-secure-itsap40016) — practical guidance on encrypting data at rest and in transit, including full-disk, file, and backup encryption. The direct reference for the data-at-rest prompt.
- [NIST SP 800-52 Rev. 2: Guidelines for the Selection, Configuration, and Use of TLS Implementations](https://csrc.nist.gov/pubs/sp/800/52/r2/final) — protecting data in transit with TLS.
- [Fortinet: Encryption Algorithms (IPsec/TLS for FortiGate)](https://docs.fortinet.com/document/fortigate/7.6.3/administration-guide/238852/encryption-algorithms) — a concrete example of choosing algorithms for data in transit.

### Key management

*Supports: Investigate — key management, secure key distribution, and rotation*

- [NIST SP 800-57 Part 1 Rev. 5: Recommendation for Key Management — Part 1: General](https://csrc.nist.gov/pubs/sp/800/57/pt1/r5/final) — the core reference for the full key lifecycle: generation, protection, distribution, crypto-periods, rotation, and destruction. The direct reference for the key-management prompt.
