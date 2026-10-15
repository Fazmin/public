# What Is a CTF?

> **Last reviewed:** October 2026 · **Questions or corrections:** apd1280 at mcmaster dot ca.

Capture the Flag (CTF) competitions are cybersecurity events where participants solve technical challenges to find hidden strings called **flags**. Challenges cover areas such as web security, cryptography, digital forensics, reverse engineering, and open-source intelligence (OSINT). CTFs give you permission to practise attack and defence techniques on systems built for that purpose. That permission covers only what each event puts in scope. It doesn't extend to anything else, even systems you can reach from the competition. See [Ethics and Rules](ethics-and-rules.md).

## Who Can Participate?

CTFs are suitable for participants with a wide range of experience levels. New participants are encouraged to join, ask questions, and work collaboratively with other team members. You don't need to be an expert, and you don't need to know every category before competing. Most people start with one or two areas and build from there.

## Types of CTF

- **Jeopardy:** A board of challenges in different categories, each worth points. Most beginner events use this format.
- **Attack-defence:** Each team defends its own services while attacking other teams' services, within rules the event sets.
- **King of the hill:** Teams compete to take and keep control of a shared target.

Events can be online or in person, last from a few hours to several days, and may be for individuals or teams. Some have eligibility rules, such as being a student or living in a particular country, so check before you register.

## Common Challenge Categories

| Category | What you do | A good fit if you enjoy... |
|---|---|---|
| Web | Find and exploit flaws in web applications | Building or tinkering with websites |
| Cryptography | Break weak or misused encryption and encoding | Maths and puzzles |
| Forensics | Recover evidence from files, disk images, memory, or network captures | Detective work |
| OSINT | Find information using public sources | Research and searching |
| Reverse engineering | Work out what a program does without its source code | Taking things apart |
| Binary exploitation ("pwn") | Exploit memory-safety bugs in programs | Low-level programming |
| Miscellaneous | Everything else: scripting, logic puzzles, Linux, networking | Variety |

You don't need to know every category before competing. Pick one that sounds interesting and start there. As you discover what you don't know about a discipline, return to the free learning resources here to help meet new learning goals.

## How CTF Competitions Work

Although each competition is different, the usual process is:

1. Participate in a prep session (if it's your first time, or you want to meet-up with the team)
2. Receive registration instructions and meetup details from a coordinator/event lead.
3. Register for the event per instructions, individually or as a team.
4. Read the event rules, including the scope and any limits on tools or AI assistance.
5. Sign in to the competition platform, and connect to the event VPN if one is used (e.g. attack/defend).
6. Choose a challenge. Each has a description and a point value, and may include files or a target address.
7. Investigate using tools the rules allow, staying within scope.
8. Find the flag and submit it through the platform.
9. Earn points for each correct submission. Some events award fewer points as more teams solve a challenge, or charge points for hints.

If you're stuck or something seems broken, ask the organisers through the event's official support channel.

### Flags

Flags usually follow a format the event announces, such as:

```text
example{sample_flag}
```

- Submit the flag exactly as you found it, including the prefix and braces, unless the event says otherwise. Flags are usually case-sensitive.
- Some challenges include decoy flags. If a flag is rejected, check the format before assuming you've found the wrong thing.
- Don't guess or brute-force flag submissions. Many events limit attempts, and automated guessing breaks the rules.
- Never share flags with other teams.
- If you find a flag-like string somewhere unexpected, such as outside a challenge, report it rather than submitting it.

## Prepare for Your First CTF

Before competing:

1. Read the [Ethics and Rules](ethics-and-rules.md).
2. Set up an isolated environment using the [Lab Setup](lab-setup.md) guide, ideally with a mentor's help.
3. Join a team or find people to work with, through workshops, your club, or community channels.
4. Try a few beginner challenges on a practice platform such as [picoCTF](https://picoctf.org).
5. Decide how you'll keep notes, so you can learn from what you tried.
6. Plan breaks, and come ready to have fun.

## Next Steps

Start with a beginner-friendly category and a small practice challenge. Focus on understanding the process, not on solving everything.

It's normal not to solve any challenges in your first few competitions. Progress means understanding a little more each time. After an event, read write-ups for challenges you attempted (once the event allows them to be published), then try those challenges again. You can find upcoming events, including beginner-friendly ones, on [CTFtime](https://ctftime.org).

## Glossary

| Term | Meaning |
|---|---|
| Challenge ("chal") | A single task in a CTF, usually worth a set number of points |
| Event VPN | A private network connection some CTFs use to give you access to challenge targets |
| First blood | The first team to solve a challenge, sometimes rewarded with bonus points |
| Flag | The secret string you find and submit to prove you solved a challenge |
| Hint | Extra help for a challenge, sometimes costing points |
| OSINT | Open-source intelligence: information gathered from public sources |
| Pwn | Short for binary exploitation; also slang for taking control of a system |
| Scope | The systems and actions an event authorises. Anything outside it is off limits. |
| Scoreboard | The platform page that ranks teams by points |
| Write-up | A published explanation of how a challenge was solved, usually shared after an event ends |
