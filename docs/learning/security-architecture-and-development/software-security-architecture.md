# Software Security Architecture

## Description

Designing software systems that ensure they are resistant to attacks. This includes defining secure components, interactions, and protections such as authentication and authorization mechanisms. Secure architecture prevents vulnerabilities from being baked into the software, reducing risks such as data breaches and malware exploitation.

## Why This Matters

Software security architecture is essential because designing software with security in mind prevents vulnerabilities from being built into systems. By defining secure components, interactions, and protections, staff can rely on software that resists attacks, protects data, and supports trustworthy operations. Enterprise operations depend on software systems for business functions, administration, communication, and infrastructure. Secure software architecture helps the organization:

- Prevent vulnerabilities that could compromise critical systems.
- Ensure robust authentication, authorization, and access controls.
- Reduce the risk of data breaches, malware exploitation, and operational disruptions.
- Maintain reliable and secure software services across departments.

Applying secure architectural principles allows staff to deploy systems that are resilient, maintainable, and aligned with organizational security requirements. By integrating software security architecture into system design and daily use, the organization promotes safe, resilient, and reliable software that supports business operations.

## Skill Development

- Reflect: How does the use of secure software architecture prevent potential vulnerabilities from being integrated into a system?
- Investigate: What are the key principles of a secure software design that an architect should consider when designing access control models?
- Research: In secure architecture design, how can the principle of least privilege be applied to both user roles and system components?
- Investigate: OWASP added "Insecure Design" (A04:2021) to its Top 10 to highlight weaknesses that come from the architecture itself rather than from coding mistakes. What is the difference between an insecure-design flaw and an implementation bug, and how do secure design patterns and threat modeling help prevent insecure design?
- Investigate: In a system built from multiple components and services, how should interactions across trust boundaries be secured — validating all input, authenticating service-to-service calls (for example with mutual TLS), and treating every component's input as untrusted — so that one compromised component cannot undermine the whole system?

## Learning Resources

> **Scope and design note:** Architecture decides which vulnerabilities are even possible: a sound design makes whole classes of attack hard to express, while a flawed one cannot be patched away later, only redesigned. Two ideas carry most of the weight. First, design-level flaws ("insecure design") are distinct from coding bugs — a scanner finds the bug, but only review and threat modeling find the flaw — so model threats at the design stage and revisit the model as the system changes. Second, trust nothing implicitly: enforce least privilege for users and components alike, authenticate interactions across trust boundaries, and treat every component's input as untrusted, so a single compromised part does not bring down the whole.

### Reference and further reading

- [O'Reilly: *Solutions Architect's Handbook*](https://www.oreilly.com/library/view/solutions-architects-handbook/9781838645649/) and [a search for software security architecture](https://www.oreilly.com/search/?q=software%20security%20architecture&type=book&rows=100)
- [McMaster Library: Software security architecture (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Software%20Security%20Architecture&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Software security architecture (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Software%20Security%20Architecture&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)
  
### Secure architecture foundations

*Supports: Reflect — how secure architecture prevents built-in vulnerabilities; the architecture concepts behind every prompt*

- [Wikipedia: Software architecture](https://en.wikipedia.org/wiki/Software_architecture) and [Enterprise information security architecture](https://en.wikipedia.org/wiki/Enterprise_information_security_architecture) — background on architecture generally and on security architecture as a discipline.
- [NIST SP 800-160 Vol. 1 Rev. 1: Engineering Trustworthy Secure Systems](https://csrc.nist.gov/pubs/sp/800/160/v1/r1/final) — reference for engineering security into a system's architecture from the outset.
- [NIST SP 800-218: Secure Software Development Framework (SSDF) v1.1](https://csrc.nist.gov/pubs/sp/800/218/final) — recommended secure-development practices, including design-phase activities, across the software lifecycle.

### Secure design, access control, and least privilege

*Supports: Investigate — principles for designing access control models; Research — applying least privilege to roles and components*

- [OWASP Application Security Verification Standard (ASVS)](https://owasp.org/www-project-application-security-verification-standard/) — a catalog of security requirements for architecture, authentication, access control, and more, usable as a design checklist.
- [OWASP: Authorization Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html) — designing access control: enforcing least privilege, deny-by-default, and server-side authorization. The direct reference for the access-control and least-privilege prompts.
- [CCCS: Zero Trust Security Model (ITSAP.10.008)](https://www.cyber.gc.ca/en/guidance/zero-trust-security-model-itsap10008) — the zero trust model, which applies least privilege and "never trust, always verify" at the architectural level.

### Insecure design and architectural threat modeling

*Supports: Investigate — insecure design vs. implementation bugs; Investigate — securing interactions across trust boundaries*

- [OWASP Top 10 — A04:2021 Insecure Design](https://owasp.org/Top10/A04_2021-Insecure_Design/) — the category for flaws rooted in the design itself, and the secure design patterns and threat-modeling practices that prevent them. The direct reference for the insecure-design prompt.
- [OWASP: Threat Modeling Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html) — identifying trust boundaries, data flows, and threats (e.g., with STRIDE) at the design stage. The direct reference for the trust-boundary prompt.
- [CCCS: Security Considerations for Edge Devices (ITSM.80.101)](https://www.cyber.gc.ca/en/guidance/security-considerations-edge-devices-itsm80101) — why the components exposed at trust boundaries are frequent targets.
- [CCCS: Guidance on Securely Configuring Network Protocols (ITSP.40.062)](https://www.cyber.gc.ca/en/guidance/guidance-securely-configuring-network-protocols-itsp40062) — securing the protocols that carry interactions between components.

### Reference architectures and vendor perspectives

- [Cisco: Security Reference Architecture](https://www.cisco.com/c/en/us/products/security/cisco-security-reference-architecture.html) — a worked example of an enterprise security reference architecture.
- [Fortinet: Security Fabric](https://www.fortinet.com/solutions/enterprise-midsize-business/security-fabric) — a vendor architecture for integrating security controls across an environment.
