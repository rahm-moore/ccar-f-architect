# CCAR-F & Claude Professional Notes

Running notes by domain and by course. Add entries as you go — date-stamp new sections.

## Standing Assistance Objectives
Locked in scope for ongoing support in this repo:
1. Track and organize — keep progress tracker, notes, and resources current as courses are completed.
2. Explain concepts — walk through topics across all five domains with examples.
3. Quiz — generate scenario-based practice questions per domain, review wrong answers.
4. Review work — critique CLAUDE.md files, tool schemas, agent designs, prompts against exam-relevant best practices.
5. Research — pull official Anthropic documentation on request; flag third-party/unverified sources.
6. Build study aids — summary sheets, flashcards, study calendar tied to target exam date.
7. Close the Domain 5 gap — hunt down real material on CALM framework, prompt caching, and context compaction.

## 2026-09-11
- Confirmed official exam code is CCAR-F (Anthropic Academy page anchor `#ccarf-prep`); "CCA-F" is informal shorthand used by third parties.
- Completed Claude Code 101 (certificate on file, LinkedIn post drafted separately).
- Identified gap: no registered course maps cleanly to Context Management & Reliability domain (15%) — covers CALM framework, prompt caching / cache_control breakpoints, conversation compaction, token budgeting.

## Domain 1 — Agentic Architecture & Orchestration (27%)
_(notes go here as you work through Introduction to agent skills / subagents)_

## Domain 2 — Claude Code Configuration & Workflows (20%)
_(notes from Claude Code 101 / Claude Code in Action / Cowork)_

## Domain 3 — Prompt Engineering & Structured Output (20%)
_(notes from Claude 101 / Building with the Claude API)_

## Domain 4 — Tool Design & MCP Integration (18%)
_(notes from Introduction to MCP / MCP Advanced Topics)_

### 2026-09-19
- Completed MCP: Advanced Topics — found it especially interesting.
- Covered transport mechanisms: switching between HTTP streaming and local (stdio) MCP server transport.
- **Action item (real work, not just exam prep):** audit current MCP server configs and update/confirm transport handling for HTTP streaming vs. local usage.

## Domain 5 — Context Management & Reliability (15%)
_(gap — log findings here once a source is identified)_

## 2026-09-23 (cont'd) — CCAR-P practice bank built + Gemini exam-logistics data point
- Built `ccar-p-practice-test-generator.html`: 35 original questions across all 7 CCAR-P domains, weighted proportionally, length-balanced/position-shuffled distractors from the start this time. Committed to repo + published as Cowork artifact.
- Two technical details surfaced via Rahm's Gemini quiz session, folded into the question bank: (1) prompt caching depends on exact prefix matching from the start of the prompt — fragmenting/randomizing static content breaks cache hits; (2) production safety/guardrail checks should run as an independent, async, low-cost model classifier rather than re-running the expensive primary model multiple times for a vote.
- Gemini also reported CCAR-P logistics: cost $175 USD (free for eligible Anthropic partners), 12-month validity renewable via reassessment. Differs from the $125/no-stated-validity figures we had for CCAR-F — **unverified, from an AI-generated summary, flag for official confirmation.**
- Still haven't accessed the official Anthropic Partner Academy CCAR-P page directly (login-gated for this session) — asked Rahm to share screenshots of his own logged-in view, same as he did for Foundations.

## 2026-09-23 — Pivot to CCAR-P
- Discovered a mismatch while scheduling: Pearson VUE only shows CCAR-P (Professional) as pre-approved, while Bounteous's internal dashboard only shows a CCA-F (Foundations) nomination. Rahm confirmed his role actually needs Professional — pivoting target.
- Found a detailed third-party blueprint (claudecertificationguide.com) for CCAR-P: 63 standalone items, 7 domains (Integration 19%, Solution Design & Architecture 17%, Evaluation/Testing/Optimisation 16%, Governance/Safety/Risk 14%, Stakeholder Communication/Lifecycle 14%, Claude Models/Prompting/Context Engineering 13%, Developer Productivity/Operational Enablement 7%). Not yet confirmed against Anthropic's own materials.
- No prerequisite chain confirmed — Foundations not required to sit Professional.
- Real gap: Governance/Safety/Risk, Stakeholder Communication/Lifecycle, and Evaluation/Testing/Optimisation (35%+ of exam) are genuinely new territory, not covered by anything done so far.
- **Open action:** confirm with manager/L&D that Bounteous has actually authorized/nominated Professional, separate from the Pearson VUE pre-approval, before investing further prep time.

