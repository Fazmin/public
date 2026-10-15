# Host Security

## Description

Host security focuses on securing individual endpoints including workstations and servers against compromise. This includes hardening systems by disabling unnecessary services, applying security patches, enforcing access controls, and installing endpoint protection solutions. Regular auditing and system monitoring ensure that anomalies are detected quickly, reducing the window of opportunity for attackers to gain persistence or move laterally within the environment.

## Why This Matters

Host security matters because every workstation and server represents a potential entry point for attackers. If even a single device is misconfigured, unpatched, or compromised, it can provide access to institutional data, credentials, or internal systems. Strong host security ensures that endpoints are hardened, monitored, and protected.

### Typical Best Practices

- Enforce baseline configurations by disabling unnecessary services.
- Keep devices updated with security patches.
- Limit access through proper account permissions and privilege control.
- Use endpoint protection and EDR tools to detect malware and post-compromise activity.
- Ensure secure server configurations for critical applications and databases.
- Maintain detailed audit logs to support incident response.

## Skill Development

- Reflect: Can you explain the importance of system hardening and how it contributes to a secure baseline configuration?
- Investigate: From an endpoint protection standpoint, what role do EDR tools play in detecting post-compromise activity?
- Research: How can audit logging be configured on hosts to ensure actionable insights without generating excessive noise?
- Investigate: How should an organization prioritize and deploy security patches across a diverse fleet of hosts, and what are the trade-offs between patching quickly (reducing exposure) and delaying to test (avoiding broken systems)?
- Reflect: A hardened baseline degrades over time as software is installed and settings change — known as configuration drift. How can an organization detect and correct drift, and verify that hosts still match the approved secure baseline?

## Learning Resources

> **Operational note:** Two cautions run through host security. First, EDR and host audit logging capture detailed user activity, so logging should be proportionate and disclosed through policy, with extra care on personal or BYOD devices. Second, hardening changes and patches can break systems: test them on a representative sample and stage the rollout rather than pushing an unproven baseline or patch to the whole fleet at once.

### Reference and further reading

- [McMaster Library: Host security (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Host%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=rtype,include,books&facet=searchcreationdate,include,2010%7C,%7C2025&lang=en&offset=0)
- [O'Reilly: Endpoint and host security](https://www.oreilly.com/search/?q=endpoint%20security%20hardening&type=book&type=article&type=shortcut&rows=100)

### Hardening and secure baselines

*Supports: Reflect — system hardening and secure baseline; Reflect — configuration drift*

- [CIS Benchmarks](https://www.cisecurity.org/cis-benchmarks) — the de facto, freely available hardening baselines for operating systems, servers, cloud platforms, and applications. The practical starting point for "what does a hardened configuration look like."
- [CIS Control 4: Secure Configuration of Enterprise Assets and Software](https://www.cisecurity.org/controls/secure-configuration-of-enterprise-assets-and-software) — the safeguards for establishing and maintaining secure configurations, including managing drift.
- [NIST SP 800-123: Guide to General Server Security](https://nvlpubs.nist.gov/nistpubs/legacy/sp/nistspecialpublication800-123.pdf) — server hardening fundamentals.
- [NIST SP 800-128: Guide for Security-Focused Configuration Management of Information Systems](https://csrc.nist.gov/pubs/sp/800/128/upd1/final) — how to establish a baseline and keep systems matching it over time, the direct reference for the configuration-drift prompt.
- [CCCS: Baseline Cyber Security Controls for Small and Medium Organizations](https://www.cyber.gc.ca/en/guidance/baseline-cyber-security-controls-small-and-medium-organizations)
- [Wikipedia: Hardening (computing)](https://en.wikipedia.org/wiki/Hardening_(computing)) — background on the concept.

### Patch and vulnerability management

*Supports: Investigate — prioritizing and deploying patches across a fleet*

- [NIST SP 800-40 Rev. 4: Guide to Enterprise Patch Management Planning](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-40r4.pdf) — treats patching as preventive maintenance, with guidance on prioritization, risk response, and the people-and-process side of keeping a fleet current.
- [CIS Control 7: Continuous Vulnerability Management](https://www.cisecurity.org/controls/continuous-vulnerability-management) — identifying and remediating vulnerabilities on an ongoing basis.

### Endpoint protection and EDR

*Supports: Investigate — EDR and detecting post-compromise activity*

- [MITRE ATT&CK: Enterprise matrix](https://attack.mitre.org/matrices/enterprise/) — the catalog of post-compromise techniques (persistence, privilege escalation, lateral movement, defense evasion) that EDR tools are designed to detect. The best way to understand *what* EDR is looking for after an attacker is already on a host.
- [CIS Control 10: Malware Defenses](https://www.cisecurity.org/controls/malware-defenses) — where anti-malware and EDR fit in a controls framework.
- [Wikipedia: Endpoint security](https://en.wikipedia.org/wiki/Endpoint_security) and [Host-based intrusion detection system (HIDS)](https://en.wikipedia.org/wiki/Host-based_intrusion_detection_system) — concepts.
- [Fortinet: What Is Endpoint Detection and Response (EDR)?](https://www.fortinet.com/resources/cyberglossary/what-is-edr) and [Palo Alto Networks: What Is EDR?](https://www.paloaltonetworks.com/cyberpedia/what-is-endpoint-detection-and-response-edr) — vendor-neutral explainers of how EDR works.
- [Cisco Secure Endpoint](https://www.cisco.com/site/us/en/products/security/endpoint-security/secure-endpoint/index.html) and [FortiEDR](https://www.fortinet.com/products/endpoint-security/fortiedr) — example EDR products.

### Audit logging and monitoring on hosts

*Supports: Research — configuring host audit logging for actionable insight without noise*

- [NIST SP 800-92: Guide to Computer Security Log Management](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-92.pdf) — what to log, how to prioritize, and how to manage volume; the core guidance for balancing signal against noise. (It dates to 2006; a Revision 1 is in development — see the [NIST Log Management project](https://csrc.nist.gov/Projects/log-management).)
- [CIS Control 8: Audit Log Management](https://www.cisecurity.org/controls/audit-log-management) — practical safeguards for collecting, centralizing, and retaining host logs.
- [CCCS: Top 10 IT Security Actions (ITSM.10.089)](https://www.cyber.gc.ca/en/guidance/top-10-it-security-actions-protect-internet-connected-networks-and-information-itsm10089) — includes patching, hardening, and administrative-privilege controls that apply directly to hosts.

### Choosing and governing host-security solutions

- [CCCS: Choosing the Best Cyber Security Solution for Your Organization (ITSM.10.023)](https://www.cyber.gc.ca/en/guidance/choosing-best-cyber-security-solution-your-organization-itsm10023)
