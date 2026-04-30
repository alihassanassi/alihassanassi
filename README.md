# JARVIS

A local-first AI cybersecurity operations console. One machine, no cloud, 
no telemetry. ~241,000+ lines across 731 Python files. 27+ subsystems 
across 33 directories. 260+ registered tools. Built solo.

---

## What it is

JARVIS is an autonomous operator. It runs bug bounty recon, watches its 
own behavior for drift, talks through a full voice pipeline, and logs 
every action it takes into a hash-chained audit log currently at 81,000+ 
records. It is designed under one hard constraint: it cannot be told to 
ignore its own safety rules, because the rules are not policy — they are 
architecture.

## Core architecture

**phi4-mini reasoning core.** All security analysis, tool selection, 
and conversation runs on phi4-mini via Ollama. Locally hosted. No API 
keys. No data leaves the machine.

**6-layer memory.** Working → episodic → semantic → preference → 
project → system. Promotion rules move knowledge through the stack as 
it earns persistence.

**7-gate safety chain, all fail-closed.** Config gate, command 
blocklist, scope gate, autonomy policy, approval gate, audit gate, 
hardware kill switch. Every gate fails closed. Offensive tools like 
`sqlmap`, `metasploit`, `hydra`, and report submission are flagged 
never-autonomous and require explicit operator approval.

**Hash-chained audit log.** Every tool call, finding, memory write, 
and policy decision is written into an immutable chain. Chain 
integrity is verified on every boot. Currently 81,000+ records and 
counting.

**Hardware kill switch.** Ctrl+Alt+Shift+K plus a sentinel file on 
disk. Dual-mechanism, software-bypass resistant. Halts all autonomous 
operations immediately.

**Consciousness layer.** Soul engine, emotional intelligence, persona 
drift tracking, inner voice daemon, and cross-session relationship 
tracking. Not ornamental — they govern when JARVIS speaks, what it 
raises unprompted, and how it remembers the operator between sessions.

**Voice I/O pipeline.** Kokoro ONNX primary (~100ms, CPU), Piper and 
SAPI fallbacks. Seven personas. Whisper STT with wake word and 
barge-in handling.

**Autonomous recon pipeline.** subfinder → httpx → nuclei → ffuf → JS 
secret extraction → historical URL discovery. SmartScope pre-probe 
filters auth walls and internal hostnames before any scanning. Scope 
enforcement pulls directly from HackerOne's program pages — never 
from third-party aggregators.

## Philosophy

AI should serve the individual. Local, private, loyal, answering to 
nobody but the person who built it. This is why JARVIS runs entirely 
on local hardware rather than in someone else's cloud.

The interesting problem in building a personal AI isn't intelligence — 
it's presence. And the interesting problem in building an autonomous 
security agent isn't capability — it's restraint.

## Research

Architectural writing on the design choices behind the system is 
published at [alihasanassi.com](https://alihasanassi.com).

## Status

Active development. Single-operator system. 
