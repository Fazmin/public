# Authentication

## Description

Authentication is the process of validating the identity of a subject by verifying one or more authentication factors: something the subject knows, such as a password; has, such as a smart card; or is, such as a biometric trait. Strong authentication mechanisms, including multi-factor authentication (MFA), help protect against impersonation and credential-based attacks.

## Why This Matters

Authentication matters because it verifies that the person or system attempting to access a resource is truly who they claim to be. Even if identification is accurate, without strong authentication an attacker could impersonate legitimate users, steal credentials, or gain unauthorized access. In a large organization with diverse users, remote access needs, and high-value systems, robust authentication prevents many of the most common and dangerous attacks, including password guessing, phishing, credential stuffing, and unauthorized device access. Enterprise operations depend on reliable authentication to protect administrative data, cloud services, and internal systems used every day by staff. Effective authentication helps operational teams:

- Prevent unauthorized access to HR, finance, and business information systems.
- Protect staff login sessions from credential theft or impersonation.
- Enforce MFA for remote work, VPNs, and cloud applications.
- Ensure that only approved devices and users can access sensitive tools.
- Reduce the risk of phishing-based account compromise.
- Maintain compliance with organizational security standards and external regulations.
- Staff rely on strong authentication to securely access administrative systems, cloud tools, and remote work environments.
- Technical teams use MFA, secure tokens, or device-based authentication to connect to sensitive systems and collaboration platforms.
- End users depend on secure login methods for email, Wi-Fi, business applications, and shared resources, reducing their exposure to credential theft.

Without strong authentication, routine operational activities could be hijacked by attackers, placing confidential information and critical systems at risk. By ensuring that only legitimate users can access enterprise resources, authentication strengthens the security of daily activities across the organization.

## Skill Development

- Investigate: What factors should be considered when selecting authentication methods for systems handling sensitive or regulated data?
- Reflect: How can multi-factor authentication be implemented effectively without introducing excessive friction for end users?
- Research: What are the common weaknesses of knowledge-based authentication, and how can they be mitigated?
- Reflect: Not all MFA is equally strong — SMS codes and push approvals can be phished, SIM-swapped, or defeated by push-fatigue and real-time relay attacks. What makes an authentication method *phishing-resistant* (such as FIDO2/WebAuthn passkeys or PIV/smart cards), and when should an organization require it rather than ordinary MFA?
- Investigate: Why is the account-recovery and password-reset process often the weakest point in an authentication system, and how can it be hardened without locking out legitimate users?

## Learning Resources

> **Ethics and scope note:** Authentication systems handle highly sensitive data — passwords, MFA secrets, biometric templates, phone numbers. Store credentials hashed and salted, never log them, and protect biometric data as the sensitive personal information it is. Balance strength against accessibility and inclusion: an authentication method that is hard for some legitimate users (no smartphone, a disability, no reliable cell signal) to use can lock them out, so offer more than one strong option.

### Reference and further reading

