<div align="center">

# 🧭 HubWork

**An operating hub for running many projects with many AI coding agents — shared memory, task cards, leases and an automatic dispatcher.**

[🌐 Website](https://work.aicollabx.org) · [📄 Investor brief](INVESTOR_BRIEF.md) · [How it works](#how-it-works) · [Roadmap](#roadmap)

![status](https://img.shields.io/badge/status-in%20daily%20use-blue) ![agents](https://img.shields.io/badge/agents-Claude%20Code%20%7C%20Codex%20%7C%20Gemini%20CLI%20%7C%20Hermes-orange) ![lang](https://img.shields.io/badge/python-3.14-green)

</div>

---

## The problem

A solo founder using several AI agents (Claude Code, Codex, Gemini CLI, Hermes) across many projects hits the same walls every day:

- each session starts cold and re-reads everything (wasted tokens, lost context);
- two agents edit the same thing, or a delegated job dies silently on quota;
- nobody knows what's actually running, what's waiting on the human, and what's done.

## The solution

HubWork is a file-based "brain" plus a CLI (`hub`) that every agent shares:

- 🗂️ **Task cards** with owner, type, AUTO level, proof command and done condition
- 🔒 **Leases & checkpoints** so only one agent works a card at a time; stalled leases are reclaimed
- 🤖 **Dispatcher** that hands ready cards to the cheapest capable agent, within daily quota caps
- 🧠 **Tiered memory** — per-project `state.md`, decisions, handoffs; `hub brief` gives each session a compact start
- 🛡️ **Safety levels** (`AUTO=code/ops/live`) — risky actions always need the human
- 📊 **Status & reports** — what's running, what's waiting on you, token/quota usage, weekly reports
- ⏸️ **Quota-aware** — agents pause and resume when a provider's quota resets

## How it works

```
 Human ──► hub new / approve ──► queue/<id>.md (task card)
                                     │
            dispatcher (launchd) ────┤──► Claude Code / Codex / Gemini / Hermes
                                     │        claim → checkpoint → done
                                     ▼
              projects/<p>/state.md · events/*.jsonl · ledger/ (runs, tokens)
```

## Status

🚧 **In daily use** by the founder to run 10+ projects (edtech, smart-home, research automation); 350+ task cards, 2,800+ commits since Oct 2026 with multiple agents. Source is private for now; this repo hosts public docs and the roadmap.

## Roadmap

- [x] Task cards, leases, checkpoints, dispatcher
- [x] Multi-agent quota caps and pause/resume
- [x] Session brief + tiered memory lint
- [ ] Web dashboard
- [ ] Packaged CLI for other founders/teams
- [ ] Hosted multi-user version

## Contact

Cao Duc Chung — ✉️ hello@aicollabx.org — 🌐 [work.aicollabx.org](https://work.aicollabx.org)
