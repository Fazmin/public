# Account Management

## Description

Account management encompasses the lifecycle processes of provisioning, maintaining, and deprovisioning user accounts. This includes implementing role-based access control (RBAC), enforcing the principle of least privilege, conducting regular access reviews, and disabling or removing dormant accounts to reduce the attack surface.

## Why This Matters

Account management matters because it ensures that users have appropriate access to organizational systems while minimizing the risk of unauthorized activity. Proper management of account lifecycles from creation to deactivation reduces the attack surface, enforces least privilege, and maintains compliance with security policies. Without effective account management, dormant, misconfigured, or excessive privileges can be exploited by attackers or lead to accidental data exposure. Operations rely on account management to maintain control over administrative systems, cloud platforms, and shared IT resources. Effective account management helps operational teams:

- Provision and deprovision user accounts efficiently to reduce administrative overhead.
- Implement role-based access control (RBAC) to ensure users have only the access they need.
- Conduct regular access reviews to identify and remove inactive or unnecessary accounts.
- Prevent privilege creep for staff, contractors, and third-party users.
- Support compliance with internal governance, audit, and cybersecurity requirements.
- Minimize the risk of insider threats or misuse due to excessive or outdated privileges.
- Staff rely on automated and manual account processes to manage employee and contractor access, enforce least privilege, and maintain secure administrative operations.
- Technical teams depend on proper account provisioning to access shared computing resources and collaboration tools without risk of unauthorized access.
- End users benefit indirectly, as their accounts are created, monitored, and disabled according to policy, reducing the risk of account misuse and maintaining safe access to business systems.

Without proper account management, operational systems could be vulnerable to unauthorized access, data breaches, and policy violations. By managing accounts effectively, the organization ensures security, reduces risk, and maintains stable and trustworthy operations across its systems.

## Skill Development

- Reflect: How can automated account provisioning and deprovisioning reduce security risks and administrative overhead?
- Research: What are the implications of failing to conduct periodic access reviews for user and privileged accounts?
- Reflect: How should account management policies be structured to support compliance with industry security frameworks?
- Investigate: How does managing non-human identities — service accounts, API keys, tokens, and machine accounts — differ from managing human user accounts? Why are these often the most over-privileged and least-reviewed accounts, and what practices (clear ownership, inventory, scoping, and rotation) bring them under control?
- Reflect: How do the principles of least privilege and separation of duties limit the damage a single compromised or misused account can cause, and how can "privilege creep" be detected and reversed through access reviews and role design?

## Learning Resources

> **Scope and oversight note:** Account and access data is sensitive and often tied to HR records, so handle it accordingly and keep access reviews consistent and documented. Automation amplifies whatever rules you give it: provisioning wired to an accurate source of truth (such as an HR system) enforces least privilege at scale, but a bad role definition grants bad access at scale just as fast — so pair automation with human oversight, clear role definitions, and audit.

### Reference and further reading

- [Wikipedia: Identity and access management (IAM)](https://en.wikipedia.org/wiki/Identity_and_access_management)
- [IBM: What Is Identity and Access Management (IAM)?](https://www.ibm.com/think/topics/identity-access-management)
- [O'Reilly: Identity and Access Management](https://www.oreilly.com/search/?q=Learning%3A%20Identity%20and%20Access%20Management&type=article&type=book&type=shortcut&rows=100)
- [McMaster Library: Account management in information security (videos, 2010–2025)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Account%20Management%20Information%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2025&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Account management in information security (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Account%20Management%20Information%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=rtype,include,books&facet=searchcreationdate,include,2010%7C,%7C2025&lang=en&offset=0)

### Standards and control frameworks

*Supports: Reflect — structuring policy for compliance frameworks; Research — access reviews*

- [NIST SP 800-53 Rev. 5: Security and Privacy Controls](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) — the Access Control (AC) family is the backbone here, especially **AC-2 (Account Management)** — which maps directly to this topic's lifecycle — and **AC-6 (Least Privilege)**.
- [NIST Identity and Access Management Resource Center](https://www.nist.gov/identity-and-access-management) — NIST's hub for IAM guidance and projects.
- [CIS Control 5: Account Management](https://www.cisecurity.org/controls/account-management) — concise, prescriptive safeguards for inventorying accounts, disabling dormant ones, and managing the account lifecycle. The most on-point framework control for this page.
- [CIS Control 6: Access Control Management](https://www.cisecurity.org/controls/access-control-management) — the companion control covering granting, reviewing, and revoking access rights.
- [CCCS: Annex 3A — Security Control Catalogue (ITSG-33)](https://www.cyber.gc.ca/en/guidance/annex-3a-security-control-catalogue-itsg-33) — the Canadian control catalogue with equivalent account-management controls.

### Account lifecycle and automated provisioning

*Supports: Reflect — automated provisioning and deprovisioning*

- [SCIM — System for Cross-domain Identity Management](https://scim.cloud/) — the open standard that automates provisioning and deprovisioning of accounts across applications, so a change in the source of truth propagates (and revokes) access automatically. The direct answer to the automation prompt.
- [Microsoft: Azure Identity Management and Access Control Security Best Practices](https://learn.microsoft.com/en-us/azure/security/fundamentals/identity-management-best-practices) — practical guidance including automating the joiner–mover–leaver lifecycle.

### Access reviews and least privilege

*Supports: Research — access reviews; Reflect — least privilege and privilege creep*

- [Microsoft Entra: Access Reviews](https://learn.microsoft.com/en-us/entra/id-governance/access-reviews-overview) — how periodic access reviews are run in practice to find and remove unneeded access, directly supporting the access-review prompt.
- [Okta: Principle of Least Privilege — Definition, Methods & Examples](https://www.okta.com/identity-101/minimum-access-policy/)
- [CCCS: Managing and Controlling Administrative Privileges (ITSAP.10.094)](https://www.cyber.gc.ca/en/guidance/managing-and-controlling-administrative-privileges-itsap10094) — privileged accounts are the highest-risk ones to review and keep least-privileged.

### Non-human identities and service accounts

*Supports: Investigate — managing service accounts and machine identities*

- [Cloud Security Alliance: Introducing the OWASP Non-Human Identities (NHI) Top 10](https://cloudsecurityalliance.org/articles/introducing-the-owasp-nhi-top-10-standardizing-non-human-identity-security) — an overview of the OWASP NHI Top 10, which catalogs the most common ways service accounts, API keys, and tokens are mismanaged (over-privileged, unrotated, orphaned, unmonitored) and how to govern them.

### Credential hygiene and monitoring

- [CCCS: Password Managers – Security Tips (ITSAP.30.025)](https://www.cyber.gc.ca/en/guidance/password-managers-security-itsap30025)
- [CCCS: Using Security Information and Event Management (SIEM) Tools (ITSM.80.024)](https://www.cyber.gc.ca/en/guidance/using-security-information-event-management-tools-manage-cyber-security-risks-itsm80024) — centralizing account and access events to spot misuse and support reviews.
