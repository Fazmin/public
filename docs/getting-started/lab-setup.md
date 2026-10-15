# Typical Lab Setup

> **Last reviewed:** October 2026 · 

## Purpose

This guide explains how to prepare an isolated, recoverable environment for Capture the Flag (CTF) competitions and practice.
For conduct, scope, privacy, and reporting requirements, read [Ethics and Rules](ethics-and-rules.md). This guide is for advanced users, and covers the technical side setup at a high-level. Your results may/will vary from those of the guide, exercise caution and *use official sources of documentation wherever possible*. This guide does not endorse participating in any specific learning events, any examples listed are for demonstration only. This guide is not meant to be a checklist of instructions or a substitution for learning the underlying technologies discussed herein. This guide is intended for individuals who are proficient in the technologies required to follow the guide, and are authorized to use said technologies in an appropriate learning environment, with appropriate security controls to maintain isolation from sensitive networks or devices. Readers should have advanced information technology skills, and be competent and familiar with all described practices, including software installation, troubleshooting, incident handling, and device security. All readers are asked to seek a real-time, 1-on-1 mentor for their first-time setting up a lab, or any time a significant change is made to their configuration or environment. *Team work is essential to your success.*

By the end of this guide, you will have learned about how to:

- Build a Kali Linux virtual machine (VM) from verified, official sources.
- Isolate the VM from your personal files, accounts, and local network.
- Keep your activity within a competition's scope.
- Install tools and handle challenge files without putting your host computer at risk.
- Protect your accounts, credentials, and work.
- Stop, recover, and report when something goes wrong.

## Safety Principles

Anyone can make a mistakes in a lab. This guide is designed so that any mistakes stay small and fixable.

- **Contain:** Keep tools, challenge files, and traffic inside the VM and inside the competition's scope.
- **Verify before you run:** Check where software, scripts, and commands come from before executing them.
- **Keep it recoverable:** Know how to roll back, and keep your notes somewhere a rollback can't erase.
- **Don't trade away host security:** Never weaken your host's protections to make the lab easier.
- **Stop and report:** If something goes wrong, stop first, then tell someone. Reporting early is expected and will not be held against you.

## Your First Lab

Welcome! If you've never built a lab before, you're about to learn a lot, and most of it happens before the competition starts.

Here's something experienced players know: every setup guide eventually goes out of date. Somewhere along the way, a command might fail, a menu might have moved, or a step might not fit your computer. That's normal, and it doesn't mean you've done something wrong. So don't do it alone. Ask someone from your CTF team or security community to set up with you, in person or on a call, so you can ask questions as they come up.

> **You're giving someone a chance to lead.** Plenty of people in this field want to mentor, and helping you is how they do it. Nobody is an expert in everything; just look at how many specialties appear on the [Certification Map](certification-map.md). Asking good questions is something you'll do for your whole career, so start now.

### Before You Start

- **Find a mentor.** Ask someone from your CTF team or security community to be available while you work, ideally live screen sharing.
- **Expect something to break.** Guides go out of date, including this one. A command may fail, or a menu may have moved.
- **Leave plenty of time.** Try to start learning and setting up before the event so that you don't spend the first few hours getting your environment setup.

### When You Get Stuck

