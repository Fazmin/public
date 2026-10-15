# Secret Management & Key Infrastructure

## Description

Managing secrets, such as passwords and API keys, and encryption keys through systems like Public Key Infrastructure (PKI) or secret vaults. Poor management of secrets and keys can lead to unauthorized access or decryption of sensitive data.

## Why This Matters

Secret management and key infrastructure are critical because improper handling of passwords, API keys, and encryption keys can expose sensitive data and systems to unauthorized access. Effective management ensures that only authorized users and systems can access critical resources, protecting the confidentiality, integrity, and availability of information across the organization. Enterprise operations rely on secure management of secrets and cryptographic keys to protect databases, cloud services, and administrative systems. Strong practices help the organization:

- Prevent unauthorized access to critical IT systems and applications.
- Secure cloud environments, hybrid infrastructures, and on-premise services.
- Protect sensitive organizational, financial, and operational data.
- Support compliance with legal, regulatory, and contractual obligations.

By implementing robust key management practices, staff can reduce operational risk and strengthen trust in the organization's IT ecosystem. Secret management and key infrastructure influence the daily responsibilities of staff and technical teams:

- Staff implement key management systems, maintain secure storage of passwords and API keys, and integrate hardware security modules (HSMs) to protect sensitive credentials.
- Technical teams use secure vaults, encrypted keys, and PKI tools to protect datasets, manage access, and secure cloud-based collaboration.
- End users interact with systems that enforce secure access, multi-factor authentication, and safe handling of credentials when using business applications.

By embedding secret management and key infrastructure practices into daily activities, the organization ensures strong protection of its digital assets and promotes a secure and trustworthy IT environment for all users.

## Skill Development

- Investigate: How should key management systems be designed to ensure the confidentiality and integrity of cryptographic keys across a distributed system?
- Investigate: How can organizations ensure that secret management practices are integrated into the design of their cloud and on-premise IT infrastructures?
- Research: In the context of secure design, how does the use of hardware security modules (HSMs) improve key management processes and protect sensitive data?
- Investigate: Application secrets such as API keys, database passwords, and tokens are often hardcoded in source code, configuration files, or CI/CD pipelines, leading to "secret sprawl" and leaks. How do secret vaults, secret scanning, injecting secrets at runtime (rather than committing them), and short-lived or dynamic secrets reduce this risk?
- Investigate: PKI is central to key infrastructure. How does a certificate lifecycle work — issuance by a certificate authority, validation, revocation (CRL/OCSP), and renewal — and why are expired or misissued certificates, and poor certificate lifecycle management, such common operational failure points?

## Learning Resources

> **Scope and handling note:** Secrets and keys are the highest-value targets in a system — whoever holds them can impersonate services, read encrypted data, or move freely through infrastructure. Keep them in dedicated vaults or HSMs, never in source code, configuration files, tickets, or chat; grant least-privilege access to them and log every access; rotate them regularly and prefer short-lived or dynamic secrets over long-lived static ones. Plan for both recovery and revocation — a lost key can mean data is unrecoverable, while a leaked one must be revoked or rotated immediately. Treat any secret that may have been exposed as compromised and rotate it, even if it is "probably fine."

### Reference and further reading

- [O'Reilly: Secrets management and key management](https://www.oreilly.com/search/?q=secrets%20management%20key%20management&type=book&rows=100)
- [McMaster Library: Secret management and key infrastructure (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Secret%20Management%20%26%20Key%20Infrastructure&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Secret management and key infrastructure (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Secret%20Management%20%26%20Key%20Infrastructure&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)
  
### Key management foundations

*Supports: Investigate — designing key management for confidentiality and integrity across distributed systems*

- [Wikipedia: Key management](https://en.wikipedia.org/wiki/Key_management) — the concepts: key generation, distribution, storage, rotation, and destruction.
- [NIST SP 800-57 Part 1 Rev. 5: Recommendation for Key Management — Part 1: General](https://csrc.nist.gov/pubs/sp/800/57/pt1/r5/final) — the core reference on key lifecycles, crypto-periods, and protection.
- [NIST SP 800-57 Part 2 Rev. 1: Best Practices for Key Management Organizations](https://csrc.nist.gov/pubs/sp/800/57/pt2/r1/final) — organizational policy and governance for key management.
- [NIST SP 800-57 Part 3 Rev. 1: Application-Specific Key Management Guidance](https://csrc.nist.gov/pubs/sp/800/57/pt3/r1/final) — applying key management to specific technologies (PKI, TLS, and more).
- [CCCS: Cryptographic Key Management and Ordering (Learning Hub, Course COM204C)](https://www.cyber.gc.ca/en/education-community/learning-hub/courses/cryptographic-key-management-ordering) — a structured course on managing cryptographic keys.
- [CCCS: Cryptographic Security in the Government of Canada (Learning Hub, Course CRY101C)](https://www.cyber.gc.ca/en/education-community/learning-hub/courses/cryptographic-security-gc) — broader context for applying cryptography in an organization.

### PKI and certificate lifecycle

*Supports: Investigate — PKI, the certificate lifecycle, and its failure points*

- [Wikipedia: Public key infrastructure (PKI)](https://en.wikipedia.org/wiki/Public_key_infrastructure) — certificate authorities, the chain of trust, and how PKI binds identities to public keys.
- [NIST SP 1800-16: Securing Web Transactions — TLS Server Certificate Management](https://csrc.nist.gov/pubs/sp/1800/16/final) — a practice guide for running a formal certificate management program, directly addressing why certificate lifecycle management (expiry, revocation, renewal) is a frequent failure point.

### Secret management for applications and the cloud

*Supports: Investigate — integrating secret management into cloud and on-premise design; Investigate — secret sprawl and hardcoded secrets*

- [OWASP: Secrets Management Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html) — avoiding hardcoded secrets, using centralized vaults, rotation, CI/CD and cloud secret handling. The direct reference for the secret-sprawl prompt.
- [HashiCorp Vault: Key Management Secrets Engine](https://developer.hashicorp.com/vault/docs/secrets/key-management) — an example of a secret and key vault that stores, distributes, and rotates secrets centrally.
- [CCCS: Guidance on Cloud Service Cryptography (ITSP.50.106)](https://www.cyber.gc.ca/en/guidance/guidance-cloud-service-cryptography-itsp50106) — managing keys and secrets (including customer-managed keys) in cloud services.

### Hardware-protected keys (HSMs)

*Supports: Research — how HSMs improve key management and protect sensitive data*

- [Palo Alto Networks: Secure Keys with a Hardware Security Module](https://docs.paloaltonetworks.com/ngfw/administration/certificate-management/secure-keys-with-hardware-security-module) — using an HSM so private keys never leave tamper-resistant hardware.
- [Palo Alto Networks: Encrypt Master Key Using an HSM](https://docs.paloaltonetworks.com/ngfw/administration/certificate-management/secure-keys-with-hardware-security-module/encrypt-master-key-using-hsm) — protecting the master key that wraps other secrets with an HSM.