## Practice Test Generator (2026-09-20)
- Consolidated Practice Test 1 + 2 into one 40-question bank: `ccar-f-practice-test-generator.html`, committed to this repo.
- Test 1's distractors were rewritten to fix a real flaw you caught: correct answers were longer than distractors and predictable. Both sets now have length-balanced options with correct answers shuffled across A/B/C/D.
- Generator draws a random 20-question set each load, weighted to real exam domain proportions (27/20/20/18/15), so no two attempts are identical.
- Score history now persists via the browser's localStorage (per-browser, not synced across devices) — a "Past Attempts" table shows date/score/percentage, with a clear-history option.
- Also published as a live Cowork artifact (`ccar-f-practice-test-generator`) for quick access alongside the repo file.
- Note: standalone `ccar-f-practice-test-1.html` / `-2.html` artifacts are now superseded by the generator; the repo file is the source of truth going forward.
- Score result: "barely passed" Practice Test 2 (harder, balanced version) — good sign of real reasoning rather than pattern-matching, but flagged for continued review before exam day.

## 2026-09-23 (cont'd) — Practice bank expanded to 64 questions from real Module 1 content
- Pulled actual lesson content from the Drive folder (Google Docs, canvas-rendered so needed screenshots rather than text extraction): "2 - How Claude Behaves," "3 - Platform Map & Primitives," "5.1/5.2 - Platform Map & Primitives," "7 - Decomposition."
- Confirmed real official framework details: the four behavior properties are Non-determinism → why evaluation frameworks exist; Knowledge boundary → why retrieval/tools exist; Context as a finite resource → why context strategy is a design decision; Confidence is not validity → why human-in-the-loop placement matters. The three platform layers are Entry Points (Claude.ai, Claude Code, custom apps), Build-time interfaces (API, SDKs, MCP, Agent SDK), Delivery routes (Anthropic direct, AWS Bedrock, GCP Vertex AI, MS Foundry). The seven primitives and their one-word jobs: Tools=Act, MCP=Connect, Subagents=Isolate/parallelize, Hooks=Guarantee, Skills=Package a procedure, Agent Teams=Coordinate peers, Dynamic Workflows=Compose at runtime. Decomposition uses a three-owner framework: what Claude does / what existing systems do / what humans do.
- This confirms my earlier checkpoint-answer mapping (sent before Rahm submitted) was correct.
- Added 29 new questions to `ccar-p-practice-test-generator.html`: 9 grounded directly in the above Module 1 content (all filed under Solution Design & Architecture, since that's the module's real domain), plus 20 additional original questions spread across the other 6 domains to keep the bank proportional to exam weighting. Bank is now 64 questions total (was 35), test draw size increased from 20 to 30, verdict thresholds rescaled (21/27 instead of 14/18). Verified via script: 64 questions, 0 structural errors, correct-answer position distribution 17/17/16/14 across A/B/C/D (still balanced, no positional tell).
- Domain distribution in bank: Integration 11, Solution Design & Architecture 15 (heaviest, since it's the only domain with real official-course grounding so far), Evaluation 9, Governance 9, Stakeholder 8, Models/Prompting 7, Dev Productivity 5.
- Rahm's plan: take this test once he finishes Module 1. As more modules/lessons get pasted or pulled from Drive, keep growing whichever domain they map to.

## 2026-09-26 — Module 1 (Claude Platform & Solution Design) complete — knowledge locked in
Rahm finished all 34 screens of Module 1. Confirmed, official content now on record in this repo:

**Four behavior properties (from "How Claude Behaves"):**
- Non-determinism → why evaluation frameworks exist (same input can produce different outputs across runs; a single run can't certify behavior)
- Knowledge boundary → why retrieval/tools exist (model is reliable on common/recent/consistent topics, unreliable on rare/private/fast-changing ones)
- Context as a finite resource → why context strategy is a design decision (fixed token budget; what's kept/reordered/left out is a deliberate choice)
- Confidence is not validity → why human-in-the-loop placement matters (fluent tone ≠ correctness)
- Case study: a team shipped a financial reconciliation pipeline after a demo ran cleanly 5x in a row, treating non-determinism as if it were deterministic. Lesson: a demo is not evidence of determinism.

**Three platform layers (from "Platform Map & Primitives"):**
- Entry Points: what a person/system directly interacts with (Claude.ai, Claude Code, custom apps)
- Build-time interfaces: how an engineer programs against Claude (direct API, SDKs, MCP, Agent SDK)
- Delivery routes: where API traffic terminates (Anthropic direct, AWS Bedrock, GCP Vertex AI, MS Foundry)
- Case study: a retail banking proposal put Claude Code (an engineering entry point) in front of non-technical branch staff — collapsing entry point and build-time interface into one because "it's all Claude."

**Seven primitives and their one-word jobs:**
Tools=Act, MCP=Connect, Subagents=Isolate/parallelize, Hooks=Guarantee, Skills=Package a procedure, Agent Teams=Coordinate peers, Dynamic Workflows=Compose at runtime.

**Three-owner decomposition framework (from "Decomposition"):**
What Claude does (language understanding, summarization, planning, drafting, tool-mediated action) / what existing systems do (already-reliable services partner has paid for) / what humans do (judgment calls, exception paths, approvals). Common architect mistake: collapsing all three into "what Claude does."

**"Watch Out: Entry Points & Governance" case study (regional bank operations assistant, rejected proposal):**
Three failure mechanisms, all stemming from carrying forward defaults instead of deriving choices from the actual user/work: (1) entry point (Claude Code) chosen before the user was named — branch staff don't run terminals; (2) MCP carried forward from a prior project with no reuse justification — only one consuming client existed; (3) compliance (highest-consequence path) assigned to subagents (weakest deterministic guarantee) instead of deterministic server-side code. Correct answer: a custom web app calling the API directly, SSO-authenticated, compliance in server-side code, tool calls audited at the server boundary.

**Reusable prompt asset exercise (Support Reply Drafter, from "The brief"):** worked through the three design decisions — cache breakpoint placed after all stable content (persona/tone/policy/schema/few-shot examples) and before the per-request ticket+manual-excerpt pair; refund/timeline guardrail enforced structurally via a closed output-schema enum plus booleans the calling code validates and gates on, not just a stated instruction; packaged as a Skill (bundles instructions + validator script as one versioned unit) rather than a template, since policy updates need to ship as a single change that travels with the asset.

## 2026-09-26 — Practice generator merged into one file with a CCAR-F/CCAR-P switch
- Retired the two separate generator files in favor of one: `ccar-practice-test-generator.html`. It has a UI toggle at the top (CCAR-F / CCAR-P) that swaps question bank, domain weights, test size, verdict thresholds, accent color, and — importantly — localStorage history key, so score history stays separate per exam and persists across visits (last-selected exam is remembered too).
- Added 6 new grounded questions to each bank (12 total) from today's Watch Out case study and the reusable prompt asset exercise: CCAR-F picked these up across Agentic Architecture, Tool/MCP Integration, Claude Code Configuration, Context Management, and Prompt Engineering; CCAR-P picked them up across Solution Design, Governance (x2), Integration, Models/Prompting, and Developer Productivity — meaningfully improving real-content coverage in domains that were previously only original/unofficial questions (Governance, Integration, Dev Productivity now have official-source grounding too).
- New totals: CCAR-F bank 46 questions (was 40), CCAR-P bank 70 questions (was 64). Verified via script: domain weights sum to 1.0 for both, zero structural errors, zero duplicate questions across both banks. Also ran the actual page script against a stubbed DOM (no jsdom available in the sandbox, so hand-rolled minimal stubs) to confirm the switch/render/submit/history logic executes without throwing.
- Old artifacts (`ccar-f-practice-test-generator`, `ccar-p-practice-test-generator`) superseded — see resources.md for the new single artifact id.

## General Claude Professional Notes
_(anything useful for day-to-day Claude/Claude Code work at Bounteous, not exam-specific)_