1. Stop. Don't try random fixes from the internet or GenAI, especially ones that turn off security features.
2. Note the step you were on, the exact command, and the full error message. A screenshot helps.
3. Check [Troubleshooting](#troubleshooting).
4. Ask your mentor or team channel, and share what you noted.

If you find a mistake in this guide, report it to apd1280 at mcmaster dot ca so the next person doesn't hit it.

## Choosing Your Setup

The recommended setup for new participants is:

- VirtualBox on your personal (host) computer, on a new (standard) user account.
- The official prebuilt Kali Linux VirtualBox image
- NAT networking, with the competition VPN configured inside the VM

**Apple Silicon Macs (M-series):** The standard Kali VirtualBox image is built for x86 processors and will not run on these Macs. Use Kali's ARM64 image with a hypervisor that supports Apple Silicon, such as UTM, VMware Fusion, or a VirtualBox release that supports Arm hosts. Follow Kali's virtualization documentation for your hypervisor. Everything else in this guide still applies.

Other options include a bootable Kali USB drive, another Linux VM (for example, hosted on Proxmox), or an approved cloud workspace. These need more care; see the optional sections near the end.

If you don't have administrator rights on your computer, or it doesn't meet the requirements below, talk to your instructor or team lead before trying workarounds.

## Prerequisites

Before beginning, confirm that:

- **Hardware virtualization is enabled.**
  - Windows: **Task Manager → Performance → CPU** should show *Virtualization: Enabled*.
  - Linux: `lscpu | grep -i virtualization` should show VT-x or AMD-V.
  - If it is disabled, enable Intel VT-x or AMD-V (sometimes called SVM) in your computer's UEFI/BIOS settings.
- **Your host is up to date**, and its security protections (antivirus, firewall, Secure Boot, Memory Integrity) are turned on.
- **Your host disk is encrypted** (BitLocker, FileVault, or LUKS). Your VM will hold competition credentials, and laptops get lost.
- **Your important host files are backed up.** Installing a hypervisor and changing boot settings is usually safe, but not always.
- You have enough CPU, memory, and disk space (see below).
- You know the competition's VPN and tooling requirements, if any.

> **Do not disable host protections to make the lab work.** Common "fixes" found online include turning off Windows Memory Integrity, Virtualization-Based Security, or Secure Boot, or adding broad antivirus exclusions. These weaken your host for everything you do, not just the lab. See [Troubleshooting](#troubleshooting) for safer options.

## Recommended VM Resources

| Resource | Minimum | Recommended |
|---|---:|---:|
| RAM | 2 GB | 4 GB or more |
| CPU | 1–2 cores | 2–4 cores |
| Free disk space | 20 GB | 50 GB or more, on an SSD |
| Video memory | Default | 64–128 MB for a graphical desktop |

The prebuilt image's virtual disk grows as you use it and can become much larger than the download. Snapshots also use disk space.

Leave enough RAM, CPU, and disk for your host to keep running smoothly. Do not allocate all host resources to the VM.

## Install VirtualBox

Download VirtualBox only from its official website:

[Download VirtualBox](https://www.virtualbox.org/wiki/Downloads)

1. Download the installer for your operating system.
2. Run the installer.
3. Accept the default options unless your environment requires changes.
4. Open VirtualBox and confirm that it starts successfully.

Keep VirtualBox updated. Hypervisor security fixes protect your host from problems inside the VM.

Host-specific notes:

- **macOS:** You may need to approve VirtualBox in **System Settings → Privacy & Security**, then restart.
- **Linux with Secure Boot:** VirtualBox's kernel modules must be signed before they will load. Follow the VirtualBox manual or your distribution's instructions rather than disabling Secure Boot.
- **Windows:** If Hyper-V or Memory Integrity is active, VirtualBox may run slowly (a green turtle icon appears in the VM's status bar). See [Troubleshooting](#troubleshooting).

## Install the Extension Pack (Optional)

The VirtualBox Extension Pack adds features such as USB 2.0 and USB 3.0 passthrough and remote display (VRDP). Check the VirtualBox manual for the current feature list for your version.

Most CTF players don't need it. USB passthrough also adds another path between the VM and your host. Install the Extension Pack only when you need a specific feature.

Before installing:

- The Extension Pack uses a different licence from VirtualBox itself. Read it before installing on a university- or employer-owned computer, as organisational use may require a commercial licence.
- The Extension Pack version must match your installed VirtualBox version.

[Download the VirtualBox Extension Pack](https://www.virtualbox.org/wiki/Downloads)

1. Download the matching `.vbox-extpack` file.
2. Open VirtualBox.
3. Open **File → Tools → Extension Pack Manager**, or the equivalent menu for your version.
4. Select **Add** and choose the downloaded file.
5. Review and accept the licence agreement.

## Download and Verify Kali Linux

Download the prebuilt VirtualBox image only from the official site:

[Download Kali Linux](https://www.kali.org/get-kali/#kali-virtual-machines)

Verifying a download answers two questions:

- **Integrity:** Is the file complete and undamaged? A SHA-256 checksum answers this.
- **Authenticity:** Did the file really come from Kali? A GPG signature answers this. A checksum alone does not, because anyone who can replace the file on a website can replace the checksum too.

Don't rely on MD5 or SHA-1. Both are broken and can't be trusted to detect deliberate tampering.

### Check the checksum

On Linux or macOS:

```bash
sha256sum kali-linux-*-virtualbox-amd64.7z
```

On Windows (PowerShell):

```powershell
Get-FileHash .\kali-linux-*-virtualbox-amd64.7z -Algorithm SHA256
```

Compare the output with the SHA-256 value published on the Kali download page. Every character must match. PowerShell shows uppercase letters; that difference doesn't matter.

### Verify the signature (recommended)

Kali publishes a signed `SHA256SUMS` file for each release. The full steps, and the official signing key fingerprint to compare against, are in Kali's documentation:

[Kali: Downloading Kali Linux and verifying images](https://www.kali.org/docs/introduction/download-official-kali-linux-images/)

In outline:

1. Import Kali's signing key and confirm its fingerprint matches the one in the documentation.
2. Download `SHA256SUMS` and `SHA256SUMS.gpg` from the same release folder as your image.
3. Run `gpg --verify SHA256SUMS.gpg SHA256SUMS` and confirm it reports a good signature from Kali's signing key.
4. Confirm your image's checksum matches the entry in `SHA256SUMS`.

If any check fails, delete the file and download it again from the official site. **Never use an image that fails verification.**

## Import Kali into VirtualBox

The image is a `.7z` archive. On Windows, extract it with 7-Zip. On macOS and Linux, use `7z` (from the p7zip package) or a compatible archive tool.

1. Extract the archive to a folder with enough free space.
2. Open VirtualBox.
3. Select **Machine → Add**.
4. Select the extracted `.vbox` file.
5. Rename the VM to something recognizable, such as `Kali Linux CTF`.
6. Complete [Apply VM Safety Settings](#apply-vm-safety-settings) before starting the VM for the first time.
7. Start the VM.

The image initially uses:

```text
Username: kali
Password: kali
```

Change the default password immediately, using a strong password you don't use anywhere else:

```bash
passwd
```

Then update the system:

```bash
sudo apt update
sudo apt full-upgrade -y
sudo reboot
```

### Guest Additions

The prebuilt image includes VirtualBox Guest Additions, which provide display resizing, the shared clipboard, drag-and-drop, and shared folders. Display resizing is harmless. The clipboard, drag-and-drop, and shared folders create paths between the VM and your host, so the next section turns them off.

## Apply VM Safety Settings

With the VM powered off, open **Settings** in VirtualBox and apply these defaults.

Treat every challenge file as untrusted. These settings apply all the time, not only when you think a file is suspicious.

| Setting | Where (may vary by version) | Default for CTF |
|---|---|---|
| Shared clipboard | General → Features (General → Advanced in older versions) | Disabled |
| Drag and drop | General → Features (General → Advanced in older versions) | Disabled |
| Shared folders | Shared Folders | None |
| USB controller | USB | Disabled unless needed |
| Audio | Audio | Disabled unless needed |
| Serial ports | Serial Ports | Disabled |
| 3D acceleration | Display | Disabled |
| Network | Network → Adapter 1 | NAT |

Also:

- Do not mount drives containing personal or sensitive data.
- Do not sign in to personal, university, or work accounts inside the VM. Use only the CTF platform account described in [Protect Your Accounts and Secrets](#protect-your-accounts-and-secrets).
- Keep competition tools and files inside the VM.

To move your own notes and scripts between the VM and your host safely, see [Notes, Backups, and Moving Files](#notes-backups-and-moving-files).

## Configure Networking

### NAT (default)

Use NAT as the default network mode. It stops other devices from connecting *into* your VM.

> **NAT does not stop your VM from reaching out.** A VM on NAT can still connect to your host and to every device on your home, residence, or campus network. A mistyped target range, such as `192.168.1.0/24` instead of the competition subnet, will scan your housemates' devices, your router, or your university's network. Use the [scope guardrails](#scope-guardrails) below.

### Bridged Networking

Avoid Bridged Networking unless the event specifically requires it. Bridged mode places the VM directly on the same network as your host, where every other device can see it.

### Host-Only and Internal Networks

- **Host-Only + NAT:** Use only when you need host-to-guest communication while keeping internet access.
- **Host-Only or Internal Network on its own:** Use for practice targets such as intentionally vulnerable VMs. See [Practice Lab](#practice-lab-between-events).

### Scope Guardrails

Certain event types will involve network scanning, or a cyber range for attack/defense against other competitors. Before running any network scanning or attack tool:

1. Write the event's in-scope ranges into a file, copied directly from the official event information:

   ```text
   # scope.txt
   10.10.10.0/24
   ```

2. Give the file to your tools instead of typing ranges by hand:

   ```bash
   nmap -iL scope.txt
   ```

3. Confirm that traffic to a target goes through the VPN interface:

   ```bash
   ip route get 10.10.10.5
   ```

   The output should name your VPN interface, such as `dev tun0`. If it shows `eth0` instead, stop: the target isn't being reached through the VPN.

If you're unsure whether something is in scope, ask the organisers before acting.

### Emergency Stop

Learn how to cut the VM off immediately, before you need to:

- **Fastest:** In the VM window, open **Devices → Network** and untick **Connect Network Adapter**.
- Disconnect the VPN.
- Power off the VM (**Machine → ACPI Shutdown**, or close the window and choose **Power off the machine**).

Then follow [When Something Goes Wrong](#when-something-goes-wrong).

## Harden the VM

Complete these steps before creating your clean snapshot, so that the baseline includes them.

### Firewall

Block unsolicited incoming connections. Install `ufw` if it isn't already present:

```bash
sudo apt install ufw
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
sudo ufw status verbose
```

If a challenge needs a listener (for example, to catch a reverse shell), allow it only on the VPN interface, and only while you need it:

```bash
sudo ufw allow in on tun0 to any port 4444 proto tcp
# When finished:
sudo ufw delete allow in on tun0 to any port 4444 proto tcp
```

> **Docker bypasses `ufw`.** Ports published with `docker run -p` can be reachable even when `ufw` blocks them. Bind containers to localhost instead, for example `-p 127.0.0.1:8080:8080`.

**Advanced (optional): allow outgoing traffic only through the VPN.** This prevents accidental scans of your local network, but it also blocks normal internet access. Test it before an event, not during one:

```bash
sudo ufw default deny outgoing
sudo ufw allow out on tun0
sudo ufw allow out to <VPN-server-IP> port <VPN-port> proto <udp-or-tcp>
# To undo:
sudo ufw default allow outgoing
```

Use the server address, port, and protocol from your event's VPN configuration file.

### SSH

Kali doesn't run an SSH server by default. Confirm it's off:

```bash
systemctl is-active ssh
```

The expected output is `inactive`. If you do need SSH:

- Use key-based authentication and disable password login.
- Allow it through the firewall only from the addresses that need it.
- Turn it off when you're done: `sudo systemctl disable --now ssh`.

Never leave SSH open on a shared competition VPN.

### AppArmor

Confirm AppArmor is loaded:

```bash
sudo aa-status
```

### Least Privilege

- Work as your normal user, and use `sudo` only for commands that need it.
- Never run challenge binaries or downloaded scripts with `sudo`.

## Install CTF Tools Safely

Kali includes many tools, and CTF players commonly add more. Typical examples by category:

| Category | Common tools |
|---|---|
| Web | Burp Suite, browser developer tools, ffuf |
| Cryptography | Python with pycryptodome, SageMath, CyberChef |
| Binary exploitation | pwntools, gdb with pwndbg or GEF |
| Reverse engineering | Ghidra, radare2 |
| Forensics | Wireshark, binwalk, exiftool, Volatility |
| Password cracking | hashcat, John the Ripper |

Take a snapshot before installing a large set of tools.

### Use Trusted Sources

- Prefer Kali's own packages (`sudo apt install <package>`). They are signed and maintained.
- Otherwise, install from the project's official repository or website. Check that it really is the official project: follow links from its documentation rather than search results, and look at the account name and the project's history.

### Python Packages

Recent Kali releases block system-wide `pip install` to protect the operating system. Use one of these instead:

```bash
# Command-line tools
pipx install <tool>

# Libraries for your own scripts, such as pwntools
python3 -m venv ~/venvs/ctf
source ~/venvs/ctf/bin/activate
pip install pwntools
```

Don't override this protection with `--break-system-packages` unless you understand the risks.

### Treat Downloaded Code as Untrusted

- **Fake exploits exist.** Proof-of-concept repositories, gists, and scripts shared in chat are sometimes malware aimed at security learners. Read code before you run it, especially anything found through search results or offered by strangers.
- **Don't pipe downloads into a shell** (`curl ... | bash`). Download the script, read it, then run it.
- **Pasted commands can hide content.** Text copied from websites can include hidden characters or extra commands. Paste into a text editor first and read it before running it.
- **Be wary of unsolicited help.** Treat direct messages offering tools, "fixed" exploits, or flags as suspicious.

## Handle Challenge Files Safely

- Download challenge files inside the VM, not on your host. Host antivirus may flag them, and they don't belong there anyway.
- Never run challenge binaries or tools on your host.
- Avoid sharing a clipboard with the host if you are copying code or files.
- Inspect before executing. `file`, `strings`, and a disassembler tell you a lot without running anything.
- Before running anything that looks like real malware rather than a puzzle, take a snapshot and disconnect the network adapter. Better still, use a separate, disposable analysis VM.
- **Windows-only challenges** (`.exe`, `.dll`, .NET) need a separate Windows VM with its own clean snapshot, or Wine for simple cases. Apply the same safety settings to that VM.
- Never plug USB drives handed out at events, or found lying around, into your host.

## Protect Your Accounts and Secrets

- **Use a separate CTF identity.** Create a handle and email address that aren't linked to your personal accounts.
- **Use a password manager** and a unique password for every platform. Turn on multi-factor authentication wherever it's offered.
- **Treat these as secrets:** VPN configuration files, platform API tokens, cloud access keys, and team credentials. Never post them in chat, screenshots, write-ups, or repositories.
- **Restrict permissions** on VPN configuration files: `chmod 600 event.ovpn`.
- **Remember that snapshots and VM exports contain everything in the VM**, including secrets. Don't share them.

## Notes, Backups, and Moving Files

Restoring a snapshot erases everything created since it was taken, including your notes, scripts, and write-ups. Snapshots are stored with the VM, so they aren't backups either.

Keep your work somewhere a rollback can't reach:

- **A private git repository** for scripts and write-ups. Add a `.gitignore` so secrets can't be committed by accident:

  ```text
  # VPN configs (OpenVPN and WireGuard), keys, and environment files
  *.ovpn
  *.conf
  *.key
  .env
  ```

  Keep write-ups private until the event's rules allow publication.
- **A notes tool** outside the VM, or one that syncs from it.
- **Occasional VM exports** (**File → Export Appliance**) kept on separate storage, if you've customised the VM heavily.

**Moving files safely:** Push notes and scripts from the VM to your private repository, then pull them on your host. Move only text you've written yourself, never challenge files or binaries.

If you must temporarily enable a shared folder, point it at a dedicated empty folder (never your home or documents folder), and remove it as soon as you're done.

## Create a Clean Snapshot

Create the snapshot after updating, applying safety settings, hardening, and installing your standard tools. Do it **before** adding any event-specific VPN configuration or credentials.

1. Shut down Kali.
2. Select the VM in VirtualBox.
3. Open **Snapshots**.
4. Create a snapshot named `Clean CTF Baseline`.
5. Add the date and a brief description.

Take extra snapshots before major tool installations or analysing suspicious files.

## Validate the Setup

Run these checks inside the VM:

```bash
ip address               # NAT: a private address such as 10.0.2.15
ip route                 # NAT: default route via 10.0.2.2
ping -c 4 1.1.1.1        # Internet access: expect replies
ping -c 4 example.com    # DNS: the name should resolve to an address
sudo ufw status          # Status: active
systemctl is-active ssh  # inactive
sudo aa-status           # apparmor module is loaded
```

Checklist:

- [ ] Kali starts successfully.
- [ ] The default password has been changed.
- [ ] The network mode is NAT, unless the event requires otherwise.
- [ ] Internet access and DNS resolution work.
- [ ] Shared clipboard, drag-and-drop, and shared folders are disabled.
- [ ] USB, audio, serial ports, and 3D acceleration are disabled unless needed.
- [ ] The firewall is active and denies incoming connections.
- [ ] SSH is not running (or is key-only and firewalled).
- [ ] AppArmor is loaded.
- [ ] You know how to disconnect the network adapter quickly.
- [ ] Your notes are backed up outside the VM.
- [ ] The `Clean CTF Baseline` snapshot exists.

## Before Each Event: Connect the Competition VPN

Configure the VPN inside the VM, not on your host. Challenges that connect back to you, such as reverse shells, need to reach your VPN address. If the VPN ran on your host, VirtualBox's NAT would block those connections.

1. Download the configuration from the official event platform only. Don't use configuration files shared by other people.
2. Protect it:

   ```bash
   chmod 600 event.ovpn
   ```

3. Connect:

   ```bash
   # OpenVPN
   sudo openvpn --config event.ovpn

   # WireGuard
   sudo wg-quick up ./event.conf
   ```

4. Confirm the connection and routes:

   ```bash
   ip address
   ip route
   ```

   You should see a new VPN interface with an address (often `tun0` for OpenVPN, or named after the configuration file for WireGuard), and a route to the competition's target range through it.

5. Create `scope.txt` from the official event information (see [Scope Guardrails](#scope-guardrails)).

Don't run a personal or corporate VPN at the same time. Conflicting routes can send traffic somewhere you didn't intend. If the connection drops repeatedly or large transfers stall, check the event's documentation or ask the organisers.

> **Other competitors can reach you.** On many competition VPNs, every participant shares the same network. Keep the firewall's deny-incoming default, open listener ports only on the VPN interface and only while needed, and don't run services you don't need.

After the event, disconnect the VPN, delete the configuration file if it's no longer needed, and restore or refresh your baseline.

## During the Competition

- Stay within the scope in `scope.txt` and the event rules.
- Don't attack the competition platform, scoreboard, VPN servers, or other players unless the rules explicitly allow it.
- Use rate limits with brute-force and fuzzing tools (most have thread or delay options). Aggressive tools can take down shared infrastructure for everyone.
- Don't use wireless attack tools against any network you don't own or have written permission to test.
- Don't run scans or attack tools from campus or workplace networks unless you've confirmed that network's acceptable-use policy allows it.
- If something unexpected happens, use the [Emergency Stop](#emergency-stop).
- Take breaks. See [Wellbeing and Community](#wellbeing-and-community).

## Practice Lab (Between Events)

- **Intentionally vulnerable VMs:** Connect them to a Host-Only or Internal Network only, never NAT or Bridged. An Internal Network is the most isolated: VMs on it can't reach your host or the internet. Add a second adapter to your Kali VM on the same Internal Network to reach them.
- **Challenge containers:** If you run challenges in Docker, bind their ports to localhost (`-p 127.0.0.1:1337:1337`) so they aren't exposed to your network.
- **Practice platforms:** [picoCTF](https://picoctf.org), [OverTheWire](https://overthewire.org), and event listings on [CTFtime](https://ctftime.org). Follow each platform's rules and attack only the targets it provides.

## Optional: Kali on a USB Drive

A bootable Kali USB can provide a portable environment without installing Kali on the host.

Common boot modes include:

- **Live:** Changes are discarded after shutdown.
- **Live with persistence:** Files and settings are retained.
- **Forensic mode:** Internal drives are not mounted automatically. This reduces accidental changes but doesn't protect the drives: anyone with root access can still mount them.

> **Warning:** Creating or repartitioning a bootable USB can erase data, including your host's own drive if you select the wrong device. Back up first, disconnect other external drives, confirm the target device carefully, and follow the current official Kali documentation.

- If you keep anything on the drive, use encrypted persistence: [Kali: Adding encrypted persistence to a live USB](https://www.kali.org/docs/usb/usb-persistence-encryption/).
- A lost USB drive with unencrypted persistence exposes everything on it, including VPN configurations and credentials.
- Don't boot Kali on school/work computers or other shared machines without permission.

For most new participants, a VM is simpler and safer to manage.

## Optional: Cloud Workspace

Cloud-hosted workspaces can be useful, but they require more administration, and mistakes cost money.

Before using one:

- Confirm that the event permits cloud-hosted infrastructure.
- Ensure you have received adequate training (ideally an entry-level cloud cert) on how to setup and secure a cloud environment, including alerts for usage and billing.
- Read the provider's acceptable-use policy. Scanning third parties from cloud infrastructure can get your account suspended.
- Understand the billing model, especially for GPU instances used for password cracking.
- Set **hard spending limits** where the provider offers them, not just alerts. Alerts often arrive after the money is spent. Student credits or prepaid plans add another safety net.
- Enable multi-factor authentication on the cloud account.
- Restrict inbound access to your own IP address, and use key-based SSH only. Exposed instances are found and attacked by strangers within hours.
- Never commit cloud access keys to a repository. Leaked keys are found automatically and abused quickly, often for cryptocurrency mining billed to you.
- Shut down and delete resources after the event. Understand where residual data may continue to generate billing expenses (e.g. snapshots, logs)

Do not use a cloud workspace for the first time during a live competition. Cloud workspaces should be used by experienced practicioners, or their guests (who can receive remote connection instructions).

## Maintenance

- Kali is a rolling release. Update before each event (`sudo apt update && sudo apt full-upgrade`), then refresh your baseline snapshot.
- Keep VirtualBox and your host operating system updated.
- Delete snapshots you no longer need. Long snapshot chains use disk space and can slow the VM.
- After each event, change any passwords shared with your team and delete old VPN configurations.

## Troubleshooting

| Problem | Likely cause | Safer fix |
|---|---|---|
| "VT-x is not available" or the VM won't start | Virtualization disabled in UEFI/BIOS | Enable Intel VT-x or AMD-V/SVM in UEFI settings |
| VM is very slow; green turtle icon in the status bar (Windows) | Hyper-V, Virtualization-Based Security, or Memory Integrity is active | Accept slower performance, give the VM more resources, or use a hypervisor designed to coexist with Hyper-V. Don't turn off Memory Integrity or VBS without discussing it with your instructor. |
| VirtualBox won't start on macOS | VirtualBox not yet approved | Approve it in **System Settings → Privacy & Security**, then restart |
| VirtualBox kernel modules won't load (Linux host) | Secure Boot blocks unsigned modules | Sign the modules as described in the VirtualBox manual or your distribution's guide; don't disable Secure Boot |
| Image won't run on an Apple Silicon Mac | x86 image on an Arm host | Use Kali's ARM64 image (see [Choosing Your Setup](#choosing-your-setup)) |
| Host antivirus quarantines downloads | Challenge files or tools downloaded on the host | Download inside the VM. Don't add broad antivirus exclusions. |
| Black screen after import | Display settings | Check the graphics controller and video memory in **Settings → Display** |
| `pip install` fails with "externally-managed-environment" | Kali protects its system Python | Use `pipx` or a virtual environment (see [Python Packages](#python-packages)) |
| VPN connects but large transfers stall | MTU mismatch | Check the event's documentation or ask the organisers |
| Host or VM disk is full | The virtual disk and snapshots have grown | Delete unused snapshots and free host disk space |

## When Something Goes Wrong

Use this procedure if you think you have:

- sent traffic outside the competition's scope,
- run something that may have affected your host,
- exposed credentials, or
- found a real vulnerability in the event's infrastructure (don't explore it further).

1. **Stop.** Disconnect the network adapter (**Devices → Network**, untick **Connect Network Adapter**), disconnect the VPN, and stop any running tools.
2. **Write down what happened:** what you ran, against what, and when. Do this before you forget, and before you delete anything.
3. **Report it** to the event organisers and to your instructor or team lead. Reporting early limits harm and is expected. It will not be held against you.
4. **Rotate exposed credentials:** change passwords, revoke tokens and keys, and request a new VPN configuration if needed.
5. **Recover:** restore the clean snapshot or rebuild the VM. If your host may be affected, scan it with up-to-date security software and ask for help before continuing. If in doubt, rebuild.

It's advisable to have contacts listed before an event, and to discuss these steps with your teammates. Accidents happen, so reinforce a culture of blameless support: it's us versus the problem. Incidents are best avoided, but can bring out the best in each other with the right leadership. Be that leader!

### Rolling Back

When a tool installation or challenge damages the VM:

1. Make sure your notes are saved outside the VM.
2. Shut down the VM.
3. Restore the `Clean CTF Baseline` snapshot.
4. Reapply only the required event configuration.
5. Create a new snapshot if the baseline needs to be updated.

A rollback only undoes changes **inside** the VM. It can't undo traffic already sent, credentials already exposed, or files already copied to your host.
After handling suspicious files, consider deleting and recreating the VM rather than continuing to trust it.

## Wellbeing and Community

- Follow the event's code of conduct. Report harassment to the organisers, and to your instructor or event coordinator if it involves your team.
- Competitions often run for 24–48 hours. Plan breaks, eat, sleep, and stop when you're too tired to think clearly. Tired people make the mistakes this guide is trying to prevent.
- Check-in on the wellbeing of your team members, and help keep each other aligned with conduct standards if you notice behavioural changes. Competitions are fun, difficult, and can be high-energy and high emotion: please help them bring out the best in ourselves and each other. Act professional, and demonstrate care and compassion. Cybersecurity is a team sport!
- OSINT challenges sometimes involve real people. Stay within what the challenge asks, and don't publish personal information you find. Engage in adequate training and preparation before engaging with real-world OSINT challenges like TraceLabs: these can contain sensitive and distressing material. Only engage if you have the appropriate preparation, understanding, and support. This guide is not intended for, nor does it endorse those type of challenges, but we recognize that generative AI or search engines may recommend them to you.
- Forensics files and other challenges can occasionally contain distressing material, such as TraceLabs competitions. It's fine to step away and let your team or the organisers know.
- Large public events can attract competitors who exhibit anti-social or immature behaviour in shared competition spaces. Event organizers tend to enforce a code of conduct, but that doesn't mean you won't experience this behaviour in the shared space. There is less accountability in CTF events than there would be in a traditional learning space (e.g. classroom), step away and/or notify event organizers if there is abuse or violations of code of conduct.


## References and Tutorials

Official documentation:

- [VirtualBox User Manual](https://www.virtualbox.org/manual/), especially the Security Guide chapter
- [Kali Linux Documentation](https://www.kali.org/docs/), including the virtualization and USB sections
- [Ethics and Rules](ethics-and-rules.md)
