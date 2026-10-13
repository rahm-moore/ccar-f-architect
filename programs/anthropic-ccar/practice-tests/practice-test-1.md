# CCAR-F Practice Test 1

Original, scenario-based practice questions modeled on the five published exam domains and their weights. Not reproductions of any real Anthropic exam content — use for concept-checking, not as a guarantee of real exam phrasing.

20 questions, weighted roughly to domain proportions:
- Agentic Architecture & Orchestration (27%) — 5 questions
- Claude Code Configuration & Workflows (20%) — 4 questions
- Prompt Engineering & Structured Output (20%) — 4 questions
- Tool Design & MCP Integration (18%) — 4 questions
- Context Management & Reliability (15%) — 3 questions

Answer key with explanations is at the bottom — don't peek until you've committed to an answer.

---

## Domain 1: Agentic Architecture & Orchestration

**1.** You're designing a Claude Code workflow where a main agent needs to research a topic across 15 files, summarize findings, and only then make an edit. The research step would otherwise consume most of the context window. What's the best architectural choice?
A) Have the main agent read all 15 files directly into its own context
B) Delegate the research to a subagent that returns only a condensed summary to the main agent's context
C) Split the task into 15 separate top-level conversations
D) Use a larger context window model for the main agent only

**2.** A hub-and-spoke multi-agent design assigns one orchestrator agent to delegate to several specialized subagents. What is the primary reliability risk this pattern introduces?
A) Subagents cannot access tools
B) The orchestrator becomes a single point of failure and context bottleneck if it accumulates too much state
C) Subagents automatically share full context with each other
D) Hub-and-spoke designs cannot be used with Claude Code

**3.** When should you prefer an agentic loop (plan → act → observe → repeat) over a single-shot prompt?
A) When the task is fully specified upfront and requires no intermediate verification
B) When the task requires adapting based on the results of intermediate tool calls
C) Only when using the Claude API directly, never in Claude Code
D) Agentic loops should be avoided for cost reasons in all cases

**4.** A subagent you designed keeps re-reading the same file on every turn, wasting tokens. What's the most likely design fix?
A) Increase the subagent's max_tokens
B) Have the subagent cache or summarize the file's relevant contents into its own working memory instead of re-fetching
C) Switch the subagent to a smaller model
D) Remove the subagent and merge its work into the main agent

**5.** Which of the following best describes "task decomposition" in agentic architecture?
A) Reducing a model's context window size
B) Breaking a complex goal into smaller, independently executable subtasks assigned to agents or tool calls
C) Compressing conversation history
D) Splitting a single API request into multiple HTTP packets

---

## Domain 2: Claude Code Configuration & Workflows

**6.** What is the primary purpose of a `CLAUDE.md` file in a project repository?
A) It stores API keys for the project
B) It provides persistent project-level context and conventions that Claude Code reads at the start of a session
C) It replaces the need for a README
D) It is only used for CI/CD pipeline configuration, not for Claude itself

**7.** A team wants a repeatable, one-word way to trigger a specific multi-step review process in Claude Code across all their repos. What should they build?
A) A custom slash command
B) A new CLAUDE.md file per repo with no shared logic
C) A subagent with no defined trigger
D) A GitHub Action with no Claude Code involvement

**8.** In a CI/CD pipeline, what's a key reliability consideration when invoking Claude Code non-interactively (headless mode)?
A) Headless mode requires no error handling since it never fails
B) Ensuring the invocation has bounded scope, clear success/failure signals, and doesn't require interactive confirmation
C) Headless mode automatically retries indefinitely by default
D) CI/CD pipelines cannot invoke Claude Code at all

**9.** Your organization wants engineers to inherit consistent coding conventions across every project without copy-pasting the same instructions repeatedly. What's the best mechanism?
A) A hierarchy of CLAUDE.md files (e.g., a root/org-level file plus per-project overrides)
B) Emailing conventions to each engineer individually
C) Hardcoding conventions into each prompt manually every session
D) There is no way to share context across projects

---

## Domain 3: Prompt Engineering & Structured Output

**10.** You need Claude's response to reliably parse as valid JSON matching a specific schema for downstream automation. What's the most robust approach?
A) Ask nicely in the prompt and hope for the best
B) Use tool use / structured output enforcement (e.g., a defined schema via tool definitions) rather than relying purely on prompt instructions
C) Always use a larger model instead
D) Parse the response as freeform text and regex out the data

**11.** A structured-output call occasionally returns a response that fails schema validation. What's the best resilient pattern?
A) Immediately give up and surface the raw error to the end user
B) Implement a validation-and-retry loop that feeds the validation error back to Claude for correction
C) Silently discard invalid responses with no logging
D) Switch to an unstructured prompt permanently

**12.** Few-shot prompting is most useful for which of the following?
A) Reducing the model's context window usage
B) Demonstrating a desired output format or reasoning pattern via examples so the model generalizes correctly
C) Bypassing the need for a system prompt entirely
D) Guaranteeing zero hallucination

**13.** What's the key difference between "programmatic enforcement" and "prompt-based guidance" for structured output?
A) They are the same thing
B) Programmatic enforcement (e.g., tool schemas, validation code) guarantees structural compliance; prompt-based guidance only increases the likelihood of compliance
C) Prompt-based guidance is always more reliable
D) Programmatic enforcement cannot be combined with prompts

