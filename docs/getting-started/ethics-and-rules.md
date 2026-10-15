# CTF Ethics, Rules, and Best Practices

> **Last reviewed:** October 2026 · **Questions or corrections: apd1280 at mcmaster dot ca.

CTF activities should be performed safely, respectfully, and only within authorised environments and systems. Follow the competition rules, institutional policies, applicable laws, and instructions from event organisers.

This document starts with the principles behind our rules, then sets out the rules themselves. The principles matter most when something happens that no rule anticipated.

**Where this applies:** CTF competitions, practice platforms, team training, and your own lab. Where an event's published rules are stricter than these, follow the event's rules. For the technical side of staying safe, see the [Lab Setup](lab-setup.md) guide.

## Principles

**Capability isn't permission.**
Security skills can protect or harm. What separates a security practitioner from an attacker isn't skill or tools; it's consent and intent.

**Respect people and their consent.**
Authorisation is consent: a system's owner decides what happens to it. The same applies to information about people. Being able to find information doesn't mean the person agreed to have it collected, combined, or shared.

**Avoid harm, and keep it proportionate.**
Even within scope, cause no more disruption than you need to learn or solve the challenge. Consider everyone affected, not only the target: other teams, shared infrastructure, and the people who run the event.

**Be honest.**
Be truthful about what you did, including mistakes and what you don't know. Don't misrepresent your skills, your results, or who did the work.

**Be accountable.**
You're responsible for everything done on your behalf, including by scripts, automated tools, and AI agents. "The tool did it" isn't an excuse. Help create a positive and supportive culture of accountability: us versus the problem. Blame and shame are antitherial to accountability: pointing fingers to punish stops true responsibility and growth from happening.

**Treat the law as the minimum.**
Something can be legal and still cause harm. When rules, law, and ethics seem to point in different directions, stop and seek advice rather than acting alone.

**Work within your competence.**
Don't do things you don't understand where mistakes could affect others. Knowing when to ask for help is part of being competent.

**Be fair and inclusive.**
People start with different hardware, time, and backgrounds. Welcome newcomers, share what you know, and don't gatekeep. Diverse teams notice more, which makes everyone more secure, and every new learner is a leadership opportunity for those slightly ahead on a shared pathway.

**Protect the community's trust.**
Your behaviour reflects on your team, your friends, your institution, and the field.

**Look after yourself and others.**
Good behaviour includes how you treat people under pressure: tired teammates, newcomers asking basic questions, and yourself.

## When the Rules Aren't Clear

Before acting in an unclear situation, here are some questions to ask:

1. Do I have clear permission from the owner for this specific action, right now?
2. Who could be harmed, including people who aren't the target?
3. Can this be undone if I'm wrong?
4. Would I be comfortable explaining exactly what I did to the system's owner, the organisers, and my instructor?

If the answer to any of these is "no" or "I'm not sure," stop and ask.

## Core Rules

Core rules for a competition typically include:

- Follow the event's published rules.
- Interact only with systems explicitly included in the competition scope.
- Stop and ask for guidance when the scope is unclear or something unsafe occurs.
- Respect other participants, organisers, and support staff.
- Protect personal, institutional, and competition information.
- Avoid disrupting the competition platform or other teams.
- Report accidental out-of-scope access to an organiser immediately.
- Be honest about mistakes, and report them rather than hiding them.

## Authorisation and Scope

**What's in scope.** Only the hosts, addresses, ports, and challenges that an event lists as targets. Unless the rules explicitly say otherwise, these are always out of scope:

- The scoreboard and competition platform
- VPN servers and other event infrastructure
- Organisers', sponsors', and support staff's systems and accounts
- Other teams and participants

**Reachable isn't authorised.** A system you can reach through the competition VPN, or from inside a challenge, isn't in scope unless it's listed.

**Permission ends with the event.** Stop all tools, scans, scripts, and listeners when the competition ends. Event infrastructure, especially in the cloud, is often reassigned to unrelated organisations soon afterwards, so the same address may belong to someone else tomorrow.

**Event formats differ.** In attack-defence competitions, attacking other teams' services may be part of the game, within limits the rules define. Read the rules for each event; don't assume.

**Outside competitions, you need explicit, written permission.** Testing your school's website, your employer's network, a friend's device, or any public service without the owner's written authorisation is not acceptable, even "just to see," and even if nothing is damaged. Permission from someone who doesn't own the system isn't authorisation. Learning how to make a secure home lab is a foundational skill.

