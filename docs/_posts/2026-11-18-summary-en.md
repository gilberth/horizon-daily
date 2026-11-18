---
layout: default
title: "Horizon Summary: 2026-11-18 (EN)"
date: 2026-11-18
lang: en
---

> From 307 items, 20 important content pieces were selected

---

**Technology News**
1. [OpenAI Releases GPT-6.2 Astra and Sol with Reduced API Pricing](#item-tech-news-1) ⭐️ 8.0/10
2. [Critical OpenJDK Vulnerability &\#x27;Java4Shell&\#x27; Enables Remote Code Execution on AVX-512 Systems](#item-tech-news-2) ⭐️ 8.0/10
3. [OpenAI GPT-6.2 Astra and Sol Are Generally Available on Amazon Bedrock](#item-tech-news-3) ⭐️ 8.0/10
4. [Simon Willison and Prime Radiant Release External Sandbox Servers for Coding Agents](#item-tech-news-4) ⭐️ 7.0/10
5. [Datasette Lite Rewritten with Service Workers and Pyodide](#item-tech-news-5) ⭐️ 7.0/10
6. [Microsoft Details Device Code Phishing Risks Targeting AI Coding Agents](#item-tech-news-6) ⭐️ 7.0/10
7. [Cisco Talos Analyzes Blockchain-Based Dead Drops for Resilient Malware C2](#item-tech-news-7) ⭐️ 7.0/10
8. [OPTIMJACK Campaign Compromised Optimizely CDN to Inject Malicious Scripts Across 178 Organizations](#item-tech-news-8) ⭐️ 7.0/10
9. [Microsoft Announces Windows Server 2028 with Enhanced Security Focus](#item-tech-news-9) ⭐️ 7.0/10
10. [Cloud Credentials Leaked in Public Docker Hub Images Are Exploited Within Seconds](#item-tech-news-10) ⭐️ 7.0/10
11. [Japan Takes Fugaku Supercomputer Offline Following Cyberattack](#item-tech-news-11) ⭐️ 7.0/10
12. [Researchers Hijack Popular Kokoro AI Model Account on Hugging Face](#item-tech-news-12) ⭐️ 7.0/10
13. [CISA Warns of Active Exploitation in Critical Puppet Enterprise RCE Vulnerability](#item-tech-news-13) ⭐️ 7.0/10
14. [CISA Urges Immediate Patching of Java4Shell JVM Flaw](#item-tech-news-14) ⭐️ 7.0/10
15. [Malicious PyPI Releases of Microsoft&\#x27;s Agent Framework Steal Cloud Credentials via Startup Hooks](#item-tech-news-15) ⭐️ 7.0/10
16. [Researchers Demonstrate Exploits Bypassing Telegram&\#x27;s Android Widget Sandbox](#item-tech-news-16) ⭐️ 7.0/10
17. [Oracle Prepares 11 Java SE Patches as Unconfirmed OpenJDK Flaw Emerges](#item-tech-news-17) ⭐️ 7.0/10
18. [Trigram Campaign Targets Developers Across 50 AI and Blockchain Brands with Infostealers](#item-tech-news-18) ⭐️ 7.0/10
19. [Researchers Detail iOS Audio Flaw That Bypassed Microphone Denials](#item-tech-news-19) ⭐️ 7.0/10
20. [AWS Interconnect Multicloud Connectivity with Microsoft Azure Reaches General Availability](#item-tech-news-20) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenAI Releases GPT-6.2 Astra and Sol with Reduced API Pricing](https://simonwillison.net/2026/Nov/17/gpt62-astra-and-sol/) ⭐️ 8.0/10

OpenAI has released GPT-6.2 Astra and GPT-6.2 Sol, accessible in the API as gpt-6.2-astra and gpt-6.2-sol. GPT-6.2 Astra is priced at $8 per million input tokens and $40 per million output tokens—an 80% discount over 6 Astra—with cached input dropped to $0.40 per million tokens. GPT-6.2 Sol maintains the previous generation&\#x27;s pricing of $2 per million input and $10 per million output tokens.

rss · Simon Willison · Nov 17, 22:38

**「Background」** OpenAI previously offered its frontier model GPT-6 Astra at $10 per million input tokens and $50 per million output tokens, alongside earlier iterations of its efficient Sol model priced at $2 per million input and $10 per million output tokens. Prompt caching has become a standard API mechanism to lower costs for repetitive or continuous agentic workflows by serving reused prompt prefixes at steep discounts.

**「Impact」** Developers running extended agentic sessions can lower operational costs due to the 60% reduction in Astra&\#x27;s prompt caching price from $1 to $0.40 per million tokens.

**Tags**: `#artificial intelligence`, `#large language models`, `#openai`, `#api pricing`

---

<a id="item-tech-news-2"></a>
### [Critical OpenJDK Vulnerability &\#x27;Java4Shell&\#x27; Enables Remote Code Execution on AVX-512 Systems](https://blog.talosintelligence.com/java4shell/) ⭐️ 8.0/10

A critical vulnerability tracked as CVE-2026-114938 and dubbed &quot;Java4Shell&quot; affects OpenJDK Java 17.0.6 and later, as well as Java 21, 25, 27, and specific GraalVM builds running on x86-64 processors that support AVX-512 VBMI. An unauthenticated attacker sending a malformed Base64 string ending with an extra &\#x27;=&\#x27; causes the optimized decoder to write 62 or 63 fixed bytes out of bounds, which security firm Calif demonstrated can achieve unauthenticated remote code execution on default installations of Jenkins, Jira, Confluence, Keycloak, JFrog Artifactory, and PingFederate. Oracle and the OpenJDK project have released official patches, while independent security labs have confirmed crashes and memory disclosure but have not yet independently reproduced full remote code execution.

rss · Cisco Talos · Nov 18, 01:53

**「Background」** To accelerate throughput, the JVM JIT-compiles frequently executed Base64 decoding routines into optimized implementations that leverage hardware vector extensions like AVX-512 VBMI on compatible Intel and AMD x86-64 processors. Because web and enterprise servers routinely decode Base64-encoded authentication headers, tokens, and artifacts before verifying credentials, incoming requests reach this decoder without requiring valid user authentication.

**「Impact」** Administrators running affected JVM versions on AVX-512 VBMI-capable Intel or AMD systems must apply vendor updates or apply the interim mitigation flag \`-XX:UseAVX=2\` on x86-64 JVM starts to disable AVX-512 execution until patches can be deployed.

**Tags**: `#Security`, `#Java`, `#OpenJDK`, `#Vulnerability`, `#Computer Systems`

---

<a id="item-tech-news-3"></a>
### [OpenAI GPT-6.2 Astra and Sol Are Generally Available on Amazon Bedrock](https://aws.amazon.com/about-aws/whats-new/2026/11/openai-gpt-6-2-astra-sol-amazon-bedrock/) ⭐️ 8.0/10

AWS announced the general availability of OpenAI&\#x27;s GPT-6.2 Astra and GPT-6.2 Sol models on Amazon Bedrock. GPT-6.2 Astra targets complex reasoning, multimodal analysis, and agentic workflows, featuring an optional Ultrafast mode designed for latency-sensitive applications. GPT-6.2 Sol is tailored for high-volume, cost-sensitive tasks such as software implementation, debugging, and document analysis, with both models accessible via the Bedrock console and supported APIs.

rss · AWS Whats New · Nov 17, 17:17

**「Background」** Amazon Bedrock provides managed API access to foundational models alongside enterprise security, access governance, and auditing controls. The GPT-6.2 lineup follows OpenAI&\#x27;s previous generation models on the platform, with GPT-6.2 Sol succeeding GPT-6.1 Sol for cost- and latency-sensitive recurring workflows.

**「Impact」** Developers and organizations using AWS can now deploy OpenAI&\#x27;s GPT-6.2 Astra and Sol models directly within their existing Amazon Bedrock environments, managing access and audit logging under AWS governance controls.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.aws.amazon.com/bedrock/latest/userguide/model-card-openai-gpt-6-2-sol.html">GPT-6.2 Sol - Amazon Bedrock - docs.aws.amazon.com</a></li>

</ul>
</details>

**Tags**: `#artificial intelligence`, `#Amazon Bedrock`, `#OpenAI`, `#large language models`, `#cloud computing`

---

<a id="item-tech-news-4"></a>
### [Simon Willison and Prime Radiant Release External Sandbox Servers for Coding Agents](https://simonwillison.net/2026/Nov/17/external-sandboxes-for-coding-agents/) ⭐️ 7.0/10

Simon Willison and AI research lab Prime Radiant introduced the &\#x27;external sandbox&\#x27; pattern, isolating agent-executed code inside a dedicated environment while the agent orchestrates from outside. To demonstrate the pattern, they released three server implementations providing a shared localhost API: external-sandbox-v86 \(Node.js with v86 running Alpine Linux in WebAssembly\), external-sandbox-container \(Python using Apple Containers with Alpine Linux\), and external-sandbox-quicksand \(Python using Microsoft&\#x27;s QEMU-based Quicksand library\). The implementations also include an optional HTTP/HTTPS allow-list proxy for network restrictions and a credential replacement mechanism that injects secrets without exposing them directly to the agent.

rss · Simon Willison · Nov 17, 22:52

**「Background」** AI coding agents frequently require running shell commands and scripts directly on host environments, creating severe security risks from unintended mistakes or prompt-injection attacks. To isolate untrusted workloads, emerging tools like Microsoft&\#x27;s Quicksand provide asynchronous Python interfaces that bundle QEMU and lightweight Linux virtual machines specifically tailored for agent execution.

**「Impact」** Developers using agents like Claude Code, Codex, or Pi can configure their tools to execute untrusted code through these local sandbox APIs, preventing prompt injection attacks or erroneous commands from altering host machines or exfiltrating credentials.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/microsoft/quicksand">GitHub - microsoft/quicksand: Quickly sandbox your AI agent.</a></li>

</ul>
</details>

**Tags**: `#AI Agents`, `#Sandboxing`, `#Security`, `#Software Engineering`

---

<a id="item-tech-news-5"></a>
### [Datasette Lite Rewritten with Service Workers and Pyodide](https://simonwillison.net/2026/Nov/17/datasette-lite/) ⭐️ 7.0/10

Simon Willison has released an architectural rewrite of Datasette Lite that runs the full server-side Python application client-side in the browser using Pyodide and service workers. Through URL parameters, users can configure specific Datasette git commits or PyPI versions, install plugins, load CORS-enabled databases, and select from 163 WebAssembly-compiled SQLite versions. The service worker intercepts requests for pages and static assets inside an iframe, routing them via session IDs to dedicated web workers so that each browser tab maintains independent state.

rss · Simon Willison · Nov 17, 16:48

**「Background」** Launched in 2022, the original Datasette Lite executed Python inside a WebAssembly Pyodide web worker and rendered screens by injecting returned HTML into the parent page with innerHTML. That approach prevented scripts from running and broke asset loading for JavaScript-dependent features and visualization plugins.

**「Impact」** Developers and contributors can reproduce bugs, verify fixes across distinct Datasette and SQLite versions, and share live demos with visual plugins via a single URL without deploying a dedicated web server.

**Tags**: `#WebAssembly`, `#Pyodide`, `#Python`, `#Datasette`, `#SQLite`

---

<a id="item-tech-news-6"></a>
### [Microsoft Details Device Code Phishing Risks Targeting AI Coding Agents](https://www.microsoft.com/en-us/security/blog/2026/11/17/the-risks-of-device-code-authentication-for-ai-coding-agents/) ⭐️ 7.0/10

Microsoft Security Research published proof-of-concept findings demonstrating how OAuth device code phishing can be used to compromise developer environments via AI coding agents such as GitHub Copilot CLI. In a controlled lab simulation, an attacker-initiated device authorization approved by a victim enabled researchers to steer active sessions, inject misleading context into agent memory, inspect cloud-synchronized session history, and access private repositories. Microsoft noted that these vectors exploit existing features operating as designed rather than unauthenticated vulnerabilities, and emphasized that the attacks have not been observed in the wild.

rss · Microsoft Security Blog · Nov 17, 15:00

**「OAuth Device Flow Phishing」** The OAuth 2.0 device authorization grant enables browserless tools, such as command-line interfaces, to authenticate by prompting users to enter a short verification code on a provider&\#x27;s website. Attackers exploit this mechanism through device code phishing by initiating the request themselves and tricking a victim into approving the code on the authentic login domain.

**「Impact」** Developers and organizations using CLI-based AI tools face potential unauthorized command execution and persistent context tampering if users approve attacker-generated device verification codes on legitimate service domains.

**Tags**: `#AI Security`, `#Software Engineering`, `#Authentication`, `#Phishing`

---

<a id="item-tech-news-7"></a>
### [Cisco Talos Analyzes Blockchain-Based Dead Drops for Resilient Malware C2](https://blog.talosintelligence.com/the-challenge-of-defending-against-bulletproof-dead-drops-on-public-blockchains/) ⭐️ 7.0/10

Threat actors are increasingly using public blockchains, including Bitcoin transactions, EVM smart contracts via EtherHiding, TRON wallets, and Solana memo programs, as immutable dead drops to host and update malware command-and-control configurations. Malware retrieves these encrypted endpoints into host memory via read-only remote procedure call \(RPC\) queries, evading traditional domain seizures, null-routing, and registrar takedowns. Because public ledgers cannot be altered or removed by hosting providers or law enforcement, the operational endpoints remain permanently available.

rss · Cisco Talos · Nov 18, 11:00

**「Background」** Malware operators have long relied on evasion techniques like domain generation algorithms, peer-to-peer overlays, and dead drop resolvers on third-party web platforms to prevent infrastructure takedowns, but defenders have consistently neutralized them through domain sinkholing and account suspensions. Techniques like EtherHiding emerged to counter these countermeasures by embedding encrypted C2 addresses directly into smart contracts on blockchains like Polygon, making resolution instructions tamper-proof and immune to conventional takedown requests.

**「Impact」** Enterprise security teams must shift away from static domain blocklists toward monitoring anomalous outbound JSON-RPC queries to public blockchain nodes and inspecting endpoint memory for decrypted C2 payloads.

<details><summary>References</summary>
<ul>
<li><a href="https://www.guidepointsecurity.com/blog/etherhiding-exposed-deep-dive/">EtherHiding Exposed: Inside a Blockchain-powered Malware</a></li>
<li><a href="https://www.chainalysis.com/blog/etherhiding-blockchain-dead-drops/">EtherHiding &amp; Blockchain Dead Drops: On-Chain Malware C2 ...</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#malware analysis`, `#blockchain`, `#command and control`, `#network security`

---

<a id="item-tech-news-8"></a>
### [OPTIMJACK Campaign Compromised Optimizely CDN to Inject Malicious Scripts Across 178 Organizations](https://unit42.paloaltonetworks.com/optimjack-supply-chain-attack/) ⭐️ 7.0/10

On November 16, 2026, an attacker exploited a vulnerability in Optimizely&\#x27;s Web Experimentation platform to inject malicious JavaScript into customer accounts&\#x27; custom Project JavaScript fields. The tampered code was served directly via Optimizely&\#x27;s legitimate CDN under its own security certificate to visitors across at least 178 organizations, targeting media, technology, and financial services sites. The injected payload executed cryptocurrency wallet swapping, payment card skimming from checkout forms, and delivery attempts of the Coruna and DarkSword exploit kits to iOS and iPadOS devices before Optimizely patched the flaw and removed the code on November 17.

rss · Palo Alto Unit 42 · Nov 17, 20:43

**「Background」** Modern websites routinely embed dynamic third-party scripts, analytics tags, and experimentation tools that run directly in end users&\#x27; browsers with the same privileges as first-party code. When an upstream vendor or its content delivery network is compromised, attackers can bypass site-level perimeter defenses by leveraging trusted domains and vendor certificates.

**「Impact」** Affected organizations must audit all project modifications made during the exposure window and treat payment card details entered into checkout forms on affected pages as potentially compromised.

**Tags**: `#supply chain security`, `#web development`, `#cybersecurity`, `#javascript`

---

<a id="item-tech-news-9"></a>
### [Microsoft Announces Windows Server 2028 with Enhanced Security Focus](https://www.bleepingcomputer.com/news/microsoft/microsoft-announces-windows-server-2028-with-hardened-security/) ⭐️ 7.0/10

Microsoft has announced Windows Server 2028, the upcoming major release of its enterprise server operating system, during the Ignite 2026 conference. The new release is planned to focus primarily on hardened security features for enterprise environments. Specific technical architecture specifications, hardware compatibility requirements, and a general availability timeline were not fully detailed in the initial announcement.

rss · BleepingComputer · Nov 18, 09:24

**「Background」** Microsoft periodically releases major Long-Term Servicing Channel \(LTSC\) versions of its enterprise server operating system, with preview channels offering early access to core platform updates. Windows Server 2028 follows these release cycles to update enterprise identity, management, automation, storage, and virtualization features.

<details><summary>References</summary>
<ul>
<li><a href="https://learn.microsoft.com/en-us/windows-server/get-started/whats-new-windows-server-2028">Windows Server 2028 Preview: New features | Microsoft Learn</a></li>

</ul>
</details>

**Tags**: `#Windows Server`, `#Operating Systems`, `#Enterprise Security`, `#Microsoft`

---

<a id="item-tech-news-10"></a>
### [Cloud Credentials Leaked in Public Docker Hub Images Are Exploited Within Seconds](https://www.bleepingcomputer.com/news/security/cloud-keys-leaked-in-docker-hub-images-are-stolen-within-seconds/) ⭐️ 7.0/10

Automated threat actors are actively monitoring public Docker Hub repositories, extracting and exploiting exposed credentials and access secrets in as little as eight seconds after an image is published. This automated harvesting targets sensitive cloud access keys inadvertently baked into container layers during builds. The rapid exploitation window leaves virtually no margin for manual remediation, underscoring the necessity of immediate secret revocation alongside automated pre-commit and CI/CD secret scanning.

rss · BleepingComputer · Nov 17, 21:27

**「Secret Exposure Risks in Container Registries」** Container images pushed to public registries such as Docker Hub frequently contain embedded secrets, including API tokens, cloud provider access keys, and private credentials inadvertently baked into image layers. Because registry feeds and public repositories are publicly inspectable, automated scanners can monitor new image pushes in real time to harvest sensitive data.

**「Immediate Risk and Remediation」** Developers and organizations accidentally publishing secrets to Docker Hub cannot rely on subsequent deletions or overwrites to prevent unauthorized access, making immediate secret revocation and automated pre-push secret scanning essential.

**Tags**: `#cloud-security`, `#docker`, `#devsecops`, `#secret-management`

---

<a id="item-tech-news-11"></a>
### [Japan Takes Fugaku Supercomputer Offline Following Cyberattack](https://www.bleepingcomputer.com/news/security/japan-takes-fugaku-supercomputer-offlline-after-cyberattack/) ⭐️ 7.0/10

Japan&\#x27;s RIKEN Center for Computational Science has taken the Fugaku supercomputer offline following a security breach. The operational shutdown halts access to the system while administrators investigate the intrusion and secure the high-performance computing infrastructure.

rss · BleepingComputer · Nov 17, 20:51

**「Background」** Fugaku, developed jointly by RIKEN and Fujitsu, is one of the world&\#x27;s most powerful supercomputers used extensively for scientific research, simulation, and academic workloads in Japan.

**「Impact」** Researchers and organizations utilizing Fugaku face suspended computational workloads and system downtime while the facility investigates and remediates the breach.

**Tags**: `#supercomputing`, `#cybersecurity`, `#hardware`, `#infrastructure`, `#high-performance computing`

---

<a id="item-tech-news-12"></a>
### [Researchers Hijack Popular Kokoro AI Model Account on Hugging Face](https://www.bleepingcomputer.com/news/security/researchers-hijack-hugging-face-account-for-popular-kokoro-ai-model/) ⭐️ 7.0/10

Security researchers successfully hijacked the Hugging Face repository for Kokoro, a widely used open-source text-to-speech AI model integrated into projects across Google, NVIDIA, AMD, Intel, and Amazon Web Services. The takeover was enabled by a lack of account ownership verification on the platform. The demonstration highlights an AI supply chain risk where malicious actors could potentially alter models depended on by major enterprise ecosystems.

rss · BleepingComputer · Nov 17, 18:21

**「Hugging Face Repository Security」** Open-source AI hubs such as Hugging Face serve as critical supply-chain foundations by hosting model weights and code dependencies integrated across major tech stacks. Security researchers have increasingly scrutinized these registries for platform-level authentication and ownership verification gaps that could expose downstream consumers to unauthorized takeovers or supply-chain poisoning.

**「Supply Chain Vulnerability」** Organizations relying on Kokoro—including downstream projects across major cloud and hardware vendors—risk running compromised code or weights if Hugging Face repositories can be hijacked without identity or ownership validation.

**Tags**: `#AI Security`, `#Supply Chain Security`, `#Hugging Face`, `#Machine Learning`, `#Text-to-Speech`

---

<a id="item-tech-news-13"></a>
### [CISA Warns of Active Exploitation in Critical Puppet Enterprise RCE Vulnerability](https://thehackernews.com/2026/11/hackers-exploiting-critical-puppet-rce.html) ⭐️ 7.0/10

CISA has added CVE-2026-115731, a critical deserialization flaw with a CVSS score of 9.4, to its Known Exploited Vulnerabilities catalog following reports of in-the-wild exploitation. The vulnerability allows an attacker possessing any CA-signed agent certificate to execute arbitrary code as the service user on the Puppet Server by sending a crafted rich-data type in a report PUT request. Perforce addressed the flaw across Puppet Enterprise versions 2026.0.1, 2025.12.1, and 2023.8.13, as well as Puppet Core 9.1.3 and 8.22.2, while OpenVox released fixes in Server versions 9.2.0 and 8.18.0.

rss · The Hacker News · Nov 18, 08:24

**「Background」** Puppet is a centralized infrastructure-as-code and configuration management platform where agents submit state reports to a central server authenticated via certificates. If a deployment&\#x27;s certificate authority is set to auto-sign requests without strong verification, unauthenticated network attackers can acquire the valid agent certificates necessary to reach authenticated server endpoints.

**「Impact」** Administrators must upgrade affected Puppet Enterprise, Puppet Core, or OpenVox installations immediately, with U.S. Federal Civilian Executive Branch agencies mandated to patch by December 1, 2026. Gaining remote code execution on the Puppet server allows attackers to extract CA signing keys, impersonate managed nodes, and potentially distribute malicious configurations or ransomware across the entire fleet.

**Tags**: `#security`, `#devops`, `#infrastructure`, `#vulnerability`

---

<a id="item-tech-news-14"></a>
### [CISA Urges Immediate Patching of Java4Shell JVM Flaw](https://thehackernews.com/2026/11/cisa-urges-immediate-patching-of.html) ⭐️ 7.0/10

The U.S. Cybersecurity and Infrastructure Security Agency \(CISA\) has issued an advisory urging organizations to patch CVE-2026-114938, dubbed &quot;Java4Shell,&quot; an out-of-bounds write vulnerability in the x86-64 HotSpot JVM&\#x27;s Base64 decoder. The flaw carries a CVSS score of 8.1 and enables unauthenticated remote code execution or denial-of-service via crafted Base64 input on systems running vulnerable OpenJDK builds from 17.0.6 onward, including versions 21 and 25. Vulnerability requires an x86-64 host or virtual machine supporting the AVX-512 VBMI CPU extension with Base64 intrinsics enabled. Patches have been released by Oracle and OpenJDK, and no in-the-wild exploitation has been observed to date.

rss · The Hacker News · Nov 18, 08:24

**「Background」** Modern HotSpot Java Virtual Machine releases implement architecture-specific vector intrinsics, such as AVX-512 VBMI instructions on x86-64 processors, to accelerate common tasks like Base64 decoding. Memory safety bugs within native JVM intrinsics can bypass Java&\#x27;s language-level runtime bounds checks and corrupt underlying process memory.

**「Impact」** Administrators must update unpatched OpenJDK runtimes across standalone hosts, container images, and bundled applications such as Keycloak, Jira, Confluence, and Jenkins, or apply temporary mitigations such as restricting the JVM to AVX2 via \`-XX:UseAVX=2\` on affected AVX-512 VBMI hardware.

**Tags**: `#cybersecurity`, `#java`, `#vulnerability`, `#jvm`, `#cisa`

---

<a id="item-tech-news-15"></a>
### [Malicious PyPI Releases of Microsoft&\#x27;s Agent Framework Steal Cloud Credentials via Startup Hooks](https://thehackernews.com/2026/11/attackers-compromise-microsofts-agent.html) ⭐️ 7.0/10

Threat actors compromised Microsoft&\#x27;s open-source \`agent-framework\` PyPI package on November 17, 2026, publishing malicious versions 1.26.1 and 1.26.2 to steal developer and cloud credentials. Once installed, the packages drop \`.pth\` files into \`site-packages\` that execute automatically on every Python launch, even if the library is never imported. The malware harvests local credentials, environment variables, GitHub Actions and Azure DevOps OIDC tokens, and Azure managed-identity tokens, exfiltrating them to a remote webhook before PyPI quarantined both versions.

rss · The Hacker News · Nov 18, 06:45

**「Background」** Microsoft&\#x27;s \`agent-framework\` is an open-source Python meta-package used to orchestrate AI agents, averaging around 190,000 monthly downloads. In Python environments, wheel packages can drop \`.pth\` path configuration files into \`site-packages\`, which the Python interpreter executes automatically on startup before user scripts or explicit imports run.

**「Impact」** Environments that installed \`agent-framework\` versions 1.26.1 or 1.26.2 must isolate affected systems, pin dependencies to safe version 1.26.0, rotate all local and cloud secrets, and audit Azure and GitHub Actions identity access logs for unauthorized activity.

**Tags**: `#supply-chain security`, `#python`, `#pypi`, `#ai agents`, `#cybersecurity`

---

<a id="item-tech-news-16"></a>
### [Researchers Demonstrate Exploits Bypassing Telegram&\#x27;s Android Widget Sandbox](https://thehackernews.com/2026/11/researchers-claim-two-rce-exploits-that.html) ⭐️ 7.0/10

Security firm NebuSec demonstrated two remote code execution exploits that escape the sandbox defenses introduced in Telegram for Android 13.2.2 \(7303\). Telegram had isolated its QuickJS bot widget engine into a separate process protected by a seccomp filter, but researchers bypassed these controls on a test server by exploiting an uncovered widget bug and chaining another with a kernel vulnerability. Technical reviews revealed that the published seccomp implementation leaves ioctl unfiltered and operates in audit mode, while Telegram has restricted widget distribution to approved bots on its live service.

rss · The Hacker News · Nov 17, 19:34

**「Background」** Telegram recently introduced interactive bot widgets whose JavaScript executes locally on client devices via the lightweight QuickJS engine. In response to initial reports of remote code execution, Telegram for Android version 13.2.2 isolated the engine into a dedicated process and implemented a seccomp filter to monitor and restrict operating system calls.

**「Impact」** Android users face potential device compromises through malicious bot widgets until complete sandbox enforcement is deployed, prompting security recommendations to avoid launching interactive widgets.

**Tags**: `#Security`, `#Vulnerability`, `#Android`, `#Telegram`, `#Remote Code Execution`

---

<a id="item-tech-news-17"></a>
### [Oracle Prepares 11 Java SE Patches as Unconfirmed OpenJDK Flaw Emerges](https://thehackernews.com/2026/11/oracle-to-patch-11-java-flaws-today-as.html) ⭐️ 7.0/10

Oracle scheduled security updates on November 17, 2026, to address 11 remotely exploitable vulnerabilities in Java SE with CVSS scores reaching up to 8.1. In parallel, security firm Calif claimed to discover an unconfirmed remote code execution flaw dubbed Java4Shell \(CVE-2026-114938\) reportedly carrying a 9.2 CVSS score in OpenJDK 17.0.6 and later. Independent analyses by Upwind and Equixly indicate the suspected flaw resides in Java&\#x27;s AVX-512 Base64 decoder on x86-64 hardware, likely resulting in virtual machine crashes rather than confirmed remote execution.

rss · The Hacker News · Nov 17, 15:17

**「Background」** Oracle maintains monthly security update schedules between its quarterly Critical Patch Updates to provide targeted fixes for Java products. The OpenJDK Base64 decoding optimizations leverage x86-64 AVX-512 VBMI instructions introduced across modern JDK releases to accelerate processing of untrusted base64 input streams.

**「Impact」** Administrators using affected Oracle Java builds—including Java 8, 11, 17, 21, 25, and 27—must prepare to deploy the updated release builds or test interim JVM flags such as -XX:-UseBASE64Intrinsics to disable the affected AVX-512 intrinsics.

**Tags**: `#Java`, `#OpenJDK`, `#Computer Security`, `#Vulnerabilities`

---

<a id="item-tech-news-18"></a>
### [Trigram Campaign Targets Developers Across 50 AI and Blockchain Brands with Infostealers](https://thehackernews.com/2026/11/trigram-campaign-impersonates-about-50.html) ⭐️ 7.0/10

A cyber threat campaign dubbed Trigram is impersonating approximately 50 brands across the AI and blockchain sectors to deliver infostealers and the Overlord remote access trojan to software developers. The campaign employs multiple attack vectors, including fake recruitment portals, malicious Visual Studio Code and Cursor extensions, and a forged commit in the antd-img-crop repository that triggers malware via an npm prebuild hook. Across Windows, macOS, and Linux targets, the payloads extract browser credentials, keychains, cryptocurrency wallets, SSH keys, and .env files.

rss · The Hacker News · Nov 17, 15:17

**「Background」** The activity shares operational similarities with North Korea-aligned clusters, including Kimsuky and UNK\_DeadDrop&\#x27;s &quot;Contagious Interview&quot; recruitment-lure operations. Prior investigations across 2026 documented related toolsets delivering the Overlord trojan through counterfeit Zoom installers and malicious coding assessments.

**「Impact」** Developers working in AI and cryptocurrency environments risk system compromise and credential theft if they run untrusted recruitment verification commands, install unverified editor extensions, or execute build hooks from unvetted repository commits.

**Tags**: `#cybersecurity`, `#supply-chain security`, `#software engineering`, `#malware`, `#infostealers`

---

<a id="item-tech-news-19"></a>
### [Researchers Detail iOS Audio Flaw That Bypassed Microphone Denials](https://thehackernews.com/2026/11/researchers-detail-iphone-flaw-that-let.html) ⭐️ 7.0/10

Security researchers have disclosed CVE-2026-65339, a patched vulnerability in Apple&\#x27;s audiomxd audio service that allowed installed sandboxed apps to record microphone audio even after users explicitly denied permission. The exploit relied on spoofing audit tokens to impersonate audiomxd, bypassing Transparency, Consent, and Control checks and in some test builds suppressing the system&\#x27;s orange recording indicator. Apple addressed the flaw across multiple operating systems, including iOS 26.6.1 and iPadOS 26.6.1 on August 17, by enforcing kernel-verified caller identities and restricting token overrides to apps holding a private entitlement.

rss · The Hacker News · Nov 17, 12:14

**「Background」** iOS delegates microphone access decisions to the Transparency, Consent, and Control \(TCC\) framework, which validates requesting process identities via audit tokens and triggers privacy alerts alongside visual recording indicators. In affected builds, the audiomxd daemon accepted an app-supplied audit token without verification, mistakenly treating external apps as the internal audio service itself.

**「Impact」** Because there are no user-facing settings to block this impersonation bypass and no historical logs to determine if an app previously recorded audio without consent, users and administrators must upgrade to iOS 26.6.1, iOS 18.7.11, or corresponding platform updates to ensure microphone protections remain enforced.

**Tags**: `#iOS Security`, `#Mobile Security`, `#Vulnerability Research`, `#Privacy`

---

<a id="item-tech-news-20"></a>
### [AWS Interconnect Multicloud Connectivity with Microsoft Azure Reaches General Availability](https://aws.amazon.com/about-aws/whats-new/2026/11/aws-announces-AWS-interconnect-multicloud-azure-ga/) ⭐️ 7.0/10

AWS announced the general availability of AWS Interconnect - multicloud support for Microsoft Azure, enabling managed private connectivity between workloads across both providers. The service is initially available in the us-east-1 \(N. Virginia\), ap-southeast-2 \(Sydney\), and eu-central-1 \(Frankfurt\) regions via the AWS Management Console, CLI, and API. This follows an August public preview and extends AWS Interconnect&\#x27;s existing multicloud private networking support alongside Google Cloud and Oracle Cloud Infrastructure.

rss · AWS Whats New · Nov 17, 16:00

**「Background」** Connecting workloads across different cloud service providers historically required customers to build and manage custom, multi-layered network architectures to route private traffic. Prior to this general availability release, Microsoft Azure introduced public preview support for AWS Interconnect in August, adopting the open specification already supported for Google Cloud and Oracle Cloud Infrastructure.

**「Impact」** Organizations operating hybrid AWS and Azure environments can provision direct private connections natively without designing and maintaining custom multi-layered networking infrastructure across the two cloud providers.

**Tags**: `#AWS`, `#Microsoft Azure`, `#Cloud Computing`, `#Computer Systems`, `#Networking`

---