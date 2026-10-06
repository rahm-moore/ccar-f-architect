# CCAR-P Study Progress Tracker (formerly CCAR-F — pivoted 2026-09-23)

**PIVOT NOTICE (2026-09-23):** Target changed from CCAR-F (Foundations) to CCAR-P (Claude Certified Architect – Professional), per Rahm's confirmation this is what his role/Pearson VUE pre-approval actually requires. Bounteous's internal dashboard still only shows a CCA-F (Foundations) nomination — worth confirming with L&D/manager that Professional is properly authorized on that side too, separate from whatever granted the Pearson VUE pre-approval.

Everything below the "Legacy CCAR-F Tracking" section reflects the OLD Foundations-focused plan and is kept for reference/reusable background knowledge — Foundations content isn't wasted, it's the assumed technical base Professional builds on, but it does NOT map onto Professional's domains directly.

CCAR-P: 63 standalone (non-scenario) items, 7 domains, 120 min, proctored via Pearson VUE, passing score 720/1000. No prerequisite — Foundations is not required to sit Professional.
**Source note:** exam guide is third-party. Two independent sources (claudecertificationguide.com and tutorialsdojo.com) now agree exactly on domain names and weights, which is a good confidence signal, but neither is Anthropic's own site — still treat as directional pending official confirmation.

## CCAR-P: The Seven Domains
| Domain | Weight | Focus |
|---|---|---|
| Integration | 19% | Wiring Claude into enterprise systems and data — **heaviest domain** |
| Solution Design & Architecture | 17% | Model, architecture, and API-pattern selection |
| Evaluation, Testing & Optimisation | 16% | Measuring quality, testing rigorously, tuning for cost/performance |
| Governance, Safety & Risk Management | 14% | Compliance, safety controls, managing risk — **new vs. Foundations** |
| Stakeholder Communication & Lifecycle Management | 14% | Explaining/defending decisions; managing the system over time — **new vs. Foundations** |
| Claude Models, Prompting & Context Engineering | 13% | Choosing/steering models; engineering context at scale |
| Developer Productivity & Operational Enablement | 7% | Enabling teams to build and operate effectively — **new vs. Foundations** |

The three domains marked "new vs. Foundations" (governance, stakeholder/lifecycle, developer enablement) are 35% of the exam and don't appear on the Foundations blueprint at all — this is the real net-new content, not just "more of the same."

## What Carries Over from Foundations Work
- Agentic architecture/orchestration knowledge (subagents, agent skills) → feeds Solution Design & Architecture and Integration
- MCP Advanced Topics → feeds Integration domain directly
- Building with the Claude API (structured output, prompt engineering) → feeds Claude Models, Prompting & Context Engineering
- Claude Code 101 / in Action → feeds Developer Productivity & Operational Enablement (smaller domain, 7%)
- **Gap (fully closed 2026-10-06):** this originally flagged Governance/Safety/Risk, Stakeholder Communication/Lifecycle, and Evaluation/Testing/Optimisation as unaddressed. As of 2026-10-02, Governance/Safety/Risk and Evaluation/Testing/Optimisation were complete (Modules 3 and 2) and Stakeholder Communication/Lifecycle was in progress (Module 4). **As of 2026-10-06, all five official modules are complete** — Module 4 (Stakeholder Communication/Lifecycle) and Module 5 (Developer Productivity & Operational Enablement) both finished. No domain gap remains.

## ✅ OFFICIAL COURSE FOUND (2026-09-23): Claude Certified Architect – Professional Prep Course
Confirmed directly from Rahm's logged-in Anthropic Academy view — free, register button live. This replaces the "no course identified" gaps below with a real, official curriculum.

