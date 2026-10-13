# CCAR-F & Claude Professional Resources

Curated links and materials. Official sources first, third-party second (flagged as unofficial).

## Official
- Anthropic Academy (course portal): https://anthropic-partners.skilljar.com
- Claude Certified Architect – Foundations page: https://anthropic.skilljar.com/claude-certified-architect-foundations-certification/444989
- Claude Docs: https://docs.claude.com
- Anthropic Support: https://support.claude.com

## Exam Logistics
- Format: 60 questions, 120 min, proctored, closed-book, scenario-based
- Passing score: 720/1000
- Delivered via: Pearson VUE
- Cost: $125 USD (verify current price at registration)
- Official code: CCAR-F (informal shorthand seen elsewhere: CCA-F)

## Bounteous Internal (employer resources — separate from Anthropic/Skilljar)
- Certifications portal: https://certifications.bounteous.tools — internal "Claude Certified Architect — Foundations" track with its own 11 prep modules, dashboard progress bar, and a self-reported exam-status field (L&D verifies outcome). Internally labeled "CCA-F" on this portal.
- Setup guide: https://certifications.bounteous.tools/setup — how to get hands-on API/Claude Code practice without a claude.ai login
- AI Gateway: https://gateway.bounteous.tools — routes Claude Code / Anthropic SDKs through Bounteous instead of claude.ai/api.anthropic.com directly (uses `ANTHROPIC_BASE_URL` + `ANTHROPIC_AUTH_TOKEN`, not a personal Anthropic key)
- Gateway key portal: https://gateway.bounteous.tools/portal — mints personal `sk-...` gateway key (SSO via Microsoft, shown once — treat like a password, never commit to git)
- Gateway model access: Sonnet (`claude-sonnet-4-6`) and Haiku (`claude-haiku-4-5-20251001`) only — no Opus; pin the model explicitly to avoid a 403
- Bounteous AI Gateway runbook — referenced from the internal portal's "Building with the Claude API" module; useful for hands-on practice tied to Domain 3

**Security note:** the gateway key is a credential. I won't ever request, view, or enter it on your behalf — grab and store it yourself per the portal's instructions.

## CCAR-P (Claude Certified Architect – Professional) — ACTIVE TARGET as of 2026-09-23
Pivoted from CCAR-F to CCAR-P — see study-progress.md for the full pivot notice and domain breakdown.

- Confirmed via Anthropic's own Academy site that "Claude Certified Architect – Professional" exists as a distinct listed certification: https://anthropic-partners.skilljar.com/claude-certified-architect-professional-certification (login-gated for this session; Rahm has access via Bounteous SSO and has shared full page content directly)
- Format: 63 standalone (non-scenario) questions across 7 domains, 120 min, 720/1000 to pass
- Focus: production ownership — building, shipping, defending architecture to stakeholders, governance/compliance/lifecycle — vs. CCAR-F's "can you design a working system"
- Target candidate: ~3+ years in architecture/platform engineering (vs. ~6 months hands-on Claude experience for CCAR-F) — recommended, not required; no mandatory prerequisites
- No prerequisite requirement between the two certs
- **Unverified (via Gemini AI-mode, not yet confirmed on the real registration page):** cost $175 USD (free for eligible Anthropic partners), 12-month validity renewable via reassessment

### ✅ Official CCAR-P Prep Course (confirmed 2026-09-23)
"Claude Certified Architect – Professional Prep Course" — free, registration button live on Rahm's logged-in Anthropic Academy view. 5 lessons, ~733 minutes total. Full lesson list and domain mapping now in study-progress.md.

Module 1 ("Claude Platform & Solution Design") structure, for reference: 34 screens across 12 sections (Module Introduction, How Claude Behaves, Platform Map & Primitives, Decomposition, Pattern Selection, Reference Architectures, RAG Pipeline Design, Model & Context Strategy, Prompting as Architecture, Entry Points & Governance, Assembly & Recap, Module Complete), with 11 checkpoints and hands-on exercises (RAG pipeline design, reusable prompt asset, cost & latency calculator).

