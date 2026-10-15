# Software Development Lifecycle

## Description

The Software Development Lifecycle (SDLC) is a structured approach to creating and maintaining software systems, which includes stages such as planning, design, development, testing, deployment, and maintenance. This process ensures that security considerations are integrated at every phase, reducing vulnerabilities and improving the software's reliability and resilience. By following a secure SDLC, organizations can identify and mitigate potential risks early in the development process, thereby minimizing the chances of security flaws in the final product.

## Why This Matters

The Software Development Lifecycle matters because it integrates security into every stage of software creation, from planning to maintenance. By embedding security considerations early and continuously throughout development, organizations can reduce vulnerabilities, prevent coding flaws, and produce reliable, resilient applications. This proactive approach minimizes the risk of security breaches, data loss, or system downtime caused by insecure software. Enterprise operations depend on a variety of software systems for administration, business management, and communication. Secure SDLC practices help operational teams:

- Incorporate security requirements during planning and design to prevent flaws later.
- Ensure that deployed software aligns with policy, regulatory, and compliance standards.
- Detect vulnerabilities early through secure coding, testing, and code reviews.
- Maintain robust, reliable software for administrative dashboards, portals, and internal applications.
- Facilitate patching and updates during maintenance to reduce long-term risk.

Without secure SDLC practices, operational software could contain exploitable vulnerabilities, disrupting services and compromising sensitive data. Organizational staff who have development responsibilities are often instructed to follow structured SDLC procedures to create, deploy, and maintain internal software safely. These procedures may be part of training, onboarding, documentation, or at least culture. SDLC practices will vary from organization to organization in terms of how they're operationalized and recognized officially. By integrating security into the SDLC, the organization ensures software is developed, maintained, and updated with risk reduction and resilience in mind.

## Skill Development

- Investigate: What could a SDLC workflow look like for a particular organization or type of development?
- Reflect: Can you explain the key phases of the Software Development Lifecycle (SDLC) and how they contribute to secure software development?
- Reflect: From an information security perspective, how can the SDLC help mitigate security risks throughout the software development process?
- Reflect: How does, or could, your role contribute to ensuring security is integrated throughout the SDLC?
- Investigate: How does DevSecOps "shift security left" and automate it within a CI/CD pipeline — adding SAST, DAST, software composition analysis, and secrets scanning as automated gates — and how does that change the traditional phase-by-phase secure SDLC?
- Investigate: How are software supply chain risks managed within the SDLC — vetting and updating open-source dependencies, generating a software bill of materials (SBOM), and protecting the build pipeline against tampering (for example, using a framework like SLSA)?

## Learning Resources

> **Scope and practice note:** A secure SDLC works because security is present at every phase, not bolted on before release: security requirements and threat modeling in design, secure coding and review during development, security testing before deployment, and patching through maintenance. The cost of fixing a flaw rises sharply the later it is found, which is the whole argument for "shifting left." Two cautions matter today: most of a modern application is third-party and open-source code, so the supply chain and the build pipeline are part of the lifecycle and need protecting; and automated pipeline gates speed things up but can be misconfigured or bypassed, so treat them as part of the process, not a rubber stamp.

### Reference and further reading

- [O'Reilly: Secure software development lifecycle](https://www.oreilly.com/search/?q=secure%20software%20development%20lifecycle&type=book&rows=100)
- [McMaster Library: Software development lifecycle (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Software%20Development%20Lifecycle&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Software development lifecycle (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Software%20Development%20Lifecycle&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=rtype,include,books&facet=searchcreationdate,include,2010%7C,%7C2026&lang=en&offset=0)
  
### SDLC foundations and phases

*Supports: Investigate — what an SDLC workflow looks like; Reflect — key phases and how they contribute to security*

- [Wikipedia: Software development process (SDLC)](https://en.wikipedia.org/wiki/Software_development_process) — the phases and common process models (waterfall, iterative, agile).
- [NIST Glossary: Software development life cycle](https://csrc.nist.gov/glossary/term/software_development_life_cycle) — a precise definition.
- [Palo Alto Networks: What Is a Secure Software Development Lifecycle (Secure SDLC)?](https://www.paloaltonetworks.com/cyberpedia/what-is-secure-software-development-lifecycle) and [Snyk: Secure Software Development Lifecycle (SSDLC)](https://snyk.io/articles/secure-sdlc/) — overviews of adding security to each phase.

### Secure SDLC frameworks and governance

*Supports: Reflect — how the SDLC mitigates risk; Reflect — your role in integrating security*

- [NIST SP 800-218: Secure Software Development Framework (SSDF) v1.1](https://csrc.nist.gov/pubs/sp/800/218/final) — the core reference: recommended secure practices mapped across the lifecycle.
- [CCCS and partners: Joint Guidance on a Software Security Code of Practice](https://www.cyber.gc.ca/en/news-events/joint-guidance-software-security-code-practice) — baseline secure-development principles for vendors.
- [CCCS: IT Security Risk Management — A Lifecycle Approach (ITSG-33)](https://www.cyber.gc.ca/en/guidance/it-security-risk-management-lifecycle-approach-itsg-33) — integrating risk management across the system lifecycle.
- [CCCS: Cyber Security in the GC for Software Development Teams (Learning Hub course)](https://www.cyber.gc.ca/en/education-community/learning-hub/courses/335-cyber-security-gc-software-development-teams) — a course on applying ITSG-33 within software development.

### DevSecOps and pipeline automation

*Supports: Investigate — shifting security left and automating it in CI/CD*

- [OWASP DevSecOps Guideline](https://owasp.org/www-project-devsecops-guideline/) — building and operating a secure delivery pipeline with vendor-neutral tooling. The direct reference for the DevSecOps prompt.
- [Palo Alto Networks: Cloud Code Security](https://www.paloaltonetworks.com/prisma/cloud/cloud-code-security) and [Rapid7: InsightAppSec (DAST)](https://www.rapid7.com/products/insightappsec/) — examples of security testing integrated into development and pipelines.
- [Veracode: Secure the SDLC in 6 Steps](https://www.veracode.com/resources/ebooks/secure-the-software-development-lifecycle-in-6-steps/) and [Software Development Lifecycle (SDLC)](https://www.veracode.com/security/software-development-lifecycle-sdlc) — practical steps for operationalizing a secure SDLC.

### Software supply chain in the SDLC

*Supports: Investigate — managing supply chain risk, open-source dependencies, SBOM, and build integrity*

- [CCCS: Protecting Your Organization from Software Supply Chain Threats (ITSM.10.071)](https://www.cyber.gc.ca/en/guidance/protecting-your-organization-software-supply-chain-threats-itsm10071) — the direct reference for supply-chain risk.
- [CCCS: Security Considerations When Using Open Source Software (ITSAP.10.059)](https://www.cyber.gc.ca/en/guidance/security-considerations-when-using-open-source-software-itsap10059) — vetting and managing open-source dependencies.
- [CISA: Software Bill of Materials (SBOM)](https://www.cisa.gov/sbom) — inventorying components so a disclosed dependency flaw can be found fast.
- [SLSA (Supply-chain Levels for Software Artifacts)](https://slsa.dev/) — a framework for protecting the integrity of the build pipeline itself.
