---
layout: default
title: "Horizon Summary: 2026-11-24 (EN)"
date: 2026-11-24
lang: en
---

> From 77 items, 9 important content pieces were selected

---

**Technology News**
1. [Z.ai Releases GLM-5.4 Coding Model Featuring Looped Transformer Architecture](#item-tech-news-1) ⭐️ 7.0/10
2. [Ladybird Releases First Pre-Compiled Alpha for macOS and Linux](#item-tech-news-2) ⭐️ 7.0/10
3. [OpenRouter Drops Three AI Providers Over Prompt and Secret Leakage](#item-tech-news-3) ⭐️ 7.0/10
4. [Microsoft Azure API Management Classic Flaw Exploited to Steal Customer Secrets](#item-tech-news-4) ⭐️ 7.0/10
5. [OpenAI and Cisco Launch Shirudo to Mitigate Linux Exploits via Dynamic eBPF](#item-tech-news-5) ⭐️ 7.0/10
6. [CISA Adds Actively Exploited Flaws in N-able MailAssure and MONAI Label to KEV](#item-tech-news-6) ⭐️ 7.0/10
7. [Critical binary-parser Vulnerability Enables Code Injection via Parser Definitions](#item-tech-news-7) ⭐️ 7.0/10
8. [ScreenConnect Flaw CVE-2026-84869 Exploited in Attacks Hijacking MSP Technician Workstations](#item-tech-news-8) ⭐️ 7.0/10
9. [AWS WAF Adds Automated Discovery and Protection for LLM, MCP, and A2A Endpoints](#item-tech-news-9) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Z.ai Releases GLM-5.4 Coding Model Featuring Looped Transformer Architecture](https://simonwillison.net/2026/Nov/23/glm-54/) ⭐️ 7.0/10

Z.ai has launched GLM-5.4, a new model targeted at generalized coding tasks that implements a looped transformer architecture. The architecture executes a group of weight-shared layers across multiple iterations per forward pass, effectively deepening the network and refining hidden states without expanding the model&\#x27;s parameter count. GLM-5.4 is currently not released as open weights and requires a Z.ai Coding Plan subscription to access via their OpenAI-compatible API endpoint.

rss · Simon Willison · Nov 23, 23:40

**「Background」** Standard transformer architectures execute each layer exactly once per forward pass during token generation. In contrast, looped transformers reuse a subset of weight-shared layers across multiple iterations to refine internal hidden states, effectively increasing computational depth and reasoning capacity without expanding the model&\#x27;s total parameter count.

**「Impact」** Developers attempting to use GLM-5.4 via Z.ai&\#x27;s OpenAI-compatible API cannot access it under the standard API tier and must subscribe to the dedicated Coding Plan.

**Tags**: `#Machine Learning`, `#Transformer Architectures`, `#AI Code Generation`, `#Large Language Models`

---

<a id="item-tech-news-2"></a>
### [Ladybird Releases First Pre-Compiled Alpha for macOS and Linux](https://simonwillison.net/2026/Nov/23/ladybird/) ⭐️ 7.0/10

The Ladybird browser project has launched its first pre-compiled alpha release for macOS and Linux, allowing users to test the independent browser without compiling it from source. The project implements custom engines for HTML parsing, CSS, layout, JavaScript, and WebAssembly, while relying on external libraries like HarfBuzz, Skia, ffmpeg, and SQLite. The browser employs a multi-process architecture that isolates tabs into separate WebContent processes.

rss · Simon Willison · Nov 23, 21:46

**「Origins and Earlier Development」** Ladybird originated as an HTML viewer and browser project within SerenityOS, relying on its predecessor&\#x27;s custom components before evolving into a standalone browser. Ahead of the alpha binaries, the team relied heavily on AI coding agents such as Claude Code and Codex to accelerate development, including porting parts of its LibJS JavaScript engine to Rust.

**「Impact」** Users can evaluate client-side WebAssembly applications like Pyodide and ffmpeg directly, but web applications relying on newer APIs—such as ServiceWorker&\#x27;s startMessages—currently fail due to missing feature implementations.

**Tags**: `#web-browsers`, `#open-source`, `#systems-engineering`, `#ladybird`

---

<a id="item-tech-news-3"></a>
### [OpenRouter Drops Three AI Providers Over Prompt and Secret Leakage](https://www.bleepingcomputer.com/news/security/openrouter-drops-ai-providers-over-leaked-prompts-and-secrets/) ⭐️ 7.0/10

AI routing platform OpenRouter has removed three model providers after discovering violations of its data-handling policies that exposed user prompts and sensitive secrets. The action directly revokes routing access to these vendors to prevent further unauthorized exposure of user data across its API infrastructure.

rss · BleepingComputer · Nov 23, 20:00

**「Background」** OpenRouter operates an API routing platform that aggregates various third-party AI inference providers, offering features such as Zero Data Retention \(ZDR\) to ensure prompts and completions are not logged or stored. When upstream model hosting providers retain or expose request payloads, it undermines these privacy commitments and risks leaking proprietary user prompts and API secrets.

**「Impact」** Developers routing API traffic through OpenRouter risk exposure of user prompts and embedded secrets transmitted to the compromised inference providers, necessitating an immediate audit and rotation of any credentials or private data passed through affected endpoints.

<details><summary>References</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/openrouter-drops-3-providers-after.html">OpenRouter Drops 3 Providers After Researchers Catch Months ...</a></li>
<li><a href="https://www.unite.ai/openrouter-cuts-three-providers-after-ai-prompt-exposure-findings/">OpenRouter Cuts Three Providers After AI Prompt Exposure ...</a></li>
<li><a href="https://aviatrix.ai/threat-research-center/openrouter-drops-ai-providers-leaked-prompts-secrets-2026/">OpenRouter AI Provider Breach 2026: Leaked Prompts ...</a></li>

</ul>
</details>

**Tags**: `#artificial intelligence`, `#data security`, `#ai safety`, `#api infrastructure`

---

<a id="item-tech-news-4"></a>
### [Microsoft Azure API Management Classic Flaw Exploited to Steal Customer Secrets](https://www.bleepingcomputer.com/news/security/microsoft-azure-flaw-exploited-to-steal-customers-api-credentials/) ⭐️ 7.0/10

Microsoft warned customers that an actively exploited vulnerability in Azure API Management \(APIM\) Classic tiers allowed unauthorized access to management functionality and stored secrets, affecting organizations including Norwegian energy firms Equinor and Skagerak Energi. The flaw enabled attackers to search for access tokens, subscription keys, Named Values secrets, and client credentials associated with identity providers when instances were not configured according to documented best practices. Microsoft closed the access path on November 19, 2026, confirmed that v2 tier instances are unaffected, and issued guidance on November 21 urging customers to identify and rotate exposed credentials.

rss · BleepingComputer · Nov 23, 19:42

**「Background」** Azure API Management acts as an API gateway that enables organizations to publish, secure, and manage backend services while storing configuration secrets, identity provider keys, and tokens. Microsoft maintains legacy Classic tiers alongside newer v2 tiers, which feature distinct architecture and security boundaries.

**「Action Required for Classic APIM Users」** Organizations running Azure API Management on Classic tiers must audit and rotate exposed credentials—including Named Values secrets, identity provider keys, and direct management API tokens—because Microsoft&\#x27;s server-side fix closed the access path without invalidating previously compromised credentials.

<details><summary>References</summary>
<ul>
<li><a href="https://threataft.com/articles/azure-apim-classic-no-cve-norway-energy-secret-exposure">Azure APIM Flaw: No CVE, Secrets Out, Equinor Hit</a></li>

</ul>
</details>

**Tags**: `#cloud security`, `#azure`, `#api management`, `#cybersecurity`, `#vulnerability`

---

<a id="item-tech-news-5"></a>
### [OpenAI and Cisco Launch Shirudo to Mitigate Linux Exploits via Dynamic eBPF](https://thehackernews.com/2026/11/openai-and-cisco-unveil-ai-assisted.html) ⭐️ 7.0/10

OpenAI and Cisco have introduced Shirudo, an open-source Linux security runtime designed to let AI guardian agents generate and deploy dynamic eBPF mitigations without restarting systems. Built on Isovalent&\#x27;s Tetragon framework, the tool packages verified mitigations into cryptographically signed .bee files distributed via OCI registries and verified with TPMs before kernel loading. In an initial controlled test, OpenAI reported that a Codex-generated shield successfully blocked a Java4Shell exploit against an active Elasticsearch service without downtime.

rss · The Hacker News · Nov 24, 06:02

**「Background」** Extended Berkeley Packet Filter \(eBPF\) provides a sandboxed execution environment inside the Linux kernel, allowing administrators to inspect system events and enforce security policies without modifying kernel source code or rebooting. Shirudo adapts Tetragon, an eBPF-based security monitoring platform open-sourced by Isovalent in May 2022, to allow automated agent-generated bytecode injection.

**「Impact」** Linux systems administrators can apply interim, kernel-level behavioral blocks against newly disclosed vulnerabilities while awaiting upstream vendor patches, reducing exposure windows without interrupting live production workloads.

**Tags**: `#Linux`, `#eBPF`, `#Cybersecurity`, `#Artificial Intelligence`, `#Open Source`

---

<a id="item-tech-news-6"></a>
### [CISA Adds Actively Exploited Flaws in N-able MailAssure and MONAI Label to KEV](https://thehackernews.com/2026/11/hackers-exploit-n-able-mailassure-flaw.html) ⭐️ 7.0/10

The U.S. Cybersecurity and Infrastructure Security Agency \(CISA\) added two actively exploited critical vulnerabilities to its Known Exploited Vulnerabilities catalog: an authenticated server-side request forgery flaw in N-able MailAssure \(CVE-2026-134624, CVSS 9.3\) and an unauthenticated path traversal vulnerability in open-source medical imaging tool MONAI Label \(CVE-2026-133968, CVSS 9.8\). According to Amazon Integrated Security, autonomous AI agents powered by the CAIRN engine discovered and exploited the MONAI Label zero-day in roughly 11 minutes during a campaign against East Asian universities, using it to write a payload to sitecustomize.py and trigger an API endpoint to achieve root reverse-shell access. N-able reported that it remediated the single hosted server affected by CVE-2026-134624 after a November 16 service disruption, while Federal Civilian Executive Branch agencies have been directed to apply relevant fixes for both flaws by November 26, 2026.

rss · The Hacker News · Nov 24, 06:02

**「Autonomous Agent Exploitation」** Horizon&\#x27;s November 21 digest reported that Amazon Threat Intelligence observed a suspected Chinese-nexus threat actor using the Cairn AI framework to autonomously discover and exploit an unpatched zero-day vulnerability in an open-source medical imaging AI application. CISA maintains the Known Exploited Vulnerabilities catalog to mandate patching deadlines for federal agencies when security flaws see confirmed in-the-wild exploitation.

**「Impact」** Federal Civilian Executive Branch agencies must patch or remediate the exploited vulnerabilities across N-able MailAssure and MONAI Label deployments by November 26, 2026, while organizations running MONAI Label must upgrade to version 0.8.6 or newer to prevent unauthenticated remote code execution.

<details><summary>References</summary>
<ul>
<li><a href="https://aws.amazon.com/blogs/security/chinese-nexus-actors-cairn-ai-agents-found-a-zero-day-on-their-own/">2026-11-21 — Chinese-Nexus Actor&#x27;s Cairn AI Agents Autonomously Discovered and Exploited a Zero-Day</a></li>
<li><a href="https://www.tenable.com/cve/CVE-2026-133968">CVE-2026-133968 | Tenable®</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#vulnerabilities`, `#MONAI Label`, `#AI security`

---

<a id="item-tech-news-7"></a>
### [Critical binary-parser Vulnerability Enables Code Injection via Parser Definitions](https://thehackernews.com/2026/11/critical-binary-parser-flaw-enables.html) ⭐️ 7.0/10

A critical code injection vulnerability, CVE-2026-134814 with a CVSS score up to 9.2, was disclosed in the Node.js binary-parser library for versions prior to 2.3.1. The flaw occurs because string options passed to Context.generateOption\(\)—including length, lengthInBytes, key, tag, offset, and namely\(\) aliases—are inserted into generated JavaScript without adequate validation, enabling arbitrary code execution during parser compilation. Maintainer Keichi Takahashi resolved the issue in version 2.3.1 by validating these options as identifier paths, while clarifying that parsing untrusted binary data using trusted parser definitions is unaffected.

rss · The Hacker News · Nov 23, 13:22

**「Background」** The binary-parser library generates dynamic JavaScript parsing routines to process structured binary buffers. CVE-2026-134814 represents an incomplete remediation of CVE-2026-1245, a code injection flaw addressed in January 2026 that involved insufficient validation of field names and encoding parameters.

**「Impact」** Applications that construct parser definitions from untrusted input must upgrade to binary-parser 2.3.1 or later to prevent arbitrary JavaScript execution in the host Node.js process. In addition, existing definitions that used raw string expressions like &\#x27;len - 1&\#x27; will now be rejected and must be refactored into functions.

**Tags**: `#software security`, `#vulnerabilities`, `#nodejs`, `#javascript`, `#code injection`

---

<a id="item-tech-news-8"></a>
### [ScreenConnect Flaw CVE-2026-84869 Exploited in Attacks Hijacking MSP Technician Workstations](https://thehackernews.com/2026/11/hackers-exploit-critical-screenconnect.html) ⭐️ 7.0/10

Threat actors are actively exploiting a critical vulnerability in ConnectWise ScreenConnect, tracked as CVE-2026-84869 with a CVSS score of 9.9, to compromise managed service provider technician workstations without user interaction. The flaw allows an attacker-controlled guest session to push and execute malicious batch files directly on a connecting technician&\#x27;s host client without triggering any prompts. Researchers observed widespread blind scanning and targeted campaigns that install rogue ScreenConnect clients and persist payloads in the Windows Startup folder, prompting recommendations to update technician clients to version 26.6.5 or later.

rss · The Hacker News · Nov 23, 12:41

**「Background」** ConnectWise ScreenConnect remote support software typically allows technicians to manage file transfers and execution between their host machine and a client&\#x27;s guest system. In this attack vector, malicious actors register unauthorized guest sessions—often mimicking online machines or slipping into legitimate support sessions—to reverse the standard control flow and attack the technician upon connection.

**「Impact」** Organizations running ScreenConnect must immediately upgrade technician host clients to version 26.6.5 or higher, or mitigate risk by removing the TransferFiles permission across roles and session groups to prevent guest-initiated remote code execution and downstream credential exposure.

**Tags**: `#cybersecurity`, `#vulnerability`, `#remote code execution`, `#systems administration`, `#malware`

---

<a id="item-tech-news-9"></a>
### [AWS WAF Adds Automated Discovery and Protection for LLM, MCP, and A2A Endpoints](https://aws.amazon.com/about-aws/whats-new/2026/11/waf-ai-endpoint-discovery-protection/) ⭐️ 7.0/10

AWS has made automated AI endpoint discovery and protection generally available across AWS Organizations for LLM, Model Context Protocol \(MCP\), and Agent2Agent \(A2A\) endpoints behind Amazon CloudFront, Application Load Balancers, and Amazon API Gateway. Discovery operates agentlessly via the new API Gateway API Portal in 32 regions by analyzing traffic logs and service configurations to flag unprotected or shadow AI interfaces. Protection is handled by the new AWS WAF AI Security managed rule group across seven regions, which validates protocol compliance to block malformed MCP and A2A traffic while optionally querying Amazon Bedrock Guardrails&\#x27; InvokeGuardrailsCheck API to inspect for prompt injection, jailbreaks, and sensitive data leaks.

rss · AWS Whats New · Nov 23, 18:47

**「Background」** As organizations deploy agentic workflows and tool integrations, interfaces like Anthropic&\#x27;s Model Context Protocol \(MCP\) and Agent2Agent \(A2A\) specifications increasingly route external calls and system access through HTTP endpoints. Securing these interfaces traditionally requires custom API filtering or application-level middleware to identify undocumented shadow endpoints and prevent prompt injection or malformed payload attacks.

**「Impact」** Organizations deploying agentic workflows can identify undocumented or exposed MCP and A2A servers without deploying monitoring agents, but enabling Bedrock-backed content inspection incurs additional AWS WAF and separate Bedrock API usage fees.

**Tags**: `#AWS WAF`, `#Model Context Protocol`, `#AI Security`, `#Amazon Bedrock`, `#Cloud Infrastructure`

---