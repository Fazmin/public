# DNS and WHOIS Queries

## Description

DNS and WHOIS queries are fundamental OSINT techniques used to gather detailed information about a domain’s registration, ownership, infrastructure, and associated network assets. By querying DNS records, analysts can uncover domain names, subdomains, IP addresses, mail servers, and other critical network components. WHOIS data reveals registration details such as registrant contact information, domain creation and expiration dates, and registrar details. Combined, these queries help build an intelligence picture that supports vulnerability assessments, threat hunting, and incident response investigations.

## Why This Matters

DNS and WHOIS queries matter because they provide foundational visibility into how network traffic is being routed and which domains are being interacted with. As attackers increasingly rely on newly registered, rapidly changing, or misconfigured domains, DNS and WHOIS data help identify suspicious patterns early. Proactive monitoring of these queries strengthens the ability to detect phishing sites, domain spoofing, and malicious infrastructure before they cause harm. Enterprise operations depend heavily on secure network communication, cloud services, and online platforms. Effective DNS and WHOIS monitoring helps operational teams:
- Identify malicious or unauthorized domains communicating with university systems (e.g., phishing, malware callbacks, compromised accounts)
- Verify the legitimacy and ownership of domains interacting with administrative services to prevent fraudulent access or impersonation attempts
- Detect anomalies in DNS traffic that could indicate misconfigurations or emerging attacks such as DNS tunneling or exfiltration
- Maintain uninterrupted and secure access to internal and third-party services by quickly identifying and responding to domain-related issues
- Verifying the legitimacy of external research partners’ infrastructure before tools, datasets, or code are accessed
- Identifying suspicious domain activity

## Skill Development

- Investigate: What types of DNS records are most relevant for mapping the attack surface of a domain, and how can they be leveraged during security assessments?
- Research: How can WHOIS data assist in attributing ownership and identifying potential points of contact during a cybersecurity investigation?
- Research: What privacy protection mechanisms exist for WHOIS data, and how do they impact OSINT investigations?
- Reflect: In what ways can IP geolocation data from DNS queries support threat intelligence and incident response activities?
- Investigate: How did the move from WHOIS to RDAP change what registration data is publicly available and how it is accessed, and what does that mean for an investigator today?
- Investigate: How can historical and passive DNS records reveal infrastructure that a current, single DNS lookup would miss, and why does that matter when tracking a threat actor who changes hosting?

## Learning Resources

