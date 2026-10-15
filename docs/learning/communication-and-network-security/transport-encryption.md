# Transport Encryption

## Description

Transport encryption ensures the confidentiality and integrity of data as it moves between systems by encrypting communication channels. Protocols such as TLS and IPsec are commonly used to secure web traffic, email, and virtual private network (VPN) connections, protecting data from interception or tampering during transit. In an enterprise setting, encrypting data in motion is critical for safeguarding sensitive information exchanged between departments, cloud services, and remote collaborators.

## Why This Matters

Transport encryption prevents attackers from intercepting or altering data as it moves across shared or untrusted networks. Without strong encryption, credentials, research data, and internal communications can be exposed through passive sniffing or active man-in-the-middle attacks.

- Protect login sessions, administrative dashboards, and internal applications.
- Secure data exchanged between departments, remote staff, and third parties.
- Enable secure VPN access for remote work and travel.
- Prevent interception or modification of email, web portals, and internal APIs.
- Support privacy, data protection, and audit requirements.
- Reduce exposure to man-in-the-middle attacks.
- Staff rely on encrypted protocols when managing systems and connecting to cloud services.
- Technical teams depend on secure channels for data transfers and collaboration.
- End users benefit from encrypted Wi-Fi authentication and protected login sessions.

## Skill Development

- Reflect: Can you describe the role of TLS in protecting data in motion, and what happens during a TLS handshake?
- Investigate: What are some popular cryptographic suites used by servers?
- Investigate: From a threat modelling perspective, what risks does transport encryption mitigate, and what risks remain?
- Investigate: How do certificate authorities support the trust model used in encrypted transport protocols?
- Investigate: Why have TLS 1.0 and 1.1 been deprecated, what does TLS 1.3 improve over TLS 1.2 (faster handshake, removal of weak ciphers, forward secrecy by default), and how should an organization decide which protocol versions and cipher suites to allow?
- Investigate: TLS and IPsec both protect data in transit but operate at different layers of the stack. How do they differ, and when would you reach for a TLS-based approach versus an IPsec VPN?

## Learning Resources

> **Scope and privacy note:** Encryption protects data in transit, but it does not protect a compromised endpoint, validate who you are really talking to on its own (that is the certificate's job), or guarantee that a server is configured with strong, current settings. Some organizations decrypt and inspect TLS traffic at the perimeter to detect threats; this has real security value but also real privacy, trust, and performance trade-offs, so it should be disclosed through policy, scoped to what is necessary, and applied only to networks and systems you are authorized to manage. When testing TLS configurations, test only servers you own or are authorized to assess.

### Reference and further reading

- [O'Reilly: Transport encryption](https://www.oreilly.com/search/?q=Transport%20Encryption&type=book&rows=100)
- [McMaster Library: Transport encryption (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Transport%20Encryption&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Transport encryption (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Transport%20Encryption&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)

### TLS foundations and the handshake

*Supports: Reflect — the role of TLS and what happens during the handshake*

- [Wikipedia: Transport Layer Security (TLS)](https://en.wikipedia.org/wiki/Transport_Layer_Security) — how TLS works, including the handshake, record protocol, and version history.
- [OWASP: Transport Layer Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Security_Cheat_Sheet.html) — guide to configuring TLS well: which versions to allow, which cipher suites to prefer, and common mistakes. Directly supports the handshake, version, and threat prompts.

### Choosing versions and cipher suites

*Supports: Investigate — TLS 1.0/1.1 deprecation, TLS 1.2 vs. 1.3, and selecting versions and ciphers*

- [NIST SP 800-52 Rev. 2: Guidelines for the Selection, Configuration, and Use of TLS Implementations](https://csrc.nist.gov/pubs/sp/800/52/r2/final) — the standards reference for which TLS versions and cipher suites to enable (TLS 1.2 minimum, TLS 1.3 encouraged) and how to configure servers securely.
- [CCCS: Guidance on Securely Configuring Network Protocols (ITSP.40.062)](https://www.cyber.gc.ca/en/guidance/guidance-securely-configuring-network-protocols-itsp40062) — Canadian guidance on acceptable protocols, versions, and algorithms for TLS and related protocols.
- [FortiGate: Encryption Algorithm Cipher Suites](https://docs.fortinet.com/document/fortigate/7.6.3/administration-guide/484445/fortigate-encryption-algorithm-cipher-suites) and [TLS Configuration in FortiGate](https://docs.fortinet.com/document/fortigate/7.4.4/administration-guide/45329/tls-configuration) — examples of selecting versions and cipher suites on a device.

### Certificates, certificate authorities, and trust

*Supports: Investigate — how certificate authorities support the trust model*

- [Wikipedia: Certificate authority](https://en.wikipedia.org/wiki/Certificate_authority) — the role of CAs, the chain of trust, and how browsers and systems decide which certificates to trust.
- [Palo Alto Networks: Configure an SSL/TLS Service Profile](https://docs.paloaltonetworks.com/ngfw/administration/certificate-management/configure-ssl-tls-service-profile) — how certificates and allowed protocol versions are bound together in a device's TLS configuration.
- [TLS Setup in Cisco Unified Communications Manager](https://www.cisco.com/c/en/us/td/docs/voice_ip_comm/cucm/security/12_5_1/cucm_b_security-guide-1251/cucm_b_security-guide-1251_chapter_0101.html) — a product example of configuring certificates and TLS for a service.

### IPsec, VPNs, and transport at different layers

*Supports: Investigate — TLS vs. IPsec and when to use each; secure VPN access*

- [NIST SP 800-77 Rev. 1: Guide to IPsec VPNs](https://csrc.nist.gov/pubs/sp/800/77/r1/final) — how IPsec protects traffic at the network layer, the counterpart to TLS's transport-layer protection. The direct reference for the TLS-vs-IPsec prompt.
- [CCCS: Virtual Private Networks (ITSAP.80.101)](https://www.cyber.gc.ca/en/guidance/virtual-private-networks-itsap80101) — guidance on VPNs for remote work and travel.

### Encryption in web and application contexts (and inspection)

*Supports: Investigate — risks that remain after encryption; the trade-offs of TLS inspection*

- [CCCS: Web Browser Security — An Overview (ITSAP.40.017)](https://www.cyber.gc.ca/en/guidance/web-browser-security-overview-itsap40017) — how browsers rely on and signal transport encryption.
- [CCCS: Security Considerations for Your Website (ITSM.60.005)](https://www.cyber.gc.ca/en/guidance/security-considerations-your-website-itsm60005) — includes enabling HTTPS/TLS for web services.
- [Palo Alto Networks: TLS 1.3 Decryption](https://docs.paloaltonetworks.com/network-security/decryption/administration/decryption-overview/tls-1-3-ssl-decryption) — how perimeter devices decrypt and inspect TLS traffic, and why TLS 1.3 makes this harder — useful for weighing the "risks that remain" and the inspection trade-offs.
