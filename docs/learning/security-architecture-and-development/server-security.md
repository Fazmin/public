# Server Security

## Description

Protecting servers, which host applications, databases, and other services, from threats such as unauthorized access, malware, and data breaches. It includes best practices like patch management, firewalls, and secure configurations. Servers often house critical data and services. Securing them ensures the availability and confidentiality of organizational assets.

## Why This Matters

Server security is essential because servers host critical applications, databases, and services that support an organization's operations. Protecting these systems ensures that sensitive data remains confidential, systems remain available, and organizational operations can continue without disruption. By implementing strong server security practices, staff help maintain a reliable and trustworthy digital environment. Enterprise operations rely on servers to deliver business platforms, administrative systems, financial services, and organizational infrastructure. Securing these systems helps the organization:

- Prevent unauthorized access, malware infections, and data breaches.
- Ensure high availability and reliability of critical systems.
- Apply secure configurations, firewalls, and patch management consistently.
- Maintain trust in essential IT services and operational continuity.

Proper server security protects core systems and reduces operational, financial, and reputational risks for the organization.

## Skill Development

- Investigate: How can server security be architected to ensure high availability while maintaining strict data confidentiality and integrity?
- Investigate: What server hardening practices should be followed during the design phase to prevent unauthorized access and data breaches?
- Research: In server security design, how can secure configurations and the use of firewalls be implemented to reduce attack surfaces?
- Investigate: The description names patch management as a core practice. Why is timely patch and vulnerability management one of the most important server controls, and how should an organization prioritize and safely roll out patches across a fleet of servers — testing, staging, and scheduling maintenance windows — without causing outages?
- Research: What should be logged and monitored on a server to detect misuse or compromise, and how do centralized logging, file-integrity monitoring, and auditing support incident response without burying analysts in noise?

## Learning Resources

> **Scope and operations note:** Server security is also about disciplined operations, not just one-time setup. Hardening a server and then never patching or watching it is a false sense of safety, while pushing an untested patch or configuration change to every server at once can cause an outage as damaging as an attack. Only modify on servers you are authorized to manage, test changes on a representative and isolated system first, stage rollouts, keep good backups you have actually tried to restore, and make sure monitoring is in place before you need it. Treat administrative credentials and remote-management interfaces and tools as high-value targets - expose them as little as possible.

### Reference and vendor resources

- [O'Reilly: Server security](https://www.oreilly.com/search/?q=Server%20Security&type=book&rows=100)
- [McMaster Library: Server security (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Server%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Server security (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Server%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)
  
### Server hardening and secure configuration

*Supports: Investigate — hardening practices in the design phase; Research — secure configurations and firewalls to reduce attack surface*

- [CIS Benchmarks](https://www.cisecurity.org/cis-benchmarks) — the de facto, freely available hardening baselines for operating systems, server software, and databases. The practical starting point for "what does a hardened server look like."
- [NIST SP 800-123: Guide to General Server Security](https://csrc.nist.gov/pubs/sp/800/123/final) — foundational NIST guidance on securing a server: roles, hardening, and operation.
- [Wikipedia: Hardening (computing)](https://en.wikipedia.org/wiki/Hardening_(computing)) — the concept of reducing attack surface by disabling unnecessary services and tightening configuration.
- [Cisco: UCS Hardening Guide](https://sec.cloudapps.cisco.com/security/center/resources/ucs_hardening.html) — a concrete example of hardening server infrastructure across the management, control, and data planes.
- [Cisco: Firewall Best Practices](https://sec.cloudapps.cisco.com/security/center/resources/firewall_best_practices) — configuring firewalls to limit what can reach a server.
- [CCCS: Guidance on Securely Configuring Network Protocols (ITSP.40.062)](https://www.cyber.gc.ca/en/guidance/guidance-securely-configuring-network-protocols-itsp40062) — acceptable protocols, versions, and algorithms for the services a server exposes.

### Security controls, assessment, and architecture

*Supports: Investigate — architecting for high availability with confidentiality and integrity*

- [NIST SP 800-53 Rev. 5: Security and Privacy Controls for Information Systems and Organizations](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) — the control catalog, including Access Control (AC), System and Communications Protection (SC), Configuration Management (CM), and Contingency Planning (CP) for availability.
- [NIST SP 800-53A Rev. 5: Assessing Security and Privacy Controls](https://csrc.nist.gov/pubs/sp/800/53/a/r5/final) — how to verify that those controls are implemented and effective.
- [CCCS: Baseline Cyber Security Controls for Small and Medium Organizations](https://www.cyber.gc.ca/en/guidance/baseline-cyber-security-controls-small-and-medium-organizations) — a pragmatic baseline that includes server-relevant safeguards.

### Patch and vulnerability management

*Supports: Investigate — prioritizing and safely rolling out patches across a server fleet*

- [NIST SP 800-40 Rev. 4: Guide to Enterprise Patch Management Planning](https://csrc.nist.gov/pubs/sp/800/40/r4/final) — treats patching as preventive maintenance, with guidance on prioritization, risk response, and rolling out updates without breaking systems. The direct reference for the patch-management prompt.
- [CIS Control 7: Continuous Vulnerability Management](https://www.cisecurity.org/controls/continuous-vulnerability-management) — identifying and remediating vulnerabilities on an ongoing basis.

### Logging, monitoring, and detection

*Supports: Research — what to log and monitor on a server to detect compromise*

- [NIST SP 800-92: Guide to Computer Security Log Management](https://csrc.nist.gov/pubs/sp/800/92/final) — what to log, how to prioritize, and how to manage volume so logs stay useful rather than overwhelming.
- [CIS Control 8: Audit Log Management](https://www.cisecurity.org/controls/audit-log-management) — practical safeguards for collecting, centralizing, and retaining logs to support detection and incident response.
