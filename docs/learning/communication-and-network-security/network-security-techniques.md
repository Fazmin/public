# Network Security Techniques

## Description

Network security techniques encompass a range of strategies to protect data and infrastructure, including traffic filtering, protocol hardening, access control enforcement, and active monitoring. Techniques like VLAN segmentation, port security, rate limiting, and anomaly detection help contain threats and maintain service integrity. When correctly applied, these methods enhance the overall posture of the network and support the continuous delivery of secure operations.

## Why This Matters

Network security techniques provide the practical mechanisms that enforce protection within an organization's network. While security architecture defines the structure, techniques such as VLAN segmentation, port security, protocol hardening, and anomaly detection ensure that day-to-day traffic is controlled, monitored, and contained.

### Typical best practices

- Segment networks into isolated zones using VLANs to prevent lateral movement.
- Enforce port security to stop rogue or unauthorized devices from connecting.
- Apply rate limiting to reduce denial-of-service traffic surges.
- Harden protocols and disable insecure services.
- Identify unusual traffic patterns using anomaly detection.
- Maintain compliance with internal policies and external standards.
- Isolate sensitive systems from untrusted or public networks.
- Detect unusual traffic from compromised endpoints, insider misuse, or malfunctioning devices.
- Restrict access to approved users and systems.
- Maintain stability and performance by limiting unauthorized network activity.
- Support secure remote access and collaboration with external organizations.

## Skill Development

- Reflect: Can you describe what VLAN segmentation is, and how it enhances security by limiting broadcast domains?
- Investigate: From a security operations standpoint, how can anomaly detection techniques help identify insider threats?
- Research: How does implementing port security on switches help reduce the likelihood of unauthorized device access? How is this achieved through different commercial solutions?
- Investigate: How do firewalls and access control lists (ACLs) filter traffic between network zones, and what is the difference between a traditional stateful firewall and a next-generation firewall (NGFW) that adds application awareness, intrusion prevention, and identity-based rules?
- Reflect: Traditional network security assumed a trusted internal network behind a hardened perimeter. How do zero trust and microsegmentation change that assumption, and why does a flat internal network make lateral movement easy once an attacker gains a foothold on a single host?

## Learning Resources

> **Scope and safety note:** Network monitoring and anomaly detection inspect traffic that can include personal and confidential content, so limit inspection to what is necessary, to networks that you have consent to monitor on, disclose it (through policy where appropriate), and respect the privacy and proportionality expectations that apply on your network. Treat segmentation, firewall, and protocol changes as potentially disruptive: a mis-scoped VLAN, ACL, or port-security rule can cut off critical services, so test changes on a representative segment and stage the rollout rather than pushing an unproven change across the whole network. Only test or alter networks you are authorized to manage.

### Reference and further reading

