---
layout: default
title: "Horizon Summary: 2026-11-21 (EN)"
date: 2026-11-21
lang: en
---

> From 92 items, 12 important content pieces were selected

---

**Technology News**
1. [Chinese-Nexus Actor&\#x27;s Cairn AI Agents Autonomously Discovered and Exploited a Zero-Day](#item-tech-news-1) ⭐️ 8.0/10
2. [Linux KVM Flaw CVE-2026-99312 Enables Host Memory Access on AMD Systems](#item-tech-news-2) ⭐️ 8.0/10
3. [Levent Alpöge Claims AI-Assisted Proof of Riemann Hypothesis with Claude](#item-tech-news-3) ⭐️ 7.0/10
4. [AWS STS Introduces GetScopedCredentials API to Scope Down Existing Sessions](#item-tech-news-4) ⭐️ 7.0/10
5. [Palo Alto Networks Details Impact and Fixes for Critical NGINX Vulnerabilities](#item-tech-news-5) ⭐️ 7.0/10
6. [Palo Alto Networks Details Product Impact from Critical Java Vulnerability CVE-2026-114938](#item-tech-news-6) ⭐️ 7.0/10
7. [GnuPG Patches Critical Double-Free Flaw in GPGME Library](#item-tech-news-7) ⭐️ 7.0/10
8. [Signal Enables Screenshot Restrictions to Block Mobile AI Agents](#item-tech-news-8) ⭐️ 7.0/10
9. [CISA Adds Exploited Apache, Cisco, SAP, and VMware Flaws to KEV Catalog](#item-tech-news-9) ⭐️ 7.0/10
10. [AWS Launches Graviton5-Powered EC2 T9g Burstable Instances](#item-tech-news-10) ⭐️ 7.0/10
11. [AWS Lambda Adds Python 3.15 Support and First Web Functions Python Runtime](#item-tech-news-11) ⭐️ 7.0/10
12. [Google Announces General Availability of Ambient Networking for GKE](#item-tech-news-12) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Chinese-Nexus Actor&\#x27;s Cairn AI Agents Autonomously Discovered and Exploited a Zero-Day](https://aws.amazon.com/blogs/security/chinese-nexus-actors-cairn-ai-agents-found-a-zero-day-on-their-own/) ⭐️ 8.0/10

Amazon Threat Intelligence reported that a suspected Chinese-nexus threat actor deployed Cairn, an open-source autonomous AI penetration-testing framework, to independently uncover and exploit an unpatched zero-day vulnerability. Tasked with the objective to &quot;obtain shell access,&quot; the multi-agent system identified an API endpoint in an open-source medical imaging AI application, executed a path traversal attack to write arbitrary files in about 11 minutes, and achieved a root reverse shell by modifying sitecustomize.py. While operations targeting a hardened Redis instance and a university GPU cluster failed after hours of autonomous adaptation, the zero-day discovery enabled server compromise and network pivoting before AWS alerted maintainers to release a patch.

rss · AWS Security · Nov 20, 17:30

**「Background」** Cairn is an open-source AI framework designed to coordinate multiple autonomous agents to pursue plain-language penetration-testing goals across shared graphs of planned actions. Prior to Amazon&\#x27;s investigation, cybersecurity researchers had primarily tracked threat actors deploying Cairn for financially motivated attacks against online retailers and targeted operations against enterprise sectors.

**「Impact」** Defenders face drastically compressed triage windows from autonomous agents that can map APIs and exploit flaws in minutes, requiring security operations teams to implement automated response workflows rather than relying on manual per-alert triage.

<details><summary>References</summary>
<ul>
<li><a href="https://unit42.paloaltonetworks.com/cairn-framework-ai-autonomous-attacks/">Attackers Use Autonomous AI to Target Semiconductor, Defense ...</a></li>
<li><a href="https://brandefense.io/odin-research/what-is/cairn/">Cairn AI Pentest Framework: What It Is and How to Detect It</a></li>
<li><a href="https://gambit.security/blog-posts/autonomous-ai-agents-online-retailers-25-a-company">AI Agents Are Hacking Online Retailers for $25 a Company</a></li>

</ul>
</details>

**Tags**: `#artificial intelligence`, `#cybersecurity`, `#ai agents`, `#zero-day`, `#autonomous systems`

---

<a id="item-tech-news-2"></a>
### [Linux KVM Flaw CVE-2026-99312 Enables Host Memory Access on AMD Systems](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

A vulnerability in Linux KVM, tracked as CVE-2026-99312, allows an attacker with root access inside a guest virtual machine to read and write host physical memory on AMD systems with nested virtualization enabled. Security researchers verified the flaw by reading approximately 127 GB of host RAM from a cloud instance on DigitalOcean and writing 32 bytes into host kernel memory on a bare-metal AMD test server. Upstream patches have shipped in stable Linux kernel 7.3.5 and LTS releases 6.18.64 and 6.12.118, while Intel-based hosts remain unaffected.

rss · The Hacker News · Nov 20, 12:20

**「Background」** KVM isolates guest virtual machines using nested page tables to map guest addresses to physical host memory. The vulnerability was introduced by a 2022 patch for CVE-2022-3344 that failed to properly restore the outer VM&\#x27;s page-table pointer when an INIT signal halts a nested VM, leaving the pointer directed at a freed memory page that a guest can subsequently populate with arbitrary mappings.

**「Impact」** Self-hosted infrastructure operators running AMD KVM hosts must apply patched host kernels and reboot, or disable nested virtualization via the kvm\_amd module parameter nested=0, which breaks workloads that run nested virtual machines.

**Tags**: `#Linux Kernel`, `#KVM`, `#Cloud Computing`, `#Vulnerability`, `#Hardware Security`

---

<a id="item-tech-news-3"></a>
### [Levent Alpöge Claims AI-Assisted Proof of Riemann Hypothesis with Claude](https://simonwillison.net/2026/Nov/20/levent-alpoge/) ⭐️ 7.0/10

Mathematician Levent Alpöge published a statement claiming that he and Anthropic&\#x27;s Claude have discovered and formalized an unconditional proof of the Riemann Hypothesis, as well as the Generalized Riemann Hypothesis. Alpöge stated that the proof arguments have been formalized without assumptions and suggested the method could extend to the Extended Riemann Hypothesis. The claim remains an unverified announcement from a personal document, with no independent peer review or formal verification repository yet shared in the post.

rss · Simon Willison · Nov 20, 16:30

**「Background」** The Riemann Hypothesis is one of the most famous unsolved problems in mathematics, concerning the distribution of zeros of the Riemann zeta function and carrying deep implications for prime number theory. Formal verification involves encoding mathematical definitions and proofs into machine-checked systems to guarantee logical correctness without unverified assumptions.

**Tags**: `#artificial intelligence`, `#claude`, `#mathematics`, `#formal verification`

---

<a id="item-tech-news-4"></a>
### [AWS STS Introduces GetScopedCredentials API to Scope Down Existing Sessions](https://aws.amazon.com/blogs/security/scope-down-permissions-of-existing-sessions-using-aws-sts-getscopedcredentials/) ⭐️ 7.0/10

AWS Security Token Service \(AWS STS\) has launched the \`GetScopedCredentials\` API, enabling workloads to scope down existing temporary security credentials to reduced permissions, a shorter session duration, or both. The resulting credentials retain the caller&\#x27;s IAM identity while taking the mathematical intersection of the calling session&\#x27;s effective permissions and an inline scope-down policy of up to 2,048 characters. Requested session lifetimes cannot exceed the remaining duration of the parent session, and the operation can be called iteratively on downstream credentials.

rss · AWS Security · Nov 20, 22:57

**「Credential scoping in AWS STS」** AWS Identity and Access Management and Security Token Service typically manage temporary access through mechanisms like role assumption or federated sessions, where session policies define an intersection of permissions. Workloads running under assigned temporary credentials previously lacked a direct API to dynamically restrict their own existing session&\#x27;s permissions or lifetime before delegating tasks to sub-processes.

**「Impact」** Developers building autonomous AI agent workflows, CI/CD pipelines, or multi-tenant services can now dynamically enforce least privilege at runtime by passing narrowly scoped temporary credentials to untrusted sub-agents or worker tasks without provisioning separate IAM roles.

**Tags**: `#AWS`, `#Cloud Security`, `#IAM`, `#AI Agents`, `#Computer Systems`

---

<a id="item-tech-news-5"></a>
### [Palo Alto Networks Details Impact and Fixes for Critical NGINX Vulnerabilities](https://security.paloaltonetworks.com/CVE-2026-123633) ⭐️ 7.0/10

Palo Alto Networks published an advisory detailing the impact of two critical NGINX vulnerabilities, CVE-2026-123633 and CVE-2026-123007, on its on-premise PAN-OS firewalls and Panorama appliances. The flaws involve a use-after-free in HTTP/2 proxy handling and an integer underflow in HTTP/2 flow control that can allow unauthenticated remote attackers to crash worker processes or execute arbitrary code. The vulnerabilities affect specific versions of PAN-OS 12.2, 12.1, and 11.2, but only when the HTTP/2 option is explicitly enabled.

rss · Palo Alto Networks Security · Nov 20, 23:00

**「Background」** NGINX is widely embedded as a reverse proxy and web server within networking and security platforms, including Palo Alto Networks&\#x27; PAN-OS and Panorama management systems. The underlying vulnerabilities stem from flaws in NGINX&\#x27;s HTTP/2 implementation, specifically affecting how worker processes track reusable proxy connection states and calculate flow-control window thresholds.

**「Impact」** Administrators using affected PAN-OS or Panorama versions with HTTP/2 enabled must upgrade to fixed hotfix releases, such as 12.2.4-h3, 12.1.10-h6, or 11.2.16-h3, or disable HTTP/2 support as a mitigation.

**Tags**: `#vulnerability`, `#nginx`, `#cybersecurity`, `#http2`

---

<a id="item-tech-news-6"></a>
### [Palo Alto Networks Details Product Impact from Critical Java Vulnerability CVE-2026-114938](https://security.paloaltonetworks.com/CVE-2026-114938) ⭐️ 7.0/10

Palo Alto Networks published a security advisory detailing the impact of CVE-2026-114938, a critical heap out-of-bounds write flaw in the HotSpot JVM&\#x27;s AVX-512 VBMI Base64 intrinsic decoder affecting Oracle Java SE, Oracle GraalVM, and OpenJDK. The flaw allows unauthenticated remote code execution when an application decodes crafted Base64 input on x86-64 CPUs supporting AVX-512 VBMI. Several on-premises Idira product versions are affected—including Privilege Threat Analytics, Remote Access Connector, and Secure Access with an HTML5 Gateway—while PAN-OS platforms remain unaffected and SaaS products are being patched directly.

rss · Palo Alto Networks Security · Nov 20, 17:00

**「Vulnerability Context」** To accelerate data processing, modern HotSpot Java Virtual Machine implementations replace standard portable Base64 decoding with hand-written, vectorized intrinsic routines on supported hardware. CVE-2026-114938 stems from an out-of-bounds heap write in this AVX-512 VBMI hardware intrinsic when parsing malformed input, allowing attackers to corrupt heap memory or execute arbitrary code if an application decodes untrusted Base64 payloads.

**「Impact」** Administrators using on-premises Idira deployments must upgrade to patched releases, such as Privilege Threat Analytics 15.2.3 or 14.6.4, Remote Access Connector 1.1.1002202, and Secure Access HTML5 Gateway 15.0.3.21 or 15.2.2.17, as no workarounds are available.

<details><summary>References</summary>
<ul>
<li><a href="https://www.sophos.com/en-us/security-advisories/sophos-sa-20261118-java4shell">Advisory: OpenJDK Base64 Vulnerability - Java4Shell (CVE-2026 ...</a></li>
<li><a href="https://computingforgeeks.com/java4shell-cve-2026-114938/">Java4Shell CVE-2026-114938: Patch Vulnerable OpenJDK ...</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#java`, `#vulnerability`, `#computer systems`, `#openjdk`

---

<a id="item-tech-news-7"></a>
### [GnuPG Patches Critical Double-Free Flaw in GPGME Library](https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html) ⭐️ 7.0/10

The GnuPG project has released security updates to patch a critical double-free vulnerability, tracked as CVE-2026-129975, affecting the GPGME library in versions prior to 2.3.0. Triggered by a malicious OpenPGP key containing an unusually long user ID, the flaw could enable data theft or potentially remote code execution across applications that integrate the library. Fixes are available in GPGME 2.3.1, legacy version 1.24.4, and Gpg4win 5.1.2, with no known active attacks reported.

rss · The Hacker News · Nov 21, 11:05

**「Background」** GPGME serves as the standard programming interface that software such as mail clients, XMPP clients, and Samba uses to interact with GnuPG. The bug resides in the read\_status\(\) and read\_colon\_line\(\) parsing routines, which improperly retain pointers to already freed memory if an error occurs while expanding buffers for oversized input.

**「Impact」** Administrators and developers must update shared GPGME libraries to 2.3.1 or 1.24.4 and rebuild any software that embeds statically linked copies, as no interim workarounds exist.

**Tags**: `#Security`, `#OpenPGP`, `#GnuPG`, `#Vulnerabilities`

---

<a id="item-tech-news-8"></a>
### [Signal Enables Screenshot Restrictions to Block Mobile AI Agents](https://thehackernews.com/2026/11/signal-blocks-ai-agents-from-reading.html) ⭐️ 7.0/10

Signal has enabled default screenshot restrictions across iOS and Android to prevent operating system-level AI assistants from scanning chat screens and ingesting message data. The protection applies to agentic systems in iOS 27 and compatible Android versions, though users can manually disable it under privacy settings via the &quot;Block Siri AI&quot; or &quot;Screen security&quot; toggles. Signal acknowledged the safeguard is incomplete, noting it cannot block other access pathways such as direct file-system queries or third-party agents exploiting broad accessibility permissions.

rss · The Hacker News · Nov 21, 08:49

**「Background」** Operating system vendors have increasingly integrated AI agents that scan on-screen content, accessibility frameworks, and notifications to automate tasks across local applications. Signal previously introduced a setting on Windows 11 to block screen capture following Microsoft&\#x27;s rollout of the Recall feature.

**「Impact」** Signal users who disable the new screenshot protections risk exposing their private chats to local and remote AI agent indexing, while app developers still lack standardized OS-level controls to fully opt out of screen reading, notification interception, and file-system extraction.

**Tags**: `#privacy`, `#cybersecurity`, `#ai agents`, `#signal`, `#mobile security`

---

<a id="item-tech-news-9"></a>
### [CISA Adds Exploited Apache, Cisco, SAP, and VMware Flaws to KEV Catalog](https://thehackernews.com/2026/11/hackers-exploit-critical-vmware-cisco.html) ⭐️ 7.0/10

The U.S. Cybersecurity and Infrastructure Security Agency \(CISA\) added four actively exploited vulnerabilities affecting Apache Roller \(CVE-2026-129448\), Cisco Expressway Series \(CVE-2026-76466\), SAP NetWeaver Enterprise Portal \(CVE-2025-42884\), and Broadcom VMware vCenter \(CVE-2026-123890\) to its Known Exploited Vulnerabilities catalog. The critical flaws allow remote code execution, root access via hard-coded credentials, or authentication bypass, with three carrying CVSS scores of 9.8. Active weaponization includes reports of suspected China-nexus group Armory Castle chaining the VMware flaw with a BeyondTrust flaw to deploy backdoors, and threat actors using the Cisco flaw to breach an organization. Federal Civilian Executive Branch agencies have been directed to apply the available vendor fixes by November 23, 2026.

rss · The Hacker News · Nov 21, 08:49

**「Vulnerability Context」** Broadcom patched CVE-2026-123890 across supported VMware vCenter releases on November 19, 2026, addressing an authentication bypass that researchers found threat actor Armory Castle had been weaponizing in zero-day attacks since early September. CISA&\#x27;s Known Exploited Vulnerabilities catalog mandates that federal agencies remediate actively abused security flaws under Binding Operational Directive timelines.

**「Immediate Remediation Requirements」** Federal Civilian Executive Branch agencies must apply the available security updates across VMware vCenter, Cisco Expressway, SAP NetWeaver, and Apache Roller deployments by November 23, 2026, to prevent unauthenticated remote attackers and espionage groups from gaining root access or bypassing authentication.

<details><summary>References</summary>
<ul>
<li><a href="https://www.redtigersecurity.com/advisory/vmware-vcenter-cve-2026-123890-armory-castle">VMware vCenter Zero-Day CVE-2026-123890 Exploited by ARMORY ...</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#vulnerability`, `#cisa`, `#enterprise software`, `#infrastructure`

---

<a id="item-tech-news-10"></a>
### [AWS Launches Graviton5-Powered EC2 T9g Burstable Instances](https://aws.amazon.com/about-aws/whats-new/2026/11/ec2-t9g-instances-ga/) ⭐️ 7.0/10

AWS has made Amazon EC2 T9g burstable instances generally available across multiple global regions in four sizes: nano, micro, small, and medium. Powered by Graviton5 processors and sixth-generation Nitro cards, AWS claims the new instances deliver up to 45% better price performance, 2.3x compute performance, 1.5x higher network bandwidth, and 2.8x higher EBS bandwidth compared to T4g. T9g retains the same CPU credit model with Standard and Unlimited modes, with micro and small sizes eligible under the AWS Free Tier.

rss · AWS Whats New · Nov 20, 16:00

**「Burstable EC2 Instances」** Amazon EC2&\#x27;s T-series instances offer burstable CPU performance using an accumulated credit system, providing cost-effective baseline computing power for low-to-moderate workloads like microservices, small databases, and development environments. Previous Arm-based generations in this category relied on Graviton2 processors in the T4g family.

**「Impact」** Teams running lightweight burstable workloads on T4g instances can transition directly to T9g under the identical CPU credit model to improve bandwidth and compute throughput while lowering overall running costs.

**Tags**: `#Amazon EC2`, `#AWS Graviton`, `#Cloud Computing`, `#Computer Hardware`

---

<a id="item-tech-news-11"></a>
### [AWS Lambda Adds Python 3.15 Support and First Web Functions Python Runtime](https://aws.amazon.com/about-aws/whats-new/2026/11/aws-lambda-python-315/) ⭐️ 7.0/10

AWS Lambda has launched support for Python 3.15, making it generally available for Event Functions and in public preview for Web Functions. The release introduces the first Python runtime for Web Functions, which previously only supported Node.js. Developers can deploy Python 3.15 as a managed runtime or a base container image for Event Functions across all regions where both function types are available, gaining access to language features such as explicit lazy imports, frozendict, sentinel types, and JIT compiler improvements.

rss · AWS Whats New · Nov 20, 14:59

**「Background」** AWS Lambda provides managed execution environments for serverless workloads, traditionally dividing them into standard event-driven invocations and specialized runtimes. Prior to this release, Lambda Web Functions exclusively supported Node.js for hosting HTTP-driven web applications and APIs.

**「Impact」** Python developers can now build and deploy serverless web applications and APIs directly on Lambda Web Functions without relying on Node.js, and they can use explicit lazy imports in Event Functions to potentially reduce cold start latency.

**Tags**: `#aws-lambda`, `#python`, `#serverless`, `#cloud-computing`

---

<a id="item-tech-news-12"></a>
### [Google Announces General Availability of Ambient Networking for GKE](https://cloud.google.com/blog/products/networking/ambient-networking-for-gke-sidecarless-service-mesh/) ⭐️ 7.0/10

Google has announced the general availability of ambient networking for Google Kubernetes Engine \(GKE\), providing a sidecar-less service mesh architecture for cluster workloads. The system shifts traffic routing, mutual TLS \(mTLS\), and authorization enforcement from individual pod sidecars to shared per-node L4 Envoy proxies and managed control plane services such as Traffic Director. Google claims the architecture eliminates workload restarts for proxy updates and CVE patches while delivering up to a 10x reduction in resource usage for Layer 4 mesh capabilities.

rss · Google Cloud · Nov 20, 17:00

**「Background」** Traditional service meshes inject sidecar proxy containers directly into each application pod to manage mutual TLS, routing, and telemetry, which increases memory overhead and requires pod restarts during proxy upgrades or CVE patching. The ambient mesh architecture addresses these operational constraints by shifting networking and security enforcement to shared node-level proxies and separate control planes.

**「Impact」** GKE administrators can adopt mTLS and service mesh policies at cluster creation or on existing clusters without injecting proxy containers into application pods or restarting workloads during proxy lifecycle updates.

**Tags**: `#Kubernetes`, `#GKE`, `#Service Mesh`, `#Cloud Networking`

---