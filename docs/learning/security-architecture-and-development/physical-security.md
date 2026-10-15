# Site and Facility Design and Physical Security

## Description

Securing physical locations where IT infrastructure is housed, such as data centers, with measures like access control, surveillance, and disaster-proofing. Physical breaches or environmental risks, such as floods, surges, or fires, can compromise the availability and confidentiality of systems, no matter how strong their digital defenses are.

## Why This Matters

Securing the physical spaces that house IT infrastructure is essential because no digital security measure can fully protect systems from environmental hazards, unauthorized access, or physical tampering. Well-designed facilities protect critical hardware, data, and services, ensuring continuity of enterprise operations. Enterprise operations rely on physical infrastructure such as data centers, server rooms, and network hubs. Strong physical security and site design help the organization:

- Prevent unauthorized access to servers, networking equipment, and storage systems.
- Mitigate environmental risks, including floods, fires, and power surges.
- Maintain continuous availability of IT services critical for business and administrative operations.
- Protect sensitive operational and personal data stored on physical systems.

Staff responsible for IT management benefit from clear physical security protocols that support both operational efficiency and regulatory compliance. Physical security and site design impact the daily activities of staff and technical teams:

- Staff implement and monitor access controls, alarms, surveillance systems, and disaster mitigation measures. They ensure facilities meet security standards and operational requirements.
- Technical teams rely on secure environments to safely access computing resources and stored datasets without disruption.
- End users benefit indirectly through the availability and integrity of systems used for day-to-day work and online services.

By integrating physical security into facility design and operations, the organization maintains a resilient, safe, and secure infrastructure.

## Skill Development

- Investigate: What are the key principles in designing a secure data center to ensure the confidentiality, integrity, and availability of IT infrastructure?
- Reflect: How can physical security controls, such as access control and surveillance, be integrated into the design of facilities housing critical IT systems to mitigate environmental and physical risks?
- Research: What measures can be implemented in facility design to protect against environmental threats, such as floods, fires, or power surges, that could impact the availability of critical infrastructure?
- Investigate: How do redundancy and resilience concepts — redundant power (UPS and generators), cooling, and network paths, and the Uptime Institute Tier classification (Tiers I–IV) — support continuous availability, and what trade-offs exist between a higher tier and its cost and complexity?
- Investigate: When IT infrastructure is hosted by a cloud or colocation provider, physical and environmental security becomes largely the provider's responsibility. Under the shared-responsibility model, how should an organization gain assurance over a provider's physical controls (for example, through SOC 2 or ISO/IEC 27001 audit reports), and what remains the customer's responsibility?

## Learning Resources

> **Scope and safety note:** Physical security protects what digital controls cannot, and it has to address two very different kinds of threat at once: deliberate intrusion (met with layered access control, surveillance, visitor escorting, and logging — and attention to the human factor, such as tailgating) and environmental hazards (met with redundant power and cooling, fire suppression, and flood avoidance, backed by continuity and disaster-recovery planning). Life-safety always takes priority over security — exits must allow people to leave during a fire even where that affects access control. Test alarms, access controls, and failover only with authorization and proper change control. When infrastructure sits in a cloud or colocation facility, much of this becomes the provider's responsibility, so seek assurance through independent audit reports, like a SOC2, rather than assuming it.

### Reference and further reading

- [O'Reilly: *Physical Security Assessment Handbook*, 2nd Edition](https://www.oreilly.com/library/view/physical-security-assessment/9781040047491/)
- [O'Reilly: Data center physical security](https://www.oreilly.com/search/?q=data%20center%20physical%20security&type=book&rows=100)
- [McMaster Library: Site and facility design and physical security (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Site%20and%20facility%20design%20and%20physical%20security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Site and facility design and physical security (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Site%20and%20facility%20design%20and%20physical%20security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)
  
### Secure data center design and architecture

*Supports: Investigate — key principles for confidentiality, integrity, and availability in data center design*

- [Wikipedia: Data center security](https://en.wikipedia.org/wiki/Data_center_security) — an overview of the physical and operational controls that protect a data center.
- [Cisco: SAFE Secure Data Center Architecture Guide](https://www.cisco.com/c/en/us/solutions/collateral/enterprise/design-zone-security/safe-secure-dc-architecture-guide.html) — a reference architecture for securing the data center.
- [Palo Alto Networks: Data Center Security](https://www.paloaltonetworks.com/network-security/data-center) and [Data Center Best Practice Methodology](https://docs.paloaltonetworks.com/best-practices/10-2/data-center-best-practices/data-center-best-practice-security-policy/data-center-best-practice-methodology) — design and security methodology for data centers.
- [CCCS: Cyber Centre Data Centre Virtualization Report — Best Practices (ITSP.70.010)](https://www.cyber.gc.ca/en/guidance/cyber-centre-data-centre-virtualization-report-best-practices-data-centre-virtualization) — best practices for consolidated and virtualized data centers.
- [Shared Services Canada: Data Centre Services Reference Architecture Document (RAD)](https://www.canada.ca/en/shared-services/corporate/about-us/transparency/publications/data-centre-services-rad.html) — a government reference architecture for data center services (archived; useful for reference).

### Physical access control and environmental protection

*Supports: Reflect — integrating access control and surveillance into facility design; Research — protecting against environmental threats*

- [NIST SP 800-53 Rev. 5: Security and Privacy Controls for Information Systems and Organizations](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) — especially the **Physical and Environmental Protection (PE)** control family: physical access authorization and monitoring, visitor records, fire protection, temperature and humidity controls, power and water-damage protection. The direct control catalog for both of these prompts.
- [Fortinet: Install the FortiGate Unit in a Physically Secure Location](https://docs.fortinet.com/document/fortigate/6.4.0/hardening-your-fortigate/313138/install-the-fortigate-unit-in-a-physically-secure-location) — device-level physical placement guidance.
- [CCCS: Baseline Cyber Security Controls for Small and Medium Organizations](https://www.cyber.gc.ca/en/guidance/baseline-cyber-security-controls-small-and-medium-organizations) — where physical safeguards fit within a baseline security program.

### Availability, redundancy, and resilience

*Supports: Investigate — redundancy, resilience, and the Uptime Institute tiers*

- [Uptime Institute: Tier Classification System](https://uptimeinstitute.com/tiers) — the industry standard that classifies data centers from Tier I to Tier IV by the redundancy of their power, cooling, and distribution paths. The direct reference for the resilience prompt.
- [Wikipedia: Data center](https://en.wikipedia.org/wiki/Data_center) — background on data center infrastructure, including power, cooling, and redundancy concepts.

### Cloud and colocation: shared responsibility

*Supports: Investigate — assessing a provider's physical controls under shared responsibility*

- [Wikipedia: Cloud computing security](https://en.wikipedia.org/wiki/Cloud_computing_security) — the shared-responsibility model (where physical and environmental security shifts to the provider) and how customers gain assurance through audit reports such as SOC 2 and ISO/IEC 27001.
