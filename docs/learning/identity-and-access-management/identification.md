# Identification

## Description

Identification is the process of asserting a unique identity to a system, typically through a user ID or digital certificate. It serves as the foundation for access control by establishing a claimed identity, which must then be authenticated and authorized. Identification alone does not grant access—it simply declares who the subject claims to be.

## Why This Matters

Identification matters because it establishes the claimed identity of a user, device, or service before any authentication or authorization can occur. Without reliable identification, access control systems cannot determine who is requesting access, making it impossible to enforce permissions, track user actions, or maintain accountability. In a large enterprise environment with thousands of users and systems, accurate identification is essential to prevent impersonation, misattribution, and unauthorized activity. Enterprise operations rely on clear and consistent identification processes to ensure that administrative systems, services, and digital resources are accessed only by the correct individuals. Identification supports operational teams by enabling them to:

- Associate each login or system request with a unique identity.
- Ensure that accounts belong to verified employees, contractors, or service roles.
- Maintain accurate audit trails for compliance, incident investigation, and policy enforcement.
- Reduce risks associated with duplicate or ambiguous accounts.
- Support role-based access control for administrative resources.
- Provide a foundation for secure authentication and authorization workflows.
- Staff rely on unique user IDs to access administrative systems, process records, and maintain accountability for sensitive actions.
- Technical teams depend on accurate identity assignment to manage access to shared systems, data, and collaboration platforms.
- End users use their organizational identity to authenticate into business applications, email, Wi-Fi, and digital resources throughout their day-to-day work.

Without strong identification, operational systems could misattribute actions, allow unauthorized access, or expose sensitive information through account misuse. By establishing a clear and trustworthy identity for every user and system, identification ensures the organization can protect its digital environment, enforce policies, and maintain transparent, accountable operations.

## Skill Development

- Research: What are the key elements of a secure identification process in an enterprise identity and access management framework?
- Reflect: How would you explain the role of identification in supporting auditability and traceability of user actions?
- Investigate: In what scenarios could improper or duplicate identification compromise security in a large organization?
- Reflect: The Description stresses that identification only declares a claimed identity and does not by itself grant access. Why is it important to keep identification, authentication, and authorization distinct, and what goes wrong when a system treats a claimed identifier (such as a username or employee number) as if it were proof of identity?
- Investigate: How is a person's or entity's identity verified before an account and identifier are issued (identity proofing and enrollment), and why does the strength of that initial proofing limit how much trust the resulting identity can carry? How do NIST's Identity Assurance Levels (IAL1–IAL3) frame this?

## Learning Resources

> **Privacy and design note:** Identifiers tie real people and systems to records, so choose and handle them carefully. Don't reuse sensitive government numbers (such as a Social Insurance or Social Security number) as internal identifiers; prefer opaque, unique identifiers that are not reused between people over time. Minimize and protect identity-proofing data (ID documents, biometrics) as sensitive personal information, and remember that a unique identifier is a claim to be authenticated, not proof of identity on its own.

### Reference and further reading

- [McMaster Library: Identification in information security (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Identification%20Information%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=rtype,include,books&facet=searchcreationdate,include,2010%7C,%7C2025&lang=en&offset=0)
- [O'Reilly: Identity and Access Management](https://www.oreilly.com/search/?q=Learning%3A%20Identity%20and%20Access%20Management&type=article&type=book&type=shortcut&rows=100)

### Foundations: identification, authentication, and authorization

*Supports: Reflect — keeping identification distinct from authentication and authorization; auditability*

- [Wikipedia: Digital identity](https://en.wikipedia.org/wiki/Digital_identity) and [NIST Glossary: Identity](https://csrc.nist.gov/glossary/term/identity) — the concept and its precise definition.
- [Wikipedia: Electronic authentication](https://en.wikipedia.org/wiki/Electronic_authentication) — covers how a claimed identity (identification) is then verified (authentication), useful for the distinction prompt.

### Identity proofing, enrollment, and identifiers

*Supports: Research — key elements of a secure identification process; Investigate — identity proofing and assurance levels*

- [NIST SP 800-63 Revision 4: Digital Identity Guidelines](https://pages.nist.gov/800-63-4/) — the current edition (Revision 4 was finalized in 2025, replacing the Revision 3 set). Its **Identity Assurance Levels (IAL1–IAL3)** are the standard way to express how rigorously a claimed identity was verified, central to the proofing prompt.
- [NIST SP 800-63A-4: Identity Proofing and Enrollment](https://csrc.nist.gov/pubs/sp/800/63/a/4/final) — the document specifically about establishing and verifying a claimed identity before issuing credentials. The most on-point reference for this page.
- [NIST SP 800-53 Rev. 5: Security and Privacy Controls](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) — the Identification and Authentication (IA) family, especially **IA-4 (Identifier Management)**, which governs assigning unique identifiers and preventing reuse — directly on point for the duplicate/ambiguous-identity prompt — alongside IA-2 and IA-8 (identifying organizational and non-organizational users).
- [CCCS: Identity, Credential, and Access Management (ICAM) (ITSAP.30.018)](https://www.cyber.gc.ca/en/identity-credential-and-access-management-icam-itsap30018) — how identification fits within the broader ICAM lifecycle.
- [CCCS: User Authentication Guidance for IT Systems (ITSP.30.031 V3)](https://www.cyber.gc.ca/en/guidance/user-authentication-guidance-information-technology-systems-itsp30031-v3)

### From identification to authentication and federation

*Supports: Research — identification as the foundation for secure workflows*

- [NIST SP 800-63B-4: Authentication and Authenticator Management](https://csrc.nist.gov/pubs/sp/800/63/b/4/final) — the next step after identification: proving the claimed identity.
- [NIST SP 800-63C-4: Federation and Assertions](https://csrc.nist.gov/pubs/sp/800/63/c/4/final) — how one identity is recognized across systems and organizations (single sign-on, federated identity).
- [CCCS: Steps for Effectively Deploying Multi-Factor Authentication (ITSAP.00.105)](https://www.cyber.gc.ca/en/guidance/steps-effectively-deploying-multi-factor-authentication-mfa-itsap00105)
- [CCCS: Best Practices for Passphrases and Passwords (ITSAP.30.032)](https://www.cyber.gc.ca/en/guidance/best-practices-passphrases-and-passwords-itsap30032)

### Governance and lifecycle context

*Supports: Investigate — duplicate/ambiguous identities; auditability*

- [CCCS: Annex 3A — Security Control Catalogue (ITSG-33)](https://www.cyber.gc.ca/en/guidance/annex-3a-security-control-catalogue-itsg-33)
- [Okta: What Is Identity Management and Access Control?](https://www.okta.com/identity-101/what-is-identity-management-and-access-control/)
- [Microsoft: Identity and Access Management](https://www.microsoft.com/en-us/security/business/solutions/identity-access)
- [IBM Verify (IAM)](https://www.ibm.com/products/verify)
