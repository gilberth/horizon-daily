---
layout: default
title: "Horizon Summary: 2026-11-22 (EN)"
date: 2026-11-22
lang: en
---

> From 78 items, 6 important content pieces were selected

---

**Technology News**
1. [Graham Dumpleton Introduces Muru, an AI-Assisted Rust Server for Python](#item-tech-news-1) ⭐️ 7.0/10
2. [Rackspace Spot Breach Allowed Unauthorized Workload Deployment and Secrets Access](#item-tech-news-2) ⭐️ 7.0/10
3. [Microsoft Entra Connect Health Flaw Exploited to Expose Tenant Data](#item-tech-news-3) ⭐️ 7.0/10
4. [FBI Reportedly Breached Again, Targeting Nationwide Police Database](#item-tech-news-4) ⭐️ 7.0/10
5. [OpenRouter Drops Three Providers and 125 Endpoints Following Prompt Data Thefts](#item-tech-news-5) ⭐️ 7.0/10
6. [Ghostscript Sandbox-Escape Flaw Allows Remote Code Execution via Common File Uploads](#item-tech-news-6) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Graham Dumpleton Introduces Muru, an AI-Assisted Rust Server for Python](https://simonwillison.net/2026/Nov/21/muru/) ⭐️ 7.0/10

Graham Dumpleton, creator of mod\_wsgi, is developing Muru, an AI-assisted Rust web server designed to run both WSGI and ASGI Python applications across development and production environments. Over a three-week series of technical posts starting in November 2026, Dumpleton outlined Muru&\#x27;s architecture, which includes features such as concurrent WSGI/ASGI support, development HTTPS, zero-restart releases, worker-reported scaling, and container/Kubernetes integration. The project is an active development effort rather than a finalized release, with Dumpleton using AI tools to assist implementation while applying his web server domain expertise to guide and review the architecture.

rss · Simon Willison · Nov 21, 23:56

**「Background」** Graham Dumpleton created mod\_wsgi twenty years ago to host Python applications on the Apache HTTP Server under the Web Server Gateway Interface \(WSGI\) standard. Modern Python web architectures have since expanded to include the Asynchronous Server Gateway Interface \(ASGI\) to handle asynchronous I/O and concurrent protocols alongside traditional synchronous workloads.

**Tags**: `#python`, `#rust`, `#web-servers`, `#software-architecture`, `#open-source`

---

<a id="item-tech-news-2"></a>
### [Rackspace Spot Breach Allowed Unauthorized Workload Deployment and Secrets Access](https://www.bleepingcomputer.com/news/security/rackspace-spot-breach-let-hackers-access-customer-kubernetes-secrets/) ⭐️ 7.0/10

Rackspace notified customers that attackers breached its Rackspace Spot cloud platform after obtaining compromised credentials. The unauthorized access allowed the intruders to deploy their own workloads and access sensitive Kubernetes secrets stored within customer clusters. Rackspace has not detailed the full number of affected accounts or whether customer secrets were exfiltrated.

rss · BleepingComputer · Nov 21, 22:59

**「Background」** Rackspace Spot is an open-market cloud service that offers discounted spot instances and managed Kubernetes clusters for running containerized workloads. In Kubernetes environments, Secrets store sensitive data such as API tokens, passwords, and encryption keys needed by applications across the cluster.

**「Impact」** Affected Rackspace Spot customers must audit their environments for unauthorized workloads and immediately rotate any credentials, API keys, and sensitive data stored as Kubernetes secrets in their clusters to prevent further unauthorized access.

**Tags**: `#cloud security`, `#kubernetes`, `#rackspace`, `#data breach`

---

<a id="item-tech-news-3"></a>
### [Microsoft Entra Connect Health Flaw Exploited to Expose Tenant Data](https://www.bleepingcomputer.com/news/security/microsoft-entra-connect-health-flaw-exploited-to-steal-tenant-data/) ⭐️ 7.0/10

Microsoft is warning organizations of a security breach resulting from an exploited vulnerability in its Entra Connect Health service. Threat actors leveraged the flaw to gain unauthorized access to customer tenant configuration details and administrator email addresses. Microsoft has not disclosed further technical specifications regarding the vulnerability or the full scope of affected tenants in the initial disclosure.

rss · BleepingComputer · Nov 21, 18:01

**「Prerequisites」** Microsoft Entra Connect Health is an identity management monitoring tool used by enterprise hybrid environments to oversee on-premises identity infrastructure such as Active Directory and sync operations with Microsoft Entra ID. Because the service monitors synchronization status and operational metrics across identity components, it regularly processes tenant configurations and administrative contact data.

**「Impact」** Affected enterprise administrators face heightened phishing, social engineering, and reconnaissance risks due to the exposure of administrative contact emails and tenant configuration settings.

<details><summary>References</summary>
<ul>
<li><a href="https://cybersecuritynews.com/microsoft-entra-connect-health-flaw/">Hackers Exploit Microsoft Entra Connect Health Flaw to Access ...</a></li>
<li><a href="https://techbytes.app/posts/microsoft-entra-connect-health-flaw-exploited-to-access-tenant-data/">Microsoft Entra Connect Health flaw exploited to access ...</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#cloud security`, `#microsoft entra`, `#vulnerability`, `#enterprise IT`

---

<a id="item-tech-news-4"></a>
### [FBI Reportedly Breached Again, Targeting Nationwide Police Database](https://www.bleepingcomputer.com/news/security/fbi-reportedly-hacked-again-this-time-targeting-nationwide-police-database/) ⭐️ 7.0/10

FBI systems have reportedly suffered a cyber breach for the second time in two months. The intrusion targeted the agency&\#x27;s National Crime Information Center \(NCIC\), a critical nationwide database utilized to share criminal justice and operational data across local, state, and federal law enforcement agencies. Specific details regarding the extent of compromised records or the intrusion vector have not yet been disclosed.

rss · BleepingComputer · Nov 21, 14:26

**「Background」** The National Crime Information Center \(NCIC\) operates as a central computerized index that enables local, state, and federal law enforcement agencies nationwide to share criminal justice and operational data.

**Tags**: `#cybersecurity`, `#data breach`, `#government IT`, `#infosec`

---

<a id="item-tech-news-5"></a>
### [OpenRouter Drops Three Providers and 125 Endpoints Following Prompt Data Thefts](https://thehackernews.com/2026/11/openrouter-drops-3-providers-after.html) ⭐️ 7.0/10

AI gateway OpenRouter removed three hosting providers and stripped 125 endpoints of Zero Data Retention eligibility after Dragos researchers uncovered widespread, undetected theft of prompt data across multiple third-party inference providers. Using two million canary-seeded prompts between July and November, researchers found that attackers intercepted traffic—including requests marked for Zero Data Retention and rejected queries—to extract and exploit AWS keys, clone private repositories, and test credentials. While OpenRouter stated its own systems were not breached, provider disclosures from Phala, Together AI, and Novita detailed separate incidents involving server compromise, GitHub credential leaks, and unauthorized traffic routing to external model APIs.

rss · The Hacker News · Nov 22, 05:06

**「Background」** AI routing services allow developers to access multiple third-party model hosts through a unified API, often advertising Zero Data Retention settings to prevent prompt storage. To audit whether these privacy commitments hold across multi-hop inference supply chains, researchers at Dragos seeded approximately two million test prompts with trackable canary tokens and unique credentials between July and November 2026.

**「Impact」** Developers and organizations routing inference through affected providers—including those utilizing Zero Data Retention—must rotate any API keys, credentials, or secrets included in their prompts, while users directing requests to Phala&\#x27;s DeepSeek V4 Flash 0731 between October 21 and November 8 must treat all transmitted request data as exposed.

<details><summary>References</summary>
<ul>
<li><a href="https://www.dragos.com/blog/ai-supply-chain-security-canary-tokens">AI Supply Chain Security: What Canary Tokens Found | Dragos ...</a></li>
<li><a href="https://www.rescana.com/post/dragos-canary-tokens-compromised-ai-inference-providers-what-ai-router-customers-should-do-now">Dragos Canary Tokens Expose Compromised AI Inference ...</a></li>

</ul>
</details>

**Tags**: `#ai security`, `#data breach`, `#openrouter`, `#llm inference`, `#privacy`

---

<a id="item-tech-news-6"></a>
### [Ghostscript Sandbox-Escape Flaw Allows Remote Code Execution via Common File Uploads](https://thehackernews.com/2026/11/researchers-demonstrate-ghostscript.html) ⭐️ 7.0/10

Security firm pwn.ai demonstrated remote code execution via CVE-2026-125396, a font-loading use-after-free vulnerability in Ghostscript that bypasses the \`-dSAFER\` sandbox. Although classified as a local flaw, researchers triggered it remotely across roughly ten applications—including Roundcube webmail, Debian 13 print queues, and WordPress plugins—because libraries like ImageMagick, Pillow, and libvips delegate disguised PostScript or EPS files to Ghostscript without direct application calls. Artifex resolved the issue in Ghostscript version 10.08.0 on September 8, and there are currently no reports of exploitation in the wild.

rss · The Hacker News · Nov 22, 05:03

**「Background」** Ghostscript relies on its \`-dSAFER\` sandbox mode to prevent untrusted PostScript documents and PDFs from executing arbitrary operating system commands or accessing unauthorized files during rendering.

**「Impact」** System administrators and developers must verify and update Ghostscript installations across container images and application bundles, as distribution patching remains uneven and host OS package updates will not remediate isolated or containerized renderers.

**Tags**: `#cybersecurity`, `#vulnerability`, `#ghostscript`, `#software engineering`

---