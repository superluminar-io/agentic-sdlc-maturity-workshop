# 01 · Technical Maturity Questionnaire

Pre-work and assessment questions for the Agentic SDLC Maturity Workshop. Grouped by the **seven platform primitives**, each split into a **BUILD track** (engineers shipping product *with* agents, the internal SDLC-productivity track) and a **RUN track** (agents shipped *to* customers, running in production).

> The single most important thing this questionnaire does is keep BUILD and RUN apart. The two tracks are co-equal subjects, not a sequence: a client may come to adopt agentic coding well across engineering with no agent product in sight (a build-primary engagement), or to harden something already shipped (a run-primary one), or both. A client strong on one track will instinctively answer the other track's questions optimistically. Do not let the two blur. The gap between them, in whichever direction, is the headline finding.

**How to use it.** Send the *light readiness screen* and the *pre-work* sections as intake ahead of the session; much can be answered async. Reserve the *in-session probes* for the room, where you can push past first answers and ask for evidence (see `03-facilitator-field-guide.md` (section 1) for what evidence counts).

---

## Light readiness screen (the go/no-go gate)

Answer these first. They are deliberately blunt yes/no questions, and they are the first thing we confirm together at the open of the session, before scoring anything. The point is honest: a clear no beats an expensive maybe. If too many are "no", the most useful thing we can do is tell you the engagement should not start yet, name what is missing, and say what would make it ready. That is a finding worth having early, not a failure. The screen applies whether your engagement is build-primary (adopting agentic coding across engineering) or run-primary (hardening a shipped feature); a few items read slightly differently for each, noted inline.

Mark each Yes or No. A "No" is a blocker flag. Count the flags at the end.

| # | Item | Yes / No | Blocker flag if "No" |
|---|---|---|---|
| 1 | There is a named **engineering sponsor** (VP/Dir Eng or CTO) who owns this and can say yes or no. | | ▢ |
| 2 | There is **budget** allocated, or under active consideration, for a first build this year. | | ▢ |
| 3 | There is a **team that could build and operate** what we recommend, in-house or via a partner (a stated partner-reliance plan counts). | | ▢ |
| 4 | There is a **baseline cloud / Bedrock presence** (or equivalent) to build on (AWS by default; tell us whatever you actually run). | | ▢ |
| 5 | We can get access to a **real codebase, feature, or repo** to work with (build-primary: a repo and CI to put agentic coding onto; run-primary: a live or pilot agentic feature). | | ▢ |
| 6 | There is a **security / data-protection contact** we can put the residency, governance, and isolation questions to. | | ▢ |
| 7 | There is **no hard regulatory prohibition** that blocks the work outright. | | ▢ |
| 8 | The **timeline** in your head is realistic (weeks-to-months for a first build, not "live next week"). | | ▢ |
| 9 | There is **appetite to act** on the finding: someone will fund and own the first build, not just receive the report. | | ▢ |
| 10 | The **engineers who would adopt the tooling** (build) or **own the feature** (run) are open to it rather than set against it. | | ▢ |

> **How we read it (confirmed live, finalised off-line).** We total the flags with you at the open. The verdict is then settled off-line alongside the rest of the diagnosis and lands as a one-box read in the report:
> - **Proceed (0–2 flags).** Nothing here blocks a full diagnostic. We name any flags as watch-items and carry on.
> - **Proceed with caution (3–4 flags).** Workable, but with real gaps. We name each blocker and what would close it, and we shape the engagement around them.
> - **Pause (5+ flags).** The honest call is that a full diagnostic should wait. We name the specific blockers and the smallest thing that would change the answer. A clear no now is cheaper than an expensive maybe later.
>
> Whatever the count, we name the specific blockers rather than leaving a bare number. The screen is a gate on the engagement, not a score to optimise.

---

## Who answers what

