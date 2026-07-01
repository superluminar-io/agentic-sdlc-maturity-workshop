# 02 · Facilitator Runbook

How to run the Agentic SDLC Maturity Workshop end to end. The structure follows the three steps; the output is the 8-deliverable report. **No slideware.** The on-screen deck (`facilitator-deck-outline.md`) is thin and exists only to anchor the room.

> This is a diagnostic for engineering leaders, not training. We read, we design, we scope. The client leaves with a decision, not another workshop.

---

## Pre-workshop checklist

- [ ] Confirm sponsor and attendees (see roster below). The decision-maker must be in the room for Step 3.
- [ ] Send `01-technical-maturity-questionnaire.md` as intake at least one week ahead.
- [ ] **Light readiness screen** (intake, top of `01`) reviewed; any blocker flags noted to confirm or clear at the open. If it reads Pause, raise that with the sponsor *before* the session rather than running a full diagnostic on an engagement that should not start yet.
- [ ] Establish whether this is a **build-primary** engagement (adopting agentic coding across engineering, no agent product) or **run-primary** (hardening a shipped feature), or both. It sets which track the worked examples and the live pain live on.
- [ ] Collect async answers; identify the worked examples: the one or two production agentic features (run-primary), or the teams/repos where agentic coding is furthest along and most ad hoc (build-primary).
- [ ] Confirm the **compliance obligations** early (what binds the data: regulation, contract, certification, data class), and derive the residency / sovereignty bar from them. It shapes the target.
- [ ] Pre-fill draft scores from intake (pencil, not pen; they will move in the room).
- [ ] Open the client's row in the **Agentic SDLC Maturity Engagements** Notion workbook: that is where capture goes (scorecard, ladder, topology grid, cost), so the field guide's Team Topologies and cost sections (`03-facilitator-field-guide.md`, sections 3 and 6) are reference only, not open to write into.
- [ ] Keep the field guide (`03-facilitator-field-guide.md`) at hand to score *against*, not to write into: it carries the scoring rubric (section 1), the ladder rubric (section 2), the managed vs OSS guidance (section 4), and the architecture patterns (section 5) in workshop order. The first-build selection (section 7 of the field guide) is off-line work after the session, so it is not open in the room.
- [ ] Confirm format (on-site / remote). The shared surface for live capture is the Notion workbook row, with a whiteboard for sketching as needed.
- [ ] If the AI Readiness Workshop has run for this client, read its findings so the first build aligns.

---

## The room

| Role | Why they're here |
| --- | --- |
| Sponsor (VP/Dir Eng or CTO) | Owns the decision in Step 3. |
| Platform / infra lead | Ground truth on the shared substrate (or its absence). |
| 1–2 stream-aligned eng leads | What teams actually build and ship. |
| AI-guild rep (if any) | How practice spreads. |
| Security / data-protection contact | EU residency, EU AI Act, guardrails, governance. |
| Two superluminar consultants | Run it together. Both engineers; no fixed split, they share leading the room, capturing, and the architecture and synthesis work. |

---

## Engagement shape

The customer-facing session is one part of the engagement, not the whole of it. Most of the design, and all of the report writing, happen off-line. Treat the session as the place you gather inputs and align on the finding with the client; the decisions, the finalised placement, the selected first build, the design, are made afterwards, off-line. Indicative shape, re-size per client:

| Phase | Who | Indicative effort |
| --- | --- | --- |
| 1 · Intake & pre-analysis | superluminar | Review the questionnaire, pre-score, pick the features to probe, draft the residency line. ~0.5 to 1 day before the session. |
| 2 · Working session(s) with the client | the two consultants + the room | The agenda below: a long half-day to a day live. Split across two sittings for a larger org (assessment first, then target and roadmap). |
| 3 · Off-line analysis, design & synthesis | superluminar | Finalise the two-track placement with evidence, design the AWS-native target and draw it, settle managed vs open source, select and scope the first build, size effort and estimate run cost. Several days. |
| 4 · Report write-up | superluminar | Assemble the 8 deliverables into the report. ~1 to 2 days. |
| 5 · Readout & handover | a consultant + sponsor | Walk the client through the report and the decision. ~1 to 2 hours. |

This is the *diagnostic* engagement's own effort. It is separate from the recommended first build's effort sized in the field guide's cost basis (`03-facilitator-field-guide.md`, section 6). Do not let the half-day session below stand in for the engagement: the real work is phases 3 and 4.

