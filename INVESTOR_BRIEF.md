# HubWork — Investor Brief

*v2 · 21 Nov 2026 · Founder: Cao Duc Chung (Vietnam) · hello@aicollabx.org · [work.aicollabx.org](https://work.aicollabx.org)*

## 1. One line

An operating system for **one person (or a small team) running many projects with many AI coding agents**: shared memory, task cards, leases, a quota-aware dispatcher and human-in-the-loop safety.

## 2. The problem

AI agents (Claude Code, Codex, Gemini CLI, Hermes…) can now write and run real software. A founder with several of them hits new bottlenecks:

- **Cold starts:** every session re-reads the whole project, which burns tokens and loses decisions.
- **Collisions:** two agents edit the same thing, or redo work already done.
- **Silent failures:** a delegated job dies on quota at 2 a.m. and nobody notices until morning.
- **No oversight:** it's unclear what's running, what's waiting on the human, and what's risky.
- **Cost:** each provider has its own quota. Without routing, you pay for the top model on routine work.

Most existing tools are built around either *human* task tracking or *one agent / one framework*. Our hypothesis is that a vendor-neutral control layer for **many heterogeneous agents across projects** is missing for solo founders and small teams; see the competition table below.

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

## 4. Traction (internal use only, founder is the sole user; counted 21 Nov 2026 from the hub repo and ledger)

- **In daily use since October 2026** to run **10+ projects**: an edtech product ([HubStudy](https://github.com/tarochi0001-stack/hubstudy)), smart-home, data-collection and research automation.
- **350+ task cards** processed, **2,800+ commits** to the hub since Oct 19, 2026, **~1,300 dispatcher ledger events**.
- Coordinates **Claude Code, Codex, Gemini CLI, Hermes and other agents** in one queue.
- ~24k lines of Python, 110+ test files.
- **HubStudy (~34k lines of Python/JS) was largely built by agents coordinated through HubWork.** This is our main evidence. We have no external users yet.
- How we counted: `ls queue | wc -l`, `git log | wc -l` on the hub repo, and line counts of `coordinator.jsonl` and `hubctl/*.py`. The repo is private; we can show a screen-share audit on request.

## 5. Competition

| Alternative | Overlap | Our angle (hypothesis) |
|---|---|---|
| Linear / Jira / Plane | Task tracking | Built for humans. We add leases, agent dispatch and quota recovery |
| GitHub Copilot coding agent, Devin, OpenHands | A single coding agent | We coordinate *many* of them across vendors |
| CrewAI / LangGraph | Multi-agent frameworks (code-level) | Ops layer for existing CLI agents, no rewrite needed |
| GitHub Actions + Slack/Telegram + logs | DIY stack | One opinionated system with safety levels and memory |

## 6. Why now

- Coding agents crossed the "useful" threshold in 2025–2026. Solo founders and small teams now run several agents in parallel.
- Model providers sell quota and credits per vendor, so cost-aware routing across vendors is becoming a real need.
- Reliable, safe autonomy (who may deploy, spend or touch keys) is the main blocker for companies adopting agents.

## 7. Business model (hypotheses, not validated)

| Phase | Offer |
|---|---|
| 1. Open-core CLI | Free local hub for solo developers (community and distribution) |
| 2. Pro | Hosted dashboard, team leases, cross-machine sync, alerts: ~$15–30 per seat per month |
| 3. Team / agency | Policy controls, audit log, cost reporting across providers |

## 8. Roadmap & use of credits

| Next 6 months | Milestone |
|---|---|
| Month 1–2 | Web dashboard; one-command install for other developers |
| Month 3–4 | 20 external alpha users. Success: ≥40% active in week 4; ≥70% of jobs completed without manual rescue; cost per job reported |
| Month 5–6 | Hosted multi-user beta; pricing test |

Credits go to: running agent fleets (Claude, OpenAI and Gemini APIs) for development and evaluation, hosting the dashboard, and CI.

## 9. Risks & mitigation

| Risk | Mitigation |
|---|---|
| Providers ship their own orchestration | Stay vendor-neutral. The value is coordinating *across* vendors |
| Security of autonomous agents | Safety levels built in, secrets never stored in memory, human approval for risky actions |
| Solo founder | The product itself multiplies one founder's output (see HubStudy) |

## 10. Ask

AI and cloud credits to run agent fleets for development and evaluation over 6 months, plus accelerator mentoring on developer go-to-market. Open to pre-seed conversations.

## 11. Team

**Cao Duc Chung, solo founder (full-time).**
- Bachelor of Business Administration, University of Economics.
- 10 years in sales at MobiFone (Vietnam telecom operator), specialising in developing IT projects for business customers: scoping needs, selling and coordinating delivery.
- Last 3 years: 100% of time on researching and learning AI, now 100% dedicated to AI products for work and education.
- Mission: products that serve everyday needs for ordinary people.
- Why this founder: a sales and project-delivery background (customer discovery, B2B/B2B2C channels such as schools and telecom partners) paired with hands-on AI building, shipping production code through agent orchestration rather than a large engineering team.

Gap we know: no second technical co-founder; HubWork itself is the leverage that lets one founder run 10+ projects.