- [O'Reilly: Network security](https://www.oreilly.com/search/?q=Network%20Security%20Techniques&type=book&rows=100&topics=Network%20Security)
- [McMaster Library: Network security techniques (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Network%20Security%20Techniques&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Network security techniques (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Network%20Security%20Techniques&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=rtype,include,books&facet=searchcreationdate,include,2010%7C,%7C2026&lang=en&offset=0)

### Segmentation and network zones

*Supports: VLAN segmentation and broadcast domains; Reflect — flat networks and lateral movement*

- [Palo Alto Networks: What Is Network Segmentation?](https://www.paloaltonetworks.com/cyberpedia/what-is-network-segmentation) — explainer of segmentation, microsegmentation, and why isolating zones limits the blast radius of a compromise.
- [Cisco: Segmentation Strategy](https://community.cisco.com/t5/security-knowledge-base/segmentation-strategy/ta-p/3757424) — practical guidance on planning and enforcing segmentation.
- [Fortinet: VLAN Segmentation](https://docs.fortinet.com/document/fortigate/7.0.0/ngfw-deployment/871340/vlan-segmentation) — configuring VLAN-based segmentation on a firewall/NGFW.
- [CCCS: Baseline Security Requirements for Network Security Zones (ITSP.80.022)](https://www.cyber.gc.ca/en/guidance/baseline-security-requirements-network-security-zones-version-20-itsp80022) — the reference model for defining and separating network security zones.
- [CCCS: Cloud Network Security Zones (ITSP.80.023)](https://www.cyber.gc.ca/en/guidance/cloud-network-security-zones-itsp80023) — applying the zone model to cloud environments.

### Firewalls, filtering, and protocol hardening

*Supports: Investigate — firewalls, ACLs, and stateful vs next-generation firewalls; protocol hardening*

- [NIST SP 800-41 Rev. 1: Guidelines on Firewalls and Firewall Policy](https://csrc.nist.gov/pubs/sp/800/41/r1/final) — the core NIST reference on firewall types (packet filter, stateful, application-proxy), ACLs, and building a firewall policy. Directly on point for the firewall/NGFW prompt.
- [Fortinet: Intrusion Prevention](https://docs.fortinet.com/document/fortigate/7.4.3/administration-guide/565562/intrusion-prevention) — how an NGFW adds intrusion prevention on top of traditional stateful filtering.
- [CCCS: Wi-Fi Security (ITSP.80.002)](https://www.cyber.gc.ca/en/guidance/wi-fi-security-itsp80002) — hardening wireless access, a common weak point in network perimeters.

### Monitoring, anomaly detection, and intrusion prevention

*Supports: Anomaly detection and insider threats; monitoring for compromised or malfunctioning devices*

- [NIST SP 800-94: Guide to Intrusion Detection and Prevention Systems (IDPS)](https://csrc.nist.gov/pubs/sp/800/94/final) — what IDS/IPS do, signature vs anomaly-based detection, and where sensors sit on a network. The foundational reference for the anomaly-detection prompt.
- [CIS Control 13: Network Monitoring and Defense](https://www.cisecurity.org/controls/network-monitoring-and-defense) — the safeguards for detecting and responding to anomalous traffic across a network.
- [MITRE ATT&CK: Lateral Movement (TA0008)](https://attack.mitre.org/tactics/TA0008/) — the techniques attackers use to move between hosts once inside; understanding these is what makes anomalous east-west traffic meaningful, and shows why segmentation matters.

### Port security and device access control

*Supports: Port security on switches and commercial solutions; restricting access to approved devices*

- [Cisco: Implementing Port Security to Switchports to Avoid Vulnerability](https://community.cisco.com/t5/networking-knowledge-base/implementing-portsecurity-to-switchports-to-avoid-vulnerability/ta-p/4906158) — configuring port security to limit which devices can connect to a switch port.
- [CIS Control 12: Network Infrastructure Management](https://www.cisecurity.org/controls/network-infrastructure-management) — securely managing switches, routers, and other infrastructure, including device access control.
- [CCCS: Best Practices for Data Centre Virtualization (ITSP.70.010)](https://www.cyber.gc.ca/en/guidance/cyber-centre-data-centre-virtualization-report-best-practices-data-centre-virtualization) — segmentation and access control in virtualized infrastructure.

### Zero trust and modern network strategy

*Supports: Reflect — zero trust and microsegmentation vs the perimeter model*

- [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/pubs/sp/800/207/final) — the definitive description of zero trust: no implicit trust based on network location, and access decisions made per request. The direct reference for the perimeter-vs-zero-trust prompt.
- [Wikipedia: Network security](https://en.wikipedia.org/wiki/Network_security) — background on the concepts and their evolution.

### Standards, testing, and governance

- [NIST SP 800-53 Rev. 5: Security and Privacy Controls](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) — the System and Communications Protection (SC) and Access Control (AC) families that underpin network controls.
- [NIST SP 800-115: Technical Guide to Information Security Testing and Assessment](https://csrc.nist.gov/pubs/sp/800/115/final) — how to safely and authorizedly test network defenses, including segmentation and firewall rules.
