# Specialized Networking

## Description

Specialized networking refers to environments that require unique security considerations due to their function or protocol stack. Examples include research lab networks, industrial control systems, and high-performance computing clusters, all of which may operate with different availability, confidentiality, and performance requirements. Security measures must be tailored to these contexts, ensuring that controls do not impede function while still addressing relevant risks such as unauthorized access, lateral movement, or protocol-specific attacks.

## Why This Matters

Specialized networking is essential because many enterprise systems operate outside the bounds of traditional IT. Industrial control systems, HPC clusters, and other specialized environments each have different performance expectations, protocol requirements, and risk profiles.

### Typical best practices

- Protect building automation systems and industrial control equipment without disrupting facility operations.
- Keep HPC clusters secure while enabling resource sharing across teams and departments.
- Segment sensitive or high-risk environments to contain compromise.
- Apply controls that account for performance, safety, or protocol constraints.
- Monitor specialized segments for equipment failure or cyber intrusion.
- Meet governance, compliance, and operational technology requirements.
- Staff maintain segmentation, access controls, and monitoring for office networks, industrial systems, and HPC infrastructure.
- Technical staff depend on stable, protected networking to operate instruments and run simulations.
- End users benefit when specialized systems in labs and workshop spaces remain secure and reliable.

## Skill Development

- Reflect: Can you explain how security controls for industrial control systems differ from those used in traditional IT networks?
- Reflect: From a governance perspective, how should security be approached in high-performance computing environments with shared resources?
- Investigate: How does asset classification influence the design of security controls in a specialized network segment?
- Investigate: Operational technology often runs legacy, hard-to-patch devices that cannot tolerate downtime or active scanning, and where availability and physical safety outrank confidentiality. Given those constraints, how do approaches like network segmentation (zones and conduits), passive monitoring, and compensating controls secure OT when traditional IT practices such as frequent patching and vulnerability scanning are not safe to apply?
- Investigate: Research networks hold valuable intellectual property and sensitive data and are targeted by both criminal and state-sponsored actors. What specific threats do research laboratories face, and how can a research network be secured without impeding scientific collaboration and access to specialized instruments?

## Learning Resources

> **Scope and safety note:** In specialized environments, safety and availability often outrank confidentiality. A control that is routine in IT — active scanning, a forced patch or reboot, or blocking traffic — can halt a physical process or damage equipment, so coordinate with system operators, use passive or read-only monitoring where possible, and test changes under proper change control rather than on a live safety-critical system. Research networks hold sensitive intellectual property and are targeted by capable actors, so protect data without needlessly blocking legitimate collaboration. Only assess or alter networks and equipment you are authorized to touch.

### Reference and further reading

- [O'Reilly: High-performance computing networks](https://www.oreilly.com/search/?q=high%20performance%20computing%20network&type=book&rows=100)
- [McMaster Library: Specialized networking (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Specialized%20Networking&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Specialized networking (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Specialized%20Networking&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)

### Industrial control systems and operational technology (ICS/OT)

*Supports: Reflect — ICS vs. traditional IT controls; Investigate — securing legacy, safety-critical OT; asset classification in OT*

- [NIST SP 800-82 Rev. 3: Guide to Operational Technology (OT) Security](https://csrc.nist.gov/pubs/sp/800/82/r3/final) — the core reference (updated in 2023 and renamed from "Industrial Control Systems" to "Operational Technology"). Explains why OT prioritizes safety and availability, how to inventory and classify OT assets, and how to apply segmentation and compensating controls when patching and scanning are not safe.
- [CCCS: Security Considerations for Industrial Control Systems (ITSAP.00.050)](https://www.cyber.gc.ca/en/guidance/security-considerations-industrial-control-systems-itsap00050) — concise guidance on the risks specific to ICS.
- [CCCS: Protect Your Operational Technology (ITSAP.00.051)](https://www.cyber.gc.ca/en/guidance/protect-your-operational-technology-itsap00051) — practical OT protection measures.
- [Cisco: OT/ICS and Industrial IoT Security](https://www.cisco.com/site/us/en/products/security/industrial-security/index.html) — vendor approach to securing industrial networks.
- [Cisco: Networking and Security in Industrial Automation Environments](https://www.cisco.com/c/en/us/td/docs/solutions/Verticals/Industrial_Automation/IA_Horizontal/DG/Industrial-AutomationDG.html) — a detailed design guide for industrial networks, including segmentation into zones and conduits.
- [Fortinet: OT Security](https://www.fortinet.com/solutions/ot-security) — vendor solutions for monitoring and segmenting OT networks.

### High-performance computing (HPC)

*Supports: Reflect — HPC governance with shared resources; Investigate — asset classification in a specialized segment*

- [NIST SP 800-223: High-Performance Computing Security — Architecture, Threat Analysis, and Security Posture](https://csrc.nist.gov/pubs/sp/800/223/final) — the dedicated NIST reference (finalized 2024). It models an HPC system as functional zones (access, management, compute, high-performance interconnect, and storage) and analyzes threats and controls for each — directly useful for both the HPC governance and asset-classification prompts.
- [Wikipedia: High-performance computing](https://en.wikipedia.org/wiki/High-performance_computing) — background on HPC systems and how they are used.

### Research laboratories and critical specialized systems

*Supports: Investigate — research laboratory threats and securing research networks; monitoring specialized segments*

- [CCCS: The Cyber Threat to Research Laboratories](https://www.cyber.gc.ca/en/guidance/cyber-threat-research-laboratories) — a threat assessment of the risks to research labs (ransomware, data and IP theft, state-sponsored espionage, and the physical-safety risk of compromised lab equipment). The direct reference for the research-network prompt.
- [CCCS: Cyber Security Readiness Goals — Securing Our Most Critical Systems](https://www.cyber.gc.ca/en/cyber-security-readiness/cyber-security-readiness-goals-securing-our-most-critical-systems) — baseline goals for protecting critical and specialized systems.