**5 lessons, ~733 minutes (~12.2 hours) total:**
| # | Lesson | Duration | Maps to Domain(s) |
|---|---|---|---|
| 1 | Claude Platform & Solution Design | 238 min | Solution Design & Architecture (17%) **+** Claude Models, Prompting & Context Engineering (13%) — combined; includes RAG pipeline design, model/context strategy, prompting-as-architecture, entry points/governance |
| 2 | Enterprise Integration & Production | 158 min | Integration (19%) |
| 3 | Responsible AI, Safety & Risk for Architects | 114 min | Governance, Safety & Risk Management (14%) |
| 4 | Stakeholder Engagement, Lifecycle & GTM | 178 min | Stakeholder Communication & Lifecycle Management (14%) |
| 5 | Team Enablement & Operational Productivity | 45 min | Developer Productivity & Operational Enablement (7%) |

**⚠️ Notable gap in the official course itself:** no lesson is dedicated to Evaluation, Testing & Optimisation (16% of the exam). Module 1's description mentions "evaluations as the gate before any model swap" and a checkpoint called "Cost & Latency Calculator," so some content is folded in — but it's not a standalone lesson like the other domains get. Worth watching closely once we're through Module 1 to see how much real coverage this gets; may still need supplemental material for this domain specifically.

**Recommended prerequisites (not required) per the course page:** Claude 101 ✅, Claude Code in Action ✅, AI Fluency: Framework & Foundations (⚠️ check — may be different from "AI Fluency for Small Businesses," which is only 6/10 done), Building with the Claude API ✅, Introduction to Model Context Protocol (skipped, went straight to Advanced), **AI Capabilities and Limitations (new course, not previously tracked — need to check registration status)**.

## CCAR-P Course Coverage (updated tracker — 2026-10-06: ALL MODULES COMPLETE)

**Correction (2026-10-02):** An earlier check of the Google Drive `CCAR-P` folder mislabeled which Drive folder was Module 2 vs. Module 3. Verified directly against folder IDs since then — the mapping below is confirmed correct.

| Drive Module | Maps to Official Lesson | Domain(s) | Status |
|---|---|---|---|
| Module 1 | Lesson 1, "Claude Platform & Solution Design" (238 min) | Solution Design & Architecture (17%) + Claude Models, Prompting & Context Engineering (13%) | **✅ COMPLETE (2026-09-26)** — all 33 screens through "Recap · Assembly & Recap" |
| Module 2 | Lesson 2, "Enterprise Integration & Production" (158 min) | Integration (19%) — **and** Evaluation, Testing & Optimisation (16%), which turns out to be folded in here, not missing | **✅ COMPLETE (2026-09-29)** — 21 screens through "Module Complete · Architect," covering Evals, POC-to-Prod, Sizing/Feasibility, Integration patterns, and A/B Testing & Observability |
| Module 3 | Lesson 3, "Responsible AI, Safety & Risk for Architects" (114 min) | Governance, Safety & Risk Management (14%) | **✅ COMPLETE (2026-10-02)** — 22 screens through "Module Complete · Architect," covering Alignment, Guardrails, Fairness, Review Routing, and Compliance |
| Module 4 | Lesson 4, "Stakeholder Engagement, Lifecycle & GTM" (178 min) | Stakeholder Communication & Lifecycle Management (14%) | **✅ COMPLETE (2026-10-06)** — 20 screens through "Module Complete · Architect," covering Discovery, Tradeoffs & GTM (demo design, decision framing), Feedback Loops (SLAs, production signal governance), Documentation (handoff/compliance/returning-architect readers), and Entry Point & Outcomes (multi-platform routing, customer outcome docs) |
| Module 5 | Lesson 5, "Team Enablement & Operational Productivity" (45 min) | Developer Productivity & Operational Enablement (7%) | **✅ COMPLETE (2026-10-06)** — 10 screens through "Module Complete · Architect," covering Team Setup (shared environment, rollout, Skill distribution governance, spend posture), Dev Workflows (diligence, verification checklists), and Operational Support (symptom-to-cause diagnosis, runbooks, escalation paths) |

