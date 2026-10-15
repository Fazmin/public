# Metadata Analysis

## Description

Metadata Analysis in OSINT involves extracting and examining hidden data embedded within files such as documents, images, or videos to uncover contextual information that is not immediately visible. This can include details like creation and modification dates, authorship, device information, software used, and sometimes location data. Utilizing tools like ExifTool or similar utilities, analysts can leverage metadata to track digital footprints, verify file authenticity, or gather additional clues relevant to investigations, and penetration testing.

## Why This Matters

Metadata analysis matters because files often contain hidden information that can reveal details about their origin, history, and context. Documents, images, and videos may include creation and modification dates, authorship, device information, software used, and sometimes geolocation. By extracting and analyzing metadata, investigators and security professionals can track digital footprints, verify authenticity, detect tampering, and uncover information that may not be apparent from the visible content alone. We handle a vast amount of digital content, including administrative documents, internal communications, and public-facing media. Metadata analysis helps operational teams:

- Identify the origin and authenticity of critical documents ensuring that official communications and records are reliable.
- Detect unintentional disclosures of sensitive information embedded in file metadata shared externally.
- Support incident investigations and auditing processes by providing insights into document creation, modification, and access.
- Maintain compliance with privacy policies and information security regulations by recognizing and mitigating metadata-related exposure risks

Without metadata awareness, it's possible to expose sensitive information or misinterpret the source and context of digital files, impacting trust and security. Metadata helps verifying the authenticity and version history of datasets or publications to prevent errors or fraudulent claims. It can be used to tracking authorship, software, and device details for proper attribution in collaborative research projects, supporting the reproducibility and traceability of research outputs through accurate metadata records. By integrating metadata analysis, research teams safeguard the validity and credibility of their work while protecting sensitive information.

## Skill Development
- Explore: What types of metadata are commonly found in digital files, and how can they aid in understanding the origin and history of the file?
- Explore: How can metadata analysis contribute to verifying the integrity and authenticity of a file during an investigation?
- Reflect: What risks or privacy concerns can arise from metadata exposure in publicly shared documents or images?
- Explore: How do different file formats affect the availability and type of metadata that can be extracted?
- Reflect: What are the best practices for using metadata tools like ExifTool to ensure comprehensive and accurate data extraction?

## Learning Resources

### Books and further reading

- [McMaster Library](https://mcmaster.primo.exlibrisgroup.com/discovery/search?query=any,contains,osint,%20Metadata%20Analysis&tab=OCULDiscoveryNetwork&search_scope=OCULDiscoveryNetwork&vid=01OCUL_MU:OMNI&lang=en&offset=0)
- [O'Reilly](https://www.oreilly.com/search/?q=Metadata%20Analysis&type=book&type=shortcut&type=radar&type=shortcut&type=article-other&rows=100&topics=Metadata)

### Background and overviews

- [Wikipedia: Metadata](https://en.wikipedia.org/wiki/Metadata)
- [NIST Glossary: Metadata](https://csrc.nist.gov/glossary/term/metadata)
- [Fidelis Security: Metadata Analysis – Process, Techniques, and Best Practices](https://fidelissecurity.com/cybersecurity-101/network-security/metadata-analysis/)
- [Cyberpedia by ReasonLabs: What is Metadata Analysis?](https://cyberpedia.reasonlabs.com/EN/metadata%20analysis.html)

### Types of metadata and file formats

*Supports: Explore — common types of metadata; Explore — how file formats affect available metadata*

- [ExifTool Tag Names](https://exiftool.org/TagNames/) — the most complete reference of metadata tags, organized by format. Comparing the tables for images, PDFs, and video shows how much the file format determines what metadata exists.
- [IPTC Photo Metadata Standard](https://iptc.org/standards/photo-metadata/iptc-standard/) — the most widely used standard for descriptive photo metadata (captions, creators, rights). It leaves technical metadata to other standards such as Exif, illustrating how a single image can carry several overlapping metadata layers.

### Verifying integrity and authenticity

*Supports: Explore — verifying integrity and authenticity; Explore — corroborating metadata that may be stripped or altered*

- [SWGDE Best Practices for Image Authentication (18-I-001-2.0)](https://www.swgde.org/documents/published-complete-listing/18-i-001-best-practices-for-image-authentication/) — forensic methodology, possible results, and limitations of image authentication, including how authentication differs from demonstrating integrity.
- [NIST SP 800-86: Guide to Integrating Forensic Techniques into Incident Response](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-86.pdf) — covers data file integrity and file creation, modification, and access times from an IT (rather than law-enforcement) perspective. Published in 2006, but the fundamentals still apply.
- [C2PA (Coalition for Content Provenance and Authenticity)](https://c2pa.org/) — the open standard behind Content Credentials: cryptographically signed provenance metadata recording how a file was created and edited, including by AI tools.

### Privacy risks and safe sharing

*Supports: Reflect — privacy risks of metadata exposure; Reflect — reviewing and removing metadata before external sharing*

- [Canadian Centre for Cyber Security: Digital Footprint (ITSAP.00.133)](https://www.cyber.gc.ca/en/guidance/digital-footprint-itsap00133)
- [Outpost24: How to Analyze Metadata and Hide It from Hackers](https://outpost24.com/blog/metadata-hackers-best-friend/)
- [Microsoft Support: Remove Hidden Data and Personal Information by Inspecting Documents](https://support.microsoft.com/en-us/office/remove-hidden-data-and-personal-information-by-inspecting-documents-presentations-or-workbooks-356b7b5d-77af-44fe-a07f-9aa4d085966f) — how to use Document Inspector in Word, Excel, and PowerPoint, and an inventory of the hidden data Office files can contain. Inspect a copy, since removed data can't always be restored.
- [MAT2 (Metadata Anonymisation Toolkit)](https://0xacab.org/jvoisin/mat2) — open-source metadata cleaner for images, PDFs, office, and audio files. Its documentation notes that an empty result doesn't prove a file is clean, and that it removes metadata only, not watermarks or content.
- [Citizen Evidence Lab: Sending Encrypted Photos While Preserving Metadata](https://citizenevidence.org/2020/04/20/sending-encrypted-photos-while-preserving-metadata/) — how messaging apps strip metadata and compress images, why EXIF data can be edited, and how sharing full metadata can put people at risk.

### Using ExifTool well

*Supports: Reflect — best practices for ExifTool*

- [ExifTool FAQ](https://exiftool.org/faq.html) — by default ExifTool prints descriptions rather than tag names; FAQ #3 explains how to show tag names and the group each tag belongs to, which is essential for accurate extraction.

> **Good learning practice:** Use local tools rather than online metadata viewers for sensitive/personal files, since online tools and viewers require uploading the file to a server that you do not control. Work from the original file rather than a copy downloaded from social media, and save the full metadata output rather than only the fields that look relevant.

### Connecting to other OSINT techniques

- [FOCA (Fingerprinting Organizations with Collected Archives)](https://github.com/ElevenPaths/FOCA) — finds an organization's published documents through Google, Bing, and DuckDuckGo, then extracts their metadata, linking metadata analysis with search engine exploitation. Runs on Windows and requires SQL Server.