> **Ethics and scope note:** Registration and DNS records can contain personal information (a registrant's name, address, or email), and much of it is now redacted by default for privacy reasons. Use these lookups for legitimate, authorized purposes, respect each service's terms and rate limits, and do not use registrant contact details to harass an individual. Passive, read-only lookups touch only third-party data services; actively probing a target's own DNS infrastructure is a different matter and needs authorization.

### Reference and further reading

- [McMaster Library: DNS and WHOIS](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,DNS,%20whois&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&lang=en&offset=0)
- [Authentic8: Adversary infrastructure and OSINT techniques](https://authentic8.com/blog/adversary-cyber-infrastructure-osint-techniques/)

### How DNS and registration data work

*Supports: all record-type and attribution questions*

- [Cloudflare Learning: What is DNS?](https://www.cloudflare.com/learning/dns/what-is-dns/) — a clear, vendor-neutral explanation of how DNS resolution works, a better starting point than the Wikipedia article for understanding the records in practice.
- [Wikipedia: List of DNS record types](https://en.wikipedia.org/wiki/List_of_DNS_record_types) — a reference for the records that matter in an assessment (A/AAAA, MX, NS, TXT, CNAME, SOA, and so on).
- [IANA Root Zone Database](https://www.iana.org/domains/root/db) — the authoritative list of top-level domains and their registries, useful for knowing where a domain's records ultimately come from.

### Running lookups (WHOIS and RDAP)

*Supports: Investigate — extracting target-specific information; attribution*

- [ICANN Lookup (RDAP)](https://lookup.icann.org/) — ICANN's official registration-data lookup, now RDAP-based. The authoritative first stop for gTLD registration data.
- [ICANN: Launching RDAP; Sunsetting WHOIS (announcement)](https://www.icann.org/en/announcements/details/icann-update-launching-rdap-sunsetting-whois-27-01-2025-en) — the primary source on the January 2025 transition and why it happened; also explains the Registration Data Request Service (RDRS) for requesting nonpublic data with a legitimate interest.
- [Wikipedia: WHOIS](https://en.wikipedia.org/wiki/WHOIS) and [Wikipedia: RDAP](https://en.wikipedia.org/wiki/Registration_Data_Access_Protocol) — background on both protocols and how they relate.

### DNS reconnaissance and history

*Supports: mapping attack surface; tracking infrastructure over time*

- [MXToolbox](https://mxtoolbox.com/) — free web lookups for MX, SPF, DNS, and blacklist checks; a quick way to inspect a domain's mail and DNS configuration.
- [ViewDNS.info](https://viewdns.info/) — a free collection of DNS and domain tools, including reverse IP lookup, DNS records, and IP history.
- [SecurityTrails (DNS Trails)](https://securitytrails.com/dns-trails) — current and historical DNS records, passive DNS, and WHOIS history. Historical and passive data (seeing where a domain *used* to point) is what lets an investigator follow infrastructure a single live lookup would miss; some history requires a free account.
- [MITRE ATT&CK: Gather Victim Network Information – DNS (T1590.002)](https://attack.mitre.org/techniques/T1590/002/) — the adversary's view of DNS reconnaissance, linking this technique to the subdomain-enumeration work elsewhere in this collection.

### IP geolocation and infrastructure context

*Supports: Reflect — IP geolocation for threat intel and incident response*

- [MaxMind GeoIP](https://www.maxmind.com/en/geoip-databases) — a standard source for mapping an IP address to an approximate location and network (ASN). A caution worth teaching: IP geolocation gives the hosting or network location, not necessarily the operator's real location, and VPNs, proxies, and cloud hosting routinely break the assumption.
- [Wikipedia: Internet geolocation](https://en.wikipedia.org/wiki/Internet_geolocation) — background on how (and how imperfectly) IP addresses map to physical locations.

### Privacy, redaction, and the limits of the data

*Supports: Reflect — privacy mechanisms and their impact; the RDAP transition*

- [ICANN: Registration Data Request Service (RDRS)](https://www.icann.org/rdrs) — the formal channel for requesting redacted registration data for a legitimate purpose (abuse reporting, law enforcement, IP enforcement, cybersecurity).
- [Lu et al. (NDSS 2021): From WHOIS to WHOWAS – Domain Registration Privacy under the GDPR](https://www.ndss-symposium.org/ndss-paper/from-whois-to-whowas-a-large-scale-measurement-study-of-domain-registration-privacy-under-the-gdpr/) — a large-scale measurement of how GDPR drove mass redaction of registrant data, with over 85% of surveyed large providers redacting EEA records and many redacting non-EEA records too. The clearest evidence for why attribution from registration data is now much harder.

### Defensive and standards context

*Supports: Reflect — supporting security operations; mapping attack surface*

- [NIST SP 800-81r3: Secure DNS Deployment Guide (final, March 2026)](https://csrc.nist.gov/pubs/sp/800/81/r3/final) — the current edition (it supersedes the 2013 SP 800-81-2). It frames DNS as an active security control, covers DNSSEC, encrypted DNS (DoH/DoT/DoQ), Protective DNS, and using DNS logs for detection and incident response.
- [Canadian Centre for Cyber Security: Protective DNS (ITSAP.40.019)](https://www.cyber.gc.ca/en/guidance/protective-domain-name-system-itsap40019) — a concise overview of how Protective DNS blocks connections to known-malicious domains.
- [CISA: Protective DNS](https://www.cisa.gov/resources-tools/services/protective-domain-name-system-resolver) — the U.S. counterpart, useful for the operational-security framing.

