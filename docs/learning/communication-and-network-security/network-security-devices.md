# Network Security Devices

## Description

Network security devices are essential for enforcing perimeter and internal defenses within the network. Firewalls filter traffic based on defined policies, intrusion detection and prevention systems (IDS/IPS) monitor for malicious activity, and network access control (NAC) ensures that only compliant devices can connect to organizational resources. These devices work together to reduce attack surfaces, enforce policy, and support incident detection and response in real time.

## Why This Matters

Network security devices form the backbone of an organization's ability to detect, prevent, and respond to cyber threats. Firewalls, IDS/IPS systems, and NAC work together to enforce policies, prevent unauthorized access, and monitor activity across the organizational environment.

### Typical best practices

- Enforce traffic controls through firewalls that protect internal systems from external and lateral threats.
- Detect and respond to suspicious activity using IDS/IPS signatures, anomaly detection, and automated blocking.
- Ensure only approved and compliant devices connect through NAC.
- Maintain compliance with organizational policies and cybersecurity guidelines.
- Monitor and log key network events for audits, investigations, and incident response.
- Enable fine-grained firewall policies for collaboration while protecting sensitive datasets.
- Detect malicious activity targeting lab systems, IoT devices, specialized equipment, or HPC clusters.
- Provide secure remote access and controlled connectivity to cloud or cross-organization projects.
- Keep sensitive networks isolated from threats originating in public or easily accessed networks.
- Preserve the integrity, confidentiality, and availability of sensitive environments.

## Skill Development

- Reflect: Can you explain what a firewall policy is, and how it might be designed to support both collaboration and network protection in a learning environment?
- Investigate: From a risk management perspective, what are the advantages and limitations of relying solely on Intrusion Detection Systems (IDS) and Intrusion Prevention Systems (IPS) for threat detection? Who are the prominent vendors and solutions in this space, and how do they differ?
- Investigate: How does network access control (NAC) contribute to endpoint security in a bring-your-own-device (BYOD) environment?
- Reflect: Network security devices are themselves high-value targets — a compromised firewall, VPN concentrator, or other edge device gives an attacker a powerful foothold and often sits outside normal endpoint monitoring. How should an organization harden, patch, log, and monitor the security devices themselves, and why have internet-facing edge devices become such a frequent target?
- Investigate: Firewalls, IDS/IPS, and NAC are classic perimeter and network-edge controls. How does a zero trust approach change the role of these devices, and why is a strong perimeter no longer sufficient on its own in an environment with remote users, cloud services, and lateral-movement threats?

## Learning Resources

> **Scope and safety note:** These devices sit inline and can see or block a great deal of traffic. IDS/IPS, NAC, and logging inspect traffic and device posture that may include personal and confidential content, so limit inspection to what is necessary, disclose it through policy, and respect privacy and proportionality. Because firewalls, IPS, and NAC can block legitimate activity (a false-positive IPS signature or an over-strict NAC rule can lock users out of critical services), test new policies on a representative segment and stage the rollout. Finally, the security devices are themselves high-value targets: keep them patched, hardened, and monitored, and only configure or test devices you are authorized to manage.

### Standards and reference

