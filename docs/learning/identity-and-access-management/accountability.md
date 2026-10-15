# Accountability

## Description

Accountability ensures that actions performed by a subject on an information system can be uniquely traced back to that subject. This requires effective identification, authentication, and robust audit logging. Accountability supports non-repudiation, policy enforcement, and incident investigation by maintaining visibility into user activities.

## Why This Matters

Accountability matters because it ensures that all actions on enterprise systems can be traced to the responsible user or system. Without accountability, it becomes difficult to detect misuse, enforce policies, or investigate incidents. In an environment with diverse users, shared resources, and sensitive data, accountability enables transparency, supports compliance, and deters malicious or negligent behavior. Operations rely on accountability to maintain control over administrative systems, cloud applications, and shared IT resources. Strong accountability helps operational teams:

- Track user activity in administrative, financial, and HR systems.
- Enforce security policies by linking actions to individual users or groups.
- Detect unauthorized or suspicious activity in real time.
- Support incident response and forensic investigations.
- Ensure compliance with internal governance, privacy, and audit requirements.
- Deter misuse by establishing non-repudiation of user actions.
- Staff rely on audit logs and monitoring tools to track administrative actions, enforce compliance, and investigate incidents.
- Technical teams depend on accountability controls to document access to shared systems and resources.
- End users benefit indirectly, as accountable systems reduce the risk of unauthorized access, ensuring safe and reliable use of business applications and networks.

Without accountability, operational teams cannot reliably enforce policies, detect policy violations, or respond effectively to security incidents. By maintaining visibility into user activities, accountability ensures that the organization can respond to incidents, enforce policy, and preserve trust across its operations.

## Skill Development

- Investigate: What types of technical and administrative controls are necessary to establish strong accountability in information systems for confidential information?
- Research: How do audit logs contribute to accountability during forensic investigations or incident response?
- Reflect: What risks arise if accountability is not adequately enforced in shared access environments?
- Investigate: What is non-repudiation, and which mechanisms make it achievable — unique identity per user, strong authentication, synchronized and trustworthy timestamps, tamper-evident logging, and digital signatures? Why does accountability break down when generic, shared, or service accounts are used, and how should those accounts be handled?
- Reflect: Accountability depends on logs that are complete, time-accurate, and tamper-resistant. How can audit logs be protected from alteration or deletion by a malicious insider or an attacker who gains privileged access (for example, MITRE ATT&CK's Indicator Removal technique), and what retention and centralization practices keep logs trustworthy over time?

## Learning Resources

> **Ethics and scope note:** Accountability depends on monitoring people, so it carries a privacy obligation. Activity logging should be proportionate to the risk, limited to what is needed to trace actions and investigate incidents, disclosed to users through policy, and retained and access-controlled according to privacy and records-management rules. Collecting more than necessary, or leaving audit logs broadly accessible, creates its own risk.

### Reference and further reading

- [McMaster Library: Accountability in information security (videos, 2010–2025)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Accountability%20Information%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2025&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Accountability in information security (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Accountability%20Information%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=rtype,include,books&facet=searchcreationdate,include,2010%7C,%7C2025&lang=en&offset=0)
- [O'Reilly: Identity and Access Management](https://www.oreilly.com/search/?q=Learning%3A%20Identity%20and%20Access%20Management&type=article&type=book&type=shortcut&rows=100)
  
### Foundations: accountability, AAA, and non-repudiation

*Supports: the controls prompt; the non-repudiation prompt*

- [Wikipedia: Accountability](https://en.wikipedia.org/wiki/Accountability) — background on the concept.
- [NIST Glossary: Non-repudiation](https://csrc.nist.gov/glossary/term/non_repudiation) — the precise definition of the property the Description names: assurance that an actor cannot later deny having performed an action. Non-repudiation is what accountability ultimately provides, and it is the anchor for the new skill prompt.

### Controls that establish accountability

*Supports: Investigate — technical and administrative controls for strong accountability*

- [NIST SP 800-53 Rev. 5: Security and Privacy Controls for Information Systems and Organizations](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) — the control catalogue. For accountability, the key families are Audit and Accountability (AU), Identification and Authentication (IA), and Access Control (AC): unique identity, authentication, and logging are what make tracing possible.
- [CCCS: Annex 3A — Security Control Catalogue (ITSG-33)](https://www.cyber.gc.ca/en/guidance/annex-3a-security-control-catalogue-itsg-33) — the Canadian control catalogue, with equivalent audit and accountability controls.
- [CCCS: Top 10 IT Security Actions No. 3 — Managing and Controlling Administrative Privileges (ITSM.10.094)](https://www.cyber.gc.ca/en/guidance/top-10-it-security-actions-no3-managing-controlling-administrative-privileges-itsm10094) — administrative actions are the highest-value events to hold accountable.
- [CCCS: Top 10 IT Security Actions No. 4 — Harden Operating Systems and Applications (ITSM.10.090)](https://www.cyber.gc.ca/en/guidance/top-10-security-actions-number-4-harden-operating-systems-and-applications-itsm10090)

### Audit logging and log management

*Supports: Investigate — controls; Research — audit logs for accountability*

- [NIST SP 800-92: Guide to Computer Security Log Management](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-92.pdf) — the foundational guide to generating, storing, and analyzing logs. It is from 2006 and a Revision 1 ("Log Management Planning Guide") is in development; check the [NIST Log Management project page](https://csrc.nist.gov/Projects/log-management) for current status.
- [CIS Control 8: Audit Log Management](https://www.cisecurity.org/controls/audit-log-management) — a concise, practical set of safeguards for collecting, centralizing, retaining, and reviewing logs; a strong complement to the NIST guidance and directly on point for the audit-log prompts.
- [CCCS: Using Security Information and Event Management (SIEM) Tools (ITSM.80.024)](https://www.cyber.gc.ca/en/guidance/using-security-information-event-management-tools-manage-cyber-security-risks-itsm80024) — how SIEM centralizes logs to detect suspicious activity in real time.
- [Microsoft: Audit Logging and Monitoring Overview](https://learn.microsoft.com/en-us/compliance/assurance/assurance-audit-logging)
- [Ping Identity: What Is an Audit Trail?](https://www.pingidentity.com/en/resources/blog/post/audit-trail.html)
- [IBM Cloud: Audit Logging](https://cloud.ibm.com/docs/framework-financial-services?topic=framework-financial-services-shared-logging-audit)

### Logs in forensics and incident response

*Supports: Research — how audit logs contribute during forensic investigations or incident response*

- [NIST SP 800-86: Guide to Integrating Forensic Techniques into Incident Response](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-86.pdf) — how logs and other data are collected, examined, and analyzed to reconstruct what happened during an incident, from an IT (rather than law-enforcement) perspective.

### Log integrity, retention, and tampering

*Supports: Reflect — protecting logs from alteration; risks in shared environments*

- [MITRE ATT&CK: Indicator Removal (T1070)](https://attack.mitre.org/techniques/T1070/) — how adversaries clear or tamper with logs to destroy evidence of their activity. Its sub-techniques and detection guidance explain why accountability depends on tamper-evident, centralized, off-host logging — if an attacker who gains privileged access can edit the logs, the audit trail cannot be trusted.
- CIS Control 8 (above) — also covers log retention and centralization, which keep a trustworthy record even when an individual host is compromised.

### Governance and management context

- [NIST SP 800-100: Information Security Handbook – A Guide for Managers](https://nvlpubs.nist.gov/nistpubs/legacy/sp/nistspecialpublication800-100.pdf) — where accountability, logging, and audit fit within an overall security management program.
