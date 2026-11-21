# HubWork — Investor Brief

*November 2026 · Founder: Cao Duc Chung (Vietnam) · hello@aicollabx.org · [work.aicollabx.org](https://work.aicollabx.org)*

## 1. One line

An operating system for **one person (or a small team) running many projects with many AI coding agents**: shared memory, task cards, leases, a quota-aware dispatcher and human-in-the-loop safety.

## 2. The problem

AI agents (Claude Code, Codex, Gemini CLI, Hermes…) can now write and run real software. A founder with several of them hits new bottlenecks:

- **Cold starts:** every session re-reads the whole project, which burns tokens and loses decisions.
- **Collisions:** two agents edit the same thing, or redo work already done.
- **Silent failures:** a delegated job dies on quota at 2 a.m. and nobody notices until morning.
- **No oversight:** it's unclear what's running, what's waiting on the human, and what's risky.
- **Cost:** each provider has its own quota. Without routing, you pay for the top model on routine work.

Existing tools (issue trackers, agent frameworks) manage either *humans* or *one agent*. None of them run a **fleet of heterogeneous agents across projects** day to day.

## 3. The product (working today)

| Capability | What it does |
|---|---|
| **Task cards** | Each job has owner, type (code / investigate / ops / live), done-condition, proof command and AUTO level |
| **Leases & checkpoints** | One agent per card. Stalled leases are reclaimed and progress is checkpointed |
| **Dispatcher** | Runs on a schedule (launchd). Hands ready cards to the cheapest capable agent within daily caps per provider |
| **Quota-aware pause/resume** | When a provider runs out, the job pauses and auto-resumes after the reset |
| **Delegation watch** | Background jobs are monitored for death, stall and completion, with alerts sent to the human |
| **Tiered memory** | Per-project `state.md`, decisions and handoffs. `hub brief` gives each new session a compact start |
| **Safety levels** | `AUTO=code / ops / live / full`. Money, keys, live risk and deletion always need the human |
| **Reports** | Status board, "waiting on you" list, token/quota ledger, weekly report, Telegram notifications |

## 4. Traction (real usage, founder as user #1)

- **In daily use since October 2026** to run **10+ projects**: an edtech product ([HubStudy](https://github.com/tarochi0001-stack/hubstudy)), smart-home, data-collection and research automation.
- **350+ task cards** processed, **2,800+ commits** to the hub since Oct 19, 2026, **~1,300 dispatcher ledger events**.
- Coordinates **Claude Code, Codex, Gemini CLI, Hermes and other agents** in one queue.
- ~24k lines of Python, 110+ test files.
- **HubStudy (~34k lines) was largely built by agents coordinated through HubWork.** That is the strongest proof that the system works.

## 5. Why now

- Coding agents crossed the "useful" threshold in 2025–2026. Solo founders and small teams now run several agents in parallel.
- Model providers sell quota and credits per vendor, so cost-aware routing across vendors is becoming a real need.
- Reliable, safe autonomy (who may deploy, spend or touch keys) is the main blocker for companies adopting agents.

## 6. Business model (planned)

| Phase | Offer |
|---|---|
| 1. Open-core CLI | Free local hub for solo developers (community and distribution) |
| 2. Pro | Hosted dashboard, team leases, cross-machine sync, alerts: ~$15–30 per seat per month |
| 3. Team / agency | Policy controls, audit log, cost reporting across providers |

## 7. Roadmap & use of credits

| Next 6 months | Milestone |
|---|---|
| Month 1–2 | Web dashboard; one-command install for other developers |
| Month 3–4 | 20 external alpha users (developer communities in Vietnam and SEA) |
| Month 5–6 | Hosted multi-user beta; pricing test |

Credits go to: running agent fleets (Claude, OpenAI and Gemini APIs) for development and evaluation, hosting the dashboard, and CI.

## 8. Risks & mitigation

| Risk | Mitigation |
|---|---|
| Providers ship their own orchestration | Stay vendor-neutral. The value is coordinating *across* vendors |
| Security of autonomous agents | Safety levels built in, secrets never stored in memory, human approval for risky actions |
| Solo founder | The product itself multiplies one founder's output (see HubStudy) |

## 9. Ask

AI and cloud credits plus accelerator support to package HubWork for external users. Open to pre-seed conversations.