| Respondent | Best placed to answer |
| --- | --- |
| **Platform / infrastructure team lead** | LLM gateway, identity & access, observability, sandbox/isolation, vector store, the org's shared substrate (or absence of one). |
| **Engineering leads (stream-aligned)** | What their teams actually build and ship, the hand-built plumbing per feature, what's live in production. |
| **AI-guild representative** (if one exists) | Shared prompts/skills, patterns, evals, how practice spreads (or doesn't). |
| **Stream-aligned team reps** (1–2) | Ground truth on a real agentic feature: how it was built, how it's run, what got hard in the last 20%. |
| **Security / data-protection contact** | GDPR, EU AI Act exposure, data residency line, guardrails, governance. |

Mark each answer with **who** gave it. Conflicting answers between the platform lead ("we have a gateway") and a stream-aligned lead ("I've never used it") are themselves findings.

---

## Artifacts to bring / request

The room is for probing fact, not reconstructing it from memory. Request these ahead of the session and have them open when you probe, so each answer lands on something you can read rather than a recollection. If an artifact does not exist, that absence is itself a finding: note it. Map each to the primitive(s) it grounds.

| Artifact | Grounds (primitive) | What it lets you check |
| --- | --- | --- |
| The repo's `AGENTS.md` (or equivalent agent-config / system-prompt file) | All seven (entry point) | Whether agent behaviour is defined in one governed place or scattered per repo; who edits it. |
| The LLM-gateway config (routing rules, model allow-list, key management) | 1 · LLM gateway | Whether a gateway exists in fact, what it routes, who can add a model, whether prod goes through it. |
| A sample agent trajectory / trace (one real request, end to end) | 6 · Observability, 4 · Sandbox/isolation | Whether a full trajectory can even be produced; what steps and tool calls are visible. |
| The eval set(s) and a recent eval run (with results) | 7 · Evals | Whether evals exist, what they cover (output vs trajectory), when they last ran, what they caught. |
| IAM policies / agent identity config (roles, scopes, delegation) | 5 · Identity & access | Whether agents have own identity or a shared role; whether access is least-privilege and auditable. |
| The memory / state config for one live feature (store, partitioning) | 2 · Agentic memory, 3 · RAG/knowledge | Where session and long-term state live; whether tenant isolation is enforced or assumed. |
| The retrieval pipeline definition for one live feature | 3 · RAG/knowledge | How many pipelines exist; whether source-doc access control and partitioning are real. |
| The sandbox / execution-isolation config (where tool calls run) | 4 · Sandbox/isolation | Whether per-session isolation is enforced mechanically or by convention. |
| An incident timeline for a production agent issue (the last one) | 6 · Observability, 4, 5 | Time-to-diagnose, what was visible, what was not, who was paged. |
| The CI pipeline definition (with any eval / gate stages) | 7 · Evals, 1 · LLM gateway | Whether any eval is a hard gate or advisory; what runs before a change ships. |

> If the client can only bring two things, the choice follows the engagement. Run-primary: ask for one live feature's trajectory/trace and its eval run; those two carry the most across the run track, where over-rating is worst. Build-primary: ask for the repo's `AGENTS.md` (or its absence) and the CI pipeline definition; those two show whether agentic coding is governed and gated, or ad hoc, which is the build-track equivalent.

---

## Evidence to capture (convention)

Scoring and the two-track placement are built off-line from the notes, not from the live scores. So for every primitive, the notes must carry the evidence the score rests on, not just the score. For each primitive, capture at least:

- **The last incident and time-to-diagnose.** When did this primitive last break or surprise someone, and how long to find what happened? A number is the asset (e.g. "configurator gave wrong price, ~3 days to diagnose, no trajectory").
- **Who owns it.** Name the team or person accountable for this primitive, not the org-chart answer. "No one" is a valid and common finding.
- **Enforced mechanically or by convention.** Is the control real (a config, a gate, a policy that blocks) or a shared intention ("we're careful")? Record which, and the artifact that proves it.

Where a primitive's section below is thin on this, the evidence convention above still applies. Keep the **BUILD vs RUN** separation intact when you capture: an evidence line on the build track does not transfer to the run track. The most common error is recording build-track evidence against a run-track score.

---

## Section 0 · Context (pre-work)

- Company, sector, rough engineer headcount, primary cloud (confirm AWS), key regions.
- Compliance obligations that bind this data: what actually applies beyond GDPR (sector rules, public-sector or defence requirements, certification schemes such as BSI C5, contractual data-handling commitments, data classification, where customers and data subjects sit)? We derive any residency or sovereignty bar from these, rather than asking how sovereign they would like to be. The derived bar then decides the target: in-region AWS, the AWS European Sovereign Cloud (service-limited, not a drop-in), or an EU-native provider (Scaleway, STACKIT) where the bar is strictest and an AgentCore-style stack may not exist.
- GDPR / EU AI Act exposure: are any agentic features customer-facing, and do they process personal data?
- How many teams ship product? Roughly how many have started building agentic features? Separately: how widely do engineers already build *with* agents (coding assistants, agentic SDLC tooling) day to day?
- For the run track: name the one or two most mature agentic features in production (or the most ambitious pilot). These become the worked examples. If there is no customer-facing agent product at all, say so plainly; that is a clean build-primary engagement, not a gap to apologise for.
- For the build track: name where agentic coding is furthest along (a team, a repo, a golden path) and where it is ad hoc. This grounds the build-track worked example.
- What prompted this workshop? Two common shapes, equally valid: *"we want to adopt agentic coding well across engineering"* (build-primary) and *"we shipped a working-looking demo that got hard in the last 20%"* (run-primary). Capture which, or both, in their words.

---

## Primitive 1 · LLM gateway

*A single, governed entry point to models, rather than per-app keys and direct calls.*

**Pre-work**
- How do applications and developers call models today? Direct SDK/API calls, per-team keys, or a shared gateway?
- Is there any central place that handles model access, routing, rate limits, cost attribution, or logging?

**BUILD track probes** *(probe to the same depth as run; for a build-primary client this is the binding track)*
- Do engineers' coding agents / dev tooling go through a shared gateway, or each their own key?
- Is there model routing for dev use (e.g. cheaper model for simple tasks, a stronger model for hard ones)?
- Who can add a model? Is it governed or self-serve-chaos? Can you attribute dev-agent spend per team, or is it an unallocated lump?
- Is there a rate limit or budget guard on dev use, or can one runaway agent loop burn the month's tokens unnoticed?
- When a new model ships, how long until engineers can use it through the sanctioned path: a config change, or each team wiring its own key?

**RUN track probes**
- Do *production*, customer-facing agentic features call models through a governed gateway, or directly?
- Is there per-feature cost attribution and rate limiting in production?
- If a model needs swapping in production, is that a config change or a code change per feature?

---

## Primitive 2 · Agentic memory

*Shared, governed conversational / session memory rather than per-app, hand-rolled state.*

**Pre-work**
- How do agentic features remember context across turns or sessions today? Where does that state live?

**BUILD track probes** *(probe to the same depth as run)*
- Do dev-facing agents share any memory substrate, or is each tool's memory bespoke?
- Do coding agents carry project context across a session (the repo's conventions, an `AGENTS.md`, prior decisions), or start cold every time?
- Are memory patterns documented and reused across teams, or does each team rediscover them?
- When a coding agent's context is wrong or stale, can engineers see why, or is it a black box?

**RUN track probes**
- For a live customer-facing feature, where is session/long-term memory stored, and who built it?
- Is memory isolated per tenant / per user? How is that enforced?
- Is the same memory layer reused across features, or rebuilt each time?

---

## Primitive 3 · RAG / knowledge

*Retrieval over the org's knowledge as a shared, governed capability.*

**Pre-work**
- Do any features retrieve over internal/customer documents? What's the retrieval stack (vector store, embeddings, pipeline)?
- Are there multiple independent RAG implementations?

**BUILD track probes** *(probe to the same depth as run)*
- Do engineers have a shared, sanctioned way to give a dev agent the org's knowledge (internal docs, runbooks, architecture, past decisions), or does each pilot wire its own?
- Can a coding agent retrieve over the codebase and its history reliably, or is it limited to the open files?
- Any standardisation on Bedrock Knowledge Bases or equivalent for dev use?
- Is the knowledge a dev agent retrieves kept fresh, or does it drift from what the code actually does?

**RUN track probes**
- For production features, is retrieval governed (access control on source docs, freshness, eval of retrieval quality)?
- Is tenant data correctly partitioned in retrieval?
- How many separate RAG pipelines are in production? (Many = a consolidation finding.)

---

## Primitive 4 · Sandbox / per-session isolation

*Running other people's inputs through an agent with tools, safely, with per-session isolation. The line between a demo and a product.*

**Pre-work**
- When an agent executes tools / code in response to user input, where does that run? Is each session isolated?

**BUILD track probes**
- When engineers let agents run tools or code locally / in CI, is there any isolation, or full-trust execution?
- Can a dev agent execute code or commands pulled from a repo, an issue, or a web page without review? What stops a poisoned input running on a developer's machine or in CI?
- Is there an allow-list of tools and commands a dev agent may call, or can it reach the whole shell, filesystem, and network?

**RUN track probes** *(this is the production-readiness primitive; probe hardest here)*
- For a customer-facing agent with tools: is each session sandboxed and isolated from others?
- Could one tenant's session affect or observe another's? How is that prevented?
- Is tool execution constrained (allow-list, least privilege), or can the agent reach anything the service can?
- Has this been threat-modelled? By whom?

> Clients almost always over-rate this on run. "We're careful" is not isolation. Ask *how* it is enforced, mechanically.

---

## Primitive 5 · Identity & access

*Agents with their own identity and least-privilege access, not a shared service role.*

**Pre-work**
- How do agents authenticate to the systems and tools they use? Shared role, per-agent identity, or user-delegated?

**BUILD track probes**
- Do dev agents act as the developer, a shared service account, or something governed?
- When a dev agent commits, opens a PR, or calls an internal API, whose identity is on the action? Can you tell a human's action from an agent's in the audit trail?
- Can a dev agent reach production systems or secrets directly, or is it confined to dev and proposal-only?

**RUN track probes**
- Does each production agent have its own identity? Is access least-privilege and auditable?
- When an agent acts on behalf of a user, is that delegation modelled (e.g. AgentCore Identity), or does the agent hold broad credentials?
- Can you answer "which agent did this, on whose behalf?" from logs?

---

## Primitive 6 · Observability

*Tracing, trajectories, and metrics for agent behaviour, as a shared capability.*

**Pre-work**
- What visibility exists into what agents do? Logs, traces, trajectory capture, metrics, dashboards?

**BUILD track probes** *(probe to the same depth as run)*
- Can engineers see and debug a dev agent's trajectory (steps, tool calls, decisions), or only its final output?
- Is dev tracing shared/standard, or per-tool?
- Can a lead see how agentic coding is actually being used across teams (adoption, where it helps, where it stalls), or is that invisible?
- When a coding agent produces something wrong or wasteful, can the team reconstruct what it did, or is it lost?

**RUN track probes**
- For a production agent, can you trace a full request trajectory end to end?
- Are there metrics on quality, cost, latency, failure modes in production?
- When a customer reports a bad agent response, how long to find what happened? (A number is a finding.)
- Is production observability the same substrate as dev tracing, or weaker?

---

## Primitive 7 · Evals

*Trajectory and output evaluation, ideally as gates, not vibes.*

**Pre-work**
- How is agent quality measured before a change ships? Manual review, eval sets, automated gates, nothing?

**BUILD track probes** *(probe to the same depth as run; for a build-primary client this is where "agentic coding done well" is proven or not)*
- Are there code-quality / output evals for agent-written code, and do they wire into CI as a gate, or is review the only check?
- When a coding agent writes code, what stops a plausible-but-wrong change reaching `main`: a human reviewer, a test suite, an eval, or nothing beyond the author?
- Are eval sets shared across teams or per-team?
- Is there any measure of whether agentic coding is improving cycle time, quality, or throughput, or is the benefit asserted rather than measured?

**RUN track probes**
- Before a customer-facing agent change ships, is it evaluated? Manually or automatically?
- Are there **trajectory** evals (did the agent take a sensible path) as well as **output** evals?
- Is any eval a **hard release gate** in CI/CD, or is it advisory?
- Has a regressing agent change ever reached production? How was it caught?

---

## Section 8 · Team & organisation (Team Topologies)

*Feeds D3. See `03-facilitator-field-guide.md` (section 3).*

**Pre-work**
- Rough org chart: how many stream-aligned (product) teams? Is there a platform/infrastructure team? An enabling team or guild?

**In-session probes**
- **Stream-aligned:** how many teams ship product? How many have built agentic features? Does each build its own agent plumbing?
- **Platform:** is there a team that owns a *shared agent substrate* (not just cloud/infra)? Or is that a gap?
- **Enabling:** is there an AI guild / enabling function? What does it actually share, and onto *what*: a shared platform, or a vacuum?
- **The structural questions:** Is the guild "enabling onto a vacuum"? Are stream-aligned teams "rebuilding the plumbing per feature"? (These two phrases name the most common failure pattern. Listen for them.)

---

## Section 9 · The triggering story (in-session)

Ask the sponsor to walk through what prompted this. The story takes one of two shapes; both are valid, and a client may carry both. Capture verbatim where useful.

**If run-primary (a shipped feature that got hard):**
- Who built the first working version, and how fast? (Often: "a product owner, in days.")
- Where did it get hard? (Integration, edge cases, multi-tenant isolation, correctness, customer-facing guardrails: the last 20%.)
- What's it running on now? Shared substrate or hand-built plumbing?
- This story usually *is* the executive summary in miniature: builds fast, runs immaturely, gap is the finding.

**If build-primary (adopting agentic coding across engineering):**
- What does "adopting agentic coding well" mean to them, and why now? (Often: "everyone's using copilots ad hoc and we want leverage, consistency, and trust, not chaos.")
- Where does it work today, and where does it stall? (A team that flies vs a team that fights the tooling; a repo with an `AGENTS.md` vs forty repos without.)
- What's the fear? (Plausible-but-wrong code reaching `main`; a poisoned input running on a developer's machine; spend with no attribution; benefit asserted, never measured.)
- This story is the executive summary in miniature too: the build track is uneven and ungoverned, the gap is between teams that have figured it out and the org that has not made it a shared, gated capability.

Whichever shape, capture which track the live pain lives on. It points the first build at the weaker track.

---

## Worked example · Reimann Software GmbH (illustrative)

This is a model of good capture, not a summary: the build answer, the run answer, and the **evidence** the off-line score rests on, per primitive. Notice that almost every primitive splits build-strong from run-weak, and that the useful part of each entry is the evidence line, not the number. Reimann is B2B SaaS (CPQ for industrial manufacturers), ~280 engineers, Karlsruhe, on AWS in `eu-central-1`, EU residency a hard line. The placement that falls out of this is **Build L2, Run L1**.

**Context (Section 0).** ~30 teams ship product; ~5 have built an agentic feature, each on its own plumbing. Customer-facing features process personal data. The workshop was prompted by the configurator assistant (Section 9 below).

**Primitive 1 · LLM gateway, ~3.0.**
- *Build:* dev agents go through a central gateway with model routing; governed, the platform lead owns it.
- *Run:* production features call Bedrock directly, per feature. Swapping a model in production is a code change per feature, not a config change.
- *Evidence:* gateway config seen for dev; no production traffic flows through it. Enforced for build, absent for run.

**Primitive 2 · Agentic memory, ~2.0.**
- *Build and run:* per-app and ad hoc. The configurator assistant hand-rolled its own session store; no shared memory layer, no pattern reused across teams.
- *Evidence:* memory config exists for the configurator feature only; tenant isolation is assumed, not enforced in code. Owner: the feature team, not a platform.

**Primitive 3 · RAG / knowledge, ~3.0.**
- *Build:* a couple of Bedrock Knowledge Base pilots, not yet a sanctioned shared path.
- *Run:* each feature wires its own retrieval, with no governed source-doc access control or retrieval-quality eval. Several independent pipelines, which is itself a consolidation finding.
- *Evidence:* two pilot Knowledge Bases named; no standard anyone is held to.

**Primitive 4 · Sandbox / per-session isolation, ~1.5 (the standout gap).**
- *Run:* the configurator assistant runs tool calls with no per-session isolation. One tenant's session is not provably isolated from another's, and tool execution is broad rather than allow-listed. Not threat-modelled.
- *Evidence:* no isolation config exists, and that absence is the finding. This is the line between a demo and a product, and the first thing a platform foundation fixes.

**Primitive 5 · Identity & access, ~2.0.**
- *Run:* production agents share a service role rather than holding their own identity; acting-on-behalf-of-a-user delegation is not modelled. You cannot answer "which agent did this, on whose behalf?" from logs.
- *Evidence:* IAM shows a shared role, no per-agent identity. Ownership ambiguous.

**Primitive 6 · Observability, ~2.5.**
- *Build:* engineers can see and debug a dev agent's trajectory.
- *Run:* production tracing is weaker than dev; a full request trajectory cannot reliably be reconstructed.
- *Evidence (the incident):* the configurator returned a wrong price in production; ~3 days to diagnose because no trajectory was captured. The number is the finding.

**Primitive 7 · Evals, ~2.5.**
- *Build:* code-quality evals wire into CI.
- *Run:* manual eval before release, no trajectory evals, and no eval is a hard release gate. A regressing change has reached production and was caught by a customer, not by a gate.
- *Evidence:* CI config shows code evals but no agent release gate.

**Team & organisation (Section 8).** ~30 stream-aligned teams. A cloud and infrastructure platform team exists, but no one owns the agent substrate (Gap). An informal AI guild spreads prompts and tools but enables onto a vacuum (Partial). Plumbing is rebuilt per feature.

**Triggering story (Section 9).** A product owner stood up a working-looking configurator assistant with Claude in days. The last 20%, integration, multi-tenant isolation, correctness, and customer-facing guardrails, is where it got hard. It still runs on hand-built plumbing.

**Resulting placement:** Build L2, Run L1. The gap between the tracks is the finding, and it points at first build A (platform foundation) in `03-facilitator-field-guide.md` (section 7). Two consultants working from these captured evidence lines would land on the same placement, which is the point of capturing evidence and not just a score.

---

## Worked example · Aurum Pay GmbH (build-primary, illustrative)

The second worked example is a **build-primary client with no customer-facing agent product at all**, to show that this is a complete, first-class engagement, not a precursor to the run track. Aurum Pay is a B2B fintech (payments and reconciliation for mid-market finance teams), ~140 engineers, Berlin, on AWS in `eu-central-1`, PCI-DSS scope and GDPR a hard line. They came in to **adopt agentic coding well across engineering**: copilots are in use ad hoc, some teams fly with them and some fight them, and leadership wants leverage, consistency, and trust rather than chaos. There is no agent shipped to customers, and none planned this year. The placement that falls out of this is **Build L1, Run L0 (n/a)**.

Notice that the run track is genuinely *not applicable* here, not "weak". You do not invent run-track findings to fill the table; you record that there is no production agent, and the whole diagnosis lives on the build track. The build-track probes carry the engagement, which is exactly why they get equal depth in the questionnaire.

**Context (Section 0).** ~18 teams ship product; agentic coding is used by maybe half, unevenly, with no shared path. No customer-facing agentic feature exists. The workshop was prompted by the build-primary triggering story (Section 9 below), not by a shipped feature.

**Primitive 1 · LLM gateway, ~1.5.**
- *Build:* engineers call models from their IDE tooling on per-team keys; no shared dev-agent gateway, no routing, no per-team spend attribution. One team's runaway agent loop burned a noticeable token bill last month and no one noticed until billing did.
- *Run:* n/a, no production agent.
- *Evidence:* per-team keys seen in two teams' configs; the billing surprise is the number. No sanctioned path anyone is held to.

**Primitive 2 · Agentic memory, ~1.0.**
- *Build:* coding agents start cold; there is no `AGENTS.md`, no shared project-context convention, so each engineer re-explains the codebase to the agent every session. Patterns are not documented or reused.
- *Run:* n/a.
- *Evidence:* no `AGENTS.md` in the flagship repo, and that absence is the finding.

**Primitive 3 · RAG / knowledge, ~1.5.**
- *Build:* no sanctioned way to give a coding agent the org's knowledge (runbooks, architecture decisions, the reconciliation domain rules); agents work from open files only. One team wired an ad hoc retrieval over its own docs.
- *Run:* n/a.
- *Evidence:* one team's bespoke retrieval named; no shared standard.

**Primitive 4 · Sandbox / per-session isolation, ~2.0.**
- *Build:* coding agents run tools and commands on developer machines and in CI with broad trust. There is no allow-list of tools or commands; an agent could execute code pulled from an issue or a web page without review. Not threat-modelled for the dev path.
- *Run:* n/a.
- *Evidence:* CI config shows agents with full shell access; no allow-list. For a PCI-scope org this is a live finding even with no customer-facing agent.

**Primitive 5 · Identity & access, ~2.0.**
- *Build:* coding agents act as the developer's own credentials; when an agent opens a PR or calls an internal API, you cannot tell a human's action from an agent's in the audit trail. Agents are confined to dev, which is the one thing done right.
- *Run:* n/a.
- *Evidence:* commits and PRs carry the human's identity with no agent marker. Confinement to dev is real; attribution is not.

**Primitive 6 · Observability, ~1.5.**
- *Build:* individual engineers can see their own agent's trajectory in their IDE, but a lead has no view of how agentic coding is used across teams, where it helps, or where it stalls. Adoption and benefit are invisible.
- *Run:* n/a.
- *Evidence:* no shared dev-agent telemetry exists; benefit is asserted, not seen.

**Primitive 7 · Evals, ~1.5.**
- *Build:* there are no code-quality evals for agent-written code wired into CI; review is the only check, and a plausible-but-wrong change can reach `main` on a thin review. Whether agentic coding improves cycle time or quality is asserted, never measured.
- *Run:* n/a.
- *Evidence:* CI has tests but no agent-output eval gate; no adoption or cycle-time metric exists.

**Team & organisation (Section 8).** ~18 stream-aligned teams. A cloud and infrastructure platform team exists, but no one owns a shared dev-agent substrate (Gap). An informal community of practice swaps prompts in a Slack channel but enables onto a vacuum (Partial): there is no platform for it to enable onto. Each team that adopts agentic coding rebuilds its own setup.

**Triggering story (Section 9).** Half the teams use coding agents, unevenly. One team has an `AGENTS.md` and a tight loop and ships fast; another fights the tooling and has quietly abandoned it. Leadership's words: "we want this done well across engineering, with leverage and trust, not forty teams each inventing it and a plausible-wrong change slipping into `main`." The fear is ungoverned spend, unattributable agent actions in a PCI-scope codebase, and benefit no one can measure.

**Resulting placement:** Build L1, Run L0 (n/a). There is no track gap to read because there is no run track; the finding is that the build track is uneven and ungoverned, strong in one team and absent in the next, with no shared, gated capability. It points at first build **D (internal golden path for building with agents)** in `03-facilitator-field-guide.md` (section 7): a shared dev-agent gateway, an `AGENTS.md` reviewed in PRs, prompt/skill libraries, code-quality evals into CI, and the community of practice formalised as an enabling team. Two consultants working from these evidence lines would land on the same placement and the same first build.

---

## Worked example · Brightwell GmbH (both tracks, illustrative)

The third worked example is a **both-tracks client**: a real run track and a real build track, both emerging, neither yet a governed capability. It exists to show that a client can land on **both** tracks at once, so the kit does not read as "pick a lane". Brightwell is a B2B SaaS analytics company, ~200 engineers, Hamburg, on AWS in `eu-central-1`, EU residency a hard line. They ship a customer-facing agentic analytics assistant (the run track) *and* engineering is adopting agentic coding (the build track). Both are early, both have real gaps. Track-primary is **Both**. The placement that falls out of this is **Build L1, Run L1**.

The two tracks are scored on their own evidence and **never averaged**: a build read and a run read sit side by side, and the finding is that *both* are emerging, not that one number splits the difference. Here build and run land at the same rung, with neither ahead. When both are this early, the leverage is rarely a track-specific feature; it is the **substrate the two tracks share** (gateway, runtime, identity, observability, eval gate), which is why this client converges on a composite platform build rather than a build-track or run-track point fix.

**Context (Section 0).** ~20 teams ship product. One product team runs the customer-facing analytics assistant in production on its own hand-built plumbing; across engineering, agentic coding is in ad hoc use with no shared path. Both efforts started in the last year, both are someone's side initiative rather than a platform.

**Primitive 1 · LLM gateway, ~1.5 (build and run).** *Build:* engineers call models on per-team keys, no shared dev-agent gateway. *Run:* the assistant calls Bedrock directly, no routing, no shared gateway. *Evidence:* no central gateway on either path; both rebuild model access themselves.

**Primitive 2 · Agentic memory, ~1.5.** *Run:* the assistant hand-rolled its own session store, tenant isolation assumed not enforced. *Build:* no `AGENTS.md`, coding agents start cold. *Evidence:* one bespoke run-side store, no shared build-side context convention.

**Primitive 3 · RAG / knowledge, ~2.0.** *Run:* the assistant wires its own retrieval over customer data, no governed source-doc access control. *Build:* no sanctioned way to give a coding agent the org's knowledge. *Evidence:* one run-side pipeline, no build-side standard.

**Primitive 4 · Sandbox / per-session isolation, ~1.5 (the binding run gap).** *Run:* the assistant runs tool calls with no per-session isolation; one tenant's session is not provably isolated from another's. *Build:* coding agents run tools on dev machines with broad trust, no allow-list. *Evidence:* no isolation config on either path; for a customer-facing product the run side is the live finding.

**Primitive 5 · Identity & access, ~1.5.** *Run:* the assistant uses a shared service role, no per-agent identity, no acting-on-behalf-of-a-user delegation. *Build:* coding agents act as the developer's own credentials, no agent marker in the audit trail. *Evidence:* shared role on run, human-only attribution on build.

**Primitive 6 · Observability, ~1.5.** *Run:* production tracing is thin; a full assistant trajectory cannot reliably be reconstructed. *Build:* no shared view of how agentic coding is used across teams. *Evidence:* neither path has governed telemetry; benefit and behaviour are asserted, not seen.

**Primitive 7 · Evals, ~1.5.** *Run:* manual eval before release, no trajectory evals, no hard release gate. *Build:* no code-quality eval gate in CI for agent-written code. *Evidence:* no agent eval gate on either path.

**Team & organisation (Section 8).** ~20 stream-aligned teams. A cloud and infrastructure platform team exists, but no one owns the agent substrate for *either* track (Gap). One product team carries the assistant; an informal guild spreads coding-agent tips. Both enable onto a vacuum (Partial): there is no shared platform under either.

**Triggering story (Section 9).** Two stories at once. The analytics assistant shipped, then the last 20 percent (isolation, multi-tenant correctness, customer-facing guardrails) got hard and it still runs on hand-built plumbing. In parallel, leadership wants agentic coding done well across engineering rather than forty teams each inventing it. Leadership's read: "we are doing both, and we are doing both badly, and they seem to need the same foundations."

**Resulting placement:** Build L1, Run L1, never averaged. The finding is not "L1 overall"; it is that *both tracks are emerging and neither is yet a governed capability*, and that the leverage is the substrate they share. It points at a **composite first build A** (a shared platform foundation that underpins both the run-track product platform and the build-track dev golden path) in `03-facilitator-field-guide.md` (section 7). Two consultants working from these evidence lines would land on the same side-by-side placement and the same shared-substrate build.
