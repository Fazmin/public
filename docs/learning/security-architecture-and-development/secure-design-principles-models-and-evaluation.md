# Secure Design Principles, Models, and Evaluation

## Description

Secure design principles focus on building systems and applications with security in mind from the outset. Models and evaluation frameworks help guide and assess the security of these systems. Implementing security at the design stage reduces vulnerabilities, saves costs associated with fixing issues later, and ensures that systems can withstand attacks.

## Why This Matters

Secure design principles, models, and evaluation are essential because building security into systems from the outset reduces vulnerabilities, prevents costly fixes later, and strengthens an organization's overall cybersecurity posture. By integrating security considerations during design, staff can rely on systems that are robust, resilient, and capable of protecting sensitive data and critical services. Enterprise operations rely on a wide array of applications, platforms, and services that support business and administrative functions. Secure design principles help the organization:

- Reduce the risk of vulnerabilities in software and systems.
- Ensure consistent application of access controls, encryption, and authentication.
- Prevent incidents that could disrupt core operational systems.
- Save resources by addressing security proactively rather than reactively.

Applying secure design frameworks allows staff to build systems that are reliable, maintainable, and resistant to attacks from the start. By integrating secure design and evaluation into everyday activities, an organization fosters resilient, trustworthy systems that support business operations and continuity.

## Skill Development

- Reflect: How do secure design principles contribute to the protection of information and systems throughout their lifecycle?
- Reflect: Can you describe how security models such as the Bell-LaPadula or Biba model apply to system design and their role in mitigating security risks?
- Investigate: What are some evaluation frameworks used to ensure the security of software applications and systems in the design phase?
- Reflect: The classic secure design principles — least privilege, fail-safe defaults, complete mediation, open design ("no security through obscurity"), economy of mechanism, and defense in depth — were articulated decades ago by Saltzer and Schroeder yet remain foundational. Choose a few and explain how applying, or ignoring, each one changes a system's security.
- Investigate: Threat modeling is a core design-phase activity for finding weaknesses before any code is written. How does a technique like STRIDE applied to a data-flow diagram (or an attack tree) work, and how does threat modeling complement formal evaluation frameworks such as the Common Criteria?

## Learning Resources

> **Scope and design note:** Building security in from the start is consistently cheaper and more effective than bolting it on later, which is the whole premise of secure design. Two cautions are worth keeping in mind. First, "open design" means a system's security should not depend on keeping its mechanism secret (no security through obscurity) — only the keys and secrets stay secret. Second, evaluation and certification (such as a Common Criteria rating) assure that a product met defined requirements *in a specific evaluated configuration and set of assumptions* — they are not a blanket guarantee of security, so understand the evaluated configuration before relying on it. Threat models and designs also need revisiting as a system changes, or they quietly go stale.

### Reference and further reading

- [O'Reilly: Secure software design](https://www.oreilly.com/search/?q=secure%20software%20design&type=book&rows=100)
- [McMaster Library: Secure software design (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Secure%20software%20design&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Secure software design (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Secure%20software%20design&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)

### Secure-by-design principles

*Supports: Reflect — principles across the lifecycle; Reflect — the classic Saltzer and Schroeder design principles*

- [Wikipedia: Secure by design](https://en.wikipedia.org/wiki/Secure_by_design) — the concept and the classic design principles it builds on.
- [CCCS and partners: Joint Guidance on Secure-by-Design and Default Principles ("Shifting the Balance of Cybersecurity Risk")](https://www.cyber.gc.ca/en/news-events/communications-security-establishment-cse-and-partners-issue-joint-guide-shifting-balance-cybersecurity-risk-technology-product-safety) — the modern international articulation of secure-by-design.
- [CCCS and partners: Joint Guidance on a Software Security Code of Practice](https://www.cyber.gc.ca/en/news-events/joint-guidance-software-security-code-practice) — 14 principles grouped into secure design and development, build environment, deployment and maintenance, and customer communication.
- [Fortinet: Secure-by-Design Commitments](https://www.fortinet.com/blog/industry-trends/fortinet-secure-by-design-commitments-making-measureable-progress-in-cybersecurity) and [Three Keys to Secure-by-Design Implementation](https://www.fortinet.com/blog/ciso-collective/keys-to-secure-by-design-implementation) — a vendor perspective on putting the principles into practice.
- [Palo Alto Networks: Product Security Assurance and Vulnerability Disclosure](https://www.paloaltonetworks.com/product-security-assurance) — an example of a vendor's secure-development and assurance program.

### Systems security engineering and the secure SDLC

*Supports: Reflect — secure design across the system and software lifecycle*

- [NIST SP 800-160 Vol. 1 Rev. 1: Engineering Trustworthy Secure Systems](https://csrc.nist.gov/pubs/sp/800/160/v1/r1/final) — the current (2022) foundational reference for engineering security into systems from the outset.
- [NIST SP 800-218: Secure Software Development Framework (SSDF) v1.1](https://csrc.nist.gov/pubs/sp/800/218/final) — recommended secure-development practices across each phase of the software lifecycle.

### Security models

*Supports: Reflect — Bell-LaPadula, Biba, and other models in system design*

- [Wikipedia: Bell–LaPadula model](https://en.wikipedia.org/wiki/Bell%E2%80%93LaPadula_model) — the classic **confidentiality** model ("no read up, no write down").
- [Wikipedia: Biba model](https://en.wikipedia.org/wiki/Biba_Model) — the complementary **integrity** model ("no write up, no read down"), useful for contrasting the goals different models enforce.

### Evaluation and threat modeling

*Supports: Investigate — evaluation frameworks; Investigate — threat modeling in the design phase*

- [Common Criteria for Information Technology Security Evaluation (ISO/IEC 15408)](https://www.commoncriteriaportal.org/index.cfm) — the international standard for evaluating and certifying the security of IT products against defined protection profiles and assurance levels.
- [OWASP: Threat Modeling Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html) — how to model a system with data-flow diagrams and identify threats with STRIDE. The direct reference for the threat-modeling prompt.

### Zero trust as a modern security model

*Supports: Reflect — applying models and principles (least privilege, defense in depth) to modern design*

- [CCCS: Zero Trust Security Model (ITSAP.10.008)](https://www.cyber.gc.ca/en/guidance/zero-trust-security-model-itsap10008) — a concise overview of zero trust as a design model.
- [Cisco: SAFE Secure Edge Architecture Guide](https://www.cisco.com/c/en/us/solutions/collateral/enterprise/design-zone-security/safe-secure-edge-architecture-guide.html) and [Zero Trust — Network and Cloud Security Design Guide](https://www.cisco.com/c/en/us/solutions/collateral/enterprise/design-zone-security/zt-network-cloud-dg.html) — worked reference designs.
- [Palo Alto Networks: Zero Trust Best Practices — Step 3: Standards and Designs](https://docs.paloaltonetworks.com/best-practices/zero-trust-best-practices/zero-trust-best-practices/the-five-step-methodology/step-3-standards-and-designs) — standards and designs within a zero trust methodology.