**The law applies to learners.** Unauthorised access, interference with computer systems, and interception of communications are offences in most countries, and some laws apply even when nothing is damaged. You're responsible for knowing the laws where you are.

## Keep CTF Activity Separate from Work and School Systems

Do not use institutional systems, credentials, or licensed software for competition activity unless their use has been explicitly approved.

In particular:

- Do not use campus or workplace computers unless they're designated for CTF use, such as an approved lab.
- Do not use campus or workplace networks for competition activity unless the network's acceptable-use policy permits it or you have explicit approval. If campus housing is your only connection, ask your IT department before competing.
- Do not reuse campus or workplace credentials, including your login for network access (WiFi) within learning environments. If you feel yourself typing a work or campus credential during the competition, stop and reflect.
- Do not use institution-licensed software for CTFs unless its licence allows it.
- Do not expose institutional browser sessions, tokens, or cookies to CTF tools, and do not log in to institutional systems from your CTF environment. If you don't fully undertstand the risk of session/cookie theft and how easily it happens, take extra care to observe this practice.
- Do not connect a CTF environment to a corporate or school VPN. Take care in selecting VPNs, they vary in architecture, privacy, know-your-customer, and jusidiction. 
- Do not treat competition chat as a safe place to discuss work or sensitive information. Focus your chat on team building, competition, and friendly memes :)
- If a CTF is part of a course, follow the course's academic integrity and collaboration rules as well as the event's rules foremost: defer to your instructor and institution for acceptable behaviour.

Use the [Lab Setup](lab-setup.md) guide to prepare an isolated environment.

## Protect Personal and Institutional Privacy

Do not sign in to personal, financial, social-media, work, or institutional accounts from a CTF competition system.

Examples include:

- Personal or work email
- Social media
- Banking
- Cloud storage
- Campus systems
- Password managers

This reduces the risk that malicious challenge files or untrusted tools could access session cookies, tokens, saved passwords, or personal data.