---

## The working session (agenda)

These blocks are the **customer-facing session**, not the whole engagement. Because the outputs are produced off-line, the session has one job: **gather depth.** This is the only time you have the people who hold the ground truth in one room. Spend it extracting evidence, examples, and constraints, not drafting deliverables. Every score, placement, and architecture call is provisional in the room and finalised off-line from what you gather here. The time you are not spending on slideware goes into going deeper.

**Depth principles for the room:**

- **Chase the evidence behind every answer.** A score is shorthand; the evidence sentence is the asset. Ask *how* it is enforced, *when* it last broke, *who* owns it.
- **Specifics over summaries.** Get the concrete example, the incident, the number, the artifact. "Show me" beats "tell me".
- **Capture verbatim.** The triggering story and the war stories are the executive summary in miniature. Record the words.
- **Gather the real stack in detail.** For the target architecture, capture their actual services, the plumbing each team has hand-rolled, the residency and identity constraints. The off-line design is only as good as this.
- **Capture disagreement.** "We have a gateway" from platform versus "I've never used it" from a team is itself a finding.
- **There is no box to fill live.** Do not close a thread because a deliverable looks complete. Keep pulling until the evidence is rich.

The intake questionnaire (`01`) captures the factual baseline ahead of time precisely so the room is free for this depth, not for basics.

| Block | Step | Time | Produces |
| --- | --- | --- | --- |
| 0. Frame, readiness screen & triggering story | · | 20 min | Screen verdict + exec-summary spine |
| 1. Score the primitives | 1 | 60 min | D1 |
| 2. Place on the ladder | 1 | 30 min | D2 |
| 3. Team & process read | 1 | 30 min | D3 |
| break | | 15 min | |
| 4. Target architecture (capture + sketch) | 2 | 50 min | D4 inputs |
| 5. Operating model | 2 | 30 min | D5 inputs |
| 6. Managed vs open source | 2 | 25 min | D6 inputs |
| 7. Phased roadmap | 3 | 35 min | D7 inputs |
| 8. Direction & appetite (build selected off-line) | 3 | 40 min | D8 inputs |
| 9. Close & next step | · | 15 min | The finding; report follows |

The session runs a long half-day to a day. The times are a guide, not a budget: let the evidence set the pace, and stay in a block while it is producing rich material. For a larger org, split it: assessment (Blocks 0 to 3) in one sitting, target and roadmap (Blocks 4 to 9) in another, with off-line analysis in between. Splitting is also how you buy more depth, more room per block, without a single exhausting marathon. Never short-change the triggering story or the live-pain read; those are the inputs the off-line build selection rests on.

---

## Block 0 · Frame, readiness screen & triggering story (20 min)

Set the frame: two co-equal tracks, never averaged; the gap (in whichever direction) is the finding; we end the session on that finding and a clear next step, with the recommended first build to follow in the written report. State plainly which kind of engagement this is, build-primary (adopting agentic coding across engineering) or run-primary (hardening a shipped feature), so the room knows which track carries the work. Both are complete engagements; a build-primary client with no agent product is not a precursor to anything.

**Confirm the readiness screen first.** Before scoring anything, total the light readiness screen (top of `01`) with the room and confirm or clear any blocker flags. If it reads Pause, name the blockers and the smallest thing that would change the answer, and decide with the sponsor whether to continue or stop. The verdict (Proceed / Proceed with caution / Pause) is finalised off-line and leads the report when it is Caution or Pause.

Then have the sponsor walk through what prompted this (questionnaire §9). Capture verbatim. This story usually *is* the executive summary in miniature, in either shape:
- **Run-primary:** a feature built fast that got hard in the last 20%. Builds fast, runs immaturely, the gap is the finding.
- **Build-primary:** agentic coding used unevenly across teams, leadership wanting leverage and trust over chaos. The build track is uneven and ungoverned, the gap is between the team that has figured it out and the org that has not made it shared and gated.

**Capture:** the readiness-screen flags and verdict; the triggering narrative; for run-primary, who built the first version and how fast and where it got hard; for build-primary, where agentic coding works and where it stalls and what leadership fears. Note which track the live pain lives on.

---

## Block 1 · Score the primitives (60 min) → D1

