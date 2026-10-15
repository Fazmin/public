# Authorization

## Description

Authorization is the process of determining and enforcing what actions an authenticated subject is permitted to perform on a system. It is typically implemented through access control models such as discretionary access control (DAC), mandatory access control (MAC), or role-based access control (RBAC), and must align with organizational policies and user roles.

## Why This Matters

Authorization matters because it ensures that authenticated users can perform only the actions they are permitted to, reducing the risk of accidental or malicious misuse of systems. By defining and enforcing access rights, organizations can protect sensitive data, maintain system integrity, and align user capabilities with organizational roles. Without proper authorization, even authenticated users could access or modify resources beyond their intended privileges, creating security and compliance risks. Enterprise operations depend on authorization to control access across administrative systems, shared platforms, and cloud services. Proper authorization helps operational teams:

- Implement role-based access control (RBAC) to align privileges with job responsibilities.
- Manage access control lists (ACLs) to prevent privilege creep and unauthorized system use.
- Enforce policies that segregate duties and reduce insider threats.
- Maintain compliance with internal policies, regulatory requirements, and audit standards.
- Ensure operational continuity by restricting critical system modifications to authorized personnel.
- Staff rely on authorization to enforce least privilege, manage system access, and maintain secure administrative operations.
- Technical teams depend on access controls to ensure that shared systems, computing resources, and data are used appropriately and securely.
- End users benefit from authorization mechanisms that control access to business platforms and shared resources, preventing unauthorized activity.

Without effective authorization, operational systems are vulnerable to misuse, policy violations, and potential data breaches. By managing authorization effectively, the organization maintains security, reduces risk, and ensures proper access control across its systems.

## Skill Development

- Research: What are the advantages and limitations of implementing role-based access control in a complex organization?
- Investigate: How can access control lists (ACLs) be managed effectively to prevent privilege creep?
- Reflect: What steps should be taken to ensure authorization rules remain aligned with evolving organizational roles?
- Research: The Description names DAC, MAC, and RBAC. How do these compare with attribute-based (ABAC) and relationship-based (ReBAC) access control, what factors determine which model fits a given system, and why do large organizations often combine models — for example, RBAC for broad roles plus ABAC for fine-grained, context-aware rules?
- Investigate: Why must authorization be enforced on the server for every request — never trusting the client or relying on hiding a feature in the interface — and how can an organization verify that its authorization rules actually enforce the intended policy (for example, through authorization testing and centralized policy engines / policy-as-code)?

## Learning Resources

> **Design-principle note:** The safe baseline for authorization is deny by default and fail closed — a request that isn't explicitly allowed is denied, and an error denies rather than grants access. Enforce every decision server-side, keep authorization decisions auditable, and grant the minimum needed rather than access "just in case," which is the seed of privilege creep. These principles run through the resources below.

### Reference and further reading

- [McMaster Library: Authorization in information security (videos, 2010–2025)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Authorization%20Information%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2025&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Authorization in information security (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Authorization%20Information%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=rtype,include,books&facet=searchcreationdate,include,2010%7C,%7C2025&lang=en&offset=0)
- [O'Reilly: Identity and Access Management](https://www.oreilly.com/search/?q=Learning%3A%20Identity%20and%20Access%20Management&type=article&type=book&type=shortcut&rows=100)

### Access control models

*Supports: Research — RBAC advantages and limits; Research — comparing DAC/MAC/RBAC with ABAC/ReBAC*

- [NIST: Role Based Access Control (RBAC) project](https://csrc.nist.gov/projects/role-based-access-control) — NIST's reference material on the RBAC model it helped standardize, including its strengths and limits in large organizations.
- [NIST SP 800-162: Guide to Attribute Based Access Control (ABAC)](https://csrc.nist.gov/pubs/sp/800/162/upd1/final) — the authoritative treatment of ABAC, which grants access based on attributes and context rather than fixed roles; essential for the model-comparison prompt.
- [Wikipedia: Authorization](https://en.wikipedia.org/wiki/Authorization) and [NIST Glossary: Authorization](https://csrc.nist.gov/glossary/term/authorization) — concept and precise definition.

### Designing and enforcing authorization

*Supports: Investigate — managing ACLs; Investigate — server-side enforcement and policy-as-code*

- [OWASP Authorization Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html) — the single best practical reference: enforce least privilege and deny by default, check authorization server-side on every request, prefer ABAC or ReBAC where fine-grained control is needed, protect object identifiers, fail safely, and log and test.
- [NIST SP 800-53 Rev. 5: Security and Privacy Controls](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) — see Access Control (AC) controls, especially **AC-3 (Access Enforcement)**, **AC-5 (Separation of Duties)**, and **AC-6 (Least Privilege)**.
- [Open Policy Agent (OPA)](https://www.openpolicyagent.org/) — a widely used open-source engine for externalized, centralized authorization ("policy as code"), so authorization rules are defined and tested in one place rather than scattered through application code. Directly supports the enforcement/verification prompt.
- [Microsoft: Azure Role-Based Access Control (RBAC)](https://learn.microsoft.com/en-us/azure/role-based-access-control/overview) and [IBM Verify (IAM)](https://www.ibm.com/products/verify) — vendor implementations of role- and policy-based authorization.

### Verifying that authorization matches policy

*Supports: Investigate — verifying enforcement; Reflect — keeping rules aligned*

- [OWASP Web Security Testing Guide: Authorization Testing](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/05-Authorization_Testing/) — how to test that authorization actually works, including privilege escalation, IDOR, and bypass.
- [OWASP Top 10:2025 — A01 Broken Access Control](https://owasp.org/Top10/2025/A01_2025-Broken_Access_Control/) — the failure mode this whole topic prevents, and the most common web application risk; a useful reference for what weak authorization looks like in practice.
- [NIST SP 800-192: Verification and Test Methods for Access Control Policies/Models](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-192.pdf) — systematic methods for confirming that an access-control policy enforces what it is supposed to.

### Keeping authorization aligned and governed

*Supports: Investigate — preventing privilege creep; Reflect — aligning rules with evolving roles*

- [CCCS: Implement Access Control and Authorization](https://www.cyber.gc.ca/en/guidance/implement-access-control-and-authorization) — practical steps for setting up and maintaining authorization.
- [CCCS: Managing and Controlling Administrative Privileges (ITSAP.10.094)](https://www.cyber.gc.ca/en/guidance/managing-and-controlling-administrative-privileges-itsap10094) — the highest-risk authorizations to keep least-privileged and reviewed.
- [CCCS: Annex 3A — Security Control Catalogue (ITSG-33)](https://www.cyber.gc.ca/en/guidance/annex-3a-security-control-catalogue-itsg-33)

### Zero Trust and cloud authorization

*Supports: broader context — continuous, per-request authorization*

- [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/pubs/sp/800/207/final) — reframes authorization as a continuous, per-request decision rather than a one-time gate, the model modern enterprises are moving toward.
- [CCCS: A Zero Trust Approach to Security Architecture (ITSM.10.008)](https://www.cyber.gc.ca/en/guidance/zero-trust-approach-security-architecture-itsm10008)
- [CCCS: Guidance on Cloud Security Assessment and Authorization (ITSP.50.105)](https://www.cyber.gc.ca/en/guidance/guidance-cloud-security-assessment-and-authorization-itsp50105)
