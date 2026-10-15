# Code and Script Analysis

## Description:

Code and Script Analysis in OSINT involves examining publicly available source code repositories, scripts, and commit histories to uncover sensitive information such as exposed API keys, credentials, comments revealing internal processes, or hidden clues. By systematically searching through code files, version control logs, and comments, analysts can identify potential security weaknesses or gather intelligence that may not be documented elsewhere. Efficient techniques and tools help streamline this process for effective data extraction.

## Why This Matters:

Code and script analysis matters because publicly available source code can unintentionally expose sensitive information such as API keys, credentials, or internal logic. Attackers and threat actors often search repositories and scripts to identify weaknesses, gain unauthorized access, or uncover intelligence about systems. By examining code systematically, organizations and analysts can identify these risks early and protect critical assets. An increasing number of automated systems are available to scan code and flag risks, with some operating while a developer types (e.g. Visual Studio Code plugins), and others scanning repositories.

## Why This Is Important for Operations

Organizations rely on various internally developed or publicly shared scripts and code for administrative tools, web services, and research applications. Code and script analysis helps operational teams:

- Preventing unauthorized access to sensitive datasets, experimental results, or proprietary algorithms.
- Detecting vulnerabilities in automation tools or computational workflows.
- Safeguarding intellectual property from external exploitation.
- Ensuring reproducibility and reliability of computational research outputs.
- Reduce risks associated with intellectual property theft, inadvertent leaks, or manipulation of experimental systems.
- Identify accidentally exposed credentials, tokens, or keys that could compromise systems. Accidental leaks in public code repositories can allow attackers to access administrative tools, databases, or cloud resources, and regular analysis helps prevent these breaches.
- Detect insecure coding practices or misconfigurations that could impact IT infrastructure. Mismanaged scripts or code can introduce vulnerabilities in internal applications or automation processes, and reviewing code ensures operational tools remain secure.
- Maintain compliance with IT security policies and data protection regulations. Ensuring that code does not expose sensitive information helps the organization remain compliant with privacy standards and cybersecurity policies.

Without ongoing code and script analysis, public or internal codebases could create hidden security gaps, leaving systems and data vulnerable.

## Skill Development:

- Research: What techniques can be used to identify sensitive information accidentally exposed in source code repositories?
- Research: What is OWASP, and can you identify a service that it applies to? How does ITSAP/NIST support OWASP?
- How does analyzing commit histories provide insights beyond what is visible in the current codebase?
- What role do code comments and documentation play in OSINT investigations?
- How can automated tools aid in scanning large codebases for secrets or vulnerabilities?
- What are the security implications of publicly exposed credentials or keys found in code repositories?

## Learning Resources:

## Learning Resources

> **Ethics note:** Credentials found in someone else's code must never be used or tested; doing so is unauthorized access. Report them to the repository owner or the affected service provider instead. Some scanners can "verify" a secret by attempting to log in to the service with it, so only enable verification on code you own or are explicitly authorized to assess.

### Finding exposed information in repositories

*Supports: Research — techniques for identifying exposed sensitive information; code comments and documentation*