- [Wikipedia: Network security](https://en.wikipedia.org/wiki/Network_security) — background on the concepts.
- [O'Reilly: Network security devices](https://www.oreilly.com/search/?q=Network%20Security%20Devices&type=book&rows=100&topics=Network%20Security)
- [McMaster Library: Network security devices (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Network%20Security%20Devices&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=rtype,include,books&facet=searchcreationdate,include,2010%7C,%7C2026&lang=en&offset=0)

### Firewalls and firewall policy

*Supports: Reflect — firewall policy for collaboration and protection*

- [NIST SP 800-41 Rev. 1: Guidelines on Firewalls and Firewall Policy](https://csrc.nist.gov/pubs/sp/800/41/r1/final) — the core NIST reference on firewall types (packet filter, stateful, application-proxy) and how to design a firewall policy. The most on-point reference for the firewall-policy prompt.
- [Cisco Secure Firewall](https://www.cisco.com/site/us/en/products/security/firewalls/index.html) — example enterprise firewall platform.
- [Fortinet FortiGate Next-Generation Firewalls](https://www.fortinet.com/products/next-generation-firewall) — an NGFW that adds application awareness and intrusion prevention to traditional stateful filtering.
- [Palo Alto Networks Next-Generation Firewalls](https://docs.paloaltonetworks.com/ngfw) — NGFW documentation, useful for seeing how modern firewall policy is expressed.

### Intrusion detection and prevention (IDS/IPS)

*Supports: Investigate — IDS/IPS advantages, limitations, and prominent vendors*

- [NIST SP 800-94: Guide to Intrusion Detection and Prevention Systems (IDPS)](https://csrc.nist.gov/pubs/sp/800/94/final) — how IDS and IPS work, signature vs. anomaly-based detection, sensor placement, and the limitations (false positives/negatives, evasion) central to the risk-management prompt.
- [Palo Alto Networks: Firewall vs. IDS vs. IPS](https://www.paloaltonetworks.com/cyberpedia/firewall-vs-ids-vs-ips) — a comparison of the three control types and where each fits.
- [Fortinet: What Is an Intrusion Detection System (IDS)?](https://www.fortinet.com/resources/cyberglossary/intrusion-detection-system) — explainer of IDS concepts.
- [FortiGuard Intrusion Prevention Service](https://www.fortinet.com/support/support-services/fortiguard-security-subscriptions/intrusion-prevention) — an example of a commercial IPS subscription, useful for the "prominent vendors and solutions" part of the prompt.

### Network access control (NAC) and BYOD

*Supports: Investigate — NAC and endpoint security in a BYOD environment*

- [Cisco: What Is Network Access Control (NAC)?](https://www.cisco.com/site/us/en/learn/topics/security/what-is-network-access-control-nac.html) — how NAC checks device identity and compliance (posture) before granting access.
- [Palo Alto Networks: Types of Endpoint Security](https://www.paloaltonetworks.com/cyberpedia/types-of-endpoint-security) — how endpoint controls complement NAC on unmanaged or personal devices.
- [CCCS: End User Device Security for BYOD Deployment Models (ITSM.70.003)](https://www.cyber.gc.ca/en/guidance/end-user-device-security-bring-your-own-device-byod-deployment-models-itsm70003) — reference for securing personally owned devices on an organizational network.

### Securing the devices themselves (edge devices, logging, and monitoring)

*Supports: Reflect — security devices as high-value targets*

- [CCCS and partners: Security Considerations for Edge Devices (ITSM.80.101)](https://www.cyber.gc.ca/en/guidance/security-considerations-edge-devices-itsm80101) — joint international guidance (2025) on why internet-facing edge devices such as firewalls and VPN gateways are frequent targets, and how to harden and monitor them. The direct reference for the new "devices as targets" prompt.
- [CCCS: Network Security Logging and Monitoring (ITSAP.80.085)](https://www.cyber.gc.ca/en/guidance/network-security-logging-monitoring-itsap80085) — what to log and monitor across network devices to support audits, investigations, and incident response.
- [CIS Control 12: Network Infrastructure Management](https://www.cisecurity.org/controls/network-infrastructure-management) — the safeguards for securely configuring, updating, and managing network devices themselves.

### Architecture, zones, and zero trust

*Supports: Investigate — zero trust and the changing role of perimeter devices*

- [NIST SP 800-215: Guide to a Secure Enterprise Network Landscape](https://csrc.nist.gov/pubs/sp/800/215/final) — how enterprise network security has evolved beyond a single hardened perimeter toward layered, software-defined, and policy-driven controls. Directly frames the "perimeter is no longer sufficient" prompt.
- [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/pubs/sp/800/207/final) — a strong description of zero trust: no implicit trust based on network location, with access decided per request.
- [CCCS: Baseline Security Requirements for Network Security Zones (ITSP.80.022)](https://www.cyber.gc.ca/en/guidance/baseline-security-requirements-network-security-zones-version-20-itsp80022) — how firewalls and other devices enforce separation between network security zones.