**Recommended prerequisites per the course page:** Claude 101, Claude Code in Action, AI Fluency: Framework & Foundations, Building with the Claude API, Introduction to Model Context Protocol, AI Capabilities and Limitations. The last one ("AI Capabilities and Limitations") hasn't come up before in any tracking — need to check if Rahm is registered.

### CCAR-P Study Resources (third-party, supplementary)
- **tutorialsdojo.com/ccar-p-claude-certified-architect-professional-study-guide/** — detailed domain breakdown, key topics per domain, sample practice questions (multiple-choice + multiple-response with explanations). Cross-checked against claudecertificationguide.com — both independently agree on the same 7 domains and weights, which is a good (though still unofficial) confidence signal.
- claudecertificationguide.com/blog/claude-certified-architect-professional-exam-guide — same domain breakdown; notes their dedicated CCAR-P prep track is "coming soon" as of their last update (2026-07-24)
- Tutorials Dojo's CCAR-P Practice Exams (third-party, paid) — Rahm's offered to pay if the official course + our practice generator aren't enough
- **Superseded (2026-09-26):** the separate `ccar-f-practice-test-generator.html` and `ccar-p-practice-test-generator.html` files are replaced by one merged generator: `ccar-practice-test-generator.html` — has a CCAR-F/CCAR-P toggle switch in the UI (swaps question bank, domain weights, test size, verdict thresholds, accent color, and localStorage history key, so score history stays separate per exam). CCAR-F bank: 46 questions (20-question draw). CCAR-P bank: 70 questions (30-question draw). 16 questions total (across both exams) are grounded directly in real Module 1 lesson content pulled from Rahm's Drive folder — behavior properties, platform layers, primitives, decomposition framework, the Entry Points & Governance case study, and the reusable prompt asset exercise — not just third-party sources. Published as Cowork artifact `ccar-practice-test-generator`.

## Third-Party Prep (unofficial — verify against official docs before trusting)
- Udemy CCAR-F prep course: https://www.udemy.com/share/10fcRi3@IgSCd_SEJVD60kDr9y4JFcuvoPh9WgRyd3-R6rUZnqCm_DJu5o1TOa46_cQGZNqX/
- **Udemy: "Claude Certified Architect Foundations (CCAR-F) Exam 2026"** (https://www.udemy.com/course/claude-certified-architect-foundations-ccaf-exams/) — confirmed via search to explicitly cover Domain 5 (Context Management & Reliability): CALM framework, prompt caching/cache_control breakpoints, conversation compaction, token budget management. **This is the recommended next course** — closes the one real content gap in the plan.
- Other Udemy options seen: "[CCA-F] Claude Certified Architect Foundations Exams v2 2026", "Claude Certified Architect (CCA-F, CCAR-F) - 2026 Exam Prep" — similar coverage, not independently vetted
- LinkedIn Learning (per search, not independently verified in-app): "Model Context Protocol (MCP): Hands-On with Agentic AI", "Everyday Productivity with Claude Cowork", "Claude Code in Action by Anthropic", "Claude Code 4: Agentic Coding for Professional Developers" — useful reinforcement, not gap-filling (Domain 5 wasn't found here)
- claudecertifiedarchitects.com — practice tests/blog
- claudearchitectcertification.com — domain breakdown, free prep

## Claude Professional Work (general reference)
- Claude API reference: https://docs.claude.com
- Claude Code docs: (add link once located in Academy/docs)
- Model Context Protocol spec: https://modelcontextprotocol.io
- Claude Agent SDK: (add link once located)

## To Add
- ~~Context Management & Reliability reference material~~ — found via Udemy (see Third-Party Prep above, 2026-09-23). Still worth checking Anthropic Academy periodically in case an official module appears.
