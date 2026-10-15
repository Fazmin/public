# Access Control Attacks

## Description

Access control attacks exploit weaknesses or misconfigurations in access control mechanisms to gain unauthorized access to systems or data. Examples include privilege escalation, horizontal or vertical access bypass, session hijacking, and injection of malicious input to manipulate access logic. Mitigation requires strong controls, thorough testing, and continuous monitoring.

## Why This Matters

Access control attacks matter because they exploit weaknesses in the systems that govern who can do what within enterprise networks and applications. These attacks can allow unauthorized users to escalate privileges, bypass restrictions, or manipulate data, putting sensitive information and operational systems at risk. Strong access control measures, continuous monitoring, and testing are essential to prevent these threats from compromising the security and integrity of enterprise systems. Operations rely on secure access controls to protect administrative systems, customer or employee records, and internal applications. Understanding access control attacks helps operational teams:
 
- Detect and mitigate privilege escalation attempts or unauthorized access.
- Prevent horizontal or vertical access bypass that could compromise restricted resources.
- Identify session hijacking or injection attempts targeting sensitive systems.
- Regularly test access controls to ensure they function as intended and meet security policies.
- Maintain compliance with internal governance, privacy, and audit requirements.
- Technical teams rely on secure access to shared resources, datasets, and computing environments to prevent unauthorized interference or data loss.
- End users benefit from protected internal applications and portals where access rights are enforced appropriately.

Without proactive measures, attackers could exploit vulnerabilities to disrupt operations, steal data, or cause service outages. By defending against access control attacks, the organization ensures proper privilege enforcement, reduces risk, and maintains a secure environment for business operations.

## Skill Development

- Investigate: What techniques are commonly used by attackers to bypass access control systems, and how can they be detected? Use the MITRE ATT&CK Framework to describe the techniques.
- Research: How can organizations proactively test for access control weaknesses during system development and maintenance?
- Research: What security practices can reduce the likelihood of successful access control attacks in enterprise systems?
- Research: How do different access control models — RBAC (role-based), ABAC (attribute-based), and ReBAC (relationship-based) — differ, and how does the choice of model affect the attack surface and how bugs such as IDOR or privilege escalation arise? What do "least privilege" and "deny by default" mean in practice?
- Reflect: Access control failures are often discovered only after exploitation. What logging, monitoring, and detection signals help identify a privilege-escalation or authorization-bypass attempt in progress or after the fact, and how should an incident-response process treat a suspected access-control compromise?

## Learning Resources

> **Ethics and scope note:** Access-control testing — probing for IDOR, attempting privilege escalation, replaying another user's session — is unauthorized access when performed against systems you do not own or have explicit written permission to test, and may be a criminal offence under computer-misuse law. Practice only on your own systems, on engagements you are authorized for, or on deliberately vulnerable training apps (see Testing and practice below). Findings about real systems should go to the owner through a responsible-disclosure channel.

### Reference and further reading

