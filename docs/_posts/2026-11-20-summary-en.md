---
layout: default
title: "Horizon Summary: 2026-11-20 (EN)"
date: 2026-11-20
lang: en
---

> From 132 items, 14 important content pieces were selected

---

**Technology News**
1. [PostgreSQL 19 Adds WAIT FOR LSN for Read-Your-Writes Replica Consistency](#item-tech-news-1) ⭐️ 9.0/10
2. [Palo Alto Networks Details Product Impact from Critical Java Vulnerability CVE-2026-114938](#item-tech-news-2) ⭐️ 8.0/10
3. [Critical &\#x27;NGINX2Root&\#x27; Vulnerabilities Enable Remote Code Execution and Server Takeover](#item-tech-news-3) ⭐️ 8.0/10
4. [Broadcom Patches Critical VMware vCenter Zero-Day Authentication Bypass Vulnerability](#item-tech-news-4) ⭐️ 8.0/10
5. [Google Launches Tool Retrieval Preview in Gemini API to Defer Parameter Schemas](#item-tech-news-5) ⭐️ 7.0/10
6. [Check Point Research Outlines Gatekeeper Asymmetry Doom Principle for Security Defenses](#item-tech-news-6) ⭐️ 7.0/10
7. [F5 Releases Emergency Patches for Five Critical BIG-IP Flaws](#item-tech-news-7) ⭐️ 7.0/10
8. [PHP Releases Security Updates Fixing 18 Vulnerabilities Including Critical RCE Flaws](#item-tech-news-8) ⭐️ 7.0/10
9. [Drupal Patches Critical Remote Code Execution Vulnerability](#item-tech-news-9) ⭐️ 7.0/10
10. [Armory Castle Exploited VMware vCenter Zero-Day CVE-2026-123890 for Admin Access](#item-tech-news-10) ⭐️ 7.0/10
11. [PHP Releases Patches for phpAfterShell Session Flaw CVE-2026-126714](#item-tech-news-11) ⭐️ 7.0/10
12. [AWS Marketplace Launches x402-Based Agentic Payments via Bedrock AgentCore](#item-tech-news-12) ⭐️ 7.0/10
13. [AWS Lambda Extends On-Demand Event Function Timeout to 30 Minutes](#item-tech-news-13) ⭐️ 7.0/10
14. [ARMORY CASTLE Exploits VMware vCenter Vulnerability CVE-2026-123890](#item-tech-news-14) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [PostgreSQL 19 Adds WAIT FOR LSN for Read-Your-Writes Replica Consistency](https://simonwillison.net/2026/Nov/19/postgresql-19/) ⭐️ 9.0/10

PostgreSQL 19 has been released, introducing a new WAIT FOR LSN command that provides read-your-writes consistency across standby replicas. A session connected to a standby can use WAIT FOR LSN with a target Log Sequence Number \(LSN\) from the primary to pause execution until the replica has replayed the corresponding write-ahead log. The command also supports an optional timeout parameter that raises an error if the standby fails to catch up within the specified duration.

rss · Simon Willison · Nov 19, 20:43

**「Background」** In asynchronous database replication, read queries routed to standby replicas can return stale data if the replica has not yet applied the primary node&\#x27;s latest write-ahead logs. Systems handling read-after-write workflows previously had to route immediate reads back to the primary or implement custom replica-lag tracking mechanisms.

**「Impact」** Developers routing read traffic to standby replicas can now track write positions using functions like pg\_current\_wal\_insert\_lsn\(\) and guarantee that subsequent queries on standbys see their own prior updates without relying on custom polling logic.

**Tags**: `#PostgreSQL`, `#databases`, `#open source`, `#software engineering`

---

<a id="item-tech-news-2"></a>
### [Palo Alto Networks Details Product Impact from Critical Java Vulnerability CVE-2026-114938](https://security.paloaltonetworks.com/CVE-2026-114938) ⭐️ 8.0/10

Palo Alto Networks has released a security advisory evaluating the impact of CVE-2026-114938, a critical buffer-overflow vulnerability in the HotSpot JVM&\#x27;s AVX-512 VBMI-optimized Base64 decoder. The flaw affects Oracle Java SE, Oracle GraalVM, and OpenJDK on x86-64 CPUs with hardware Base64 intrinsics enabled, allowing an unauthenticated remote attacker to trigger an out-of-bounds heap write and potentially execute code via crafted Base64 input. Several on-premises products require immediate upgrades—including Idira Privilege Threat Analytics, Remote Access Connector, and Secure Access with an HTML5 Gateway—while PAN-OS-based appliances remain unaffected and backend SaaS products are being patched directly.

rss · Palo Alto Networks Security · Nov 19, 23:00

**「Background」** To accelerate data processing, the HotSpot JVM&\#x27;s JIT compiler replaces portable \`java.util.Base64\` decoding logic with vectorized hardware intrinsics when executing on supported x86-64 CPUs with AVX-512 VBMI instructions. The upstream flaw, tracked as CVE-2026-114938, stems from a heap out-of-bounds write in this native decoding path across Oracle Java SE, Oracle GraalVM, and OpenJDK when parsing untrusted, crafted inputs.

**「Impact」** Administrators managing affected on-premises deployments must upgrade components such as Idira Privilege Threat Analytics to version 15.2.3 or 14.6.4 and Remote Access Connector to version 1.1.1002202 or later, as no workarounds exist for this vulnerability.

<details><summary>References</summary>
<ul>
<li><a href="https://security.paloaltonetworks.com/CVE-2026-114938">CVE-2026-114938 Portfolio Status: Impact of Java ...</a></li>
<li><a href="https://computingforgeeks.com/java4shell-cve-2026-114938/">Java4Shell CVE-2026-114938: Patch Vulnerable OpenJDK ...</a></li>

</ul>
</details>

**Tags**: `#java`, `#vulnerability`, `#security`, `#jvm`, `#openjdk`

---

<a id="item-tech-news-3"></a>
### [Critical &\#x27;NGINX2Root&\#x27; Vulnerabilities Enable Remote Code Execution and Server Takeover](https://www.bleepingcomputer.com/news/security/critical-nginx-nginx2root-bugs-let-attackers-hijack-servers/) ⭐️ 8.0/10

Security researchers have identified two critical vulnerabilities in NGINX dubbed &\#x27;NGINX2Root&\#x27; that permit unauthenticated remote code execution on vulnerable web servers. When chained with a Linux kernel vulnerability, the flaws allow attackers to achieve full root-level control over affected systems. Detailed technical conditions and affected version boundaries remain limited in the immediate disclosure.

rss · BleepingComputer · Nov 19, 14:57

**「Background」** NGINX operates as a web server and reverse proxy where worker processes execute network request handling under restricted user privileges. Chaining remote code execution vulnerabilities in services like NGINX with separate local privilege escalation bugs—such as Linux kernel flaws—enables attackers to break out of worker process isolation and achieve full root compromise.

**「Impact」** System administrators running affected NGINX web servers must patch the vulnerabilities immediately to prevent unauthenticated remote attackers from executing arbitrary code and escalating privileges to root.

<details><summary>References</summary>
<ul>
<li><a href="https://www.getastra.com/blog/security-advisory/nginx2root/">nginx2root: Five nginx RCE Flaws and a Kernel Bug (CVE-2026 ...</a></li>
<li><a href="https://www.bitsight.com/blog/nginx2root-cve-2026-123007-five-nginx-vulnerabilities">NGINX2Root: Exposure Details &amp; Fixes for All 5 nginx CVEs</a></li>

</ul>
</details>

**Tags**: `#security`, `#nginx`, `#vulnerabilities`, `#linux`, `#systems engineering`

---

<a id="item-tech-news-4"></a>
### [Broadcom Patches Critical VMware vCenter Zero-Day Authentication Bypass Vulnerability](https://thehackernews.com/2026/11/critical-vmware-vcenter-flaw-cvss-98.html) ⭐️ 8.0/10

Broadcom has released security patches addressing a critical CVSS 9.8 authentication bypass vulnerability \(CVE-2026-123890\) in the VMware Directory Service component of VMware vCenter Server. The flaw enables remote attackers with network access to gain unauthorized administrative access without valid credentials. Affected products include vCenter versions 8.0, 9.0, and 9.1, as well as deployments embedded in VMware Cloud Foundation, vSphere Foundation, and Telco Cloud stacks. Google&\#x27;s threat intelligence team reported that an espionage actor tracked as Armory Castle actively exploited the flaw as a zero-day starting in September 2026 before patches became available.

rss · The Hacker News · Nov 19, 15:11

**「Background」** vCenter serves as the centralized management plane for virtual machines and ESXi hosts across enterprise VMware deployments. This incident marks the second critical CVSS 9.8 authentication bypass discovered in the VMware Directory Service in 2026, following the disclosure and remediation of CVE-2026-59309 in July.

**「Impact」** Because Broadcom provides no software workarounds and the update cannot be applied via Quick Patch, administrators must execute a full emergency update. Additionally, applying vCenter 8.0 U3m or 9.0.2.0200 creates a &quot;Back-in-Time&quot; upgrade conflict that blocks subsequent upgrades to VMware Cloud Foundation 9.1.1 unless systems are upgraded to 9.1.1 first or administrators defer until VCF 9.1.2 is available.

**Tags**: `#cybersecurity`, `#vulnerability`, `#vmware`, `#virtualization`, `#system administration`

---

<a id="item-tech-news-5"></a>
### [Google Launches Tool Retrieval Preview in Gemini API to Defer Parameter Schemas](https://blog.google/innovation-and-ai/technology/developers-tools/gemini-api-tool-retrieval/) ⭐️ 7.0/10

Google launched Tool Retrieval in preview within the Gemini Interactions API, allowing AI agents to keep tool libraries on standby while deferring parameter schemas until needed. Developers configure this by adding a \`tool\_search\` tool and setting \`defer\_loading: true\` on functions or remote Model Context Protocol \(MCP\) servers, keeping full parameter definitions out of context until the model requests them by name within a single request. Alternatively, developers can specify \`&quot;execution&quot;: &quot;client&quot;\` to handle search across external registries or custom permissions at the cost of an added round trip. The preview is compatible with Gemini 3.6 and later models, including Gemini 4 variants, and incurs standard model token pricing without separate feature fees.

rss · Google AI Blog · Nov 19, 18:00

**「Background」** In standard large language model tool calling, passing full parameter schemas for dozens or hundreds of tools in every prompt consumes substantial context window space, increases input token overhead, and can degrade tool selection accuracy. Developers managing large tool suites typically had to manually filter or index tools before sending requests to the API.

**「Impact」** Developers connecting large toolsets or MCP servers can reduce prompt token overhead, improve tool-selection accuracy, and maintain stable prompt prefix caches by deferring unused tool schemas.

**Tags**: `#Gemini API`, `#AI Agents`, `#Tool Calling`, `#LLM APIs`, `#Software Engineering`

---

<a id="item-tech-news-6"></a>
### [Check Point Research Outlines Gatekeeper Asymmetry Doom Principle for Security Defenses](https://research.checkpoint.com/2026/30-years-of-gatekeeper-asymmetry-doom-the-paradox-that-makes-powerful-llms-more-vulnerable/) ⭐️ 7.0/10

Check Point Research published an analysis formulating the &quot;gatekeeper asymmetry doom&quot; principle, which asserts that security vetting inevitably fails when a gatekeeper has strictly less computational power than the target system processing the adversarial input, unless it leverages an asymmetric hard problem such as cryptography. The analysis illustrates this failure dynamic across thirty years of infosec paradigms, from static hashing and YARA pattern matching to sandbox evasions and AI guardrails bypassed by techniques like PuzzleMask. To mitigate these vulnerabilities, the researchers advise defenders to systematically narrow capability gaps by upgrading gatekeeper capacity or deploying frontier reasoning models with code execution and scaffolding.

rss · Check Point Research · Nov 19, 13:19

**「Background」** AI deployments frequently rely on external guardrail models to inspect incoming prompts and filter harmful instructions before queries reach a primary model. Check Point Research previously demonstrated this vulnerability with its PuzzleMask technique, which encoded adversarial instructions into natural prose that simple filtering classifiers could not distinguish from benign input.

**「Impact」** Security architects relying on lightweight static filters or lower-capability external guardrails to sanitize prompts for powerful frontier models face systematic circumvention unless they upgrade their defensive systems to match the target&\#x27;s reasoning capacity.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.checkpoint.com/security/puzzlemask-the-prompt-injection-hiding-in-plain-sight/">PuzzleMask: The Prompt Injection Hiding in Plain Sight</a></li>

</ul>
</details>

**Tags**: `#AI Safety`, `#LLM Security`, `#Cybersecurity`, `#AI Guardrails`

---

<a id="item-tech-news-7"></a>
### [F5 Releases Emergency Patches for Five Critical BIG-IP Flaws](https://www.bleepingcomputer.com/news/security/f5-releases-emergency-patches-for-critical-big-ip-rce-flaws/) ⭐️ 7.0/10

F5 has issued emergency security updates addressing five critical vulnerabilities affecting its BIG-IP networking devices. The flaws could allow threat actors to achieve remote code execution or induce denial-of-service states on vulnerable systems.

rss · BleepingComputer · Nov 20, 10:57

**「Background」** Horizon&\#x27;s November 19 digest reported that F5 disclosed critical CVSS 9.8 vulnerabilities across BIG-IP data plane components, including the Traffic Management Microkernel \(TMM\). The flaws allow unauthenticated attackers to terminate TMM processes or potentially achieve code execution under specific virtual server configurations.

**「Impact」** Administrators and security teams managing F5 BIG-IP appliances must apply the emergency patches to protect their enterprise infrastructure from potential unauthorized remote code execution and service disruptions.

<details><summary>References</summary>
<ul>
<li><a href="https://www.secpod.com/learn/security-research/six-critical-f5-big-ip-vulnerabilities-expose-systems-to-remote-code-execution-and-do-s-attacks">Six Critical F5 BIG-IP Flaws Enable DoS and Potential RCE</a></li>
<li><a href="https://thehackernews.com/2026/11/f5-warns-6-critical-big-ip-flaws-can.html">2026-11-19 — F5 Discloses Six Critical BIG-IP Buffer Overflows Affecting Data Plane Traffic</a></li>

</ul>
</details>

**Tags**: `#computer security`, `#vulnerabilities`, `#enterprise infrastructure`, `#remote code execution`

---

<a id="item-tech-news-8"></a>
### [PHP Releases Security Updates Fixing 18 Vulnerabilities Including Critical RCE Flaws](https://www.bleepingcomputer.com/news/security/php-security-updates-fix-18-flaws-including-critical-rce-bugs/) ⭐️ 7.0/10

The PHP Foundation has released security updates addressing 18 vulnerabilities across all supported releases, fixing critical remote code execution, use-after-free, and privilege escalation defects. Patches have been issued in PHP versions 8.2.36, 8.3.37, 8.4.28, 8.5.13, and 8.6.0. Several high-severity bugs carry CVSS scores of 9.2, including CVE-2026-126714, a time-of-check time-of-use flaw in file-based session handling that allows arbitrary deserialization when combined with interrupted writes.

rss · BleepingComputer · Nov 19, 16:28

**「Background」** PHP processes and serializes session data to disk by default, reconstructing server-side state whenever an application initiates a session. Prior to these updates, unexpected worker terminations during session write operations could leave spliced, corrupted session files on disk that the deserialization parser subsequently treated as valid object data.

**「Impact」** Administrators running affected PHP installations must upgrade to patched point releases or disable session upload progress as a temporary mitigation if immediate updates cannot be deployed.

**Tags**: `#php`, `#security`, `#vulnerabilities`, `#remote-code-execution`

---

<a id="item-tech-news-9"></a>
### [Drupal Patches Critical Remote Code Execution Vulnerability](https://www.bleepingcomputer.com/news/security/drupal-patches-critical-rce-flaw-warns-exploits-may-surface-quickly/) ⭐️ 7.0/10

The Drupal Security Team has released a security patch addressing a critical remote code execution vulnerability that allows attackers to fully take over vulnerable websites. Drupal warned site administrators that functional exploits may surface quickly following the disclosure. The update requires immediate patching by teams running affected Drupal deployments.

rss · BleepingComputer · Nov 19, 13:08

**「Background」** The vulnerability, tracked under advisory SA-CORE-2026-017 and designated CVE-2026-132165, stems from an issue where attackers under specific conditions can leverage the Drupal installer to reinstall the platform, potentially leading to remote code execution. It was identified by Anthropic&\#x27;s OSS Scanner and assigned a critical 18/25 severity rating by the Drupal Security Team.

**「Impact」** Site administrators and engineering teams managing Drupal installations must deploy the patch promptly to prevent potential server takeover via remote code execution.

<details><summary>References</summary>
<ul>
<li><a href="https://www.drupal.org/sa-core-2026-017">Critical - Remote code execution - SA-CORE-2026-017 - Drupal</a></li>
<li><a href="https://windowsforum.com/news/drupal-patches-critical-installer-rce-cve-2026-132165-updates-and-mitigation.453213/">Drupal Patches Critical Installer RCE CVE-2026-132165 ...</a></li>

</ul>
</details>

**Tags**: `#security`, `#vulnerabilities`, `#drupal`, `#open source`, `#remote code execution`

---

<a id="item-tech-news-10"></a>
### [Armory Castle Exploited VMware vCenter Zero-Day CVE-2026-123890 for Admin Access](https://thehackernews.com/2026/11/china-linked-hackers-exploit-critical.html) ⭐️ 7.0/10

Suspected China-nexus threat actor Armory Castle exploited an unauthenticated authentication bypass zero-day vulnerability in VMware vCenter Server, tracked as CVE-2026-123890 with a CVSS score of 9.8, starting in early September 2026. The flaw allows remote attackers to disclose Secure Remote Password session keys over DCE/RPC, establish an authenticated administrator session, and execute commands or exfiltrate databases using a custom Go utility named BONESAW. Patches were released on November 19, 2026, across supported products, including VMware Cloud Foundation versions 9.1.1.0200, 9.0.2.0200, and 5.2.5, as well as vCenter Server 8.0 U3m.

rss · The Hacker News · Nov 20, 09:38

**「Background」** VMware vCenter Server manages virtualization environments using the VMware Directory Service \(\`vmdird\`\) and Single Sign-On \(SSO\) interfaces for central access and identity controls. Threat group Armory Castle, formerly tracked as UNC5221, previously targeted virtualization and enterprise edge infrastructure, including using VMware logging vulnerabilities and Ivanti appliances to facilitate network intrusions.

**「Action Required for Enterprise Administrators」** System administrators must immediately upgrade affected vCenter Server and Cloud Foundation deployments to the patched releases and audit internal environments for unauthorized SSH enablement, newly created administrator accounts, or lateral access originating from port 2012.

**Tags**: `#cybersecurity`, `#vulnerability`, `#vmware`, `#zero-day`, `#system administration`

---

<a id="item-tech-news-11"></a>
### [PHP Releases Patches for phpAfterShell Session Flaw CVE-2026-126714](https://thehackernews.com/2026/11/phpaftershell-explained-how-hackers.html) ⭐️ 7.0/10

PHP maintainers have released security updates—versions 8.2.36, 8.3.37, 8.4.28, 8.5.13, and 8.6.0—to fix CVE-2026-126714, a CVSS 9.2 vulnerability dubbed phpAfterShell in the default file-based session handler. The flaw enables remote code execution when an attacker halts a session write halfway through—such as via an out-of-memory termination during file upload progress tracking—causing old and new serialized session data to splice together and instantiate arbitrary objects when paired with an application gadget chain. The fixed releases resolve the issue by emptying session files prior to each write and also disable session upload progress by default. Neither the maintainers nor reporting security firm Depthfirst have observed attacks in the wild.

rss · The Hacker News · Nov 19, 16:59

**「Background」** PHP&\#x27;s default file session handler serializes data without framing markers that signify a completed write, leaving files vulnerable to mid-write corruption if a process terminates abruptly. While earlier emergency patches addressed the related PHP2Shell vulnerability by restricting class loading during upload progress tracking, they did not alter the underlying session write mechanism that allowed incomplete data to persist on disk.

**「Impact」** Administrators must update to the patched PHP releases, as setting session.upload\_progress.enabled to 0 mitigates the upload-progress vector but does not protect against other application paths that write untrusted data into file-based sessions.

**Tags**: `#php`, `#vulnerability`, `#cybersecurity`, `#remote-code-execution`

---

<a id="item-tech-news-12"></a>
### [AWS Marketplace Launches x402-Based Agentic Payments via Bedrock AgentCore](https://aws.amazon.com/about-aws/whats-new/2026/11/marketplace-agentic-payments-agentcore/) ⭐️ 7.0/10

AWS Marketplace now supports programmatic, per-request payments for AI agents using the x402 protocol through AgentCore payments, a feature of Amazon Bedrock AgentCore. The capability allows agents to dynamically purchase paid APIs, content, and data in US dollars settled directly against an existing AWS bill, eliminating manual signups, separate API keys, and crypto wallets. Customers configure the AWS Marketplace payment connector in AgentCore payments, while sellers integrate the AWS Marketplace x402 SDK to charge agents on a per-request basis across all AWS regions where AgentCore payments is available.

rss · AWS Whats New · Nov 19, 21:30

**「Background」** Autonomous AI agents executing complex multi-step tasks often require access to external paid APIs, specialized datasets, or third-party web services mid-task. Traditionally, using these paid resources requires human intervention to manually create accounts, configure billing details, and generate API keys for each individual provider.

**「Impact」** Developers and organizations running autonomous agents can enforce budget guardrails, specify approved sellers, apply Private Marketplace policies, and audit autonomous purchases using standard AWS governance tools such as AWS CloudTrail and Cost Explorer.

**Tags**: `#AWS`, `#AI Agents`, `#Amazon Bedrock`, `#Agentic Payments`, `#Cloud Computing`

---

<a id="item-tech-news-13"></a>
### [AWS Lambda Extends On-Demand Event Function Timeout to 30 Minutes](https://aws.amazon.com/about-aws/whats-new/2026/11/aws-lambda-30-minute-ondemand-event-functions/) ⭐️ 7.0/10

AWS has doubled the maximum function execution timeout for on-demand Event Functions from 15 minutes to 30 minutes across synchronous, asynchronous, and event source mapping \(ESM\) invocations. The 30-minute limit also applies to synchronous invocations on Lambda Managed Instances, while asynchronous and ESM invocations on Managed Instances retain their existing 90-minute limit. The extended timeout is available immediately in all commercial AWS Regions and can be configured through the AWS Management Console, CLI, SDKs, CloudFormation, CDK, or SAM under standard Lambda pricing.

rss · AWS Whats New · Nov 19, 19:00

**「Lambda Execution Limits」** Since 2018, AWS Lambda has enforced a maximum execution limit of 15 minutes for standard on-demand functions, requiring workloads that exceed this threshold to be split into smaller tasks, coordinated via AWS Step Functions, or moved to container services like AWS Fargate. In September 2026, AWS introduced longer 90-minute execution windows specifically for asynchronous and event source mapping workloads running on Lambda Managed Instances.

**「Impact」** Developers running tasks such as AI inference, media transcoding, or long-running data processing can execute jobs for up to 30 minutes without needing architectural workarounds or splitting logic across multiple short-lived invocations.

**Tags**: `#AWS Lambda`, `#Serverless`, `#Cloud Computing`, `#Software Engineering`

---

<a id="item-tech-news-14"></a>
### [ARMORY CASTLE Exploits VMware vCenter Vulnerability CVE-2026-123890](https://cloud.google.com/blog/topics/threat-intelligence/armory-castle-exploits-vsphere/) ⭐️ 7.0/10

Mandiant and Google Threat Intelligence Group revealed that suspected PRC-nexus threat actor ARMORY CASTLE exploited CVE-2026-123890, an unauthenticated SRP-6a session key disclosure flaw in VMware vCenter Server over DCE/RPC. The vulnerability allows attackers to bypass remote authentication, establish an authenticated administrator@vsphere.local session, execute arbitrary commands, and extract data via the vCenter Server Directory Service RPC interface. Mandiant found the group used a custom Go utility named BONESAW as a zero-day in early September 2026 to extract LMDB databases and hijack SAML Single Sign-On credentials.

rss · Google Cloud · Nov 19, 14:00

**「Background」** VMware vCenter Server is a centralized virtual appliance used to manage ESXi host environments within VMware vSphere deployments. In this campaign, ARMORY CASTLE initially accessed networks via a zero-day in BeyondTrust Remote Support \(CVE-2026-102764\) before scanning internal networks for VMware services on ports such as 2012, 5480, and 9080.

**「Impact」** Enterprise infrastructure administrators running VMware vCenter Server must immediately apply Broadcom&\#x27;s security patches for CVE-2026-123890 and inspect systems for unauthorized administrator accounts, modified SAML STS tokens, and unexpected traffic to port 2012.

**Tags**: `#Cybersecurity`, `#Threat Intelligence`, `#VMware vSphere`, `#Vulnerability Exploitation`

---