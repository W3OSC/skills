# W3OSC Tool Catalog

All tools from the W3OSC organization. Use this to match gaps to tools.
Source: https://github.com/W3OSC

---

## multisigmonitor

**Repo:** https://github.com/W3OSC/multisigmonitor  
**What it does:** Analysis and real-time monitoring for Safe{wallet} multisig wallets. Tracks pending transactions, ownership changes, signer activity, and balance shifts. Delivers alerts.  
**Matches gaps:**
- SP-WM-016 - no Safe monitoring / no immutable alert channel
- SP-WM-008 - time-lock visibility (see pending txns awaiting delay)
- SP-WM-019 - supports external monitoring party workflow  

**When to recommend:** Any org using Safe with no active monitoring. Highest priority tool for DeFi protocols with on-chain treasury.  
**Setup complexity:** Low - TypeScript, self-hosted or run as a service.

---

## depenemy

**Repo:** https://github.com/W3OSC/depenemy  
**What it does:** Scans project dependencies for supply chain risks - malicious packages, typosquatting, suspicious metadata, version anomalies.  
**Matches gaps:**
- SP-DI-007 - no dependency scanning before deployment
- SP-DI-006 - typosquatting detection and prevention
- SP-DI-005 - package verification and integrity  

**When to recommend:** Any org with active GitHub repos and no existing dep scanning. Especially valuable for protocols with complex dependency trees.  
**Setup complexity:** Low - Python, run locally or in CI.

---

## depenemy-action

**Repo:** https://github.com/W3OSC/depenemy-action  
**What it does:** GitHub Action that runs depenemy automatically on every push/PR. Integrates supply chain scanning into existing CI/CD pipeline.  
**Matches gaps:**
- SP-DI-007 - automates dep scanning in pipeline
- SP-DI-010 - supports automated pipeline security controls  

**When to recommend:** Pair with depenemy when org already uses GitHub Actions. Drop-in addition to existing CI.  
**Setup complexity:** Very low - add to existing workflow YAML.

---

## skill-warden

**Repo:** https://github.com/W3OSC/skill-warden  
**What it does:** Security scanner for AI skills (Copilot, Claude, etc.). Detects prompt injection, jailbreak attempts, secret grabbing patterns, and other AI-specific threats in skill/prompt files.  
**Matches gaps:**
- SP-DI-002 - vetting AI-powered extensions and tools
- SP-DI-004 - scanning AI skill files for embedded threats
- SP-GS-006 - social engineering surface in AI tooling  

**When to recommend:** Any org using AI coding assistants or deploying AI skills/agents. Especially relevant if conduit or similar tools are in use.  
**Setup complexity:** Low - Python, run locally or in CI.

---

## skill-warden-action

**Repo:** https://github.com/W3OSC/skill-warden-action  
**What it does:** GitHub Action for skill-warden. Scans AI skill files on every commit, outputs SARIF for GitHub Security tab integration.  
**Matches gaps:** Same as skill-warden, automated in pipeline.  
**When to recommend:** Pair with skill-warden when org has GitHub repos containing AI skill/prompt files.  
**Setup complexity:** Very low - add to existing workflow YAML.

---

## conduit

**Repo:** https://github.com/W3OSC/conduit  
**What it does:** Connects AI agents to org accounts with human-in-the-loop approval flows, fine-grained access control, and detailed audit logs. Prevents agents from taking unsupervised actions on sensitive accounts.  
**Matches gaps:**
- SP-GS-010 - principle of least privilege for AI agent access
- SP-GS-009 - account sharing / credential sharing by agents
- SP-DI-010 - pipeline access controls for automated systems
- SP-GS-004 - immutable audit logs of sensitive actions  

**When to recommend:** Orgs actively using AI agents that interact with accounts, APIs, or on-chain systems. Growing use case as teams adopt AI tooling.  
**Setup complexity:** Medium - TypeScript, requires setup and account integration.

---

## web3-opsec-directory

**Repo:** https://github.com/W3OSC/web3-opsec-directory  
**What it does:** Curated directory of Web3 opsec tools and resources, organized by category. Community-maintained.  
**Matches gaps:** All domains - use when no specific W3OSC tool covers a gap but the user needs tooling recommendations for it (e.g. EDR, password managers, E2E comms).  
**When to recommend:** After top 5 gaps surfaced - point here for gaps not covered by a specific W3OSC tool so user can find best-in-class alternatives.  
**Setup complexity:** N/A - reference resource.

---

## web3-opsec-standard

**Repo:** https://github.com/W3OSC/web3-opsec-standard  
**Interactive tracker:** https://w3osc.github.io/web3-opsec-standard/index.html  
**What it does:** The W3OS open standard itself. Interactive checklist for tracking compliance across all 6 domains. 75 requirements, 282 control points.  
**When to recommend:** After compass session - give user the interactive tracker so they can self-track progress on all gaps (not just top 5).  
**Setup complexity:** N/A - web app, no setup.

---

## Matching Priority

When multiple tools could apply, prefer in this order:
1. Tool that directly addresses the **highest-ranked gap** in the top 5
2. Tools with **lowest setup complexity** for the org's current stack
3. GitHub Action variants over standalone tools if org already uses GitHub Actions
4. `web3-opsec-directory` as fallback when no specific W3OSC tool covers the gap

Never recommend more than one tool per gap. Don't force a tool match where none fits well.
