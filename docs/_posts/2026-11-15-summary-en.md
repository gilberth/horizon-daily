---
layout: default
title: "Horizon Summary: 2026-11-15 (EN)"
date: 2026-11-15
lang: en
---

> From 6 items, 1 important content pieces were selected

---

**Technology News**
1. [Cursor Breach Exposes Credentials and Distributes Trojanized Claude Code Extension](#item-tech-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Cursor Breach Exposes Credentials and Distributes Trojanized Claude Code Extension](https://www.bleepingcomputer.com/news/security/cursor-confirms-security-breach-led-to-malicious-claude-code-extension/) ⭐️ 7.0/10

Cursor confirmed a security breach after an attacker used an access key exposed by Fireworks AI to access a shared read-only storage bucket containing non-Privacy Mode coding agent traces and unredacted credentials affecting fewer than 0.01% of customers. The attacker leveraged these credentials to breach Cursor&\#x27;s internal systems and cache trojanized builds of Anthropic&\#x27;s Claude Code extension on the Cursor Marketplace for 11 hours on October 29, 2026. Up to 5,000 users who requested versions 2.1.312 or 2.1.313 during that window potentially received malicious builds designed to establish a persistent SSH backdoor.

rss · BleepingComputer · Nov 14, 17:27

**「Background」** Cursor shares coding session traces from users who have not enabled Privacy Mode with infrastructure providers like Fireworks AI for model training. The incident stems from a broader credential breach targeting Fireworks AI, which also compromised data across other enterprise customers including Uber and Notion.

**「Impact」** Users who downloaded versions 2.1.312 or 2.1.313 of the Claude Code extension from Cursor Marketplace on October 29 must inspect systems for unauthorized SSH access and rotate any credentials handled within the compromised environment.

**Tags**: `#developer-tools`, `#ai-security`, `#software-supply-chain`, `#cursor`

---