**The whole official CCAR-P Prep Course is now done, as of 2026-10-06.** All 7 exam domains have real, official-source coverage:
- **Evaluation, Testing & Optimisation** closed via Module 2 — evals-as-acceptance-criteria, the eval workflow, the code/model/human grading ladder with judge calibration, multi-turn evals, A/B and shadow testing, observability layers, and the failure taxonomy (prompt failure / hallucination / model mismatch / orchestrator-workers failure).
- **Governance, Safety & Risk Management** closed via Module 3 — guardrail placement and fail-open/fail-closed design, refusal handling, skill supply-chain security, the four fairness entry points, audience-specific transparency, and obligation→control→owner→evidence compliance mapping.
- **Stakeholder Communication & Lifecycle Management** closed via Module 4 — discovery's listen/translate/write-down filter, tradeoff presentation and demo design for GTM, the feedback-loop decision layer and SLA traceability, three-reader documentation (handoff recipient / compliance reviewer / returning architect), and multi-platform entry-point/outcome documentation.
- **Developer Productivity & Operational Enablement** closed via Module 5 — shared team environment baselines, champion-then-batch rollout, governed Skill distribution mechanisms, dev-workflow diligence and verification checklists, and operational support via symptom-to-cause runbooks.

**Net effect:** all 5 modules complete, all 7 domains covered by real official-source material. There is no remaining content gap in the CCAR-P Prep Course itself. Remaining open items are logistics (Bounteous/Pearson VUE nomination confirmation) rather than study content.

## CCAR-P Detailed Domain Topics (source: tutorialsdojo.com, cross-checked against claudecertificationguide.com)

### Domain 1: Solution Design & Architecture (17%)
- Business requirements → solution planning; connecting architecture choices to measurable outcomes (productivity, cost, performance)
- End-to-end architecture design: inputs, processing, outputs, feedback; choosing workflow-based, agentic, augmented-LLM, or multi-agent patterns
- Decomposition and orchestration of tools/agents/multi-agent systems
- **Carries over from:** Foundations agentic architecture, subagents, agent skills work

### Domain 2: Claude Models, Prompting & Context Engineering (13%)
- Model selection trade-offs: reasoning ability, speed, context capacity, cost
- Prompt design: system prompts, templates, few-shot/zero-shot, structured reasoning, guardrails
- Context/token management: prompt caching, modular prompts, Claude Skills for recurring instructions
- **Carries over from:** Building with the Claude API

### Domain 3: Integration (19% — heaviest domain)
- Tool/agent security: least-privilege access, auth weaknesses, avoiding unnecessary capability expansion
- RAG pipeline design: chunking, indexing, retrieval strategy matched to data/query patterns
- Protocol selection: MCP vs. direct APIs vs. CLI vs. agent-to-agent; observability and monitoring at scale
- **Carries over from:** MCP Advanced Topics (partial — RAG and enterprise integration depth is new)

### Domain 4: Evaluation, Testing & Optimisation (16%) — ✅ COMPLETE (Module 2, 2026-09-29)
- Defining eval criteria: accuracy, latency, cost, safety, security; building representative eval datasets (automated + human review)
- A/B testing, diagnosing hallucinations/prompt failures/model mismatches
- Performance monitoring: logging, observability, optimizing token use/cost/response time

### Domain 5: Governance, Safety & Risk Management (14%) — ✅ COMPLETE (Module 3, 2026-10-02)
- Guardrails and risk identification: prompt injection, data exposure, misuse, technical failure modes
- Human-in-the-loop validation for sensitive/high-impact outputs
- Compliance: GDPR, HIPAA, FedRAMP; bias, fairness, transparency, responsible data use

### Domain 6: Stakeholder Communication & Lifecycle Management (14%) — ✅ COMPLETE (Module 4, 2026-10-06)
- Discovery/requirements gathering across business, technical, legal, security, ops stakeholders
- Communicating architecture/trade-offs to technical and non-technical audiences; documentation
- Managing feedback across the full lifecycle: design → implementation handoff → monitoring → continuous improvement

### Domain 7: Developer Productivity & Operational Enablement (7%) — ✅ COMPLETE (Module 5, 2026-10-06)
- Configuring Claude Code and shared dev environments for teams (security + consistency)
- AI-assisted development workflows: code analysis, implementation, testing, documentation
- Debugging/operational support using Claude-assisted tooling
- **Carries over from:** Claude Code 101 / Claude Code in Action

