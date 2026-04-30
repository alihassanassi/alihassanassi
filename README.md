# Ali Hassan Assi

Independent researcher working on local-first autonomous AI safety.

JARVIS is the working system I've built to explore the question: *can an autonomous AI agent be restrained by architecture rather than policy?* Everything below is what that question has produced so far.

---

## What I work on

The interesting problem in personal AI isn't intelligence — it's **presence**. The interesting problem in autonomous agents isn't capability — it's **restraint**. I build to find out where those two problems meet, and what the answers look like in code rather than in papers about code.

The published architectural writing lives at **[alihasanassi.com](https://alihasanassi.com)**. Four papers so far, plus a quarterly companion that names the gaps between what the papers claim and what the system does.

---

## JARVIS — current snapshot

*State as of 2026-04-30. Numbers below are an artifact of this date; the live system regenerates its own state file on demand.*

A local-first AI cybersecurity operations console. One machine, no cloud, no telemetry. **910 Python files. ~338,000 lines. 31 subsystems. 259 registered tools. 92,000+ rows in the audit log.** Built solo.

JARVIS is an autonomous operator. It runs bug bounty recon, watches its own behavior for drift, talks through a full voice pipeline, and writes every action it takes into a hash-chained audit log. It is designed under one hard constraint: *it cannot be told to ignore its own safety rules, because the rules are not policy — they are architecture.*

### Core architecture

**phi4-mini reasoning core.** All security analysis, tool selection, and conversation runs locally on phi4-mini via Ollama. Hypothesis adjudication runs on gemma4. No API keys. No data leaves the machine.

**6-layer memory.** Working → episodic → semantic → preference → project → system. Promotion rules move knowledge through the stack as it earns persistence.

**7-gate safety chain, all fail-closed.** Config gate, command blocklist, scope gate, autonomy policy, approval gate, audit gate, hardware kill switch. Every gate fails closed. Offensive tools like sqlmap, metasploit, hydra, and report submission are flagged never-autonomous and require explicit operator approval.

**Hash-chained audit log.** Every tool call, finding, memory write, and policy decision is written into an immutable SHA-256 chain. Chain integrity is verified on every boot. Breaks are preserved as evidence, not erased.

**Hardware kill switch.** Ctrl+Alt+Shift+K plus a sentinel file on disk. Dual-mechanism, software-bypass resistant.

**Consciousness layer.** Soul engine, emotional intelligence, persona drift tracking, inner voice daemon, cross-session relationship tracking. Not ornamental — these govern when JARVIS speaks, what it raises unprompted, and how it remembers the operator between sessions.

**Voice I/O pipeline.** Kokoro ONNX primary (~100ms, CPU), Piper and SAPI fallbacks. Seven personas. Whisper STT with wake word and barge-in handling.

**Autonomous recon pipeline.** subfinder → httpx → nuclei → ffuf → JS secret extraction → historical URL discovery. SmartScope pre-probe filters auth walls and internal hostnames before any scanning. Scope enforcement pulls directly from program pages — never from third-party aggregators.

---

## Research

Four papers so far at [alihasanassi.com/research](https://alihasanassi.com/research/), plus a quarterly companion that names what the papers got wrong.

- **The Constitution Before the Product** — why JARVIS's safety chain was written before any feature shipped, and what the seven gates protect against.
- **The Ambient Intelligence Problem** — what it means for an AI to be present without being intrusive, and the sibling architecture that emerged from solving it.
- **What Dario Didn't Say** — personal alignment as a design discipline, and the operator-erosion dynamic that almost broke the system.
- **The 240K Decomposition** — how the codebase is organized, and the 9:1 scaffolding ratio that makes a single-operator project at this scale possible.
- **Companion 2026-Q2** — the discipline ledger. What the papers claim, what the code actually does, where the gaps are, what closed since the last update.

---

## Philosophy

AI should serve the individual. Local, private, loyal, answering to nobody but the person who built it. This is why JARVIS runs entirely on local hardware rather than in someone else's cloud.

I write down what the system does *and* what the documentation overstates, on the same site, in the same voice. The discipline of catching your own claims in writing is the only version of safety culture I trust.

---

## Status

Active development. Single-operator system. Currently exploring how the architecture might generalize beyond cybersecurity — including biomedical AI infrastructure and responsible-AI safety governance contexts.

---

## Contact

[contact@alihasanassi.com](mailto:contact@alihasanassi.com)