Work through all seven primitives with the field guide's scoring rubric (`03-facilitator-field-guide.md`, section 1) open. For **each primitive, score BUILD and RUN separately, 0–5.** Give the two tracks equal depth: a build-primary client's whole diagnosis lives on the build track, so do not treat its probes as the lighter half. Ask for evidence, not self-assessment. Push past "we're careful" and ask *how* it's enforced.

- LLM gateway · Agentic memory · RAG/knowledge · Sandbox/isolation · Identity & access · Observability · Evals.
- Watch for the split, in whichever direction. For a run-primary client, build scores cluster high and run low; for a build-primary client, one or two teams cluster high and the rest are absent, and the run track may be genuinely n/a (record that, do not invent run findings). The pattern is the point either way.
- Sandbox/isolation on the run track is the primitive clients most over-rate; probe hardest there when there is a production agent. On the build track, the equivalent over-rating is full-trust agent execution on dev machines and in CI ("we're careful"); probe that just as hard, especially in a regulated codebase.

**Capture:** a 0–5 score per primitive (the report's scorecard often shows the binding/lower side, with build/run noted in prose). Note one evidence sentence per score.

---

## Block 2 · Place on the ladder (30 min) → D2

With the field guide's ladder rubric (`03-facilitator-field-guide.md`, section 2): place the client on **L0–L3 for BUILD and again for RUN.** Read the level descriptors aloud and let them self-locate, then challenge. **Never average the two.** Name the gap explicitly; it is the headline. Where there is no production agent, place Run at **L0 (n/a)** and say so plainly: the diagnosis lives on the build track, and that is a complete finding, not a missing half.

**Capture:** Build Lx, Run Ly (or n/a), plus one sentence each on why, plus the gap statement (or, for a build-primary client, the statement of how uneven and ungoverned the build track is).

---

## Block 3 · Team & process read (30 min) → D3

With the field guide's Team Topologies read (`03-facilitator-field-guide.md`, section 3): map teams to platform / enabling / stream-aligned, each Have / Partial / Gap. Surface the two patterns: **"enabling onto a vacuum"** and **"plumbing rebuilt per feature."** The run-track gap is usually also an org gap.

**Capture:** status + finding per team type.

---

## Block 4 · Target architecture (50 min) → D4

With the field guide's architecture patterns (`03-facilitator-field-guide.md`, section 5): design the AWS-native target on Bedrock + AgentCore. Walk the **run path** (customer → Gateway → Runtime with per-session sandbox → Memory + Knowledge Bases → Guardrails → Claude on Bedrock with routing → Observability) and the **build/ship path** (CI/CD via CodePipeline with a trajectory + output eval gate on Bedrock Evaluations; AgentCore Identity; IAM least-privilege). Keep everything in `eu-central-1`. Use the smaller variant if the client is early on the ladder.

In the room you confirm the shape and the constraints, not the finished diagram. The detailed target architecture and the draw.io source are built off-line (see *Off-line: analysis, design & synthesis*).

**Capture:** which components are in scope, the residency line, anything client-specific that shapes the off-line design.

---

## Block 5 · Operating model (30 min) → D5

With the target operating model in the field guide's Team Topologies read (`03-facilitator-field-guide.md`, section 3): the three team types and who owns what. Platform team owns the substrate; enabling team raises practice; stream-aligned teams ship on golden paths. Be explicit about the org change required (and that the client staffs it; we design it).

**Capture:** owns / what changes, per team type.

---

## Block 6 · Managed vs open source (25 min) → D6

With the field guide's managed vs open source guidance (`03-facilitator-field-guide.md`, section 4): decide per capability. Managed by default; open source only where a concrete requirement pays for the operational load. Point to the living map at superluminar.io/agentic-stack/.

**Capture:** recommended choice + one-line why per capability.

---

## Block 7 · Phased roadmap (35 min) → D7

Walk the evidence-gated climb with the room and gather what the gates should be, but the roadmap is finalised off-line. **Phase 0 is the first build, which is selected off-line for this client** (see the off-line section and the field guide's first-build selection guide, `03-facilitator-field-guide.md`, section 7), not picked here and not automatically the platform foundation. Each later phase has a go/no-go **gate** stated as observable evidence, not ambition. Two example phasings follow, one run-primary and one build-primary, to show that the shape holds on either track. A client can also land on **both** tracks at once (the Brightwell example, Build L1 / Run L1, never averaged): the two reads stay side by side, and Phase 0 is a composite first build A whose Phase 0 gate is observed on *both* tracks (the run feature on the shared substrate, one pilot dev team on the same gateway and gate). Use whichever shape fits; off-line you re-write Phase 0 to the selected build and re-order the later phases so each gate follows from where *this* client started.

**Run-primary phasing (Reimann example, first build A, platform foundation):**

| Phase | What happens | Gate |
| --- | --- | --- |
| 0 · *Selected first build* | Build the AgentCore foundation; migrate the flagship feature onto it. | The feature runs in prod on the shared substrate, per-session isolation + eval gates passing. |
| 1 · Platform team + golden paths | Stand up platform team, formalise enabling team, migrate 2–3 features. | A stream-aligned team ships a feature without building plumbing. |
| 2 · Gates & governance | Evals as release gates across the board, agent identity & governance, A2A where needed. | A release gate blocks a regressing change in CI: proven, not assumed. |
| 3 · Agentic factory | Self-serve platform; L3 on both tracks. | Idea → prod on golden paths with no platform-team involvement. |

**Build-primary phasing (Aurum Pay example, first build D, internal golden path):**

| Phase | What happens | Gate |
| --- | --- | --- |
| 0 · *Selected first build* | Stand up the dev-agent gateway, the reviewed `AGENTS.md`, the prompt/skill library, and code-quality evals into CI on one pilot team. | A pilot team uses the shared golden path and an agent-output eval gate blocks a plausible-wrong change before `main`. |
| 1 · Enabling team + spread | Formalise the community of practice as an enabling team; roll the golden path to 2–3 more teams. | A second team adopts the golden path without rebuilding its own setup. |
| 2 · Governance & attribution | Agent identity and attribution in the dev path, tool allow-lists, spend attribution per team. | An agent action is attributable in the audit trail and a runaway loop is caught by a budget guard, not by billing. |
| 3 · Org-wide capability | Agentic coding is the default, measured path; the org can also take on a run-track build if one arrives. | Cycle-time / adoption KPIs clear their bar across teams; a new team is productive on the golden path with no platform-team involvement. |

**Capture:** the phases, gates, indicative timings (illustrative). For a build-primary client with no run track, the later phases stay entirely on the build track; do not bolt on a run-track phase that the client has no use case for.

---

## Block 8 · Direction & appetite (40 min) → D8 inputs

**You do not pick the build in the room.** Selecting and scoping the first build is the central analytical conclusion of the whole engagement, and it is made off-line against the *finalised* diagnosis (the settled scores, placement, and team read), using the field guide's first-build selection guide (`03-facilitator-field-guide.md`, section 7). Deciding it live, in forty minutes, before the scores are even off the provisional pencil, is exactly the superficial-diagnosis trap: it produces a recommendation that the evidence has not yet earned. Run the four reads off-line, not here.

What this block is for is gathering the last inputs that selection needs, and reading the room:

- **The live pain, in their words.** Read four of the selection guide is the client's live pain, and this is where you get it. What does the gap cost them right now, this month? For a run-primary client, what does the immature production agent cost; for a build-primary client, what does the uneven, ungoverned adoption cost (rework, abandoned tooling, a plausible-wrong change in `main`, unattributed spend)? Capture verbatim.
- **Appetite and what they would actually fund.** Who owns the budget for a first build, and what order of effort is realistic this quarter? A build no one will fund is not a recommendation.
- **The constraints that bound the build.** A hard deadline, a system that must not be touched, a team that would or would not own it, a compliance date.
- **The benefit and how you would know it worked (value seed for KPIs).** For the build the evidence seems to point at, get the client's own sense of the expected benefit in plain terms (order of magnitude, no ROI model) and, crucially, the **current-state baseline number** while the people who know it are in the room: today's cycle time on a pilot team, the share of teams with no `AGENTS.md`, the time-to-diagnose on the last agent incident, the count of unattributed agent actions. The baseline is hard to recover later, so capture it live; the targets are set off-line. This seeds the Value & success metrics (KPIs) produced in synthesis.
- **Test direction, do not commit.** You may say where the evidence looks to be heading and watch the reaction, but frame it as "this is where it seems to point," never "here is your build." The platform foundation is right for some clients, not all; a build-weak or org-gap client gets a different one (often candidate D, the internal golden path).

**Capture:** the live pain (verbatim), appetite and budget owner, the constraints that bound the build, the expected benefit and the **current-state baseline number** for the likely KPIs, and any direction the client themselves insists on. Not a selected build, not an effort number, not the KPI targets: those are produced off-line (see *Off-line: analysis, design & synthesis*).

---

## Block 9 · Close & next step (15 min)

Restate the **finding** (Build Lx / Run Ly, and the gap) and confirm what happens next: the recommended first build, selected and scoped from the finalised evidence, lands in the written report. The session closes on the finding and a clear next step, not on a build decided in the room. Confirm the report delivery date. *Not a vendor, a sparring partner.*

---

## Off-line: analysis, design & synthesis

The room gives you the evidence. The decisions are made here: the finalised placement, the selected first build, the design, and the report. This is where most of the engagement's hours go. Each step has a file behind it carrying the depth, so this is real analytical work, not transcription. Several days, not an afternoon.

- **Finalise the two-track placement.** Turn the live scores into the L0–L3 placement, with a written evidence line per track and the gap statement. Re-score where the room moved a number. (`03-facilitator-field-guide.md`, sections 1 and 2)
- **Design the AWS-native target.** Take the sketched components to a real target architecture for *their* stack, and draw it (editable draw.io source ships with the report). Use the smaller variant for early clients; do not over-build. (`03-facilitator-field-guide.md`, section 5)
- **Settle managed vs open source.** Finalise the per-capability calls and the reason for each, against the client's actual constraints. (`03-facilitator-field-guide.md`, section 4)
- **Select and scope the first build.** Run the four reads against the full diagnostic, pick the candidate (A to H or a named composite), and write scope, out-of-scope, and what-you-get. This is the most consequential off-line decision. The selection must sit on equal footing for both tracks: a build-weak client lands on a build-track build (often D, the internal golden path) without the structure fighting it. (`03-facilitator-field-guide.md`, section 7)
- **Size it.** Effort in person-days, and the AWS run-cost estimate from the Pricing Calculator. The day rate and price are compiled with sales. (`03-facilitator-field-guide.md`, section 6)
- **Define the value & success metrics (KPIs).** For the selected build, write the **expected benefit** in plain terms (order of magnitude, no ROI model, no NPV) and **1 to 3 KPIs**, each a metric, baseline, target, and when-measured. Use the baseline numbers captured in the room. For a build-track build, KPIs are things like "a stream-aligned team ships an agentic feature on the golden path without rebuilding plumbing", or "agentic-coding adoption / cycle-time on a pilot team clears its bar". For a run-track build, "an eval gate blocks a regressing change in CI" or "per-session isolation verified on the migrated feature". These KPIs are the same metrics the roadmap gates on, so value is measured, not promised; they feed the report's value & metrics deliverable. (`03-facilitator-field-guide.md`, section 3 value pattern, mirrored.)
- **Build the gap-to-action mapping.** Turn the diagnosis into a single sequenced action table: each **primitive/org gap → remediation** (a service or action, AWS-first with the OSS or other-cloud equivalent where it earns its place) **→ effort** (person-days) **→ priority → prerequisite-or-parallel → which phase it lands in.** This is the synthesis step that turns scores into a plan; it is the artifact reports most lack. Produced off-line from the scorecard, the team read, and the target design.
- **Write the operating model and the evidence-gated roadmap.** The three team types, then the phases with an observable gate each, ordered from where this client started. Wherever possible the gate is a KPI from the value step clearing its target. (`03-facilitator-field-guide.md`, section 3; `09`)
- **Assemble the report** against `04-report-outline.md` and the generator field map, then the readout.

> If this phase feels like filling in a template, you have under-analysed. A defensible two-track placement and a target architecture for a specific stack take the time they take.

---

## Pitfalls

- **Treating build-primary as a lesser engagement.** A client adopting agentic coding across engineering with no agent product is a complete, first-class engagement, not a warm-up for the run track. Do not invent run-track findings to fill the table, do not nudge them toward a production-platform build they have no use case for, and give the build-track probes the depth the whole diagnosis rests on. The run track can be a clean n/a.
- **Clients over-rate the RUN track (when there is one).** They build fast and assume they run well. Separate the tracks ruthlessly; demand mechanical evidence for production isolation, identity, and eval gates. The build-track equivalent over-rating is full-trust agent execution on dev machines and in CI: probe it just as hard, especially in a regulated codebase.
- **Averaging the two tracks.** Never. A "Build L2 / Run L1" is not an "L1.5". The gap is the product.
- **Slideware creep.** Keep the deck thin. The written report is the deliverable.
- **Over-engineering the target.** Managed by default. Don't design an OpenSearch-at-scale target for a low-volume client. Use the smaller architecture variant for early clients.
- **Skipping the residency question, or taking "maximum sovereignty" at face value.** Sovereignty is first-class, but derive the bar from the client's actual compliance obligations (regulation, contract, certification, data class), not from the reflexive EU ask for the most sovereign option. Over-specifying trades away services and capability for no required benefit. Confirm what genuinely binds them before designing the target.
- **Designing the org change *and* staffing it.** We design the operating model; the client staffs it. Say so.
- **A roadmap of ambition, not evidence.** Every phase gate must be an observable, falsifiable outcome.
- **Letting the gateway/substrate claim go unchallenged.** "We have a gateway" from platform vs "I've never used it" from a team is itself a finding.
- **Deciding the build in the room.** Selecting and scoping the first build is an off-line conclusion against the finalised diagnosis. Pick it live, before the scores are settled, and you have a guess dressed as a recommendation. The session gathers the inputs; the synthesis makes the call.

---

## Notes-to-report checklist

Before writing the report, confirm you have what the generator needs (see `04-report-outline.md` field map). Items marked *(room)* are captured live; items marked *(off-line)* are produced in synthesis from the evidence, not captured in the room.

Captured in the room:

- [ ] Client context line (sector, headcount, location, cloud, residency).
- [ ] **Readiness screen** flags and provisional verdict (Proceed / Caution / Pause), blockers named. *(room; verdict finalised off-line)*
- [ ] Which track the engagement is primary on (build / run / both). *(room)*
- [ ] The triggering story (for the exec summary). *(room)*
- [ ] **D1 evidence:** seven primitive scores (provisional) with build/run split + one evidence line each. Equal depth on both tracks; run as n/a where there is no production agent. *(room; finalised off-line)*
- [ ] **D2 evidence:** the build and run reads and the gap (or the build-track unevenness, where run is n/a), with a why-line per track. *(room; placement finalised off-line)*
- [ ] **D3:** three team types, Have/Partial/Gap, finding each; the two structural patterns. *(room)*
- [ ] **D4 inputs:** the real stack, the components in scope, the residency line. *(room)*
- [ ] **D8 inputs:** the live pain (verbatim), appetite and budget owner, the constraints that bound the build. *(room)*
- [ ] **Value baseline:** the current-state baseline number(s) for the likely KPIs (cycle time, adoption, time-to-diagnose, etc.), captured live. *(room; targets set off-line)*

Produced off-line in synthesis:

- [ ] **Readiness verdict finalised:** Proceed / Caution / Pause, blockers named. Leads the report if Caution or Pause. *(off-line)*
- [ ] **D1/D2 finalised:** scores and L0–L3 placement settled against the evidence. *(off-line)*
- [ ] **D4:** the target architecture designed for their stack + editable draw.io source. *(off-line)*
- [ ] **D5:** three team types, owns / what changes. *(off-line)*
- [ ] **D6:** per-capability managed/OSS choice + why. *(off-line)*
- [ ] **Value & success metrics (KPIs):** expected benefit (order of magnitude) + 1 to 3 KPIs (metric / baseline / target / when), tied to the roadmap gates. *(off-line)*
- [ ] **Gap-to-action mapping:** the action table (gap / remediation / effort / priority / prerequisite-or-parallel / phase). *(off-line)*
- [ ] **D7:** phases, gates, timings, with Phase 0 = the selected build, gates referencing the KPIs where possible. *(off-line)*
- [ ] **D8:** the selected build (via `03-facilitator-field-guide.md`, section 7), scope in/out, what-you-get, effort (person-days), timeline, run cost (via `03-facilitator-field-guide.md`, section 6). The price is compiled with sales. *(off-line)*
- [ ] Hero stats: readiness verdict, "Build Lx / Run Ly", first build name, effort, timeline, run cost. The first-engagement price is added with sales. *(off-line)*