- [McMaster Library: Access control attacks (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Access%20Control%20Attacks%20Information%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=rtype,include,books&facet=searchcreationdate,include,2010%7C,%7C2025&lang=en&offset=0)
- [O'Reilly: Identity and Access Management](https://www.oreilly.com/search/?q=Learning%3A%20Identity%20and%20Access%20Management&type=article&type=book&type=shortcut&rows=100)

### Understanding the attacks

*Supports: techniques attackers use to bypass access control; access control models and IDOR*

- [OWASP Top 10:2025 — A01 Broken Access Control](https://owasp.org/Top10/2025/A01_2025-Broken_Access_Control/) — the single most common web application risk; every application OWASP tested showed some form of it. Covers horizontal and vertical bypass, IDOR, and the server-side, deny-by-default fix.
- [PortSwigger Web Security Academy: Access control vulnerabilities](https://portswigger.net/web-security/access-control) and [Insecure direct object references (IDOR)](https://portswigger.net/web-security/access-control/idor) — clear explanations of each flaw class with free, hands-on labs.
- [Wikipedia: Access control](https://en.wikipedia.org/wiki/Access_control) — background on the concept and models.
- Related attack vectors named in the description: [Cross-Site Scripting (XSS)](https://en.wikipedia.org/wiki/Cross-site_scripting) (a common route to session hijacking via stolen cookies), [Man-in-the-Middle attack](https://en.wikipedia.org/wiki/Man-in-the-middle_attack), and [MAC flooding](https://en.wikipedia.org/wiki/MAC_flooding) (bypassing a switch's port-security access control). These sit at different layers than application authorization, but each can defeat an access control.

### Mapping attacker techniques with MITRE ATT&CK

*Supports: the first skill prompt — describe techniques using the MITRE ATT&CK Framework*

- [MITRE ATT&CK: Privilege Escalation (TA0004)](https://attack.mitre.org/tactics/TA0004/) — the tactic landing page listing the techniques adversaries use to gain higher-level permissions; a good starting map.
- [MITRE ATT&CK: Valid Accounts (T1078)](https://attack.mitre.org/techniques/T1078/) — abusing legitimate credentials to bypass access controls; note its sub-techniques (default, local, domain, cloud accounts) and the detection and mitigation guidance on the page.
- [MITRE ATT&CK: Exploitation for Privilege Escalation (T1068)](https://attack.mitre.org/techniques/T1068/) — exploiting a software flaw to gain elevated privileges.
- [MITRE ATT&CK: Abuse Elevation Control Mechanism (T1548)](https://attack.mitre.org/techniques/T1548/) — bypassing mechanisms meant to limit privilege (e.g., UAC bypass, sudo abuse).
- [MITRE ATT&CK: Steal Web Session Cookie (T1539)](https://attack.mitre.org/techniques/T1539/) and [Remote Service Session Hijacking (T1563)](https://attack.mitre.org/techniques/T1563/) — the session-hijacking techniques named in the description. Each ATT&CK page lists detection data sources, which directly supports the "how can they be detected" half of the prompt.

### Testing and practice

*Supports: proactively testing for access control weaknesses*

- [OWASP Web Security Testing Guide: Authorization Testing](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/05-Authorization_Testing/) — the standard methodology, including [Testing for Privilege Escalation](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/05-Authorization_Testing/03-Testing_for_Privilege_Escalation) and testing for IDOR and directory traversal.
- [NIST: Access Control Policy Testing (ACPT)](https://www.nist.gov/programs-projects/access-control-policy-testing-acpt) — NIST's project and tool for checking that an access-control policy actually enforces what it intends.
- [NIST SP 800-192: Verification and Test Methods for Access Control Policies/Models](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-192.pdf) — how to verify access-control policies systematically rather than by spot checks.
- [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/) and [WebGoat](https://owasp.org/www-project-webgoat/) — deliberately vulnerable applications for practising access-control testing legally and safely.

### Prevention, controls, and access-control models

*Supports: security practices that reduce risk; the RBAC/ABAC/ReBAC and least-privilege prompt*

- [OWASP Authorization Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html) — the concise checklist: enforce least privilege and deny by default, check authorization server-side on every request, prefer ABAC or ReBAC over RBAC where appropriate, protect object identifiers (against IDOR), fail safely, and log and test. The best single answer to the prevention and models prompts.
- [NIST SP 800-53 Rev. 5: Security and Privacy Controls](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) — see the Access Control (AC) family for the control-framework view, and the Audit and Accountability (AU) family for the logging that detection depends on.
- [NIST SP 800-162: Guide to Attribute Based Access Control (ABAC)](https://csrc.nist.gov/pubs/sp/800/162/upd1/final) — the authoritative treatment of ABAC, useful for the access-control-models prompt.
- [Microsoft: Identity Management and Access Control Security Best Practices](https://learn.microsoft.com/en-us/azure/security/fundamentals/identity-management-best-practices)
- [Okta: What Is Access Control and How Crucial Is It to Cybersecurity?](https://www.okta.com/identity-101/access-control/)
- [IBM: Identity and Access Management (IAM) Services](https://www.ibm.com/services/identity-access-management)
- [Palo Alto Networks: Administrative Access Best Practices](https://docs.paloaltonetworks.com/best-practices/10-1/administrative-access-best-practices)

### Detection, monitoring, and threat context

*Supports: detecting attacks in progress or after the fact; incident response*

- MITRE ATT&CK technique pages (above) — each lists the data sources and detection analytics for the technique, the practical basis for monitoring privilege escalation and account abuse.
- [Canadian Centre for Cyber Security: Top 10 IT Security Actions (ITSM.10.089)](https://www.cyber.gc.ca/en/guidance/top-10-it-security-actions-protect-internet-connected-networks-and-information-itsm10089) — includes managing administrative privileges, a core access-control control.
- [CCCS: Baseline Cyber Security Controls for Small and Medium Organizations](https://www.cyber.gc.ca/en/guidance/baseline-cyber-security-controls-small-and-medium-organizations)
- [CCCS: An Introduction to the Cyber Threat Environment](https://www.cyber.gc.ca/en/guidance/introduction-cyber-threat-environment)
- [CCCS: National Cyber Threat Assessment 2025–2026](https://www.cyber.gc.ca/en/guidance/national-cyber-threat-assessment-2025-2026)
