# Email Investigation

## Description:

Email Investigation in OSINT involves gathering and analyzing information related to an email address to uncover details about its origin, usage patterns, and associated identities. Techniques include examining email headers to trace the path and source, searching for publicly available instances of the email address across social media, forums, or data leaks, and identifying behavioral or technical patterns that may provide clues about the user or organization behind it. This analysis aids in verifying legitimacy, detecting phishing attempts, or gathering intelligence.

## Why this matters:

Email investigation matters because email is a primary vector for cyberattacks, including phishing, business email compromise, and identity spoofing. Analyzing emails helps security teams trace the source, verify legitimacy, detect fraud, and uncover connections that may indicate broader threats. Without proper email investigation, malicious actors can exploit communication channels to gain unauthorized access, steal sensitive information, or manipulate individuals and systems. Organizations rely heavily on email for administrative communication, services, coordination, and external collaborations. Email investigation helps operational teams:

- Extract and analyze information from email headers to trace the origin and path of messages. Understanding the source of an email helps identify potentially malicious actors or misconfigured systems.
- Detect patterns in email addresses to identify related accounts or impersonation attempts. Recognizing anomalies or duplicates can prevent unauthorized access and social engineering attacks.
- Locate publicly available references to university emails across forums, leaks, or social media. This helps operational teams mitigate exposure of institutional addresses and prevent potential exploitation.
- Without effective email investigation, an organization's email recipients are at higher risk of phishing attacks, fraud, or misuse of institutional communication channels.
- Verifying the legitimacy of communications before sharing sensitive datasets or findings.
- Detecting attempts to impersonate staff (e.g. executives) or steal intellectual property through targeted email attacks.
- Analyzing metadata to uncover suspicious or fraudulent patterns in collaborative communication.
- Staff can identify and report suspicious emails, ensuring administrative workflows remain secure while helping automated detection tools improve their detection data sets.

## Skill Development

- Investigate: What information can be extracted from an email header, and how does it assist in tracing the email’s origin?
- Investigate: How can patterns in email addresses help identify related accounts or potential impersonation?
- Review: What methods are effective for finding publicly available references to an email address online?
- Reflect: How does analyzing email metadata contribute to detecting phishing or fraudulent activity?
- Investigate/Reflect: What privacy and ethical considerations must be kept in mind during email investigations?
- Investigate: How do SPF, DKIM, and DMARC work, and how do their results in the Authentication-Results header help confirm whether a sender's domain was spoofed? Can you view an organization's records, and if so, what do they tell you about their infrastructure?
- Reflect: Why can information in an email header (such as the From address or display name) be forged, and what parts of the header are harder for a sender to fake? What does this mean for how much weight you place on any single field?
- Reflect: How secure is plaintext email? What is needed for an email to be considered "secure"? How should important attachments like datasets be sent?

## Learning Resources

> **Ethics and scope note:** Investigate only addresses you have a legitimate reason to examine. Some "email OSINT" tools detect accounts by triggering password-reset or sign-up flows on third-party sites, which contacts those services on the account holder's behalf and can notify them; treat these as active techniques with legal and privacy weight, not neutral lookups. Breach-exposure results reveal sensitive personal information and should be handled accordingly. 

### Reading and tracing email headers

*Supports: Investigate — what a header reveals and how it traces origin; Reflect — what can be forged*

- [Google Admin Toolbox Messageheader](https://toolbox.googleapps.com/apps/messageheader/) — paste a raw header and get a readable timeline of the servers (`Received` hops) a message passed through, plus SPF/DKIM/DMARC results.
- [MXToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx) — parses `Received` hops and authentication results; a widely used free analyzer.
- [How to view the original/full headers in Gmail (Show Original)](https://support.google.com/mail/answer/29436) — how to retrieve the raw message, the first step before any header analysis. Most mail clients have an equivalent "view source" or "show original" option.
- [RFC 5322: Internet Message Format](https://www.rfc-editor.org/rfc/rfc5322) — the standard that defines header fields such as `From`, `To`, `Date`, and `Message-ID`. A useful reference point for understanding which fields are author-supplied (and so easy to forge) versus added in transit.

### Email authentication (SPF, DKIM, DMARC)

*Supports: Investigate — how authentication results confirm or contradict a sender; Reflect — detecting spoofing*

- [Cloudflare Learning: What are DMARC, DKIM, and SPF?](https://www.cloudflare.com/learning/email-security/dmarc-dkim-spf/) — a clear, vendor-neutral overview of how the three protocols work together.
- [RFC 7489: DMARC](https://www.rfc-editor.org/rfc/rfc7489) — the specification, including how DMARC aligns the visible `From` domain with the domains validated by SPF or DKIM. Alignment is the key concept: a message can pass SPF yet still be spoofed in the `From` field that the recipient sees.
- [RFC 7208: Sender Policy Framework (SPF)](https://www.rfc-editor.org/rfc/rfc7208) and [RFC 6376: DomainKeys Identified Mail (DKIM)](https://www.rfc-editor.org/rfc/rfc6376) — the underlying standards, for deeper reference.

### Phishing, spoofing, and fraud

*Supports: Reflect — how metadata helps detect phishing or fraud*

- [CISA: Recognize and Report Phishing](https://www.cisa.gov/secure-our-world/recognize-and-report-phishing) — plain-language indicators of phishing, including sender-address and domain mismatches.
- [CISA/NSA/FBI/MS-ISAC: Phishing Guidance – Stopping the Attack Cycle at Phase One](https://www.cisa.gov/news-events/news/cisa-nsa-fbi-ms-isac-publish-guide-preventing-phishing-intrusions) — a deeper joint guide covering credential-harvesting and malware phishing techniques and mitigations.
- [MITRE ATT&CK: Phishing for Information (T1598)](https://attack.mitre.org/techniques/T1598/) — how adversaries use email to elicit information, including spoofed sender identities, which is the behavior header analysis helps detect.

### Finding public references and exposure

*Supports: Review — finding public references to an address online*

- [Have I Been Pwned](https://haveibeenpwned.com/) — checks whether an address appears in known data breaches and which data was exposed. It returns breach metadata, not leaked passwords. Pair with the discussion of how breach data creates risk.
- [Epieos](https://epieos.com/) — a reverse-email OSINT tool that checks an address against Google services and many consumer platforms using passive recognition. A good example for the "finding public references" question, and for the ethics discussion, since results can surface a person's name, photo, and linked accounts.

> **On account-enumeration tools:** Tools such as holehe and Maigret detect where an address is registered by exercising sites' password-reset or sign-up flows. Industry has deliberately closed many of these flows, so coverage is shrinking, and because they contact third-party services, they belong under the active-technique caution in the scope note above. Discuss them as a concept rather than running them against addresses you are not authorized to investigate.

### Privacy and ethics

*Supports: Investigate/Reflect — privacy and ethical considerations*

- [Berkeley Protocol on Digital Open Source Investigations](https://humanrights.berkeley.edu/programs/investigations/berkeley-protocol) — professional standards for conducting online investigations lawfully and ethically, including minimizing harm to the people being investigated.
- [Office of the Privacy Commissioner of Canada: PIPEDA in brief](https://www.priv.gc.ca/en/privacy-topics/privacy-laws-in-canada/the-personal-information-protection-and-electronic-documents-act-pipeda/pipeda_brief/) — an accessible overview of how Canadian privacy law treats personal information, useful framing for why an email address and its associated data are sensitive.
