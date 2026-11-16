---
layout: default
title: "Horizon Summary: 2026-11-16 (EN)"
date: 2026-11-16
lang: en
---

> From 16 items, 4 important content pieces were selected

---

**Technology News**
1. [NoisyTCP Vulnerability in Linux Kernel Enables Server Crashes on Default Configurations](#item-tech-news-1) ⭐️ 7.0/10
2. [FBI Warns of ARTEX AI Penetration Testing Tool Powering Global Cyberattacks](#item-tech-news-2) ⭐️ 7.0/10
3. [SANSAR Cryptomining Malware Uses Modified NVML Wrapper to Falsify Linux GPU Metrics](#item-tech-news-3) ⭐️ 7.0/10
4. [Amazon Discovers AI Agent Campaign Harvesting API Keys from AI Infrastructure](#item-tech-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [NoisyTCP Vulnerability in Linux Kernel Enables Server Crashes on Default Configurations](https://www.bleepingcomputer.com/news/linux/new-noisytcp-linux-kernel-flaw-lets-attackers-crash-servers/) ⭐️ 7.0/10

A newly disclosed 11-year-old Linux kernel vulnerability dubbed NoisyTCP affects nearly all Linux distributions. Attackers can exploit the flaw to crash servers running default installations of widespread services, including Nginx, Apache, and SSH.

rss · BleepingComputer · Nov 16, 09:30

**「Background」** Tracked as CVE-2026-99288, the flaw was identified and patched by security researcher Hyunwoo Kim after an embargo period. It stems from a pre-authentication race condition in the Linux kernel&\#x27;s TCP stack involving stale socket hash table lookups and memory reallocation.

<details><summary>References</summary>
<ul>
<li><a href="https://cybersecuritynews.com/noisytcp-linux-kernel-vulnerability/">NoisyTCP: 11-Year-Old Linux Kernel Flaw Lets Unauthenticated ...</a></li>
<li><a href="https://github.com/V4bel/NoisyTCP">GitHub - V4bel/NoisyTCP</a></li>

</ul>
</details>

**Tags**: `#linux kernel`, `#cybersecurity`, `#networking`, `#vulnerabilities`, `#systems engineering`

---

<a id="item-tech-news-2"></a>
### [FBI Warns of ARTEX AI Penetration Testing Tool Powering Global Cyberattacks](https://www.bleepingcomputer.com/news/security/fbi-warns-artex-ai-hacking-tool-is-powering-global-cyberattacks/) ⭐️ 7.0/10

The Federal Bureau of Investigation \(FBI\) has issued a warning that threat actors are actively leveraging an AI-powered penetration testing framework known as ARTEX to automate cyberattacks against organizations worldwide. According to the warning, the tool was utilized in a recent ConnectWise supply-chain breach that compromised customer Microsoft 365 environments. The alert highlights the weaponization of automated AI penetration tools in live enterprise breaches.

rss · BleepingComputer · Nov 15, 18:29

**「Background」** ARTEX is an open-source, LLM-driven autonomous penetration testing framework designed to simulate cyber operations across multiple attack stages. Security agencies and researchers have noted that threat actors increasingly weaponize such agentic platforms to automate reconnaissance, lateral movement, and privilege escalation at accelerated speeds.

**「Impact」** Organizations using ConnectWise and integrated Microsoft 365 services must review their environments for unauthorized access and audit automation-driven attack vectors targeting supply-chain trust relationships.

<details><summary>References</summary>
<ul>
<li><a href="https://cybersecuritynews.com/fbi-reveals-hackers-artex-ai-usage/">FBI Reveals How Hackers Use ARTEX AI Agents to Gain ...</a></li>
<li><a href="https://www.ic3.gov/CSA/2026/261113.pdf">Threat Overview of ARTEX Autonomous Penetration Testing Framework</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#artificial intelligence`, `#threat intelligence`, `#supply chain security`

---

<a id="item-tech-news-3"></a>
### [SANSAR Cryptomining Malware Uses Modified NVML Wrapper to Falsify Linux GPU Metrics](https://thehackernews.com/2026/11/sansar-linux-cryptomining-malware-uses.html) ⭐️ 7.0/10

Elastic Security Labs documented an attack campaign by threat group REF3364 deploying SANSAR, a Rust-based cryptomining toolkit targeting Linux environments by exploiting exposed Ray job agents. The operation installs a modified NVIDIA Management Library \(NVML\) wrapper that intercepts monitoring tools like nvidia-smi to spoof GPU utilization as 0%, falsifying temperatures between 36°C and 46°C and power draw between 100W and 200W. Alongside CPU \(XMRig 6.25.0\) and GPU \(SRBMiner-MULTI 3.6.9\) miners controlled over Tor, the malware deploys an ftrace-based kernel rootkit for persistence and an Ethereum-assisted backdoor to maintain command-and-control access.

rss · The Hacker News · Nov 16, 09:32

**「Background」** Cryptomining malware targeting Linux environments often evades detection by monitoring system activity and throttling resource usage when diagnostic tools run. To track GPU workloads, administrators rely on standard monitoring utilities like nvidia-smi, which query the NVIDIA Management Library \(NVML\) for operational metrics such as utilization, temperature, and power draw.

**「Impact」** Organizations running Ray clusters or expanding GPU infrastructure for AI workloads must restrict unauthorized job submission access and verify the file integrity of host NVML shared libraries, as standard monitoring dashboards can fail to reveal diverted compute capacity.

**Tags**: `#Cybersecurity`, `#Linux`, `#GPU`, `#Malware`, `#Artificial Intelligence Infrastructure`

---

<a id="item-tech-news-4"></a>
### [Amazon Discovers AI Agent Campaign Harvesting API Keys from AI Infrastructure](https://thehackernews.com/2026/11/amazon-uncovers-ai-agent-campaign.html) ⭐️ 7.0/10

Amazon Threat Intelligence revealed that threat actors have deployed autonomous AI agents, likely running on the open-source penetration-testing tool ARTEX, to discover internet-exposed AI applications and harvest stored AI provider keys. Captured records from Amazon&\#x27;s MadPot decoy servers show the agents systematically targeted LLM gateways and application builders—including LiteLLM, One API, and Dify—by exploiting default master keys, unauthenticated endpoints, and known vulnerabilities to fuel further automated attacks. Amazon noted that while the captured agent logs detail attempts and playbook instructions across hundreds of targets, it cannot independently verify the success of the outcomes reported by the agents.

rss · The Hacker News · Nov 16, 07:34

**「Background」** Horizon&\#x27;s November 14 digest reported that Amazon&\#x27;s MadPot honeypot intercepted telemetry from cybercrime campaigns running the open-source ARTEX penetration-testing framework to harvest AI API keys and fuel ongoing inference operations. Originally released to automate security assessments through coordinated planner and worker agents, the framework was removed by its developer in October after widespread in-the-wild abuse by threat actors.

**「Impact」** Defenders and organizations hosting AI gateways or development platforms must ensure admin interfaces are not exposed publicly without authentication, immediately change default credentials such as LiteLLM&\#x27;s default master key, and monitor cloud billing and inference logs for unexpected usage spikes.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.talosintelligence.com/artex-and-beyond/">2026-11-14 — Cisco Talos Details In-the-Wild Misuse of AI Penetration Testing Frameworks</a></li>
<li><a href="https://aws.amazon.com/blogs/security/amazon-threat-intelligence-observes-threat-actors-running-cybercrime-campaigns-with-artex-ai-agents/">2026-11-14 — Amazon Threat Intelligence Detects Cybercrime Campaigns Powered by ARTEX AI Agents</a></li>

</ul>
</details>

**Tags**: `#AI Security`, `#Cybersecurity`, `#AI Agents`, `#LiteLLM`

---