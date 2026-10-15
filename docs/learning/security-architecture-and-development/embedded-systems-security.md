# Embedded Systems Security

## Description

Embedded systems are specialized devices such as smart appliances, medical devices, or industrial controllers. Security focuses on preventing these devices from being exploited or turned into entry points for larger attacks. Embedded systems are increasingly part of critical infrastructure, including research instrumentation and building HVAC. Their vulnerabilities can lead to significant risks, from privacy violations to physical harm.

## Why This Matters

Embedded systems security is essential because these devices, ranging from smart appliances to specialized instrumentation, are increasingly integrated into critical organizational infrastructure. Compromised embedded systems can serve as entry points for attacks, threaten sensitive data, and even pose physical risks. By embedding security at the design and operational level, staff help protect both digital and physical organizational assets. Enterprise operations rely on embedded systems for building management, specialized instrumentation, healthcare devices, and industrial equipment. Securing these systems helps the organization:

- Prevent unauthorized access and tampering with critical devices.
- Protect the integrity and availability of instrumentation, infrastructure, and operational technology.
- Reduce risks associated with privacy violations, service disruption, or physical harm.
- Ensure consistent security practices across connected and IoT-enabled systems.

By prioritizing embedded systems security, staff safeguard both operational continuity and facility safety. By embedding security into both the design and use of these devices, the organization ensures a safe, reliable, and resilient digital and physical environment.

## Skill Development

- Research: When designing embedded systems, how can security be embedded into the architecture to protect against physical tampering and unauthorized access?
- Investigate: How can an organization design secure communication protocols for embedded systems that are part of larger IT infrastructures?
- Investigate: What are the most important security design considerations when developing embedded systems for industries requiring high reliability, such as healthcare or manufacturing?
- Investigate: Embedded devices often run firmware that is seldom updated and may ship with hardcoded credentials or known-vulnerable components. How do secure boot, signed firmware updates, and a software bill of materials (SBOM) help manage firmware and supply-chain risk across a device's long deployment lifecycle?
- Reflect: Many embedded and IoT devices cannot defend themselves and cannot be patched easily. Why are network segmentation and monitoring — keeping these devices off flat networks and restricting what they are allowed to communicate with — often the most practical control, and how does this relate to the embedded TCP/IP stack vulnerabilities referenced on this page?

## Learning Resources

> **Scope and safety note:** Embedded systems bridge the digital and physical worlds, so a security failure can mean not just data loss but service disruption or physical harm. Test and change embedded and operational devices only with authorization and proper change control — never probe live medical, industrial, or building-control systems that could endanger people or operations. Because many of these devices cannot be easily patched or hardened, assume they are fragile: segment them, monitor them, limit what they can reach, and treat default credentials, exposed services, and unsigned firmware as serious risks.

### Reference and further reading

- [Wikipedia: Embedded system](https://en.wikipedia.org/wiki/Embedded_system) — background on what embedded systems are and how they are built.
- [O'Reilly: Embedded systems security](https://www.oreilly.com/search/?q=Embedded%20Systems%20Security&type=book&rows=100)
- [McMaster Library: Embedded systems security (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Embedded%20Systems%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Embedded systems security (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Embedded%20Systems%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)

### Secure-by-design and hardware roots of trust

*Supports: Research — embedding security into the architecture (anti-tamper, root of trust); Investigate — high-reliability design; Investigate — firmware and supply-chain risk*

- [NIST IR 8259 Rev. 1: Foundational Cybersecurity Activities for IoT Product Manufacturers](https://csrc.nist.gov/pubs/ir/8259/r1/final) — the current (2026) baseline of security activities device makers should perform, from secure defaults to update mechanisms. The direct reference for designing security in from the start.
- [Wikipedia: Trusted Execution Environment](https://en.wikipedia.org/wiki/Trusted_execution_environment) — how a hardware root of trust, secure boot, secure elements, and isolated execution (such as Arm TrustZone or Intel SGX) establish trust in a device from power-on and resist tampering.
- [RunSafe Security: Embedded Software Cybersecurity](https://runsafesecurity.com/) — a vendor perspective on protecting embedded software and firmware from exploitation across the supply chain.

### Managing deployed devices: IoT, peripherals, firmware, and exposure

*Supports: Investigate — secure communication within larger IT infrastructure; Investigate — firmware/supply-chain; Reflect — segmentation and monitoring as compensating controls*

- [CCCS: Internet of Things (IoT) Security (ITSAP.00.012)](https://www.cyber.gc.ca/en/guidance/internet-things-iot-security-itsap00012) — practical guidance on securing connected devices, including segmentation and change of default credentials.
- [CCCS: Security Tips for Peripheral Devices (ITSAP.70.015)](https://www.cyber.gc.ca/en/guidance/security-tips-peripheral-devices-itsap70015) — risks from embedded peripherals (USB, printers, and similar) and how to manage them.
- [CCCS: Control Systems — Multiple Embedded TCP/IP Stacks Security Advisory (AV21-078 / ICSA-21-042-01)](https://www.cyber.gc.ca/en/alerts-advisories/control-systems-multiple-embedded-tcpip-stacks-security-advisory-0) — a concrete example of why embedded network stacks are a weak point, and why segmentation and monitoring matter when devices cannot be patched quickly.
- [CCCS: Baseline Cyber Security Controls for Small and Medium Organizations](https://www.cyber.gc.ca/en/guidance/baseline-cyber-security-controls-small-and-medium-organizations) — where device inventory, patching, and network controls fit in a baseline program.