Use your password manager on your host computer, never inside your CTF environment, and keep your CTF accounts separate from your personal ones. See [Protect Your Accounts and Secrets](lab-setup.md#protect-your-accounts-and-secrets).

## Real People, OSINT, and Social Engineering

Some challenges involve real people or real organisations. We do not endorse these, or any events. Should you elect to participate in one, treat their information with the care you'd want for your own.

- Collect only what a challenge requires. Don't keep, combine, or share personal information beyond that.
- Understand applicable privacy laws and regulations. Follow all collection guidelines and standards the event notes.
- Never publish personal information about anyone (doxxing), during or after an event.
- Don't contact real people you identify through OSINT.
- Don't phish, pretext, impersonate, or otherwise socially engineer real people unless the challenge explicitly includes it and names the targets. This includes trying to talk organisers or support staff into hints or access.
- Physical intrusion is out of scope unless that is the explicit goal of the event (e.g. lockpicking challenge)
- If a challenge seems to expose real personal information, stop and report it (see [Reporting Problems](#reporting-problems)).

## Tool Safety

Before using a tool:

- Understand its basic function.
- Read the documentation.
- Confirm its target, and that you have permission to interact with that target.
- Review the command before running it.
- Use the narrowest practical scope, and avoid broad network ranges.
- Set rate limits on brute-force, fuzzing, and scanning tools.
- Avoid options that could cause denial of service.
- Ask for help when uncertain.

Also:

- **Practise new tools in your own lab first**, especially tools that send network traffic. A live competition is not the place to learn what a tool does.
- **Denial of service is prohibited** unless a challenge explicitly requires it.
- **Don't run automated tools against the scoreboard or platform**, including scripts that brute-force flag submissions.
- **Don't use wireless attack tools** against networks you don't own or have written permission to test.
- **Automation and AI agents act on your behalf.** Keep them within scope, monitor what they run, and stop them when you stop.
- **Install tools from trusted sources only.** See [Install CTF Tools Safely](lab-setup.md#install-ctf-tools-safely).

## Handling Suspicious Files

Some CTF challenges include untrusted or intentionally malicious files.

When handling them:

- Use an isolated virtual machine or system that has been properly set up.
- Don't open challenge files on your host system.
- Don't copy content between your host and the virtual machine through a shared clipboard.
- Don't upload challenge files or confidential data to public services, such as malware-scanning websites, paste sites, or AI chatbots, unless the event's rules allow it and the files contain nothing sensitive. Uploads may be shared with other users of the service.
- Take a snapshot before analysis.
- Revert or rebuild the environment after analysis.
- Don't share malicious samples outside the challenge, or reuse them elsewhere.

See [Handle Challenge Files Safely](lab-setup.md#handle-challenge-files-safely) for practical steps.

## Data and Credentials You Encounter

- Never use credentials found during a CTF anywhere outside the challenge they belong to.
- If you come across what looks like real credentials or personal data, don't use or keep it. Report it.
- Delete challenge data, VPN configurations, and competition credentials when the event is over, unless the rules ask you to keep them.

## Fair Play and Integrity

- Don't share flags, solutions, or hints with other teams during an event.
- Don't collude with other teams, or use multiple, shared, or borrowed accounts.
- Follow the event's rules on AI assistance. Some events restrict it.
- Don't publish write-ups, solutions, or challenge files until the event allows it.
- In write-ups, leave out VPN configurations, credentials, and any real personal data, and credit teammates and others whose work helped you.
- If you stream or screen-share, check that the event allows it, and hide VPN configurations, tokens, flags, and personal information.

## Conduct and Community

Treat everyone with respect, online and in person: participants, organisers, volunteers, and support staff.

The following are not acceptable:

- Harassment, intimidation, or threats
- Discrimination or hateful content
- Unwelcome sexual attention or content
- Doxxing or sharing others' private information
- Disrupting other people's participation

Follow each event's code of conduct as well.

**Younger participants.** Some international events may include participants under 18. Follow the organisers' safeguarding policy, keep communication with younger participants in public, moderated channels, and report concerns to the organisers.

**Welcome newcomers.** Answer basic questions patiently. Everyone started somewhere.

## If Something Goes Wrong

If you think you've accessed something out of scope, affected a system you didn't intend to, or exposed credentials:

1. **Stop.** Stop your tools and disconnect from the network.
2. **Don't explore further**, and don't try to "clean up" on the affected system. Changes there can destroy information organisers need.
3. **Write down what happened:** what you ran, against what, and when.
4. **Report it** to an organiser or your team lead (see [How to Report](#how-to-report)).
5. **Rotate any exposed credentials.**

The lab guide's [When Something Goes Wrong](lab-setup.md#when-something-goes-wrong) section has the technical steps.

## Reporting Problems

Contact an organiser or team lead when:

- The scope is unclear.
- A target appears to belong to an unrelated organisation.
- A challenge exposes real personal information.
- You discover a vulnerability in the competition platform.
- You accidentally access an unauthorised system.
- A tool creates unexpected traffic.
- Another participant appears to be violating the rules.
- You believe credentials or sensitive information have been exposed.
- You experience or witness harassment or other conduct problems.
- You find challenge content that is distressing or inappropriate.

### How to Report

Before competing, build a list of quick report **contacts:** Event organisers, *team lead or instructor, conduct concerns
- **Report privately**, not in public channels.
- **Include** what happened, when, which systems or people were involved, and what you've done since.
- **If no one is available**, for example overnight, stop the activity and wait. Don't continue while you wait for an answer.

Do not publicly disclose the issue before organizers have had an opportunity to investigate, and if you accidentally use a work computer or network, know how to contact your security operations team for responsible and prompt disclosure.

## Vulnerabilities Outside the Competition

Sometimes a challenge, an OSINT task, or ordinary browsing leads to a real vulnerability in a system that isn't part of any competition.

- Stop. Don't explore further, download data, or keep any access.
- Never use or share what you found.
- Report it privately to the owner through their published vulnerability disclosure process, which is often linked from a `security.txt` file or a "report a vulnerability" page. If you're not sure how, ask your instructor, event organizer, or mentor for help.
- Never demand payment or anything else in exchange for details.
- Don't disclose publicly until the owner has fixed the issue or agreed to disclosure.

## Wellbeing

Competitions can be long and intense. Take breaks, eat, and sleep. It's always acceptable to step away from distressing content and let your team or the organisers know. See [Wellbeing and Community](lab-setup.md#wellbeing-and-community).

## Further Reading

These principles reflect values shared across the security profession:

- [ACM Code of Ethics and Professional Conduct](https://www.acm.org/code-of-ethics)
- [ISC2 Code of Ethics](https://www.isc2.org/ethics)
- [The Menlo Report: Ethical Principles Guiding Information and Communication Technology Research](https://www.caida.org/publications/papers/2012/menlo_report/menlo_report.pdf)

## Final Principle

When in doubt, stop and ask. CTFs are for learning, and safety is everyone's responsibility.
