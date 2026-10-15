# Social Media Profiling

## Description

Social Media Profiling is the OSINT practice of collecting, analyzing, and correlating publicly available information from social media platforms to construct a detailed profile of an individual or organization. Starting from identifiers such as usernames, aliases, or email addresses, investigators map connections, extract metadata, analyze posting habits, and identify location patterns, affiliations, and shared content. This technique is widely used in threat intelligence, penetration testing, and fraud investigations to reveal insights that may not be immediately visible through surface-level observation.

## Why This Matters

Publicly available online information can unintentionally reveal sensitive details, including patterns of life, affiliations, locations, and behaviours, that adversaries can exploit. Threat actors often use social media as a low-effort, high-reward reconnaissance tool to target individuals or organizations. Awareness of how easily data can be aggregated and analyzed helps reduce exposure, prevent social engineering, and strengthen security posture.

## Why This Is Important 

- Understand how publicly available information about people or infrastructure can be exploited for social engineering.
- Reduce impersonation risk targeting executives, faculty, or service departments.
- Protect internal processes, schedules, and organizational details disclosed through posts or metadata.
- Maintain privacy compliance and safeguard employee and departmental digital footprints.
- Identify fraudulent or malicious accounts impersonating university entities.
- Sensitive research affiliations can be mapped through OSINT.
- Public images or metadata may reveal building layouts, equipment, or locations of sensitive or controlled resources.
- Research teams may be targeted for intellectual property theft or influence campaigns.
- Staff can better understand how posts, job titles, or photos reveal exploitable information. 
- Researchers can reduce risks involving data leaks, travel patterns, or sensitive collaborations. 

## What to do if your social media account is hacked
- [Facebook: If you're worried about the security of your account, Facebook can help you.](https://www.facebook.com/hacked)
- [Instagram: If you think your Instagram account has been hacked](https://help.instagram.com/149494825257596)
- [LinkedIn: Reporting a Compromised LinkedIn Account](https://www.linkedin.com/help/linkedin/answer/a1340402/reporting-a-compromised-account?lang=en)
- [Tiktok: My Tiktok account has been hacked](https://www.tiktok.com/support/faq_detail?id=7581821084908067339_)
- [Twitter: Help with my compromised Twitter account](https://help.x.com/en/safety-and-security/x-account-compromised)
- [YouTube: Fix a hacked YouTube account](https://support.google.com/youtube/answer/76187?hl=en)

## Skill Development

1. Explore: How can publicly available social media information identify physical, social, or technical vulnerabilities during an OSINT assessment?
2. Review: What privacy and legal considerations apply before collecting and storing social media data? Which privacy and legal considerations apply to data I have shared?
3. Reflect: How can social media activity patterns identify high-risk behaviours or insider-threat indicators?
4. Explore: What techniques validate and correlate identity across online platforms?
5. Reflect: How can photo metadata, timestamps, and geotags support timeline or geolocation analysis?
6. Reflect: Account information such as display names, photos, and stated locations can be faked, and a profile may be an impersonation, a bot, or a "sock puppet." How would you assess whether an account is authentic, and why does correlation across platforms require caution rather than assumption?
7. Review: How can you reduce your own and your organization's social media exposure (privacy settings, what not to post, separating personal and professional identities), and what does profiling teach defenders about hardening that footprint?

## Learning Resources

> **Ethics and legal note:** Social media profiling concerns real, often identifiable people, so the ethical bar sits well above "it's public, so it's fair game." Investigate only with a legitimate, authorized purpose; collect the minimum necessary; and never use these techniques to stalk, harass, dox, or track a private individual. Misidentification is a real harm — people have been wrongly named and endangered by sloppy crowd-sourced OSINT — so corroborate before asserting that an account belongs to a specific person. Many platforms' terms also restrict automated collection; respect them.

### Background and reference

- [McMaster Library: OSINT and social media profiling](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,Open%20Source%20Intelligence,%20OSINT,%20Social%20Media%20Profiling&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&lang=en&offset=0)
- [Wikipedia: Social media intelligence (SOCMINT)](https://en.wikipedia.org/wiki/Social_media_intelligence) and [Social profiling](https://en.wikipedia.org/wiki/Social_profiling) — background on the discipline and its concepts.
- [NIST SP 800-53: PL-4(1), Social Media and External Site/Application Usage Restrictions](https://csf.tools/reference/nist-sp-800-53/r5/pl/pl-4/pl-4-1/) — the control-framework view of setting rules for staff social media use.
- [SEON: What Is Social Media Profiling?](https://seon.io/resources/dictionary/social-media-profiling/) — an applied overview oriented to fraud prevention.
  
### Identity correlation across platforms

*Supports: Explore — validating and correlating identity across platforms*

- [Sherlock](https://github.com/sherlock-project/sherlock) — an open-source tool that checks whether a given username exists across hundreds of sites; a fast first pass for finding where a handle appears. People reuse handles, which is what makes this work — and also why a match is a lead to verify, not proof of the same person.
- [Maigret](https://github.com/soxoj/maigret) — a more thorough fork of Sherlock that builds a dossier from a username across thousands of sites and can follow links recursively. Powerful, and a good illustration of why the correlation-caution skill item matters: automated matches include false positives.
- [WhatsMyName](https://whatsmyname.app/) — a community-maintained web tool for username enumeration, useful when you want a browser-based check rather than a command-line tool.

### Verifying accounts and spotting fakes

*Supports: Explore — identity validation; Reflect — authenticity and impersonation*

- [Verification Handbook for Disinformation and Media Manipulation: Investigating Social Media Accounts](https://datajournalism.com/read/handbook/verification-3) — the standard guide to assessing whether an account is genuine: account age, network, posting patterns, and cross-checks. Includes case studies of exposing coordinated fake pages.
- [First Draft / UBC: Verification fundamentals for social media accounts](https://blogs.ubc.ca/decodingsocialmedia2015/files/2015/01/UBCVerification.pdf) — a concise checklist (when the account was created, who it connects to, what it posts, confirming off-platform) for evaluating an account and person.

### Photo metadata, timestamps, and location

*Supports: Reflect — metadata, timestamps, and geotags for timeline/geolocation*

### Privacy, self-defense, and reducing exposure

*Supports: Review — privacy and legal considerations; Review — hardening your own footprint*

- [EFF: Surveillance Self-Defense](https://ssd.eff.org/) — practical guides to locking down accounts and limiting what you expose, directly supporting the self-defense skill item.
- [Privacy Guides](https://www.privacyguides.org/) — community-maintained, vendor-neutral recommendations for privacy-respecting tools and settings.
- [Canadian Centre for Cyber Security: Security Considerations When Using Social Media in Your Organization (ITSM.10.066)](https://www.cyber.gc.ca/en/guidance/security-considerations-when-using-social-media-your-organization-itsm10066) — organizational guidance on social media risk, aimed at the operational-security framing of this page.
- [Office of the Privacy Commissioner of Canada: PIPEDA in brief](https://www.priv.gc.ca/en/privacy-topics/privacy-laws-in-canada/the-personal-information-protection-and-electronic-documents-act-pipeda/pipeda_brief/) — a plain-language overview of how Canadian privacy law treats personal information, relevant to the "what can I lawfully collect and store" question.

### Ethics and professional standards

*Supports: Review — legal and ethical considerations; Reflect — authenticity and harm*

- [Berkeley Protocol on Digital Open Source Investigations](https://humanrights.berkeley.edu/programs/investigations/berkeley-protocol) — the UC Berkeley / UN OHCHR standard for conducting online investigations lawfully and ethically, including minimizing harm and the duty to verify before attributing. The reference point for responsible profiling.