## CCAR-P Study Materials (per tutorialsdojo.com)
- Official CCAR-P certification page and exam guide (via Anthropic Partner Academy — not yet independently accessed/confirmed)
- Official "Claude Certified Architect – Professional Certification Prep Course" (name referenced, not yet located/confirmed directly)
- Tutorials Dojo's CCAR-P Practice Exams (third-party, multiple-choice + multiple-response, with explanations)

## CCAR-P Practice Test Generator — built 2026-09-23, expanded 2026-10-02 and 2026-10-06
`ccarp-practice-test-generator.html` in the repo (`programs/anthropic-ccar/practice-tests/`): now a 112-question bank (up from 64) across all 7 domains, weighted to documented proportions, length-balanced distractors, positions shuffled across A/B/C/D from the start. Test size increased from 30 → 40 → 45 questions per run to keep pace with the larger bank.

**2026-10-02 expansion:** 30 new questions added, grounded directly in real lesson content read from the Module 2, 3, and (early) Module 4 Google Drive docs (not third-party material) — covering enterprise integration patterns, use-case sizing and feasibility, the evals framework, A/B testing and observability, guardrails, fairness, compliance, and discovery.

**2026-10-06 expansion:** 19 more questions added now that Modules 4 and 5 are fully complete, grounded in the rest of Module 4 (tradeoff presentation and GTM demo design — the decision frame, capabilities-vs-scenario demos, limit placement; production feedback loops and SLA traceability; three-reader handoff/compliance/returning-architect documentation; multi-platform entry-point and customer-outcome documentation) and all of Module 5 (shared team environment setup, champion-then-batch rollout, governed Skill distribution mechanisms, dev-workflow diligence and verification checklists, operational support via symptom-to-cause runbooks). **Every exam domain is now grounded in real official-source material — no domain in the bank still relies solely on third-party topic lists.**

**Caveat carried in the tool itself:** questions are original and written to match real course content or documented domain topics, not reproductions of any real exam or vendor content. The 7-domain weighting/format is still third-party (tutorialsdojo.com + claudecertificationguide.com) for the official exam blueprint, not yet confirmed against Anthropic's own materials — but the questions' underlying content is first-party, pulled directly from the official Anthropic Academy CCAR-P Prep Course lesson docs.

