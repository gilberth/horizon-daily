---
layout: default
title: "Horizon Summary: 2026-11-19 (EN)"
date: 2026-11-19
lang: en
---

> From 111 items, 15 important content pieces were selected

---

**Technology News**
1. [Critical NGINX HTTP/2 Integer Underflow Vulnerability CVE-2026-123007 Enables Remote Code Execution](#item-tech-news-1) ⭐️ 8.0/10
2. [AWS Lambda Adds GPU Support for Event Functions on Lambda Managed Instances](#item-tech-news-2) ⭐️ 8.0/10
3. [Microsoft&\#x27;s Agent Framework PyPI Package Compromised to Steal Developer Credentials](#item-tech-news-3) ⭐️ 7.0/10
4. [Ruby Patches Seven Memory-Safety Flaws with Five PoC RCEs](#item-tech-news-4) ⭐️ 7.0/10
5. [Researcher Demonstrates RCE Exploits Across Major Databases Using Low-Privilege Accounts](#item-tech-news-5) ⭐️ 7.0/10
6. [CISA Adds Actively Exploited Apache Axis, LiteLLM, REDCap, and Synology Flaws to KEV](#item-tech-news-6) ⭐️ 7.0/10
7. [F5 Discloses Six Critical BIG-IP Buffer Overflows Affecting Data Plane Traffic](#item-tech-news-7) ⭐️ 7.0/10
8. [Critical Unauthenticated RCE Flaw in Apache Roller Under Active Exploitation](#item-tech-news-8) ⭐️ 7.0/10
9. [Hardware Attack Bypasses TPM Lockout on Select AMD and Intel PCs](#item-tech-news-9) ⭐️ 7.0/10
10. [AWS Releases ExtendDB 1.0 for Running DynamoDB Workloads on Alternative Backends](#item-tech-news-10) ⭐️ 7.0/10
11. [Amazon RDS for MySQL Adds Support for Major Version 9.7](#item-tech-news-11) ⭐️ 7.0/10
12. [Amazon CloudFront Functions Adds Network Calls via cf.fetch and cf.beacon](#item-tech-news-12) ⭐️ 7.0/10
13. [AWS Lambda launches customer-managed runtimes for centralized runtime management](#item-tech-news-13) ⭐️ 7.0/10
14. [Google Details Sashiko, an Agentic AI Code Review System for Linux](#item-tech-news-14) ⭐️ 7.0/10
15. [Google Cloud Adapts Envoy Proxy for Agentic AI, Token Routing, and MCP](#item-tech-news-15) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Critical NGINX HTTP/2 Integer Underflow Vulnerability CVE-2026-123007 Enables Remote Code Execution](https://www.rapid7.com/blog/post/ve-cve-2026-123007-critical-nginx-http-2-integer-underflow-leads-to-rce-fixed) ⭐️ 8.0/10

Rapid7 and F5 disclosed CVE-2026-123007 \(CVSS 9.2\), a critical integer underflow vulnerability in NGINX&\#x27;s HTTP/2 implementation that allows unauthenticated remote code execution in the worker process context. By manipulating HTTP/2 flow-control credits across queued frames and cancelling streams via SETTINGS updates, an attacker triggers an unsigned integer underflow in \`h2c-&gt;send\_window\` during subsequent WINDOW\_UPDATE checks, leading to out-of-bounds memory corruption in \`memcpy\`. Rapid7 demonstrated a working exploit against NGINX version 1.31.8 on linux/amd64 with HTTP/2 and TLS enabled, though successful remote exploitation requires approximately 128 GB of data transfer and a specific glibc runtime copy routine.

rss · Rapid7 Research · Nov 18, 13:56

**「HTTP/2 Flow Control in NGINX」** Under RFC 9113, HTTP/2 manages data transmission limits using separate flow-control credit counters for individual streams and the overall connection, capping increments at 2^31-1 bytes. NGINX tracks connection credits using an unsigned 64-bit integer \(\`size\_t\`\), which requires internal logic to enforce protocol boundaries and prevent counter miscalculations when streams are queued or cancelled.

**「Impact」** Administrators running affected NGINX versions with HTTP/2 enabled must apply vendor updates, as the vulnerability exposes worker processes to arbitrary code execution, though attacks are constrained by requirements for high-bandwidth connections above roughly 300 Mbit/s to complete within default connection timeouts.

**Tags**: `#vulnerability`, `#nginx`, `#http2`, `#network security`, `#remote code execution`

---

<a id="item-tech-news-2"></a>
### [AWS Lambda Adds GPU Support for Event Functions on Lambda Managed Instances](https://aws.amazon.com/blogs/aws/aws-lambda-now-supports-gpu-instances-for-event-functions-on-lambda-managed-instances/) ⭐️ 8.0/10

AWS announced that AWS Lambda now supports EC2 G-series GPU instances for Event Functions running on Lambda Managed Instances \(LMI\). Workloads are deployed as OCI container images without requiring manual management of GPU drivers, CUDA libraries, or AMIs. The feature supports container images up to 32 GB, 3 to 48 GB of accelerator memory, up to 48 concurrent requests per execution environment, and timeouts reaching up to 90 minutes for asynchronous and event source mapping invocations.

rss · AWS News · Nov 18, 19:39

**「Background」** Running GPU workloads has traditionally required managing dedicated compute instances, handling driver and CUDA compatibility, and orchestrating custom scaling or external integrations. AWS Lambda Managed Instances provides a foundation that combines EC2-based specialized compute and pricing models with serverless execution.

**「Impact」** Developers running custom machine learning inference or media processing pipelines can now execute GPU workloads natively within event-driven Lambda architectures without managing EC2 clusters, AMIs, or CUDA drivers. To adopt the capability, teams must configure OCI container images and may need to request an EC2 G-series On-Demand instance quota increase, as new AWS accounts often start with a default limit of zero.

**Tags**: `#AWS Lambda`, `#Serverless`, `#GPU Computing`, `#Machine Learning Inference`, `#Cloud Computing`

---

<a id="item-tech-news-3"></a>
### [Microsoft&\#x27;s Agent Framework PyPI Package Compromised to Steal Developer Credentials](https://www.bleepingcomputer.com/news/security/microsofts-agent-framework-pypi-package-compromised-to-steal-credentials/) ⭐️ 7.0/10

Threat actors compromised Microsoft&\#x27;s official Agent Framework repository on PyPI and released two malicious versions targeting developers. The rogue packages were crafted to exfiltrate cloud credentials and sensitive system information from environments where the framework was installed. Developers using the package are urged to inspect their environments and verify package versions for unauthorized releases.

rss · BleepingComputer · Nov 18, 16:58

**「Background」** Microsoft&\#x27;s \`agent-framework\` is an official library distributed via the Python Package Index \(PyPI\) for developers building AI agents. Compromised package releases on PyPI represent software supply chain attacks, where threat actors poison legitimate upstream dependencies to automatically exfiltrate credentials and API keys when developers or CI/CD pipelines fetch the updates.

**「Impact」** Developers and DevOps teams who installed or updated to \`agent-framework\` versions 1.26.1 or 1.26.2 must immediately remove the infected releases and rotate any cloud credentials, tokens, or API keys exposed on their local workstations and CI/CD build environments.

<details><summary>References</summary>
<ul>
<li><a href="https://www.chainguard.dev/unchained/microsoft-agent-framework-compromised-on-pypi-november-2026">Microsoft agent-framework compromised on PyPI: 1.26.1 and 1. ...</a></li>
<li><a href="https://orca.security/resources/research/microsoft-agent-framework-pypi-supply-chain-attack-versions-1-26-1-and-1-26-2-steal-cloud-credentials/">Microsoft agent-framework PyPI Supply-Chain Attack | Orca</a></li>

</ul>
</details>

**Tags**: `#software supply chain`, `#cybersecurity`, `#pypi`, `#python`, `#ai agents`

---

<a id="item-tech-news-4"></a>
### [Ruby Patches Seven Memory-Safety Flaws with Five PoC RCEs](https://thehackernews.com/2026/11/ruby-releases-fixes-for-7-regex-and.html) ⭐️ 7.0/10

Ruby maintainers released patch versions 4.0.10, 3.4.13, and 3.3.14 to resolve seven memory-safety flaws across its regular expression engine and string case-conversion routines. Five of the seven vulnerabilities carry proof-of-concept exploits demonstrating remote code execution, with advisories rating three critical, three high, and one moderate. The vulnerabilities affect Ruby 4.0.0 through 4.0.9, 3.4.0 through 3.4.12, and 3.3.13 and earlier, while end-of-life branches such as Ruby 3.2 will not receive patches. The maintainers report no active in-the-wild attacks so far, and exposure depends on whether an application accepts untrusted input into regex compilation or case-conversion operations.

rss · The Hacker News · Nov 19, 08:42

**「Background」** This release marks the second time in a month that Ruby has patched its regular expression engine, following an October 23 update that fixed compilation bugs uncovered by GitLab. In Ruby applications, regex compilation flaws typically become exploitable when the program dynamically constructs regular expressions from untrusted user input rather than matching against developer-authored patterns.

**「Impact」** Because the vulnerabilities reside directly in the Ruby interpreter rather than gem dependencies, administrators must update and rebuild their underlying server runtimes, background workers, and container images to remediate the exposure.

**Tags**: `#ruby`, `#security`, `#vulnerabilities`, `#remote-code-execution`, `#open-source`

---

<a id="item-tech-news-5"></a>
### [Researcher Demonstrates RCE Exploits Across Major Databases Using Low-Privilege Accounts](https://thehackernews.com/2026/11/researcher-demonstrates-database-rce.html) ⭐️ 7.0/10

Security researcher Zheng Yu has published proof-of-concept remote code execution exploits targeting PostgreSQL, MySQL, ClickHouse, and Oracle Database by leveraging low-privilege SQL accounts or unauthenticated endpoints to trigger memory-corruption bugs. The exploits rely on common grants such as PostgreSQL&\#x27;s default TEMPORARY privilege or temporary table creation rights in MySQL and ClickHouse to reach vulnerable underlying C and C++ engine routines, while a chained flaw in Oracle REST Data Services and Oracle Text enables unauthenticated code execution. Patches have been issued for the PostgreSQL, MySQL, and Oracle vulnerabilities, but the reported ClickHouse integer overflow write \(tested on version 26.7.5.10\) lacks an assigned CVE or confirmed fix, and none of the attack chains have been observed in active attacks.

rss · The Hacker News · Nov 19, 08:14

**「Background」** Database role permissions typically govern access to logical data structures like tables and schemas, but they do not isolate the native C and C++ engine code responsible for query planning and execution. Standard default privileges often grant ordinary users the ability to create temporary tables and schemas, exposing underlying query engine parsers and optimizers to untrusted input.

**「Impact」** Database administrators should apply the latest security updates for PostgreSQL, MySQL, and Oracle components, contact ClickHouse regarding fixes for version 26.7.5.10, and revoke unnecessary TEMPORARY schema privileges and temporary-table creation rights from untrusted database accounts.

**Tags**: `#database-security`, `#postgresql`, `#mysql`, `#vulnerability-research`, `#cybersecurity`

---

<a id="item-tech-news-6"></a>
### [CISA Adds Actively Exploited Apache Axis, LiteLLM, REDCap, and Synology Flaws to KEV](https://thehackernews.com/2026/11/cisa-warns-of-4-exploited-flaws-linked.html) ⭐️ 7.0/10

The U.S. Cybersecurity and Infrastructure Security Agency \(CISA\) added four actively exploited vulnerabilities to its Known Exploited Vulnerabilities catalog: CVE-2026-90436 in Apache Axis 1.x, CVE-2026-90817 in REDCap, CVE-2026-40217 in BerriAI LiteLLM, and CVE-2024-10441 in Synology DSM. Observed attacks leverage the end-of-life Apache Axis flaw against platforms like Atlassian Confluence to harvest credentials, the REDCap vulnerability to deploy XMRig cryptocurrency miners, the LiteLLM flaw for LLMjacking credential theft, and the Synology flaw for C3RB3R ransomware deployment. Federal agencies are directed to remediate the Axis, REDCap, and DSM vulnerabilities by November 21, 2026, and the LiteLLM vulnerability by December 2, 2026.

rss · The Hacker News · Nov 19, 08:00

**「Background」** CISA maintains the Known Exploited Vulnerabilities catalog to alert organizations to security flaws confirmed to be weaponized by threat actors in real-world attacks. Several of these flaws stem from unmaintained or legacy software components, including Apache Axis 1.x, which has reached end-of-life status and lacks an official new release.

**「Impact」** Organizations running end-of-life Apache Axis 1.x must migrate to an alternative framework like Apache Axis 2/Java or backport recent patches manually, while Confluence administrators can mitigate CVE-2026-90436 exposure by verifying that legacy Remote API \(XML-RPC &amp; SOAP\) settings are disabled.

**Tags**: `#vulnerability`, `#cybersecurity`, `#LiteLLM`, `#CISA`, `#application security`

---

<a id="item-tech-news-7"></a>
### [F5 Discloses Six Critical BIG-IP Buffer Overflows Affecting Data Plane Traffic](https://thehackernews.com/2026/11/f5-warns-6-critical-big-ip-flaws-can.html) ⭐️ 7.0/10

F5 disclosed six critical vulnerabilities rated CVSS 9.8 in BIG-IP&\#x27;s Traffic Management Microkernel \(TMM\) that permit unauthenticated attackers to crash the data plane or potentially achieve remote code execution. Exploitation requires specific virtual server configurations, such as particular iRule commands or combined APM policy agents, across products including standard BIG-IP, BIG-IP Next for Kubernetes, and BIG-IP CNF. F5 has not observed in-the-wild exploitation and has released engineering hotfixes rather than scheduled software releases, noting that no workarounds exist for the six critical flaws.

rss · The Hacker News · Nov 18, 18:15

**「Background」** The Traffic Management Microkernel handles the data plane network processing in BIG-IP environments, which administrators frequently customize using iRules scripts or Access Policy Manager \(APM\) modules. Unlike an earlier heap-based APM vulnerability disclosed in September \(CVE-2026-94127\) involving OAuth setups, these six issues \(including CVE-2026-123637 and CVE-2026-121805\) are stack-based buffer overflows exposed directly to unauthenticated traffic matching vulnerable configurations.

**「Impact」** Network administrators managing vulnerable virtual server configurations must deploy engineering hotfixes—such as BNK-2.4.2-EHF1 or CNF-2.4.2-EHF1—while accounting for F5&\#x27;s warning that engineering hotfixes bypass standard scheduled release QA testing and carry no performance warranty.

**Tags**: `#cybersecurity`, `#vulnerability`, `#networking`, `#computer systems`

---

<a id="item-tech-news-8"></a>
### [Critical Unauthenticated RCE Flaw in Apache Roller Under Active Exploitation](https://thehackernews.com/2026/11/critical-apache-roller-rce-flaw-under.html) ⭐️ 7.0/10

The Apache Software Foundation warned that an unauthenticated remote code execution vulnerability in Apache Roller, tracked as CVE-2026-129448 with a CVSS score of 9.8, is under active exploitation in the wild. The flaw affects versions 4.0.0 through 6.1.4 and stems from the XML-RPC endpoint deserializing vendor extension types prior to authentication. Maintainers have addressed the vulnerability in Apache Roller 6.1.6 by disabling these extension types and rejecting XML-RPC requests when the feature is turned off.

rss · The Hacker News · Nov 18, 17:10

**「Background」** Apache Roller is an open-source, Java-based blogging platform that supports remote interaction through an XML-RPC endpoint. The Apache Software Foundation previously patched an identical deserialization vulnerability as CVE-2026-82384 in September 2026, but that advisory originally listed only Apache Roller 6.1.5 as affected.

**「Impact」** Administrators must upgrade affected deployments to Apache Roller 6.1.6 or apply manual mitigations—such as setting &quot;enabledForExtensions&quot; to &quot;false&quot; in WEB-INF/web.xml or removing the &quot;/roller-services/xmlrpc&quot; servlet mapping—because simply disabling XML-RPC through the administration UI does not prevent deserialization.

**Tags**: `#cybersecurity`, `#vulnerability`, `#apache roller`, `#remote code execution`, `#open source`

---

<a id="item-tech-news-9"></a>
### [Hardware Attack Bypasses TPM Lockout on Select AMD and Intel PCs](https://thehackernews.com/2026/11/flash-chip-attack-bypasses-tpm-lockout.html) ⭐️ 7.0/10

Researchers at Technische Universität Berlin developed physical hardware attacks that reset the firmware TPM failure counter on select AMD and Intel PCs, bypassing lockout protections to accelerate brute-force PIN guessing. In lab demonstrations, the approach cut the theoretical worst-case guessing time for a four-digit Windows Hello PIN on an AMD laptop from 69 days to 40 hours, and a six-digit BitLocker PIN on an Intel laptop with Winbond flash from 19 years to 20 days. AMD confirmed the firmware vulnerability as CVE-2026-43613 \(CVSS 5.1\) and plans fixes for affected processors between November and February 2027, while Intel stated the test on its platform exploited a third-party Winbond flash chip flaw rather than an Intel component. Both attacks require physical access, removing or interposing the mainboard flash chip, and custom hardware running modified firmware.

rss · The Hacker News · Nov 18, 12:28

**「Background」** Unlike dedicated discrete chips, processor-based firmware TPMs store encrypted state and failed authentication counters on the motherboard&\#x27;s external SPI flash memory. Newer systems rely on Replay-Protected Monotonic Counters \(RPMC\) inside the flash memory to detect and reject rolled-back state images, preventing attackers from restoring an earlier state to reset counter lockouts.

**「Impact」** To mitigate risk against physical attacks until motherboard vendors distribute firmware updates, users and administrators should expand Windows Hello and BitLocker PINs by at least two digits, as eight-digit PINs significantly raise the required brute-force duration.

**Tags**: `#Security`, `#Hardware Security`, `#TPM`, `#Cryptography`, `#Vulnerability`

---

<a id="item-tech-news-10"></a>
### [AWS Releases ExtendDB 1.0 for Running DynamoDB Workloads on Alternative Backends](https://aws.amazon.com/about-aws/whats-new/2026/11/aws-extenddb-1-0/) ⭐️ 7.0/10

AWS has released ExtendDB 1.0, an open-source, production-ready adapter that provides full API compatibility with Amazon DynamoDB across alternative database engines. Released under the Apache 2.0 license, the software supports PostgreSQL, SQLite, Cassandra, and MongoDB backends, allowing teams to run existing DynamoDB workloads on-premises, in other clouds, or at the edge without rewriting application code. AWS also introduced the extenddb-dev container image and @extenddb/dev npm package, which run an embedded DynamoDB-compatible endpoint on SQLite for local testing and CI pipelines.

rss · AWS Whats New · Nov 18, 20:00

**「Background」** Amazon DynamoDB is a proprietary, fully managed NoSQL database service tightly integrated with AWS infrastructure. In May 2026, AWS introduced ExtendDB as an open-source Rust implementation of the DynamoDB wire protocol to translate API calls to alternative storage backends across hybrid, local, and edge environments.

**「Impact」** Developers can deploy DynamoDB-based applications outside of AWS managed infrastructure without refactoring data access code, while using lightweight SQLite-backed environments to simplify local development and testing workflows.

<details><summary>References</summary>
<ul>
<li><a href="https://aws.amazon.com/blogs/database/introducing-extenddb-an-open-source-dynamodb-compatible-adapter-with-pluggable-storage-backends/">Introducing ExtendDB: An open source DynamoDB-compatible ...</a></li>
<li><a href="https://aws.amazon.com/about-aws/whats-new/2026/05/aws-extenddb-dynamodb/">AWS announces ExtendDB, an open source DynamoDB-compatible ...</a></li>

</ul>
</details>

**Tags**: `#Databases`, `#Amazon Web Services`, `#Open Source`, `#DynamoDB`, `#Cloud Computing`

---

<a id="item-tech-news-11"></a>
### [Amazon RDS for MySQL Adds Support for Major Version 9.7](https://aws.amazon.com/about-aws/whats-new/2026/11/amazon-rds-mysql-974-available/) ⭐️ 7.0/10

Amazon Web Services has launched support for MySQL major version 9.7 on Amazon RDS, launching with community version 9.7.4 across all AWS Regions where RDS for MySQL is offered. The update introduces JSON Duality Views to query and mutate relational data as JSON documents, an opt-in Hypergraph Optimizer designed for complex multi-join queries, and the Replication Applier Metrics component. Administrators can diagnose replication lag through two new Performance Schema tables reporting per-channel backlog, throughput, wait statistics, and worker transaction progress.

rss · AWS Whats New · Nov 18, 17:00

**「Background」** MySQL 9.7 serves as a community Long-Term Support \(LTS\) release that introduces capabilities previously restricted to enterprise editions or absent from community builds, including an opt-in Hypergraph query optimizer and writable JSON Duality Views.

**「Impact」** Existing RDS for MySQL users can upgrade instances to version 9.7 using in-place upgrades, snapshot restoration, or Amazon RDS Blue/Green Deployments to minimize downtime.

<details><summary>References</summary>
<ul>
<li><a href="https://www.besthub.dev/articles/mysql-9-7-lts-opentelemetry-json-duality-writes-hypergraph-optimizer-now-in-community-0c328917ef40">MySQL 9.7 LTS: OpenTelemetry, JSON Duality Writes ...</a></li>
<li><a href="https://www.besthub.dev/articles/mysql-9-7-lts-deep-dive-free-enterprise-features-hypergraph-optimizer-json-dml-6b4822bda495">MySQL 9.7 LTS Deep Dive: Free Enterprise Features, Hypergraph ...</a></li>

</ul>
</details>

**Tags**: `#Amazon RDS`, `#MySQL`, `#Databases`, `#Cloud Computing`

---

<a id="item-tech-news-12"></a>
### [Amazon CloudFront Functions Adds Network Calls via cf.fetch and cf.beacon](https://aws.amazon.com/about-aws/whats-new/2026/11/cloudfront-functions-network-calls/) ⭐️ 7.0/10

Amazon CloudFront Functions now supports making network calls directly from CloudFront edge locations using two new methods: \`cf.fetch\(\)\` and \`cf.beacon\(\)\`. With \`cf.fetch\(\)\`, lightweight JavaScript functions can query external APIs synchronously during request handling to perform real-time authentication, routing, or personalization, while \`cf.beacon\(\)\` enables asynchronous background analytics delivery without delaying viewer responses. Both methods integrate with existing distribution origin settings—including origin access control \(OAC\), VPC origins, and connection reuse—and are available across all edge locations for $0.10 per million calls on top of standard function invocation charges.

rss · AWS Whats New · Nov 18, 16:00

**「Edge Compute Options in CloudFront」** CloudFront Functions was designed as a lightweight, sub-millisecond execution environment for simple HTTP header and URL manipulations, but it lacked network access. Workloads requiring external API calls, remote authentication checks, or third-party service integration previously required Lambda@Edge or backend origin servers.

**「Impact」** Developers can now execute external authentication, fraud checks, and telemetry directly inside lightweight CloudFront Functions rather than maintaining heavier Lambda@Edge functions or offloading that validation logic to origin servers.

**Tags**: `#AWS`, `#Amazon CloudFront`, `#Edge Computing`, `#Serverless`, `#Cloud Infrastructure`

---

<a id="item-tech-news-13"></a>
### [AWS Lambda launches customer-managed runtimes for centralized runtime management](https://aws.amazon.com/about-aws/whats-new/2026/11/aws-lambda-customer-managed-runtimes/) ⭐️ 7.0/10

AWS Lambda has made customer-managed runtimes generally available as a standalone resource across all commercial AWS Regions. Packaged as OCI container images in Amazon ECR, these runtimes allow platform teams to centrally govern shared dependencies, certificates, and tooling without requiring individual function redeployments. Functions referencing a runtime alias pick up updates automatically during execution environment recycling while application teams continue deploying code as .zip files. There is no additional fee for the feature beyond standard Lambda execution rates and Amazon ECR storage costs.

rss · AWS Whats New · Nov 18, 15:00

**「Background」** Organizations previously relied on Lambda Layers or custom container images to distribute shared libraries and security tooling across functions, requiring each function to be rebuilt and redeployed whenever an underlying dependency updated. Concurrently with this release, AWS Lambda has rebranded standard custom runtimes as &quot;bring your own language&quot; and renamed Lambda functions to Lambda Event Functions.

**「Impact」** Platform engineers can publish runtime updates and security patches across accounts or entire AWS Organizations using resource-based policies without coordinating redeployment cycles with individual development teams.

**Tags**: `#AWS Lambda`, `#Serverless`, `#Cloud Computing`, `#DevOps`

---

<a id="item-tech-news-14"></a>
### [Google Details Sashiko, an Agentic AI Code Review System for Linux](https://cloud.google.com/blog/products/application-development/lessons-from-building-sashiko-an-agentic-code-review-system/) ⭐️ 7.0/10

Google engineers shared technical details and production metrics for Sashiko, an open-source, Gemini-powered agentic code review system donated to the Linux Foundation. To address review bottlenecks and AI-generated patch volume, Sashiko decomposes patch evaluation into planning, up to seven parallel specialist passes \(averaging roughly 100 Git tool calls per review\), and isolated per-bug verification agents requiring concrete code proof for both bugs and dismissals. Operating as a Google-hosted public service on sashiko.dev, the platform currently completes approximately 1,200 reviews daily across more than 70 opted-in Linux kernel mailing lists.

rss · Google Cloud · Nov 18, 17:00

**「Background」** Linux kernel maintenance spans more than 35 million lines of code and receives over 85,000 merged changes annually, relying heavily on manual patch reviews by maintainers to prevent memory leaks, deadlocks, and security vulnerabilities. While automated build bots and fuzzers like Syzkaller detect compilation failures and crashes, code review throughput remains the primary bottleneck as generative coding agents increase incoming patch volume.

**「Impact」** Linux kernel maintainers across more than 70 opted-in mailing lists now receive automated patch inquiries directly in standard mailing list workflows without requiring developer API keys or local token budgets.

**Tags**: `#Linux Kernel`, `#AI Code Review`, `#Agentic AI`, `#Open Source`, `#Software Engineering`

---

<a id="item-tech-news-15"></a>
### [Google Cloud Adapts Envoy Proxy for Agentic AI, Token Routing, and MCP](https://cloud.google.com/blog/products/networking/the-envoy-agentic-stack-routing-models-tokens-and-mcp/) ⭐️ 7.0/10

Google Cloud engineers detailed an architectural stack adapting the open-source Envoy proxy to manage networking for autonomous AI agents, LLM APIs, and Model Context Protocol \(MCP\) communication. The architecture adds line-rate JSON body parsing and transcoding across provider schemas, token-aware rate limiting that enforces TPM and TPD quotas, and KV-cache prefix affinity via Kubernetes Gateway API Inference Extensions. It also supports zero-body-parsing tool routing using Mcp-Method and Mcp-Name headers, automatic model fallbacks, and scale-to-zero traffic buffering for runtimes like Agent Substrate.

rss · Google Cloud · Nov 18, 17:00

**「Background」** Traditional Layer 7 proxies route traffic based on HTTP paths and headers while enforcing request-per-second rate limits, an approach that fails when LLM requests share identical endpoints like /v1/chat/completions but vary dramatically in token consumption. Autonomous agents introduce higher-order protocols where routing attributes and tool calls are embedded deep within request payloads, requiring stateful session affinity and token-based governance.

**「Impact」** Platform engineers running multi-model agent systems can swap downstream model providers or self-hosted backends via Envoy configuration updates without changing client application code, while enforcing token-budget ceilings to block runaway reasoning loops.

**Tags**: `#Envoy Proxy`, `#Agentic AI`, `#Model Context Protocol`, `#Cloud Networking`, `#AI Infrastructure`

---