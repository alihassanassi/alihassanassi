# Ali Hassan Assi

Building autonomous cybersecurity systems. Writing about AI safety.

📍 San Diego, CA
📝 Research: [alihasanassi.com/research](https://alihasanassi.com/research)
🐛 HackerOne: [@syfodyaz2](https://hackerone.com/syfodyaz2)
✉️ contact@alihasanassi.com

---

## JARVIS

A local-first AI cybersecurity operations console. One machine, no cloud, no telemetry. ~200K+ lines across 700+ Python files, 27 subsystems, 260+ registered tools. Built solo over 40 days.

JARVIS is an autonomous operator. It runs bug-bounty reconnaissance, watches its own behavior for drift, talks through a full voice pipeline, and logs every action it takes into a hash-chained audit log currently past 82,000 records. It is designed under one hard constraint: it cannot be told to ignore its own safety rules, because the rules are not policy — they are architecture.

Key properties:

- **phi4-mini reasoning core via Ollama.** All security analysis, tool selection, and conversation run locally. No API keys. No data leaves the machine.
- **Seven-gate fail-closed safety chain.** Config → command blocklist → scope → autonomy policy → approval → audit → kill switch. Every gate fails closed. Offensive tools and report submission are flagged never-autonomous.
- **Hash-chained audit log.** SHA256 chain. Every tool call, finding, memory write, and policy decision. Chain integrity verified on every boot.
- **Hardware-adjacent kill switch.** Ctrl+Alt+Shift+K plus a sentinel file on disk. Dual-mechanism, software-bypass resistant.
- **Six-layer memory.** Working → episodic → semantic → preference → project → system. Promotion rules move knowledge through the stack as it earns persistence.
- **Persistent behavior layer.** Operator-state modeling, persona-state tracking, interruption governance, cross-session memory, and an inner-voice daemon. Internally referred to as the consciousness layer. Not ornamental — these systems govern when JARVIS speaks, what it raises unprompted, and how it remembers the operator between sessions.
- **Voice I/O pipeline.** Kokoro ONNX primary (~100 ms, CPU), Piper and SAPI fallbacks. Seven personas. Whisper STT with wake-word and barge-in handling.

JARVIS itself is not public and will remain a single-operator system. The architecture and design decisions behind it are written up in the trilogy below.

## Writing

Three papers on autonomous AI safety architecture, arguing that safe autonomous AI requires three things the current industry does not build deliberately: a structural constitution below the product, an ambient-system architecture above it, and a personal-alignment layer inside the operator running it. All three are argued from one working system.

1. **The Constitution Before the Product** — a five-layer safety architecture, seven serial fail-closed gates, hash-chained audit, and a kill switch framed as covenant.
2. **The Ambient Intelligence Problem** — memory, attention, interruption, personality, and off-mode as first-class subsystems rather than UX polish.
3. **What Dario Didn't Say** — the operator-erosion dynamic and why personal alignment is a load-bearing beam of AI safety that nobody reinforces.

Read at [alihasanassi.com/research](https://alihasanassi.com/research).

## Open-source

- [ai-safety-gates](https://github.com/alihassanassi/ai-safety-gates) — clean reference implementation of the seven-gate safety chain from Paper 1, suitable for any autonomous AI system. MIT licensed.

## Philosophy

AI should serve the individual. Local, private, loyal, answering to nobody but the person who built it. The interesting problem in building a personal AI isn't intelligence — it's presence. The interesting problem in building an autonomous security agent isn't capability — it's restraint.

## Status

Active development. Not accepting contributions on JARVIS. Reference implementation above welcomes issues and small fixes.
