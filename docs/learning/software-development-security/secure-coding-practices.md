# Secure Coding Practices

## Description

Secure coding practices involve writing software code that is resistant to security vulnerabilities and reduces the risk of exploitation. This includes techniques such as input validation, proper error handling, avoiding hardcoded credentials, and using encryption to protect sensitive data. By adhering to secure coding standards, developers can minimize the chances of introducing common security flaws into the software, making it harder for attackers to exploit weaknesses and ensuring that the application behaves securely throughout its lifecycle.

## Why This Matters

Secure coding practices matter because improperly written code is a major entry point for attackers. Vulnerabilities like SQL injection, buffer overflows, or exposed credentials can be introduced during development and exploited to gain unauthorized access, steal data, or disrupt services. By integrating security into coding practices, developers reduce the risk of introducing exploitable flaws, ensuring that applications behave reliably and safely throughout their lifecycle. Enterprise operations rely on software for administrative tasks, employee management, and internal communications. Secure coding practices help operational teams:

- Prevent software vulnerabilities from compromising internal systems or sensitive data.
- Ensure that enterprise and custom applications function securely without introducing exploitable weaknesses.
- Maintain compliance with data protection regulations and IT security policies.
- Reduce the likelihood of downtime or service disruptions caused by software exploits.

Without secure coding standards, routine software development could unintentionally create serious security gaps, affecting core services and workflows. By embedding secure coding throughout development processes, the organization maintains software resilience, protects data, and reduces the overall risk of exploitation.

## Skill Development

- Research: Can you describe best practices for secure coding and how they help prevent vulnerabilities in software applications?
- Investigate: Which tools and learning resources are available to support secure coding?
- Reflect: From an information security perspective, how can secure coding practices be integrated into the development lifecycle to improve application security?
- Reflect: How does, or could, your role support the adoption and enforcement of secure coding practices in software projects?
- Investigate: Modern software is mostly third-party and open-source code, so writing your own code securely is only part of the job. How do dependency management, software composition analysis (SCA), pinning versions, and maintaining a software bill of materials (SBOM) keep the code you *depend on* secure?
- Investigate: AI coding assistants now generate a large share of production code. What secure-coding risks does AI-generated code introduce — vulnerable patterns, outdated or hallucinated dependencies, and secrets leaked into prompts or output — and how should it be reviewed, scanned, and tested before being trusted?

## Learning Resources

> **Scope and practice note:** Secure coding is prevention, and prevention is consistently cheaper and more effective than fixing a vulnerability in production. A few principles carry most of the weight: treat all input as untrusted and validate it server-side; never hardcode secrets or disable a security control "just temporarily"; fail safely and handle errors without leaking internal detail; and prefer standard, vetted libraries over writing your own security code. Scanning tools help but find only some flaws (not design or logic errors), so pair them with review. Finally, most of your real attack surface now lives in code you did not personally write — third-party dependencies and, increasingly, AI-generated code — so review and verify that too.

### Reference and further reading

- [O'Reilly: Secure coding](https://www.oreilly.com/search/?q=secure%20coding&type=book&rows=100&topics=Secure%20Coding)
- [McMaster Library: Secure coding practices (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Secure%20Coding%20Practices&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Secure coding practices (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Secure%20Coding%20Practices&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=rtype,include,books&facet=searchcreationdate,include,2010%7C,%7C2026&lang=en&offset=0)
  
### Secure coding standards and practices

*Supports: Research — best practices and how they prevent vulnerabilities; Reflect — your role in adoption and enforcement*

- [Wikipedia: Secure coding](https://en.wikipedia.org/wiki/Secure_coding) — the concept and common practices.
- [OWASP Top 10 Proactive Controls](https://owasp.org/www-project-proactive-controls/) — a developer-focused list of the most important secure-coding controls (input validation, access control, error handling, and more). 
- [SEI CERT: Top 10 Secure Coding Practices](https://wiki.sei.cmu.edu/confluence/display/seccode/Top+10+Secure+Coding+Practices) 
- [Wikipedia: CERT Coding Standards](https://en.wikipedia.org/wiki/CERT_Coding_Standards) — the language-specific (C, C++, Java) coding standards maintained by SEI CERT.
- [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/) — topic-by-topic defensive guidance (injection prevention, output encoding, password storage, and more).

### Building secure coding into the lifecycle

*Supports: Reflect — integrating secure coding into the development lifecycle*

- [NIST SP 800-218: Secure Software Development Framework (SSDF) v1.1](https://csrc.nist.gov/pubs/sp/800/218/final) — recommended practices for building security into every phase of development.
- [CCCS and partners: Joint Guidance on a Software Security Code of Practice](https://www.cyber.gc.ca/en/news-events/joint-guidance-software-security-code-practice) — baseline secure-development principles for software vendors.
- [CCCS: Cyber Security Considerations for Citizen Developers (Learning Hub)](https://www.cyber.gc.ca/en/education-community/learning-hub/courses/cyber-security-considerations-citizen-developers) — secure practices for non-professional developers building low-code/no-code and scripted solutions.

### Dependencies, secrets, and the software supply chain

*Supports: Investigate — securing third-party dependencies; Investigate — risks in AI-generated code*

- [OWASP Top 10 — A06:2021 Vulnerable and Outdated Components](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/) — the risk category for flawed or outdated dependencies, central to the supply-chain prompt.
- [CISA: Software Bill of Materials (SBOM)](https://www.cisa.gov/sbom) — why an inventory of components matters for responding when a dependency vulnerability (or an AI-pulled library) is disclosed.

### Tools for secure coding

*Supports: Investigate — tools and learning resources; Reflect — enforcement in projects*

- [Secure Code Wiki by Payatu](https://securecode.wiki/) — language-by-language secure-coding reference.
- [Snyk: Secure Coding Practices](https://snyk.io/articles/secure-coding-practices/) — developer-focused guidance, including dependency and AI-code security.
- [Checkmarx: SAST Best Practices for Secure Source Code](https://checkmarx.com/learn/sast/sast-best-practices-for-secure-source-code/) — using static analysis to enforce secure coding.
- [Veracode: Secure Coding Best Practices Handbook (PDF)](https://www.veracode.com/wp-content/uploads/secure-coding-best-practices-handbook-veracode-guide.pdf) — a developer's guide built around the OWASP Proactive Controls.
- [Palo Alto Networks: What Is Code Security?](https://www.paloaltonetworks.com/cyberpedia/what-is-code-security) and [Rapid7: Application Security Solutions](https://www.rapid7.com/solutions/application-security/) — how secure coding fits into a broader application-security program.
