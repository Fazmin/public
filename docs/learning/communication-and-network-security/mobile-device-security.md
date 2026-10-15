# Mobile Device Security

## Description

Mobile device security addresses the risks associated with smartphones, tablets, and laptops that access networks and data from various locations. These devices must be protected through strong authentication, full-disk encryption, and remote wipe capabilities in case of loss or theft. Mobile Device Management (MDM) solutions help enforce security policies, manage application access, and maintain visibility over institutional data accessed or stored on mobile devices.

## Why This Matters

Mobile device security matters because phones, tablets, and laptops regularly leave controlled environments, connect to untrusted networks, and store or access sensitive institutional data. Strong protections such as full-disk encryption, modern authentication, and MDM policy enforcement reduce the risk of data exposure and unauthorized access.

### Typical Best Practices

- If your mobile device has been issued to you, look for institutional guidance on acceptable use and security.
- Look up configuration and hardening guidance for your particular device and software.
- Enable remote wipe for lost or stolen devices.
- Enforce password strength, encryption, and operating system updates.
- Control which applications can access sensitive data.
- Maintain visibility into device compliance for remote or travelling staff.
- Reduce the risk of compromised devices accessing administrative systems.
- Encrypt data stored locally on mobile devices.
- Only install trusted software. Learn about the trust mechanisms for software on your device.
- Protect access tokens, credentials, and files synchronized from cloud services.

## Skill Development

- Reflect: Can you describe how full-disk encryption helps protect institutional and personal data on a mobile device? Can you describe what data or systems you would lose access to if your device were lost or stolen?
- Research: From a device management perspective, what is MDM, and how does it support policy enforcement? In which work or learning environments are mobile policies important?
- Investigate: How do mobile device authentication methods, such as biometrics and MFA, contribute to the concept of defense in depth?
- Investigate: How do mobile operating systems control what apps can access — permission models, app sandboxing, and app-store vetting — and how can a risky or malicious app still put institutional data at risk? What does "only install trusted software" mean in practice?
- Reflect: How does securing a personally owned (BYOD) device differ from securing a corporate-owned one, and how should an organization balance security controls (such as MDM) against the privacy of the user on their own device?

## Learning Resources

> **Privacy and loss note:** Management controls on a personal (BYOD) device can reach personal data, location, and app usage, so be transparent about what MDM can see and do, separate work and personal data where possible (containerization), and limit monitoring to what is necessary. Treat a lost or stolen device as a potential data breach: full-disk encryption, a strong unlock method, remote wipe, and prompt reporting are what keep that loss from becoming an exposure.

### Reference and further reading

- [O'Reilly: Mobile Device Security](https://www.oreilly.com/search/?q=Mobile%20Device%20Security&type=book&rows=100)
- [McMaster Library: Mobile device security (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Mobile%20Device%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=rtype,include,books&facet=searchcreationdate,include,2010%7C,%7C2025&lang=en&offset=0)
  
### Platform security and trusted software

*Supports: Investigate — app permissions and trusted software; Investigate — authentication and defense in depth*

- [Apple Platform Security](https://support.apple.com/guide/security/welcome/web) — how iOS/iPadOS enforce secure boot, app signing, sandboxing, data protection (encryption), and biometrics (Face ID/Touch ID). Explains the "trust mechanisms for software on your device."
- [Android Security](https://source.android.com/docs/security) — the equivalent for Android: verified boot, app sandboxing, permissions, and encryption; Google Play Protect vets apps in the Play Store and on-device.
- [OWASP Mobile Application Security (MAS)](https://mas.owasp.org/) — the standard for mobile app security, home of the Mobile Top 10 risks and the MASVS/MASTG. Useful for understanding how apps mishandle data and what "trusted software" really requires.

### Encryption, authentication, and device loss

*Supports: Reflect — full-disk encryption and loss impact; Investigate — biometrics/MFA and defense in depth*

- [CCCS: Using Your Mobile Device Securely (ITSAP.00.001)](https://www.cyber.gc.ca/en/guidance/using-your-mobile-device-securely-itsap00001) — practical user-facing guidance on locking, encrypting, updating, and protecting a device.
- [CCCS: Secure Your Accounts and Devices with Multi-Factor Authentication (ITSAP.30.030)](https://www.cyber.gc.ca/en/guidance/secure-your-accounts-and-devices-multi-factor-authentication-itsap30030) — how MFA and biometrics layer on top of device unlock as part of defense in depth.
- [Wikipedia: Mobile security](https://en.wikipedia.org/wiki/Mobile_security) — background on the threat landscape.

### Enterprise mobile management (MDM)

*Supports: Research — what MDM is and how it enforces policy*

- [NIST SP 800-124 Rev. 2: Guidelines for Managing the Security of Mobile Devices in the Enterprise](https://csrc.nist.gov/pubs/sp/800/124/r2/final) — the central, current NIST guidance on managing and securing enterprise mobile devices, including MDM/EMM architectures.
- [NIST NCCoE: Mobile Device Security practice guides](https://www.nccoe.nist.gov/mobile-device-security) — hands-on reference implementations for enterprise and BYOD scenarios.
- [CCCS: Security Considerations for Mobile Device Deployments (ITSAP.70.002)](https://www.cyber.gc.ca/en/guidance/security-considerations-mobile-device-deployments-itsap70002)
- MDM/EMM product references: [Cisco Meraki Systems Manager](https://www.cisco.com/site/us/en/products/security/user-device-security/meraki-systems-manager/index.html), [Cisco: What Is Endpoint Management?](https://www.cisco.com/site/us/en/learn/topics/security/what-is-endpoint-management.html), [Fortinet: What Is Mobile Device Management (MDM)?](https://www.fortinet.com/resources/cyberglossary/mobile-device-management), and [Palo Alto Networks: Set Up MDM Integration with GlobalProtect](https://docs.paloaltonetworks.com/globalprotect/administration/globalprotect-apps/deploy-the-globalprotect-app-on-mobiles/set-up-a-mobile-endpoint-management-system).

### BYOD, remote access, and untrusted networks

*Supports: Reflect — BYOD vs corporate-owned; Why This Matters — untrusted networks and travelling staff*

- [CCCS: End User Device Security for BYOD Deployment Models (ITSM.70.003)](https://www.cyber.gc.ca/en/guidance/end-user-device-security-bring-your-own-device-byod-deployment-models-itsm70003) — the direct reference for the BYOD prompt.
- [NIST SP 800-46 Rev. 2: Guide to Enterprise Telework, Remote Access, and BYOD Security](https://csrc.nist.gov/publications/detail/sp/800-46/rev-2/final) — securing devices that connect from home and untrusted networks, including the use of VPNs and the risks of public Wi-Fi.
