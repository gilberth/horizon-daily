---
layout: default
title: "Horizon Summary: 2026-11-12 (EN)"
date: 2026-11-12
lang: en
---

> From 17 items, 4 important content pieces were selected

---

**Technology News**
1. [AWS Releases Official Local Service Emulator Built with Rust and Agentic Coding](#item-tech-news-1) ⭐️ 8.0/10
2. [Anthropic Details Multi-Chip Infrastructure and Automated Porting in IPO Roadshow](#item-tech-news-2) ⭐️ 8.0/10
3. [Google Launches Gemini Decisions API with Multimodal Input Support](#item-tech-news-3) ⭐️ 7.0/10
4. [Meta AI Releases Muse Ember for Efficient Agentic Workloads](#item-tech-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [AWS Releases Official Local Service Emulator Built with Rust and Agentic Coding](https://simonwillison.net/2026/Nov/11/aws-emulator/) ⭐️ 8.0/10

AWS has released \`aws-emulator\`, an official Rust-based tool that lets developers run local tests against clones of AWS services without provisioning paid API keys. According to an account by Swaminathan Sivasubramanian, the project was developed by a swarm of AI agents that logged 29,684 commits during its first three weeks. At present, running the emulator on macOS or Windows requires Docker rather than functioning as a standalone native binary.

rss · Simon Willison · Nov 11, 21:18

**「Background」** Testing cloud-native applications locally has traditionally required live cloud accounts or third-party mock implementations like LocalStack. To build the official emulator across more than 200 AWS services, autonomous coding agents generated fidelity tests directly from AWS&\#x27;s Smithy API models and real cloud behavior before writing matching service emulations.

**「Impact」** Developers can execute automated test suites and AWS SDK or CLI calls locally without provisioning cloud accounts, paying for API usage, or managing live deployments, though macOS and Windows environments currently require Docker to run it.

<details><summary>References</summary>
<ul>
<li><a href="https://www.allthingsdistributed.com/2026/11/aws-emulator-and-the-engineers-job-when-agents-write-the-code.html">AWS Emulator and the engineer&#x27;s job when agents write the code</a></li>
<li><a href="https://daily.dev/posts/aws-emulator-and-the-engineer-s-job-when-agents-write-the-code-d2foynmlg">AWS Emulator and the engineer&#x27;s job when agents write the code</a></li>
<li><a href="https://aws.amazon.com/products/developer-tools/emulator/">Local AWS emulator for testing and CI | AWS Emulator</a></li>

</ul>
</details>

**Tags**: `#aws`, `#cloud computing`, `#rust`, `#software testing`, `#agentic coding`

---

<a id="item-tech-news-2"></a>
### [Anthropic Details Multi-Chip Infrastructure and Automated Porting in IPO Roadshow](https://simonwillison.net/2026/Nov/11/anthropic-ipo-roadshow/) ⭐️ 8.0/10

In an IPO roadshow presentation, Anthropic co-founder Tom Brown revealed that the company now trains and serves Claude across four major hardware platforms: AWS Trainium, Google TPUs, NVIDIA GPUs, and AMD GPUs. Brown claimed that Anthropic used its internal model, Mythos, to port Claude to AMD GPUs in three days with virtually no human intervention, authoring or porting nearly 100% of the required kernels. He also outlined a strategy centered on stacking algorithmic &quot;compute multipliers,&quot; projecting that future models will autonomously discover these optimizations through recursive self-improvement.

rss · Simon Willison · Nov 11, 15:11

**「Background」** Deploying frontier AI models across diverse hardware architectures traditionally requires developing bespoke compiler, kernel, and inference software stacks for each chip family, often demanding months of engineering per platform. Anthropic had previously disclosed hints of its heterogeneous compute infrastructure in postmortems documenting issues specific to its TPU deployments alongside its primary GPU clusters.

**「Impact」** Automating kernel development and deployment across heterogeneous hardware allows Anthropic to mitigate vendor lock-in to NVIDIA by flexibly reallocating training and inference workloads across AMD, AWS, and Google silicon.

**Tags**: `#artificial intelligence`, `#Anthropic`, `#AI hardware`, `#cloud compute`, `#machine learning infrastructure`

---

<a id="item-tech-news-3"></a>
### [Google Launches Gemini Decisions API with Multimodal Input Support](https://simonwillison.net/2026/Nov/11/gemini-decisions-api/) ⭐️ 7.0/10

Google released the Gemini Decisions API featuring the Gemini Decision 1 model, entering the decision-model category alongside Jev and OpenAI. The API supports yes/no, choice, and rubric-scoring questions across multimodal inputs—including text, images, audio, video, and PDFs—with pricing set at 10 cents per million input tokens and free output tokens. Unlike Jev and OpenAI, which return binary 1.0 or 0.0 scores for yes/no queries, testing shows Gemini Decision 1 outputs continuous probability values.

rss · Simon Willison · Nov 11, 22:03

**「Background」** Decision models are specialized API endpoints tailored for bounded tasks such as classification, routing, and policy checks rather than free-form text generation. Prior implementations in this category include Jev, which focuses on text inputs, and OpenAI&\#x27;s GPT-6 Luna decision model, which supports text and images.

**「Impact」** Developers building classification pipelines can evaluate video, audio, and PDF media directly under a unified decision API, but downstream systems expecting binary 1.0 or 0.0 boolean scores will need thresholding logic to handle Gemini&\#x27;s floating-point probabilities.

**Tags**: `#Artificial Intelligence`, `#Google Gemini`, `#APIs`, `#Multimodal AI`

---

<a id="item-tech-news-4"></a>
### [Meta AI Releases Muse Ember for Efficient Agentic Workloads](https://simonwillison.net/2026/Nov/10/muse-ember/) ⭐️ 7.0/10

Meta AI has released Muse Ember, a lightweight model targeting agentic tasks such as tool calls, coding subtasks, routing, and long document parsing across up to one million input tokens. For prompts of 200,000 tokens or fewer, pricing is set at $0.10 per million input tokens, $0.004 for cached input, and $0.50 per million output tokens, increasing to $0.30 input and $1.50 output beyond that threshold. According to benchmark data from Artificial Analysis, Muse Ember at its highest reasoning configurations reaches the Pareto efficiency frontier for intelligence relative to cost per task.

rss · Simon Willison · Nov 10, 07:28

**「Background」** Meta&\#x27;s Muse model family includes larger counterparts like Muse Spark and Muse Wonder designed for higher-level planning, reasoning, and orchestration. Muse Ember was created to handle the high-volume execution, tool calls, and sub-agent routing beneath those larger models at substantially lower operating costs.

**「Impact」** Developers running high-volume agent workflows gain an efficiency-frontier model option that delivers reasoning performance comparable to Claude Haiku 5.5 \(xhigh\) at roughly half the benchmark cost per task, while offering cached input pricing at $0.004 per million tokens for sub-200k prompts.

<details><summary>References</summary>
<ul>
<li><a href="https://dev.meta.ai/models/muse-ember">Muse Ember | Meta</a></li>
<li><a href="https://dev.meta.ai/docs/muse-ember">Muse Ember - Meta Model API - dev.meta.ai</a></li>

</ul>
</details>

**Tags**: `#artificial intelligence`, `#large language models`, `#ai agents`, `#meta ai`

---