# Virtualization and Cloud Computing

## Description

This topic addresses security in environments where virtual machines and cloud services are used. It covers issues such as securing virtualized infrastructure, protecting cloud data, and managing multi-tenant risks. Virtualization and cloud computing are core to modern IT infrastructure. Understanding their unique security challenges ensures sensitive data and applications remain safe.

## Why This Matters

Virtualization and cloud computing are essential because modern enterprise IT infrastructure increasingly relies on virtual machines and cloud services. Securing these environments ensures that sensitive data, applications, and services remain protected while enabling flexibility, scalability, and collaboration. By understanding the unique risks of virtualized and multi-tenant systems, staff can help maintain a secure, reliable digital environment. Enterprise operations leverage cloud services and virtualized infrastructure for business platforms, administrative systems, storage, and organization-wide applications. Security in these environments helps the organization:

- Protect data stored and processed in multi-tenant and virtual environments.
- Prevent unauthorized access or misconfigurations that could impact multiple systems.
- Ensure continuity of services despite shared infrastructure.
- Apply consistent security policies across physical, virtual, and cloud resources.

By managing virtualization and cloud security effectively, staff can safeguard essential operations, reduce risk exposure, and maintain trust in organizational systems. Virtualization and cloud computing security influence the daily responsibilities of staff and technical teams:

- Staff configure and monitor virtualized systems and cloud services, implement access controls, and ensure that security policies are enforced across environments.
- Technical teams follow best practices for using cloud storage and multi-tenant platforms, safeguarding sensitive data and project workflows.

By integrating virtualization and cloud security into everyday practices, the organization ensures resilient, reliable, and secure digital infrastructure.

## Skill Development

- Reflect: How do security risks in virtualized environments differ from traditional IT infrastructures, and what design strategies can address these risks?
- Research: When designing cloud environments, how can the risks of shared resources and multi-tenant systems be minimized?
- Investigate: What are some security design considerations for securing cloud storage and compute services in terms of confidentiality, integrity, and availability?
- Investigate: Cloud security is governed by a "shared responsibility model" that divides duties between the provider and the customer, and the split shifts across IaaS, PaaS, and SaaS. How does this model work, and why is the customer's share so often neglected — for example, through misconfigured storage, over-permissive identity and access management (IAM), or open security groups?
- Investigate: Modern virtualization increasingly means containers and orchestration (such as Kubernetes) rather than only virtual machines. How does securing containers differ from securing VMs — given shared-kernel isolation, the container image supply chain, and short-lived, ephemeral workloads — and what new controls does that require?

## Learning Resources

> **Scope and responsibility note:** The defining shift in cloud and virtualization is that you no longer control the whole stack. Under the shared responsibility model the provider secures the underlying infrastructure while you remain responsible for your data, identities, and configuration — and most real cloud incidents come from the customer side, through misconfiguration and over-permissive access rather than a provider breach. So default to least privilege, lock down storage and identity, and verify your configuration continuously. Test and change only the tenants, subscriptions, and virtual resources you are authorized to manage, and remember that one misconfiguration or a VM/hypervisor escape can affect many systems at once because the infrastructure is shared.

### Reference and further reading

- [O'Reilly: Virtualization and cloud security](https://www.oreilly.com/search/?q=cloud%20security%20virtualization&type=book&rows=100)
- [McMaster Library: Virtualization and cloud computing (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Virtualization%20and%20Cloud%20Computing&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Virtualization and cloud computing (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Virtualization%20and%20Cloud%20Computing&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)
- 
### Virtualization and hypervisor security

*Supports: Reflect — how virtualized-environment risks differ from traditional IT; Investigate — containers vs. VMs*

- [Wikipedia: Virtualization](https://en.wikipedia.org/wiki/Virtualization) — background on virtual machines, hypervisors, and isolation.
- [NIST SP 800-125: Guide to Security for Full Virtualization Technologies](https://csrc.nist.gov/pubs/sp/800/125/final) — foundational guidance on virtualization risks such as VM escape, sprawl, and isolation (dated 2011; pair it with the newer companions below).
- [NIST SP 800-125A Rev. 1: Security Recommendations for Server-based Hypervisor Platforms](https://csrc.nist.gov/pubs/sp/800/125/a/r1/final) — hardening the hypervisor itself, the most security-critical component of a virtualized host.
- [NIST SP 800-190: Application Container Security Guide](https://csrc.nist.gov/pubs/sp/800/190/final) — the direct reference for the containers prompt: image, registry, orchestrator, and runtime risks, and how container isolation differs from VM isolation.

### Cloud security foundations and shared responsibility

*Supports: Research — minimizing shared-resource/multi-tenant risk; Investigate — the shared responsibility model*

- [Wikipedia: Cloud computing security](https://en.wikipedia.org/wiki/Cloud_computing_security) — the shared responsibility model, multi-tenancy risks, and how cloud security differs from on-premise.
- [NIST SP 800-145: The NIST Definition of Cloud Computing](https://csrc.nist.gov/pubs/sp/800/145/final) — the service models (IaaS, PaaS, SaaS) and deployment models that determine where the responsibility line falls.
- [Cloud Security Alliance: Cloud Controls Matrix (CCM)](https://cloudsecurityalliance.org/research/cloud-controls-matrix) — a cloud-specific control framework (197 controls across 17 domains) for assessing a cloud environment or provider.
- [CCCS: Guidance on Cloud Security Assessment and Authorization (ITSP.50.105)](https://www.cyber.gc.ca/en/guidance/guidance-cloud-security-assessment-and-authorization-itsp50105) — assessing and authorizing cloud services for use.

### Securing cloud data, workloads, and networks

*Supports: Investigate — confidentiality, integrity, and availability of cloud storage and compute; Investigate — misconfiguration and IAM*

- [CCCS: Guidance on Defence in Depth for Cloud-Based Services (ITSP.50.104)](https://www.cyber.gc.ca/en/guidance/itsp50104-guidance-defence-depth-cloud-based-services) — layering controls across a cloud deployment.
- [CCCS: Guidance on Cloud Service Cryptography (ITSP.50.106)](https://www.cyber.gc.ca/en/guidance/guidance-cloud-service-cryptography-itsp50106) — protecting cloud data with encryption and customer-managed keys.
- [CCCS: Cloud Network Security Zones (ITSP.80.023)](https://www.cyber.gc.ca/en/guidance/cloud-network-security-zones-itsp80023) — applying segmentation and zoning to cloud networks.

### Vendor platforms and perspectives

- [Cisco: Security Cloud](https://www.cisco.com/site/us/en/products/security/security-cloud/index.html) and [Cloud Protection Suite](https://www.cisco.com/site/us/en/products/security/cloud-protection/index.html) — example cloud-security platforms.
- [Fortinet: What Is Cloud Security?](https://www.fortinet.com/resources/cyberglossary/what-is-cloud-security), [Hybrid Cloud Security](https://www.fortinet.com/solutions/enterprise-midsize-business/hybrid-cloud-security), and [Private Cloud and SDN Security](https://www.fortinet.com/solutions/enterprise-midsize-business/private-cloud-security-sdn) — vendor explainers and solutions.
- [Palo Alto Networks: Cloud Security Overview](https://www.paloaltonetworks.com/cyberpedia/cloud-security), [Prisma Cloud](https://www.paloaltonetworks.com/prisma/cloud), and [VM-Series Virtual Next-Generation Firewall](https://www.paloaltonetworks.com/network-security/vm-series-virtual-next-generation-firewall) — posture management and workload protection examples.
