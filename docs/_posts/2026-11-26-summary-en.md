---
layout: default
title: "Horizon Summary: 2026-11-26 (EN)"
date: 2026-11-26
lang: en
---

> From 93 items, 9 important content pieces were selected

---

**Technology News**
1. [AWS Lambda Previews MicroVM Orchestration with Durable Functions](#item-tech-news-1) ⭐️ 7.5/10
2. [AWS Sign-In Adds Enterprise-Managed Authorization for AI Agents Accessing MCP Servers](#item-tech-news-2) ⭐️ 7.0/10
3. [Unit 42 Documents Machine-Speed AI Agent Cyberattacks and Edge AI Defenses](#item-tech-news-3) ⭐️ 7.0/10
4. [Palo Alto Networks Warns of Fragnesia and PHP2Shell Exploits Targeting PAN-OS](#item-tech-news-4) ⭐️ 7.0/10
5. [1Password Discloses Backend Breach via Compromised Employee GitHub Account](#item-tech-news-5) ⭐️ 7.0/10
6. [Italy and Switzerland Warn of Autonomous AI-Driven Cyberattacks](#item-tech-news-6) ⭐️ 7.0/10
7. [Drupal Patches Actively Exploited Core Site Takeover Flaw CVE-2026-136716](#item-tech-news-7) ⭐️ 7.0/10
8. [GeoServer Flaws Exploited in the Wild Amid Unauthenticated RCE Warnings](#item-tech-news-8) ⭐️ 7.0/10
9. [AWS Releases Elastic Load Balancing for Envoy Into General Availability](#item-tech-news-9) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [AWS Lambda Previews MicroVM Orchestration with Durable Functions](https://aws.amazon.com/about-aws/whats-new/2026/11/lambda-durable-microvm/) ⭐️ 7.5/10

AWS launched a developer preview enabling Lambda durable functions to orchestrate Lambda MicroVMs for isolated, state-preserving compute tasks. Available via the AWS Durable Execution SDK for TypeScript and Python, the extension allows durable functions to manage MicroVM lifecycles, execute individual tasks, or coordinate multi-task sessions sharing files and memory with checkpointing and automatic retries. The capability is available in all AWS regions supporting both Lambda durable functions and MicroVMs, though AWS cautions against production use during the preview.

rss · AWS Whats New · Nov 25, 20:00

**「Background」** AWS Lambda introduced durable functions to support long-running, multi-step workflows and AI pipelines directly within serverless compute. In parallel, Lambda MicroVMs provide fast-launching, isolated sandboxes that preserve state across executions for running untrusted or dynamic code.

**「Impact」** Developers building workloads such as CI/CD jobs, security scanners, or agent-generated code sandboxes must install the extension package alongside the Durable Execution SDK and embed the companion worker library into their MicroVM images.

**Tags**: `#AWS Lambda`, `#MicroVMs`, `#Serverless Computing`, `#Cloud Infrastructure`, `#Virtualization`

---

<a id="item-tech-news-2"></a>
### [AWS Sign-In Adds Enterprise-Managed Authorization for AI Agents Accessing MCP Servers](https://aws.amazon.com/blogs/security/secure-agentic-access-to-aws-with-enterprise-managed-authorization/) ⭐️ 7.0/10

AWS Sign-In has introduced Enterprise-Managed Authorization \(EMA\) using the Identity Assertion JWT Authorization Grant \(ID-JAG\) to govern AI agent access to AWS Model Context Protocol \(MCP\) servers. The integration allows organizations to authorize AI applications, such as Claude, through existing identity providers like Okta without managing long-term credentials or prompting employees with individual consent flows. When an agent requests resource access, the enterprise IdP issues a short-lived, signed ID-JAG assertion that AWS Sign-In exchanges for an OAuth access token bound to a specific AWS IAM role.

rss · AWS Security · Nov 25, 21:00

**「Background」** AWS previously introduced OAuth-based authorization for AWS MCP Server using interactive sign-in or direct AWS credential authentication. However, authenticating an employee into an external AI application does not inherently authorize access across distinct enterprise and cloud trust domains.

**「Impact」** Enterprise administrators can centrally enforce access control policies across AI applications from their existing IdP while retaining native AWS IAM permission boundaries, eliminating the need for employees to manually approve individual MCP server connections.

**Tags**: `#AWS`, `#Model Context Protocol`, `#AI Agents`, `#Cloud Security`, `#Authentication`

---

<a id="item-tech-news-3"></a>
### [Unit 42 Documents Machine-Speed AI Agent Cyberattacks and Edge AI Defenses](https://unit42.paloaltonetworks.com/ai-threat-horizon/) ⭐️ 7.0/10

Palo Alto Networks&\#x27; Unit 42 reported real-world threat actors deploying autonomous AI agents to carry out rapid, context-aware attacks at machine speed. In one observed incident, an agentic AI attacker executed syntax-error-free commands with a median gap of just 1.4 seconds—down from an average of 24 seconds with manual errors during the preceding human operator phase—while another campaign generated 117 scripts and over 8,000 commands across 12 days. To counter this rapid enumeration and privilege escalation, Unit 42 advocates deploying millisecond-latency edge AI on endpoints and firewalls alongside behavioral baselining and automated attack isolation.

rss · Palo Alto Unit 42 · Nov 25, 15:00

**「Background」** Traditional cyberattacks rely heavily on human operators who manually issue commands, inspect system outputs, and navigate unfamiliar target environments, resulting in noticeable latency and frequent syntax errors. Security operations centers historically benchmarked effectiveness on hours-long Mean Time to Respond \(MTTR\) metrics, which depend on central cloud analysis rather than local millisecond-speed edge execution.

**「Impact」** Security operations teams must compress response metrics from hours to minutes by deploying local automated isolation policies on endpoints and firewalls to halt reconnaissance and privilege escalation before agentic attackers can exfiltrate or encrypt cloud assets.

**Tags**: `#artificial intelligence`, `#cybersecurity`, `#ai agents`, `#threat intelligence`

---

<a id="item-tech-news-4"></a>
### [Palo Alto Networks Warns of Fragnesia and PHP2Shell Exploits Targeting PAN-OS](https://www.bleepingcomputer.com/news/security/palo-alto-networks-warns-of-fragnesia-flaw-exploited-in-pan-os-attacks/) ⭐️ 7.0/10

Palo Alto Networks warned that threat actors are actively chaining exploits for the Fragnesia and PHP2Shell vulnerabilities against PAN-OS devices. The attacks target devices that have their management interfaces exposed directly to the internet. Administrators must secure and restrict external access to these management interfaces to mitigate exploitation.

rss · BleepingComputer · Nov 25, 22:05

**「Background」** The Fragnesia vulnerability \(tracked as CVE-2026-46300\) is a Linux kernel security flaw that attackers can leverage to obtain root privileges on affected devices. Prior to these attacks, Palo Alto Networks firewalls running PAN-OS branches including 10.2, 11.1, 11.2, 12.1, and 12.2 were exposed when management interfaces were left accessible from the internet.

**「Immediate Action Required」** Administrators managing PAN-OS devices must immediately restrict or disable internet access to management interfaces to protect their networks from active exploitation chains targeting these vulnerabilities.

<details><summary>References</summary>
<ul>
<li><a href="https://threataft.com/articles/palo-alto-panos-fragnesia-php2shell-root-chain">Palo Alto PAN-OS: PHP2Shell + Fragnesia Root Chain</a></li>
<li><a href="https://www.securityweek.com/palo-alto-networks-patches-fragnesia-flaw-used-to-root-firewalls/">Palo Alto Networks Patches Fragnesia Flaw Used to Root ...</a></li>

</ul>
</details>

**Tags**: `#network security`, `#vulnerabilities`, `#PAN-OS`, `#computer systems`, `#cybersecurity`

---

<a id="item-tech-news-5"></a>
### [1Password Discloses Backend Breach via Compromised Employee GitHub Account](https://www.bleepingcomputer.com/news/security/1password-customer-data-stolen-after-employee-github-account-breach/) ⭐️ 7.0/10

1Password disclosed that an attacker compromised an employee&\#x27;s corporate GitHub account, accessed private repositories and CI/CD systems, and deployed malicious code to backend services to steal administrative data for a subset of customers. The accessed metadata includes names, email addresses, public keys, Secure Remote Password protocol parameters, account identifiers, and tokens embedded in invitation and recovery emails. 1Password stated that customer password vaults, secrets, and account recovery keys were not accessed or compromised, as encrypted vault items cannot be decrypted on company servers.

rss · BleepingComputer · Nov 25, 21:33

**「Architecture and Security Model」** 1Password relies on a zero-knowledge security architecture where user vaults are encrypted locally with keys held only by the customer, meaning server-side systems store ciphertext rather than plaintext secrets. Because backend infrastructure holds account administrative metadata and provisioning endpoints rather than decryptable passwords, an attacker compromising internal services cannot directly decrypt stored vault data without those client-held keys.

**「Customer Impact and Phishing Risks」** Although encrypted vault data and master keys remain uncompromised, affected customers face heightened risks of targeted phishing due to the exposure of names, email addresses, and account metadata.

**Tags**: `#cybersecurity`, `#software security`, `#data breach`, `#devsecops`

---

<a id="item-tech-news-6"></a>
### [Italy and Switzerland Warn of Autonomous AI-Driven Cyberattacks](https://www.bleepingcomputer.com/news/security/italy-and-switzerland-warn-of-autonomous-ai-driven-cyberattacks/) ⭐️ 7.0/10

National cybersecurity agencies in Italy and Switzerland have issued warnings regarding automated cyberattacks powered by autonomous AI agents. The alerts highlight threats specifically directed at organizations operating within critical infrastructure sectors. The agencies caution that these adversarial campaigns leverage autonomous agent workflows to automate attack operations.

rss · BleepingComputer · Nov 25, 19:39

**「Shift to Autonomous Cyber Threats」** Traditional automated cyber threats typically rely on static scripts and pre-programmed exploit sequences that require human operators to adapt to target defenses. Autonomous AI-driven attacks instead deploy software agents capable of independent decision-making, adaptive reconnaissance, and dynamic lateral movement across compromised networks.

**「Impact」** Operators of critical infrastructure must adapt defensive postures to counter threat actors using autonomous AI agents that can independently conduct multi-stage attacks against government and energy systems.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theregister.com/security/2026/08/14/autonomous-ai-attacks-pose-clear-and-present-danger-to-critical-infrastructure/5287594">Autonomous AI attacks pose &#x27;clear and present danger&#x27; to ...</a></li>

</ul>
</details>

**Tags**: `#artificial intelligence`, `#cybersecurity`, `#autonomous agents`, `#critical infrastructure`

---

<a id="item-tech-news-7"></a>
### [Drupal Patches Actively Exploited Core Site Takeover Flaw CVE-2026-136716](https://thehackernews.com/2026/11/drupal-warns-of-new-highly-critical.html) ⭐️ 7.0/10

Drupal maintainers have released security updates to resolve CVE-2026-136716, a highly critical Drupal core vulnerability that allows site takeovers and is being actively exploited in the wild. The flaw stems from improper condition checks affecting sites in unusual or incomplete installation states left open after the previous Fail2Install \(CVE-2026-132165\) remediation. Patches are available in Drupal versions 11.4.14, 11.3.23, and 10.6.23, while versions 11.0.x through 11.2.x and 10.5.x or older are unsupported and will not receive fixes.

rss · The Hacker News · Nov 26, 07:02

**「Background」** The vulnerability follows the earlier remediation of CVE-2026-132165, dubbed Fail2Install, which resolved several installer vulnerabilities in Drupal core. However, that patch left certain sites in incomplete or abnormal installation states still exposed to hijacking if their installer remained accessible over the network.

**「Impact」** Administrators must update to a supported release, execute update.php, restrict remote access to install.php, and audit access logs alongside the user 1 administrator account for unauthorized modifications.

**Tags**: `#Drupal`, `#Cybersecurity`, `#Vulnerability`, `#Web Development`

---

<a id="item-tech-news-8"></a>
### [GeoServer Flaws Exploited in the Wild Amid Unauthenticated RCE Warnings](https://thehackernews.com/2026/11/hackers-exploit-two-geoserver-flaws-as.html) ⭐️ 7.0/10

Threat actors are actively probing and exploiting newly patched vulnerabilities in GeoServer, including an arbitrary file read flaw \(CVE-2026-120705\) and an authorization bypass issue \(CVE-2026-129243\). Researchers from watchTowr reported observing in-the-wild exploit probes targeting global honeypots by creating and deleting stored queries to validate vulnerable instances. Security researchers have also demonstrated that these issues can be chained with predictable &quot;remember me&quot; keys and unsafe JDBC configurations to achieve unauthenticated remote code execution. Patches addressing the underlying vulnerabilities were released in GeoServer versions 3.0.2, 2.28.6, and 2.27.7.

rss · The Hacker News · Nov 25, 12:48

**「Prior Security Issues」** GeoServer is an open-source geospatial data server that supports standards such as the Web Feature Service \(WFS\) and OpenGIS Web Services \(OWS\). The server has previously faced targeted attacks, including active zero-day exploitation of the critical flaw CVE-2026-76904 three months earlier.

**「Impact」** Organizations running internet-facing GeoServer deployments face an immediate risk of credential disclosure, session forgery, and remote server compromise, requiring administrators to update to versions 3.0.2, 2.28.6, or 2.27.7 and inspect exposed hosts for unauthorized access.

**Tags**: `#cybersecurity`, `#vulnerabilities`, `#geoserver`, `#open source`

---

<a id="item-tech-news-9"></a>
### [AWS Releases Elastic Load Balancing for Envoy Into General Availability](https://aws.amazon.com/about-aws/whats-new/2026/11/elastic-load-balancing-for-envoy-generally-available) ⭐️ 7.0/10

AWS has launched the general availability of ELB for Envoy, a new Elastic Load Balancing type that manages open-source Envoy proxies across 14 initial AWS Regions. Each load balancer deploys on dedicated Amazon EC2 instances isolated via the AWS Nitro System, with AWS automatically managing capacity, OS maintenance, and Envoy CVE security patching. Teams can import existing Envoy configurations, extensions \(such as WebAssembly and Lua scripting\), and control planes, while integrating natively with AWS Certificate Manager, AWS WAF, and VPC security groups.

rss · AWS Whats New · Nov 25, 16:00

**「Background」** Envoy is an open-source edge and service proxy widely used for cloud-native traffic routing, ingress, and service mesh architectures. Within AWS, workloads standardizing on Envoy traditionally required platform teams to deploy and self-manage fleets on EC2 or Kubernetes, handling their own capacity provisioning, multi-Availability Zone scaling, and security patching.

**「Impact」** Platform teams managing self-hosted Envoy or Envoy Gateway on Kubernetes can offload fleet patching and cross-AZ capacity scaling to AWS by adopting the ELB for Envoy remote infrastructure provider without rewriting Gateway API resources.

**Tags**: `#aws`, `#cloud-infrastructure`, `#envoy-proxy`, `#networking`, `#open-source`

---