**Refactor (prompted by Rahm asking whether this could be sold as an app):** the 57 questions that were closely grounded in specific named frameworks/terminology from the official course (Module 1's platform-map vocabulary, plus all of the 2026-10-02 and 2026-10-06 Module 2–5 batches) were rewritten from scratch — same underlying architecture/ops concept tested, but genericized scenarios with no course-specific named frameworks, product terminology, or close paraphrasing of lesson text. The original 55 pre-10-02 questions (already written to match documented topic lists rather than course text) were left as-is. Every question is now tagged:
- **`source`: `"original"`** (57) — the rewritten, genericized set, or **`"generic"`** (55) — the pre-existing industry-pattern set. A dropdown in the tool filters by this.
- **`difficulty`: `"less"`** (18), **`"challenging"`** (46), or **`"very"`** (48) — a second dropdown filters by this.

Narrowing both filters at once can return fewer than 45 questions for a run (the bank isn't evenly split across every combination) — the tool now shows a note when this happens and uses whatever's available rather than erroring.

**Still a caveat for any commercial use:** this rewrite was done by Claude in one pass, not independently legal-reviewed. Before publishing, selling, or distributing any version of this quiz, treat the "Original only" filter as a starting point, not a guarantee — have someone independently check it against the actual course material first.

## Unverified Exam Logistics (via Gemini AI-mode summary, 2026-09-23)
- Cost: $175 USD (free for eligible Anthropic partners) — differs from CCAR-F's $125
- Validity: 12 months, renewable via reassessment
- **Not yet confirmed against Anthropic's own site — treat as directional only.**

## Next Steps (updated 2026-10-06)
1. **All 5 official modules are now complete** — no remaining course content gap. Use the 112-question/45-per-run practice generator for full-coverage review across all 7 domains; a low score anywhere now reflects retention, not unstudied material.
2. Run a full practice test (or several) this week and log scores in the generator's history to find any domain that needs a second pass before scheduling the real exam.
3. Resolve the Bounteous/Pearson VUE nomination mismatch (flagged above) before scheduling the real exam — confirm Professional is actually sanctioned on Bounteous's side.
4. Re-run the deadline math once nomination/scheduling is sorted — don't assume Oct 31 or the Foundations-era 30-day framing still applies to Professional.
5. Once practice scores are consistently strong across all domains, schedule the Pearson VUE exam.

---

## Legacy CCAR-F Tracking (superseded 2026-09-23, kept for reference)

Claude Certified Architect – Foundations (CCAR-F)
60 questions, 120 min, proctored via Pearson VUE, passing score 720/1000

Last updated: 2026-09-11

## Exam Domains & Course Coverage

### 1. Agentic Architecture & Orchestration — 27%
| Course | Status | Progress |
|---|---|---|
| Introduction to agent skills | Completed | ✅ 2026-Sep-18 |
| Introduction to subagents | Completed | ✅ 2026-Sep-19 |
| Claude Code in Action | Completed | ✅ 2026-Jun-05 |

**Domain fully covered** — highest-weighted section of the exam (27%) is done.

### 2. Claude Code Configuration & Workflows — 20%
| Course | Status | Progress |
|---|---|---|
| Claude Code 101 | Completed | ✅ 2026-Sep-11 |
| Claude Code in Action | Completed | ✅ 2026-Jun-05 |
| Introduction to Claude Cowork | Not started | 0/15 lessons |

### 3. Prompt Engineering & Structured Output — 20%
| Course | Status | Progress |
|---|---|---|
| Claude 101 | Completed | ✅ 2026-Jul-29 |
| Building with the Claude API | Completed | ✅ 2026-Sep-17 |

Domain fully covered.

### 4. Tool Design & MCP Integration — 18%
| Course | Status | Progress |
|---|---|---|
| Introduction to Model Context Protocol | Skipped intentionally — revisit only if practice tests expose a fundamentals gap | 0/14 lessons |
| Model Context Protocol: Advanced Topics | Completed | ✅ 2026-Sep-19 |

### 5. Context Management & Reliability — 15%
| Course | Status | Progress |
|---|---|---|
| (none registered) | Gap | — |

**Note:** No registered course clearly targets CALM framework, prompt caching, context compaction, or token budgeting. Check Anthropic Academy for a dedicated module before exam day.

### Supplemental / Lower Priority
| Course | Status | Progress |
|---|---|---|
| AI Fluency for Small Businesses | In progress | 6/10 lessons |

## Recommended Order
1. Finish *Building with the Claude API*
2. *Introduction to subagents* + *Introduction to agent skills*
3. *Introduction to MCP* + *MCP: Advanced Topics*
4. *Introduction to Claude Cowork*
5. Circle back to *AI Fluency for Small Businesses*
6. Fill Context Management & Reliability gap (search Academy for a module)

## External Prep Resources
- Udemy CCAR-F prep courses (unofficial, third-party) — use for practice questions only, after finishing official Academy modules. Verify currency given exam launched March 2026.

## Bounteous Internal Portal (certifications.bounteous.tools)
Separate, employer-run tracker with its own 11-module path (self-reported; L&D verifies). Portal shows 0/11 · 0% enrolled as of 2026-09-11 — **needs manual "Mark complete" clicks**, it does not auto-sync with Skilljar completions.

| # | Portal Module | Maps to Skilljar Course | Skilljar Status |
|---|---|---|---|
| 01 | AI Fluency (optional) | AI Fluency for Small Businesses | In progress, 6/10 |
| 02 | Claude 101 (recommended) | Claude 101 | ✅ Completed 2026-Jul-29 |
| 03 | Claude Code 101 (optional) | Claude Code 101 | ✅ Completed 2026-Sep-11 |
| 04 | MCP Fundamentals (optional) | Introduction to Model Context Protocol | Not started |
| 05 | Claude Code in Action (optional) | Claude Code in Action | ✅ Completed 2026-Jun-05 |
| 06 | Agent Skills (optional) | Introduction to agent skills | ✅ Completed 2026-Sep-18 (click "Mark complete" on portal) |
| 07 | Introduction to Claude Cowork (optional) | Introduction to Claude Cowork | Not started |
| 08 | MCP: Advanced Topics (recommended) | Model Context Protocol: Advanced Topics | ✅ Completed 2026-Sep-19 (click "Mark complete" on portal) |
| 09 | Introduction to subagents (optional) | Introduction to subagents | ✅ Completed 2026-Sep-19 (click "Mark complete" on portal) |
| 10 | Building with the Claude API (recommended) | Building with the Claude API | ✅ Completed 2026-Sep-17 (click "Mark complete" on portal) |
| 11 | CCA-F capstone — schedule official exam, upload certificate | — | Not started |

**Action item:** go through portal modules 02, 03, 05 and click "Mark complete" to reflect actual Skilljar progress (portal won't do this automatically).

**Hands-on practice available:** Bounteous AI Gateway (see ccar-f-resources.md) lets you run Claude Code / API calls against Sonnet & Haiku without a claude.ai login — good for reinforcing Domain 1 (agentic orchestration) and Domain 3 (prompt engineering / structured output) with real exercises, not just video lessons.

## Deadline
**Updated 2026-09-23: actual deadline confirmed as October 31, 2026** — the original 30-day-from-nomination framing (9/24) was incorrect/superseded. No more crunch-mode urgency; pace is now sustainable rather than a sprint.

Exam scheduling status: still unconfirmed as of 2026-09-23 — no longer urgent given the extended timeline, but shouldn't be forgotten. Book whenever a slot lines up with being practice-test-ready.

## Current Status (as of 2026-09-23)
- Domain 1 (Agentic Architecture, 27%): ✅ fully covered
- Domain 2 (Claude Code Config, 20%): mostly covered — Introduction to Claude Cowork still open (0/15)
- Domain 3 (Prompt Engineering, 20%): ✅ fully covered
- Domain 4 (Tool Design & MCP, 18%): ✅ covered (went straight to Advanced Topics, skipped fundamentals intentionally)
- Domain 5 (Context Management & Reliability, 15%): **gap** — no registered course covers this

## Next Course
**Udemy: "Claude Certified Architect Foundations (CCAR-F) Exam 2026"** — confirmed via search to explicitly cover Domain 5 content: CALM framework, prompt caching/cache_control breakpoints, conversation compaction, token budget management. This directly closes the one real content gap remaining.

Optional reinforcement (LinkedIn Learning, not gap-filling but available): "Model Context Protocol (MCP): Hands-On with Agentic AI", "Claude Code 4: Agentic Coding for Professional Developers", "Everyday Productivity with Claude Cowork" (could double as the Cowork domain-2 course).

## Remaining Order (relaxed pace)
1. Udemy CCAR-F 2026 course — closes Domain 5 gap
2. Introduction to Claude Cowork (Skilljar, 0/15) — or substitute LinkedIn Learning's Cowork course
3. Finish AI Fluency for Small Businesses (6/10) — lowest priority, optional
4. Keep using the practice test generator periodically to track retention
5. Schedule Pearson VUE exam once practice scores are consistently strong (18+/20)

## Evening Study Calendar
Existing midday block "CCA-F Training" (11:30am–1:30pm ET) stays as-is. Evening blocks (5:00–6:30pm ET) were set up via `.ics` import for 9/11–9/23, inviting rahmind.consulting@rmoorind.com. Topics for 9/17 onward should be updated to match the revised plan above — let me know if you want a refreshed `.ics` for the remaining days.

## Notes
- Official exam code confirmed as **CCAR-F** via anchor link on Anthropic's own Academy page (`#ccarf-prep`). "CCA-F" is informal community shorthand for the same exam; the Bounteous internal portal also uses "CCA-F" as its internal label.
