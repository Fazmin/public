# Code Testing

## Description

Code testing, also known as secure code review or static code analysis, involves reviewing the source code of software applications to identify security vulnerabilities. This includes searching for common coding flaws such as buffer overflows, SQL injection, or improper access controls. Ensuring secure coding practices through regular testing is key to preventing vulnerabilities from being introduced during the development lifecycle.

## Why This Matters

Code testing matters because vulnerabilities in software can provide attackers with direct access to sensitive systems, data, or network resources. By identifying and addressing security flaws during development, the organization reduces the risk of exploitation that could compromise business data, administrative systems, or personal information. Regular testing ensures software is secure by design, preventing vulnerabilities from being introduced into production environments. Enterprise operations rely on secure applications for administrative and business activities. Code testing helps operational teams:

- Identify and remediate vulnerabilities before software deployment.
- Enforce secure coding standards and prevent common coding flaws.
- Reduce the likelihood of application-based breaches that could disrupt organizational services.
- Ensure compliance with internal policies and regulatory requirements for software security.

Without systematic code testing, even well-intentioned software could introduce critical weaknesses into operational systems. By embedding security into the software development lifecycle, an organization maintains a safer, more resilient digital environment.

## Skill Development

- Investigate: How would you perform code testing to identify security vulnerabilities in applications?
- Investigate: Which open source tools are available for code testing?
- Research: What type of challenges is AI/ML introducing to code testing?
- Reflect: From a security standpoint, what secure coding practices should be enforced in the development of software for enterprise systems?
- Reflect: How can your role contribute to ensuring that web-based applications are secure by design through code testing?
- Investigate: How do the main application security testing approaches differ — static analysis (SAST) of source code, dynamic analysis (DAST) of a running application, interactive analysis (IAST), and software composition analysis (SCA) of third-party components — and why are several needed, since each catches a different class of flaw?
- Investigate: Most modern applications are built largely from third-party and open-source dependencies, so a flaw in a library (such as Log4Shell) can be as dangerous as one in your own code. How do software composition analysis (SCA) and a software bill of materials (SBOM) help an organization find and manage vulnerable dependencies?

## Learning Resources

> **Scope and practice note:** Testing finds vulnerabilities; it does not fix them, and no single tool finds everything. Automated scanners (SAST, DAST, SCA) produce both false positives and false negatives, so pair them with manual code review and treat their output as leads to triage, not a finished verdict. Run security testing only against code and systems you are authorized to test — dynamic scanning in particular sends real traffic and can disrupt a live service, so use a test environment. The most effective pattern is to shift testing left (run it early and automatically in the pipeline) and to remember that most exploitable risk today lives in dependencies, not only in first-party code.

### Reference and further reading

- [O'Reilly: Secure code review and application security testing](https://www.oreilly.com/search/?q=secure%20code%20review%20application%20security%20testing&type=book&rows=100)
- [McMaster Library: Code testing and information security (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Computer%20Code%20Testing,%20Information%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&lang=en&offset=0)
  
### Secure code review and testing approaches

*Supports: Investigate — how to perform code testing; Investigate — SAST vs. DAST vs. IAST vs. SCA*

- [Wikipedia: Static program analysis](https://en.wikipedia.org/wiki/Static_program_analysis) — the basis of static application security testing (SAST).
- [OWASP Code Review Guide](https://owasp.org/www-project-code-review-guide/) — how to perform a structured, security-focused manual code review, which complements automated scanning.
- [Palo Alto Networks: What Is Static Application Security Testing (SAST)?](https://www.paloaltonetworks.com/cyberpedia/what-is-sast-static-application-security-testing) — static testing explained.
- [Tenable: Web App Scanning (DAST)](https://www.tenable.com/products/web-app-scanning) — an example of dynamic testing against a running application.
- [Rapid7: Application Security Testing Programs](https://www.rapid7.com/fundamentals/application-security-testing-programs/) — how the different testing types fit into an overall AppSec program.

### Tools for code testing

*Supports: Investigate — open-source tools for code testing*

- [OWASP: Source Code Analysis Tools](https://owasp.org/www-community/Source_Code_Analysis_Tools) — a maintained list of SAST tools, including open-source options. The direct reference for the open-source-tools prompt.
- [OWASP ZAP](https://www.zaproxy.org/) — the flagship free, open-source dynamic application security testing (DAST) proxy/scanner.

### Secure coding standards and the development lifecycle

*Supports: Reflect — secure coding practices for enterprise systems; Reflect — secure-by-design through code testing; Research — AI/ML challenges*

- [OWASP Top 10](https://owasp.org/www-project-top-ten/) — the most common web application vulnerability classes; the baseline of what code testing looks for.
- [NIST SP 800-218: Secure Software Development Framework (SSDF) v1.1](https://csrc.nist.gov/pubs/sp/800/218/final) — recommended secure-development practices across the lifecycle, including testing and review, into which code testing fits.
- [CCCS and partners: Joint Guidance on a Software Security Code of Practice](https://www.cyber.gc.ca/en/news-events/joint-guidance-software-security-code-practice) — baseline secure-development principles for software vendors (replaces the off-topic cloud reference on the original page).

### Software supply chain and dependencies

*Supports: Investigate — SCA, SBOM, and vulnerable third-party dependencies*

- [OWASP Top 10 — A06:2021 Vulnerable and Outdated Components](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/) — the risk category covering flawed or outdated dependencies.
- [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/) — an open-source software composition analysis (SCA) tool that flags dependencies with known CVEs.
- [CISA: Software Bill of Materials (SBOM)](https://www.cisa.gov/sbom) — what an SBOM is and why an inventory of components is essential for responding quickly when a dependency vulnerability is disclosed.