---

## Domain 4: Tool Design & MCP Integration

**14.** When designing a tool description for Claude to call correctly and consistently, what matters most?
A) Keeping the description as short as possible regardless of clarity
B) A clear, unambiguous description of what the tool does, its parameters, and when to use it
C) Omitting parameter descriptions to save tokens
D) Tool descriptions have no effect on call accuracy

**15.** What is the core purpose of the Model Context Protocol (MCP)?
A) To replace the Claude API entirely
B) To provide a standardized way for AI applications to connect to external tools, data sources, and systems
C) To compress conversation context automatically
D) To manage billing across multiple Anthropic accounts

**16.** Your MCP server needs to support both a locally-run client (stdio) and a remotely hosted client (HTTP streaming). What's the key architectural consideration?
A) The server must pick one transport permanently and can never support both
B) The server's transport layer should be able to handle both stdio and HTTP streaming connections without changing the underlying tool logic
C) Local and remote clients require entirely separate MCP servers with different tools
D) HTTP streaming is not a supported MCP transport

**17.** A tool call fails intermittently because the tool's parameters are ambiguous about units (e.g., "duration" without specifying seconds vs. minutes). What's the best fix?
A) Leave it — Claude will infer correctly most of the time
B) Update the tool schema/description to explicitly specify the expected unit
C) Remove the parameter entirely
D) Switch to a different model

---

## Domain 5: Context Management & Reliability

**18.** A long-running agentic session is approaching its context window limit. What's a reliable strategy to continue the task without losing critical information?
A) Let the session fail once the limit is hit
B) Summarize/compact older conversation turns while preserving key decisions and state, then continue with the compacted context
C) Always restart from scratch with no summary
D) Increase max_tokens to unlimited

**19.** What is the purpose of `cache_control` breakpoints in the Claude API?
A) To permanently delete old messages
B) To mark points in a prompt where content can be cached, reducing cost and latency on repeated/similar requests
C) To rate-limit API calls
D) To enforce structured output

**20.** In multi-turn conversation design, why is token budget management important?
A) It isn't — context windows are effectively unlimited
B) Without managing token budget, long conversations can silently truncate important early context or hit cost/latency limits unexpectedly
C) Token budget only matters for image inputs
D) It only affects billing, never behavior

---

## Answer Key & Explanations

**1. B** — Delegating research to a subagent keeps the bulk of file-reading out of the main agent's context; only the summary returns. This is the core value of subagent architecture for context management.

**2. B** — Centralizing coordination in one orchestrator creates a bottleneck: if it accumulates too much state or fails, the whole system is affected.

**3. B** — Agentic loops earn their cost when the next step depends on unpredictable results from a prior action (tool output, search result, etc.).

**4. B** — Re-fetching the same data repeatedly is a context/token waste; the fix is caching or summarizing into working memory rather than re-reading.

**5. B** — Task decomposition is about breaking work into smaller, assignable units — not about context size or network-level concerns.

**6. B** — CLAUDE.md is a persistent context file Claude Code reads for project conventions, not a secrets store or CI-only config.

**7. A** — Custom slash commands are built exactly for repeatable, named, multi-step triggers.

**8. B** — Headless/non-interactive invocations need bounded scope and clear success/failure signals since there's no human in the loop to intervene.

**9. A** — A CLAUDE.md hierarchy (org-level + project-level) is the mechanism for consistent, inherited context without duplication.

**10. B** — Tool use / schema-based structured output enforces structure far more reliably than instructions alone.

**11. B** — A validation-and-retry loop that feeds the specific validation error back to the model is the standard resilient pattern.

**12. B** — Few-shot examples demonstrate the desired pattern so the model generalizes the format/reasoning style.

**13. B** — Programmatic enforcement guarantees structural compliance (it's checked/validated); prompt-based guidance only nudges probability.

**14. B** — Clarity on function, parameters, and usage conditions directly drives correct and consistent tool-call behavior.

**15. B** — MCP standardizes how AI applications connect to external tools/data/systems — it's an integration protocol, not a billing or compression mechanism.

**16. B** — Good MCP server design separates transport (stdio vs. HTTP streaming) from tool logic, so the same tools work regardless of how the client connects. (Directly relevant to the update you're doing on your own MCP server right now.)

**17. B** — Ambiguity in tool parameter descriptions (like missing units) is a tool-design defect; fix it at the schema/description level.

**18. B** — Compaction/summarization that preserves key state is the standard approach to continuing past context limits.

**19. B** — `cache_control` breakpoints mark cacheable prompt segments to cut cost and latency on repeated content.

**20. B** — Poor token budget management risks silent truncation of important context or unexpected cost/latency issues, especially in long multi-turn sessions.

---

## Score Interpretation
- 18-20 correct: strong readiness on this material
- 14-17 correct: solid, but review missed domains before exam day
- Below 14: revisit the corresponding domain notes/courses before moving to the next practice test

## Next Steps
Let me know your score and which questions you missed — I'll target domain review and build Practice Test 2 to weight toward your weaker areas.