- [Wikipedia: Electronic authentication](https://en.wikipedia.org/wiki/Electronic_authentication)
- [McMaster Library: Authentication in information security (videos, 2010–2025)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Authentication%20Information%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=searchcreationdate,include,2010%7C,%7C2025&facet=rtype,include,videos&lang=en&offset=0)
- [McMaster Library: Authentication in information security (books)](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Authentication%20Information%20Security&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&facet=rtype,include,books&facet=searchcreationdate,include,2010%7C,%7C2025&lang=en&offset=0)
- [O'Reilly: Identity and Access Management](https://www.oreilly.com/search/?q=Learning%3A%20Identity%20and%20Access%20Management&type=article&type=book&type=shortcut&rows=100)
  
### Standards and assurance levels

*Supports: Investigate — selecting methods for sensitive or regulated data*

- [NIST SP 800-63 Revision 4: Digital Identity Guidelines](https://pages.nist.gov/800-63-4/) — the current edition (Revision 4 was finalized in 2025, replacing the Revision 3 set). Its Authentication Assurance Levels (AAL1–AAL3) are the standard way to match the strength of authentication to the sensitivity of a system, which is the core of the selection question.
- [NIST SP 800-63B-4: Authentication and Authenticator Management](https://csrc.nist.gov/pubs/sp/800/63/b/4/final) — the authoritative reference for authenticator types, MFA, password ("memorized secret") rules, and account-recovery and lifecycle requirements. The single most useful document for this page.
- [NIST SP 800-63A-4: Identity Proofing and Enrollment](https://csrc.nist.gov/pubs/sp/800/63/a/4/final) and [NIST SP 800-63C-4: Federation and Assertions](https://csrc.nist.gov/pubs/sp/800/63/c/4/final) — proofing (establishing who someone is before issuing credentials) and federation/single sign-on.
- [CCCS: User Authentication Guidance for IT Systems (ITSP.30.031 V3)](https://www.cyber.gc.ca/en/guidance/user-authentication-guidance-information-technology-systems-itsp30031-v3) — the Canadian technical guidance, with its own authentication levels.

### Multi-factor and phishing-resistant authentication

*Supports: Reflect — effective MFA; Reflect — phishing-resistant methods*

- [CISA: Implementing Phishing-Resistant MFA](https://www.cisa.gov/sites/default/files/publications/fact-sheet-implementing-phishing-resistant-mfa-508c.pdf) — explains why SMS and push MFA can be phished or bypassed and what qualifies as phishing-resistant (FIDO/WebAuthn, PIV). The direct answer to the new phishing-resistant prompt.
- [FIDO Alliance: Passkeys](https://fidoalliance.org/passkeys/) — how passkeys (FIDO2/WebAuthn) provide phishing-resistant, passwordless authentication.
- [CCCS: Secure Your Accounts and Devices with Multi-Factor Authentication (ITSAP.30.030)](https://www.cyber.gc.ca/en/guidance/secure-your-accounts-and-devices-multi-factor-authentication-itsap30030)
- [Microsoft: Authentication Methods in Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/authentication/overview-authentication)
- [Okta: Adaptive MFA](https://www.okta.com/learn/adaptive-mfa/) — risk-based MFA that adjusts friction to context, which is the heart of the "MFA without excessive friction" prompt.

### Passwords and knowledge-based authentication

*Supports: Research — weaknesses of knowledge-based authentication and how to mitigate them*

- [CCCS: Best Practices for Passphrases and Passwords (ITSAP.30.032)](https://www.cyber.gc.ca/en/guidance/best-practices-passphrases-and-passwords-itsap30032)
- [OWASP Authentication Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html) — practical guidance on password storage, length over complexity, checking against breached-password lists, lockout, and MFA.
- [OWASP Credential Stuffing Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Credential_Stuffing_Prevention_Cheat_Sheet.html) — defenses against the reuse of breached credentials, one of the attacks named in Why This Matters.
- NIST SP 800-63B-4 (above) — its memorized-secret rules reflect current thinking (no forced periodic rotation, screen against known-breached passwords).

### Account recovery and lifecycle

*Supports: Investigate — account recovery as the weakest point*

- [OWASP Forgot Password Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Forgot_Password_Cheat_Sheet.html) — how to design a reset/recovery flow that doesn't become the easy way in (avoiding guessable security questions, account enumeration, and weak reset tokens).
- NIST SP 800-63B-4 (above) — also specifies requirements for authenticator recovery and replacement.

### Secure configuration and vendor guidance

- [CCCS: Guidance on Securely Configuring Network Protocols (ITSP.40.062)](https://www.cyber.gc.ca/en/guidance/guidance-securely-configuring-network-protocols-itsp40062)
- [Ping Identity: Authentication Fundamentals](https://www.pingidentity.com/en/resources/identity-fundamentals/authentication.html)
- [Okta: Recommended Best Practices for Authentication (API security)](https://developer.okta.com/books/api-security/authn/best-practices/)
