---
layout: default
title: "Horizon Summary: 2026-11-14 (EN)"
date: 2026-11-14
lang: en
---

> From 28 items, 6 important content pieces were selected

---

**Technology News**
1. [Microsoft Details SCKit Worm Abusing ConnectWise ScreenConnect to Target Technicians](#item-tech-news-1) ⭐️ 7.0/10
2. [Amazon Threat Intelligence Detects Cybercrime Campaigns Powered by ARTEX AI Agents](#item-tech-news-2) ⭐️ 7.0/10
3. [Cisco Talos Details In-the-Wild Misuse of AI Penetration Testing Frameworks](#item-tech-news-3) ⭐️ 7.0/10
4. [Trezor Confirms Hardware Implants in Three Safe 5 Wallets, Issues Firmware Fix](#item-tech-news-4) ⭐️ 7.0/10
5. [PostgreSQL Patches 52 Vulnerabilities Including Authenticated RCE Flaw CVE-2026-6460](#item-tech-news-5) ⭐️ 7.0/10
6. [Mior and Skyfall Attacks Expose AMD SEV-SNP Confidential VM Data to Host Operators](#item-tech-news-6) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Microsoft Details SCKit Worm Abusing ConnectWise ScreenConnect to Target Technicians](https://www.microsoft.com/en-us/security/blog/2026/11/13/sckit-abuses-screenconnect-deploy-remote-access-target-technician-sessions/) ⭐️ 7.0/10

Microsoft Threat Intelligence reported that threat actors are compromising cloud-hosted ConnectWise ScreenConnect instances belonging to managed service providers to install unauthorized remote-access clients and deploy a malicious worm named SCKit on managed customer endpoints. The attack chain downloads a secondary attacker-controlled ScreenConnect client alongside a batch launcher and PowerShell decoder, which extracts the SCKit bundle using device-specific cryptographic keys derived from MachineGuid. Once staged, the toolkit establishes persistence via scheduled tasks and registry Run keys and deploys RelayTrap, a malicious component engineered to exploit hijacked sessions and deliver payloads back to connecting IT support technician workstations.

rss · Microsoft Security Blog · Nov 13, 21:31

**「Background」** ConnectWise ScreenConnect is a remote-support platform where a central management server facilitates sessions between support technicians and background clients running on customer endpoints. In addition to standard console authentication, the platform supports extensions like the third-party RMM+ suite, which expose remote-command APIs protected by separate access keys to automate administrative tasks.

**「Impact」** Defenders must remediate persistence mechanisms and invalidate exposed web sessions across both technician workstations and downstream endpoints, as removing unauthorized ScreenConnect clients alone does not sever attacker access or neutralize staged SCKit payloads.

**Tags**: `#cybersecurity`, `#threat intelligence`, `#malware analysis`, `#remote access software`

---

<a id="item-tech-news-2"></a>
### [Amazon Threat Intelligence Detects Cybercrime Campaigns Powered by ARTEX AI Agents](https://aws.amazon.com/blogs/security/amazon-threat-intelligence-observes-threat-actors-running-cybercrime-campaigns-with-artex-ai-agents/) ⭐️ 7.0/10

From October 3 to November 5, 2026, Amazon&\#x27;s MadPot honeypot network captured operational telemetry from threat actors running autonomous cybercrime campaigns using ARTEX, an open-source agentic penetration testing framework. The captured prompts and memory states revealed multi-agent setups running self-sustaining credential theft operations that prioritized AI model API keys to fund further inference, alongside campaigns using real-time deepfakes to bypass cryptocurrency exchange KYC checks. Amazon Threat Intelligence assessed with moderate confidence that the operations stemmed from disparate Chinese-nexus threat groups targeting AI gateways and application platforms including LiteLLM, One API, Langflow, and Dify.

rss · AWS Security · Nov 13, 20:26

**「Background」** Amazon operates MadPot, a global network of decoy threat sensors that emulates services to monitor attacker tactics without exposing customer workloads. As offensive AI frameworks evolve, open-source penetration testing tools like ARTEX automate multi-step operations using specialized planner, worker, and verification agents that coordinate through shared memory graphs.

**「Impact」** Organizations hosting internet-exposed AI proxies and orchestration platforms must audit their administrative endpoints and revoke leaked API keys, as attackers are actively exploiting misconfigurations such as default LiteLLM master keys and vulnerabilities like CVE-2025-3248 to harvest AI model credentials.

**Tags**: `#cybersecurity`, `#threat intelligence`, `#agentic AI`, `#LLM security`

---

<a id="item-tech-news-3"></a>
### [Cisco Talos Details In-the-Wild Misuse of AI Penetration Testing Frameworks](https://blog.talosintelligence.com/artex-and-beyond/) ⭐️ 7.0/10

Cisco Talos reported that threat actors are actively deploying open-source AI penetration testing frameworks—including ARTEX, Hephaestus, and PentAGI—to automate and accelerate offensive operations. ARTEX, published on GitHub in July 2026 by developer Autumn-27, uses planner and worker agents to automate reconnaissance and vulnerability testing, relying on the Model Context Protocol \(MCP\) to integrate external tools and command-and-control frameworks. State-aligned groups such as VAPOR PANDA and Storm-0940, alongside financially motivated actors, have used ARTEX to conduct mass password-spraying across more than 2,250 Microsoft 365 tenants and execute targeted intrusions across at least 14 countries.

rss · Cisco Talos · Nov 13, 20:57

**「Background」** ARTEX is an open-source penetration testing framework released on GitHub in July 2026 by a developer using the pseudonym Autumn-27. It employs large language models to coordinate planner and worker agents, automating task decomposition and tool execution across target networks with minimal manual input.

**「Impact」** Incident response teams face significantly reduced response windows as AI-orchestrated toolchains execute automated intrusion steps—such as credential discovery and cloud vault exfiltration—in minutes, necessitating rapid automated containment rather than relying solely on manual triage.

**Tags**: `#artificial intelligence`, `#cybersecurity`, `#penetration testing`, `#threat intelligence`

---

<a id="item-tech-news-4"></a>
### [Trezor Confirms Hardware Implants in Three Safe 5 Wallets, Issues Firmware Fix](https://www.bleepingcomputer.com/news/cryptocurrency/trezor-confirms-crypto-stealing-implants-in-three-wallets-releases-fix/) ⭐️ 7.0/10

Trezor confirmed that three Safe 5 hardware wallets sold between August 20 and September 23 by Southeast Asian reseller CryptoBilis contained unauthorized hardware implants. Positioned between the display and main board, the implant copies recovery phrases and passphrases shown on-screen and exfiltrates them encrypted over cellular networks without altering the device&\#x27;s firmware or Secure Element. In response, Trezor released firmware version 2.13.1 to block the implant from capturing screen data, though the update cannot protect recovery phrases exposed before its installation.

rss · BleepingComputer · Nov 13, 19:38

**「Background」** Cryptocurrency hardware wallets safeguard private keys offline, relying on on-screen display during setup so users can record recovery phrases without exposing them to host computers or networks. The incident follows a related disclosure by rival vendor Ledger, which discovered unauthorized physical implants designed to intercept setup phrases in devices distributed by the same regional reseller.

**「Impact」** Customers who purchased a Trezor wallet from CryptoBilis since March must immediately migrate their assets to a newly generated recovery phrase rather than restoring the old phrase onto a different device, as Trezor offers free replacement hardware to affected buyers.

**Tags**: `#hardware security`, `#supply chain security`, `#cryptocurrency`, `#embedded systems`

---

<a id="item-tech-news-5"></a>
### [PostgreSQL Patches 52 Vulnerabilities Including Authenticated RCE Flaw CVE-2026-6460](https://thehackernews.com/2026/11/postgresql-patches-52-flaws-including.html) ⭐️ 7.0/10

The PostgreSQL Global Development Group has released security updates addressing 52 vulnerabilities across versions 18.7, 17.12, 16.16, 15.20, and 14.25. The update resolves CVE-2026-6460, an 8.8 CVSS authenticated remote code execution flaw caused by type confusion in composite types that executes code under the database operating system user&\#x27;s privileges. The release also fixes CVE-2026-116322, an unauthenticated denial-of-service flaw triggering restarts on PostgreSQL 18 servers, as well as code execution vulnerabilities in client utilities like pg\_restore and psql.

rss · The Hacker News · Nov 13, 16:53

**「Background」** PostgreSQL composite types consist of named fields with distinct data types, and changes made to column typing mechanisms in 2004 and 2015 allowed field types to change while existing values remained in memory. Without validation, an unpatched server could interpret an old value as the updated type, permitting authenticated users with object-creation privileges to trigger memory leaks and execute arbitrary commands.

**「Impact」** Administrators must update server instances and immediately rebuild or update all installed C-language extensions, as older extension binaries can remain vulnerable and newly rebuilt extensions will fail to load on unpatched servers. Furthermore, PostgreSQL 14 has reached end-of-life with release 14.25, leaving earlier unsupported major versions without official patches.

**Tags**: `#PostgreSQL`, `#Database Security`, `#Vulnerability`, `#Open Source`

---

<a id="item-tech-news-6"></a>
### [Mior and Skyfall Attacks Expose AMD SEV-SNP Confidential VM Data to Host Operators](https://thehackernews.com/2026/11/new-mior-and-skyfall-attacks-let-rogue.html) ⭐️ 7.0/10

Researchers have demonstrated two attacks against AMD SEV-SNP confidential computing on EPYC processors, allowing rogue cloud hosts to compromise virtual machines designed to remain isolated from server operators. The Mior attack \(CVE-2026-0462\) corrupts startup memory-protection tables using a modified BIOS and PCIe device, enabling arbitrary read and write access to VM memory as well as forged attestation measurements. The Skyfall attack \(CVE-2026-40671\) abuses Transient Scheduler Attack timing leaks during intentionally aborted VM startups to recover saved register states, encryption keys, and specific memory cache lines on Zen 3 and Zen 4 chips. AMD released microcode and SEV firmware updates dated August 12 and scheduled updated platform firmware releases for server manufacturers across EPYC 7003, 8004, 8005, 9004, and 9005 series through December.

rss · The Hacker News · Nov 13, 15:27

**「AMD SEV-SNP Security Model」** AMD&\#x27;s Secure Encrypted Virtualization-Secure Nested Paging \(SEV-SNP\) provides confidential computing for EPYC processors by isolating virtual machines from potentially untrusted hosts, hypervisors, and UEFI firmware. Hardware-enforced memory encryption and a Reverse Map Table \(RMP\) managed by the Platform Security Processor track memory ownership to protect guest integrity and confidentiality.

**「Impact」** Because the mitigations reside in host microcode and platform firmware, confidential VM tenants cannot patch their instances directly and must rely on cloud hosts and server makers to deploy updated BIOS packages.

**Tags**: `#Confidential Computing`, `#Hardware Security`, `#AMD EPYC`, `#Virtualization`

---