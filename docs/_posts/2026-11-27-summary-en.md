---
layout: default
title: "Horizon Summary: 2026-11-27 (EN)"
date: 2026-11-27
lang: en
---

> From 103 items, 5 important content pieces were selected

---

**Technology News**
1. [Drupal Warns of Active Exploitation Targeting Site Takeover Vulnerability](#item-tech-news-1) ⭐️ 7.0/10
2. [NFS2ROOT Flaw in Linux Kernel NFS Server Enables Remote Root Access](#item-tech-news-2) ⭐️ 7.0/10
3. [Switzerland Confirms Autonomous AI Agents Breached Critical Infrastructure Systems](#item-tech-news-3) ⭐️ 7.0/10
4. [Unpatched Cacti 1.2.31 Zero-Day Enables Remote Code Execution via Guest Access](#item-tech-news-4) ⭐️ 7.0/10
5. [PolinRider Poisons Over 7,600 GitHub Repositories With Multi-Stage Python Malware](#item-tech-news-5) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Drupal Warns of Active Exploitation Targeting Site Takeover Vulnerability](https://www.bleepingcomputer.com/news/security/drupal-warns-of-new-access-bypass-flaw-exploited-in-attacks/) ⭐️ 7.0/10

The Drupal security team has issued a warning regarding active in-the-wild exploitation targeting a critical vulnerability that allows attackers to breach and hijack unpatched websites. Administrators managing vulnerable Drupal installations must apply security updates immediately to prevent unauthorized site takeovers.

rss · BleepingComputer · Nov 27, 10:10

**「Background」** Drupal websites rely on core access controls and modular authentication mechanisms to protect administrative functions and sensitive site resources. Vulnerabilities such as CVE-2026-136716 allow unauthenticated attackers to bypass authentication checks and execute unauthorized actions without valid credentials.

**「Impact」** Administrators managing Drupal installations in incomplete or unusual install states must apply the latest updates, restrict access, and audit administrative accounts to prevent unauthorized site takeover.

<details><summary>References</summary>
<ul>
<li><a href="https://cybersecuritynews.com/drupal-website-takeover-flaw/">Drupal Warns of Active Attacks Exploiting New Critical ...</a></li>
<li><a href="https://www.drupal.org/security">Security advisories | Drupal.org</a></li>
<li><a href="https://www.drupal.org/security">Security advisories | Drupal.org</a></li>
<li><a href="https://brandefense.io/knowledge-hub/vulnerabilities/cve-2026-136716/">CVE-2026-136716: Drupal Installer Takeover, Fix Status</a></li>

</ul>
</details>

**Tags**: `#Drupal`, `#cybersecurity`, `#vulnerability`, `#open source`

---

<a id="item-tech-news-2"></a>
### [NFS2ROOT Flaw in Linux Kernel NFS Server Enables Remote Root Access](https://www.bleepingcomputer.com/news/security/new-nfs2root-linux-flaw-can-let-attackers-gain-root-privileges/) ⭐️ 7.0/10

A 12-year-old critical vulnerability in the Linux kernel&\#x27;s Network File System \(NFS\) server, tracked as CVE-2026-99362, allows remote attackers to obtain root privileges. The flaw, designated as NFS2ROOT, exposes affected Linux deployments running vulnerable kernel NFS server configurations to full system compromise.

rss · BleepingComputer · Nov 27, 08:06

**「Background」** The Linux kernel includes an in-kernel Network File System \(NFS\) server \(nfsd\) that allows systems to share directories and files with remote clients across a network. Because the kernel-level implementation operates with full system privileges to manage filesystem operations, unresolved vulnerabilities in its request processing can expose the host operating system to severe compromise.

**「Impact」** Administrators hosting NFSv4.1 or NFSv4.2 shares face potential kernel memory corruption, server crashes, or remote code execution, but can mitigate exposure prior to patching by configuring systems to avoid negotiating minimal cached reply sizes.

<details><summary>References</summary>
<ul>
<li><a href="https://www.techbarrista.com/cve-2026-99362-ubuntu/">CVE-2026-99362 Puts Ubuntu NFS Servers at Risk</a></li>
<li><a href="https://app.opencve.io/cve/CVE-2026-99362">CVE-2026-99362 - Vulnerability Details - OpenCVE</a></li>

</ul>
</details>

**Tags**: `#Linux`, `#Security`, `#Vulnerability`, `#NFS`, `#Operating Systems`

---

<a id="item-tech-news-3"></a>
### [Switzerland Confirms Autonomous AI Agents Breached Critical Infrastructure Systems](https://thehackernews.com/2026/11/switzerland-confirms-ai-assisted.html) ⭐️ 7.0/10

Switzerland&\#x27;s National Cyber Security Centre confirmed that autonomous AI attack agents successfully compromised IT systems in four out of five recently reported intrusion attempts, including breaches at two critical infrastructure operators across at least two sectors. The agency noted that no major operational disruptions occurred, and the perpetrators as well as the specific victim organizations remain unidentified. The attacks leveraged automated offensive frameworks capable of scanning for unpatched vulnerabilities, adapting tactics in real time when challenged by defenses, and running parallel intrusions without human intervention.

rss · The Hacker News · Nov 27, 06:04

**「Background」** Offensive AI frameworks automate the discovery and exploitation of common security weaknesses, such as exposed credentials, misconfigured infrastructure, and unpatched APIs. European cybersecurity agencies, including Italy&\#x27;s CSIRT and the UK&\#x27;s NCSC, have documented an escalation in mass compromise campaigns since late 2026, citing public or open-source agent frameworks such as ARTEX, CyberStrikeAI, PentAGI, and DeepSeek Harness.

**「Impact」** To counter the rapid exploitation cycles of autonomous agents, Swiss and partner cybersecurity authorities urge defenders to apply critical security patches to internet-facing systems within 24 hours of release, isolate unpatchable assets, and enforce multi-factor authentication across all external endpoints.

**Tags**: `#Cybersecurity`, `#Artificial Intelligence`, `#Critical Infrastructure`, `#Threat Intelligence`

---

<a id="item-tech-news-4"></a>
### [Unpatched Cacti 1.2.31 Zero-Day Enables Remote Code Execution via Guest Access](https://thehackernews.com/2026/11/unpatched-cacti-zero-day-enables-rce-in.html) ⭐️ 7.0/10

A security researcher disclosed an unpatched zero-day vulnerability affecting Cacti Core 1.2.31 that allows unauthenticated remote code execution in four HTTP requests when guest access is enabled. The exploit chain, dubbed 4HTTP2SHELL and 4HTTP2ROOT, abuses the guest session via auth\_profile.php to inject SQL into the preview\_graphs\_per\_page setting. This second-order SQL injection updates Cacti&\#x27;s poller table via stacked statements, causing graph\_realtime.php to pass the attacker-controlled record directly into PHP&\#x27;s popen\(\) function.

rss · The Hacker News · Nov 27, 05:48

**「Background」** Cacti is an open-source network monitoring and fault management framework that manages devices across corporate networks using poller mechanisms. While the application&\#x27;s guest account feature has been disabled by default since version 0.8.7, instances that re-enable guest access expose interactive endpoints without requiring authenticated administrative credentials.

**「Impact」** Because Cacti routinely stores credentials and connection details for network infrastructure like routers and switches, compromised servers can serve as an internal pivot point; administrators must immediately disable the guest account and inspect the poller table for unauthorized commands until a patch is issued.

**Tags**: `#vulnerability`, `#network-monitoring`, `#open-source-security`, `#remote-code-execution`

---

<a id="item-tech-news-5"></a>
### [PolinRider Poisons Over 7,600 GitHub Repositories With Multi-Stage Python Malware](https://thehackernews.com/2026/11/north-korea-linked-polinrider-poisons.html) ⭐️ 7.0/10

Security researchers revealed that threat actors behind the North Korea-linked PolinRider campaign have compromised more than 7,600 legitimate GitHub repositories, injecting a 58-line Python loader directly into utility packages and conftest.py files. SafeDep identified the loader across 375 public repositories from 260 accounts, which executes when developers clone and run or test the projects. When executed, the loader reads transaction data from an Ethereum wallet to extract and execute JavaScript via Node.js, which then parses command-and-control server IP addresses from a second wallet address to fetch next-stage payloads.

rss · The Hacker News · Nov 26, 15:13

**「Campaign Background」** PolinRider operates as an open-source supply chain sub-cluster linked to North Korean threat actors alongside the broader &quot;Contagious Interview&quot; campaign, which historically used fraudulent job recruitment and coding assessments to compromise developer systems. Rather than distributing malware solely through package registries or phishing, the threat group leverages stolen developer tokens and credentials to directly modify legitimate source repositories into malware distribution vectors.

**「Impact」** Developers running or testing affected repositories risk having second-stage payloads executed on their systems, which tamper with tools such as VS Code, Cursor, and GitHub Desktop to maintain persistence and harvest environment secrets, browser credentials, and tokens.

**Tags**: `#Software Supply Chain`, `#Open Source Security`, `#GitHub`, `#Malware`, `#Python`

---