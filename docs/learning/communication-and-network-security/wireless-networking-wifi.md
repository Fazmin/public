# Wireless Networking (WiFi)

## Description

Wireless networking introduces unique security challenges due to the broadcast nature of radio communications. To protect enterprise networks, WiFi must be secured using strong encryption such as WPA3, mutual authentication, and segmentation of guest and internal traffic. Additional safeguards include monitoring for rogue access points, enforcing network access policies, and ensuring that mobile or unmanaged devices do not introduce risks to organizational systems and data.

## Why This Matters

Wireless networking matters because WiFi exposes the organization to risks that do not exist in wired environments. Anyone within radio range can attempt to probe the network, capture broadcasts, impersonate an access point, or connect with an unmanaged device. Strong protections such as WPA3, mutual authentication, and segmentation are essential for preventing unauthorized access, eavesdropping, and lateral movement.

### Typical best practices

- Prevent unauthorized users or rogue devices from accessing internal systems.
- Protect staff logins, administrative portals, and cloud services on mobile devices.
- Safeguard sensitive data as personnel move across buildings and shared spaces.
- Maintain secure access for laptops, tablets, and mobile devices.
- Detect and mitigate rogue access points that mimic official WiFi networks.
- Preserve network availability and performance in high-density areas.
- Staff depend on secure WiFi when working across office locations and accessing administrative systems.
- Technical teams rely on strong wireless security for mobile data collection and system access.
- End users use WiFi for business applications, collaboration tools, and organizational services.

## Skill Development

- Research: Can you explain how WPA3 improves wireless security compared to WPA2, especially in public or open network settings?
- Investigate: From a wireless architecture standpoint, how can rogue access points be detected and mitigated?
- Research: How does isolating guest WiFi traffic from internal networks help reduce the attack surface?
- Investigate: What is the difference between WPA2/WPA3-Personal (a shared passphrase) and WPA2/WPA3-Enterprise (802.1X/EAP with a RADIUS server), and why does enterprise authentication scale better, give each user their own credentials, and support the mutual authentication the page describes?
- Investigate: Beyond rogue access points, what other attacks target Wi-Fi — such as evil-twin and captive-portal phishing, deauthentication attacks, and capturing a handshake to crack a weak pre-shared key offline — and which defenses (WPA3, strong passphrases, 802.1X, and protected management frames) address them?

## Learning Resources

> **Scope and safety note:** Wi-Fi signals travel beyond the walls of a building, so assume anyone in range can observe that traffic exists. Techniques used to test wireless security — scanning for networks, capturing handshakes, standing up a test access point, or sending deauthentication frames — can disrupt service and can capture other people's traffic, so practise them only on networks you own or are explicitly authorized to assess, and never against production or neighbouring networks. On the client side, treat open and public Wi-Fi as untrusted: avoid auto-joining unknown networks and use a VPN when working remotely.

### Reference and further reading

- [O'Reilly: Wireless networking and security](https://www.oreilly.com/search/?q=Wireless%20Networking%20(WiFi)&type=book&rows=100)
- [McMaster Library: Wireless networking (videos, 2010–2026)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Wireless%20Networking%20(WiFi)&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Wireless networking (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Wireless%20Networking%20(WiFi)&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2026&facet=rtype,include,books&lang=en&offset=0)

### WPA3 and wireless encryption

*Supports: WPA3 vs. WPA2 improvements, especially on public/open networks*

- [Wi-Fi Alliance: Security (WPA3)](https://www.wi-fi.org/discover-wi-fi/security) — authoritative source from the body that defines the standards, covering WPA3 and enhancements such as Opportunistic Wireless Encryption for open networks (Wi-Fi Enhanced Open).
- [Wikipedia: Wi-Fi Protected Access (WPA)](https://en.wikipedia.org/wiki/Wi-Fi_Protected_Access) — the evolution from WPA/WPA2 to WPA3, including SAE (the WPA3 handshake) and why it resists offline password guessing.
- [Cisco: Wi-Fi Protected Access 3 (WPA3) Overview](https://www.cisco.com/c/en/us/td/docs/wireless/controller/9800/17-4/config-guide/b_wl_17_4_cg/m_wpa3.html) and [Fortinet: WPA3 Security Configuration](https://docs.fortinet.com/document/fortiap/7.4.4/fortiwifi-and-fortiap-configuration-guide/233803/wpa3-security) — examples of enabling WPA3 on enterprise equipment.

### Enterprise authentication (802.1X / EAP)

*Supports: Investigate — WPA-Personal vs. WPA-Enterprise and mutual authentication*

- [NIST SP 800-97: Establishing Wireless Robust Security Networks — A Guide to IEEE 802.11i](https://csrc.nist.gov/pubs/sp/800/97/final) — the NIST reference for robust wireless security, including the 802.11i/RSN framework and 802.1X/EAP authentication. (Published 2007; predates WPA3, so pair it with the Wi-Fi Alliance material for current protocol detail.)
- [Wikipedia: IEEE 802.1X](https://en.wikipedia.org/wiki/IEEE_802.1X) — port-based network access control: how enterprise Wi-Fi authenticates each user against a RADIUS server rather than sharing one passphrase. The direct reference for the Personal-vs-Enterprise prompt.
- [NIST SP 800-53 Rev. 5: Security and Privacy Controls](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) — the Access Control (AC) and Identification and Authentication (IA) families as they apply to wireless access.

### Rogue access points and wireless attacks

*Supports: rogue AP detection and mitigation; Investigate — evil-twin, deauth, and handshake-cracking attacks and defenses*

- [Cisco: Managing Rogue Devices](https://www.cisco.com/c/en/us/td/docs/wireless/controller/9800/config-guide/b_wl_16_10_cg/managing-rogue-devices.html) and [Fortinet: Monitoring Rogue Access Points](https://docs.fortinet.com/document/fortiap/7.6.3/fortiwifi-and-fortiap-configuration-guide/501673/monitoring-rogue-aps) — how wireless controllers detect and contain rogue and evil-twin access points.
- [Wikipedia: Evil twin (wireless networks)](https://en.wikipedia.org/wiki/Evil_twin_(wireless_networks)) — example of an access-point impersonation attack and the defenses against it.

### Guest Wi-Fi, segmentation, and secure use

*Supports: isolating guest WiFi to reduce attack surface; protecting staff on Wi-Fi*

- [CCCS: Guest Wi-Fi (ITSAP.80.023)](https://www.cyber.gc.ca/en/guidance/guest-wi-fi-itsap80023) — reference for separating guest traffic from internal networks.
- [CCCS: Wi-Fi Security (ITSP.80.002)](https://www.cyber.gc.ca/en/guidance/wi-fi-security-itsp80002) — baseline requirements for securing enterprise wireless.
- [CCCS: Protecting Your Organization While Using Wi-Fi (ITSAP.80.009)](https://www.cyber.gc.ca/en/guidance/protecting-your-organization-while-using-wi-fi-itsap80009) — user-facing guidance for safe Wi-Fi use, including public networks.
- [CCCS: Routers — Cyber Security Best Practices (ITSAP.80.019)](https://www.cyber.gc.ca/en/guidance/routers-cyber-security-best-practices-itsap80019) — securing the wireless routers and gateways that serve the network.