- [GitHub Docs: Understanding GitHub Code Search Syntax](https://docs.github.com/en/search-github/github-code-search/understanding-github-code-search-syntax) — qualifiers such as `org:`, `repo:`, `path:`, and `language:`, plus Boolean operators and regular expressions. Note that code search only indexes a repository's default branch, so it won't find secrets that exist only in older commits.
- [MITRE ATT&CK: Search Open Websites/Domains – Code Repositories (T1593.003)](https://attack.mitre.org/techniques/T1593/003/) — the adversary's view, including real-world groups that searched public repositories for exposed credentials. Its mitigation advice stresses removing leaked credentials from the commit history, not just the latest version of the code.

### Commit histories

*Supports: how commit histories reveal more than the current codebase*

- [Pro Git: Viewing the Commit History](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History) — how to read `git log`, including viewing the changes made in each commit.
- [Git Documentation: git log](https://git-scm.com/docs/git-log) — reference for options such as `-p` (show each commit's changes) and `-S` (find commits that added or removed a specific string).
- [GitHub Docs: Removing Sensitive Data from a Repository](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository) — why deleting a file in a new commit isn't enough, and how history is rewritten with git-filter-repo. GitHub notes that rotating the affected credentials is the primary fix.

### Automated scanning tools

*Supports: how automated tools aid in scanning large codebases*

- [GitHub Docs: Introduction to Secret Scanning](https://docs.github.com/en/code-security/secret-scanning/introduction) — how GitHub scans public repositories for known secret types, blocks pushes containing secrets (push protection), and alerts partner service providers directly when their credentials leak.
- [Gitleaks](https://github.com/gitleaks/gitleaks) — fast, open-source, pattern-based scanner for repositories (including full history), directories, and files; commonly used as a pre-commit hook.
- [TruffleHog](https://github.com/trufflesecurity/trufflehog) — open-source scanner with hundreds of credential detectors that also covers sources beyond Git, such as cloud storage and container images. Its verification feature tests whether a secret is live by authenticating against the service (see the ethics note above).
- [GitGuardian for Visual Studio Code](https://docs.gitguardian.com/ggshield-docs/integrations/ide-integrations/vscode) — editor extension that flags secrets as you write code; requires a GitGuardian account.
- [SonarQube for IDE: Detect Secrets in the IDE](https://www.sonarsource.com/learn/detect-secrets-in-the-ide-with-sonarlint) — step-by-step guide to secrets detection in VS Code and other editors with SonarQube for IDE (formerly SonarLint).

### OWASP, NIST, and Canadian guidance

*Supports: Research — what OWASP is, a service it applies to, and how ITSAP/NIST support OWASP*

- [OWASP: About the OWASP Foundation](https://owasp.org/about/) — who OWASP is and how its open, community-driven projects work.
- [OWASP Top 10:2025](https://owasp.org/Top10/2025/) — the standard awareness document on the most critical web application security risks. The 2025 edition added Software Supply Chain Failures and Mishandling of Exceptional Conditions.
- [OWASP Secrets Management Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html) — best practices for storing, rotating, and controlling access to secrets so they stay out of code.
- [OWASP Code Review Guide](https://owasp.org/www-project-code-review-guide/) — how to conduct secure code reviews as part of the software development life cycle.
- [NIST SP 800-218: Secure Software Development Framework (SSDF)](https://csrc.nist.gov/Projects/SSDF) — a set of secure development practices drawn from sources including OWASP; each practice maps to references in OWASP and other frameworks.
- [Canadian Centre for Cyber Security: Joint Guidance on Software Security Code of Practice](https://www.cyber.gc.ca/en/news-events/joint-guidance-software-security-code-practice) — 14 principles for secure software development and maintenance, released with the UK's National Cyber Security Centre.
- [CyberSecure Canada: Certification Tools](https://ised-isde.canada.ca/site/cybersecure-canada/en/node/17) — Government of Canada templates and how-to guides, including a guide to securing websites using OWASP.

### Security implications of exposed credentials

*Supports: security implications of publicly exposed credentials or keys*

- [Meli, McNiece & Reaves (NDSS 2019): How Bad Can It Git? Characterizing Secret Leakage in Public GitHub Repositories](https://ndss-symposium.org/ndss-paper/how-bad-can-it-git-characterizing-secret-leakage-in-public-github-repositories) — the first large-scale study of secret leakage on GitHub, finding leaks in over 100,000 repositories and thousands of new secrets leaked every day.
- [The Hacker News: The State of Secrets Sprawl 2026](https://thehackernews.com/2026/03/the-state-of-secrets-sprawl-2026-9.html) — summary of GitGuardian's annual vendor report: about 29 million new hardcoded secrets appeared on public GitHub in 2025 (up 34%), and most secrets confirmed valid in 2022 were still exploitable four years later.
