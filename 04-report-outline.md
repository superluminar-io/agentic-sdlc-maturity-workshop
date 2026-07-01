# 04 · Report Outline

The full structure of the written report: the executive summary, the 8 deliverables across 3 outcomes, and the **report generator field map**. The report is the deliverable. Keep it concrete, written down, theirs to keep. No slideware.

> Every page footer: `superluminar · Agentic SDLC Maturity Workshop`. Example reports carry an `EXAMPLE · illustrative deliverable · fictional client` watermark and a disclaimer that figures are illustrative ballparks, not a quote.

---

## Cover

- Title: **Agentic SDLC Maturity Workshop**
- Subtitle: *Where your teams stand on building and running agents, the target on AWS, and the path forward.*
- **Prepared for:** client name + one-line profile (sector · headcount · location · on AWS).
- **Prepared by:** superluminar · AWS Advanced Consulting Partner. Tagline: *Two-track maturity read & recommended first build.*

---

## Executive summary · "The short version"

The most-read page. Lead with the **finding, which is the gap between the two tracks, in whichever direction it runs.** Structure:

0. **Go/no-go verdict** *(from the light readiness screen)*. A one-box read: **Proceed / Proceed with caution / Pause**, with any blockers named. Proceed sits quietly in the hero boxes; Caution or Pause leads the page, because saying so early is the honest thing.
1. **The short version.** One paragraph stating the finding. For a **run-primary** client: you build with agents faster than you can run them in production; the last 20% (integration, multi-tenant isolation, correctness, customer-facing guardrails) is where it got hard; closing that is a platform problem, not a model problem. For a **build-primary** client: agentic coding is happening ad hoc across teams and is not yet a shared, governed, gated capability; closing that is a platform-and-practice problem. Anchor it in the triggering story for whichever shape this is.
2. **Where you stand.** Build track placement + why; run track placement + why, or **run as a clean n/a** for a build-primary client with no agent product. The lag, in whichever direction, stated plainly. Never average the two.
3. **What to do first.** The recommended first build, in two sentences, and what it lifts (the weaker track up a rung).
4. **The gap is the finding.** Restate the finding and that the first build closes it. *Not a model problem. A platform, and for build-primary clients a platform-and-practice, problem.*

### Hero stat boxes

| Box | Content |
| --- | --- |
| **Go/no-go** | *Proceed / Caution / Pause* + any blockers (from the screen). |
| **Where you stand** | `Build Lx, Run Ly` (or `Run n/a` for a build-primary client) + short label. |
| **First build to start now** | The build name + one line (e.g. "A production agent platform foundation", or "An internal golden path for agentic coding"). |
| **Indicative first engagement** | `~€XXk` · `~NN person-days` · `N–N weeks` · `~€low–high/mo run`. Price compiled with sales. |

Disclaimer line under the summary: *All figures are illustrative ballparks … not a quote.*

---

## Outcome 01 · Where you are

*An honest read on the agentic platform, the two-track maturity, and how teams are organised to build and run agents.*

### D1 · Maturity scorecard
- The seven primitives scored 0–5 (0 = absent, 5 = governed shared capability): LLM gateway, agentic memory, RAG/knowledge, sandbox/isolation, identity & access, observability, evals.
- A visual bar per primitive with the score.
- Prose splitting the scores along the **build/run line**: strong on build (what grew up serving engineers), weak on run (what production agents need), and **the standout gap** (usually sandbox/isolation, the real production-readiness gap, first thing the build fixes).
- Source: `03-facilitator-field-guide.md` (section 1, scoring rubric), `01-technical-maturity-questionnaire.md`.

### D2 · Two-track ladder placement
- The L0–L3 table for both tracks side by side, with **YOU ARE HERE** marked on each track.
- Caption: the tracks look alike at L0 and split by L3 (run adds per-session isolation, customer-facing guardrails, identity, A2A).
- A short **"AWS substrate behind L2 and L3"** note: Bedrock + AgentCore + Knowledge Bases + Guardrails + Evaluations is a substrate beneath the rungs, not a level.
- Source: `03-facilitator-field-guide.md` (section 2, ladder rubric).

### D3 · Team & process read
- Team Topologies table: stream-aligned / platform / enabling, each Have/Partial/Gap + finding.
- A **"where the gaps are"** paragraph naming "enabling onto a vacuum" and "plumbing rebuilt per feature," and the structural fix.
- Source: `03-facilitator-field-guide.md` (section 3, Team Topologies read).

---

## Outcome 02 · What good looks like for you

*The target: an AWS-native agentic platform, the operating model to match, and where managed beats open source.*

### D4 · AWS-native target architecture
- The production agent platform on Bedrock AgentCore: the **request path (run)** and the **build path (ship)**.
- A diagram (editable draw.io source provided alongside the report).
- A **"why managed AgentCore, not hand-built"** paragraph (shortest path L1 → L2 on run).
- Everything in `eu-central-1`; EU residency stated.
- Source: `03-facilitator-field-guide.md` (section 5, architecture patterns).

### D5 · Target operating model
- The three team types: owns / what changes for them.
- **The target in one line.**
- Source: `03-facilitator-field-guide.md` (section 3 target operating model).

### D6 · Managed versus open source
- Per-capability table: capability → recommended → why.
- The **rule of thumb** line (managed by default; OSS only for a concrete, paid-for reason).
- **Living reference** pointer to superluminar.io/agentic-stack/.
- Source: `03-facilitator-field-guide.md` (section 4, managed vs open source).

---

## Outcome 03 · How to get there

*A phased climb up the ladder, each step gated on evidence, and the first build that starts it.*

### D6b · Consolidated gap-to-action *(needs a generator field)*
- A single action table synthesised off-line from the scorecard, the placement, and the team read: **Gap · Track (build/run) · Remediation** (service or action, AWS-first with the OSS or other-cloud equivalent where it fits) **· Indicative effort** (person-days) **· Priority · Prerequisite or parallel · Phase.** Turns the diagnosis into a sequenced action list.
- Source: synthesised off-line from `01`, `03-facilitator-field-guide.md` (sections 1, 2, 3 and 5).

### D6c · Value & success metrics *(needs a generator field)*
- For the recommended first build, the **expected benefit** in plain terms with an order of magnitude, and **1 to 3 KPIs** (metric · baseline · target · when measured). Light and honest: no manufactured ROI, no NPV. The KPIs are the same metrics the roadmap gates on, so value is measured, not promised.
- Build-track KPIs read like "a stream-aligned team ships an agentic feature on the golden path without rebuilding plumbing", or agentic-coding adoption / cycle-time on a pilot team. Run-track KPIs read like "an eval gate blocks a regressing change in CI, proven on a real change", or "per-session isolation verified for a customer-facing feature".
- Source: `02-facilitator-runbook.md` (Block 8 + off-line), `03-facilitator-field-guide.md` (section 6, cost basis).

### D7 · Phased roadmap up the ladder
- Four phases. **Phase 0 is the client's selected first build (see D8 and `03-facilitator-field-guide.md`, section 7, first-build selection), not automatically the platform foundation.** The later phases (golden paths → gates & governance → agentic factory) are broadly stable but re-order so each phase's gate follows from where this client started.
- For each: what happens + **the gate to clear before moving on**, and **wherever possible the gate is a KPI from D6c clearing its target** (an eval gate blocking a regression, a stream-aligned team shipping on the golden path): an observable go/no-go, not ambition.
- A phase-strip visual. Timings illustrative.
- Source: `02-facilitator-runbook.md` (Block 7), `03-facilitator-field-guide.md` (section 7, first-build selection).

### D8 · Recommended first build
- **The build is selected per client from the diagnostic; it is not fixed.** Choose it with `03-facilitator-field-guide.md` (section 7, first-build selection; candidates A–H, or a named composite). The bullets below are the *Reimann example* (first build A, platform foundation); replace them with the selected build's, never paste as a template.
- **Scope** (bulleted): for the example A, the AgentCore foundation, observability + guardrails, the eval gate in CI, the flagship feature migrated as golden-path proof. *For a build-weak or org-gap client this is entirely different (e.g. an internal golden path, or a platform team + thin slice).*
- **Explicitly out of scope** (bulleted): scoped to the selected build (example: migrate-everything, staffing the org change, new features beyond the one migration).
- **What you get** (bulleted): the concrete outcome of the selected build, ending with capability transfer. *You own what we build.*
- **The decision**: fund a ~€XXk, ~NN person-day build that closes *this client's* gap; gated, EU-resident, measured. Sign-off: *Not a vendor, a sparring partner.*
- Hero boxes: The build · Effort (~NN days) · Timeline (N–N wks) · Indicative price (~€XXk + ~€low–high/mo run).
- Source: `03-facilitator-field-guide.md` (sections 7, 6 and 5: first-build selection, cost basis, architecture patterns).

---

## Report generator field map

This is the **field spec** for the report generator (route `/new/agentic`). **The form is the only input; the PDF is deterministic.** Each field takes its value from the kit artifact named in the right column, so the map doubles as a fill-in checklist. Some of these fields exist in the current draft generator; the deepened ones (the go/no-go screen, track-primary, value & KPIs, gap-to-action) are flagged in the **Generator field spec** at the end. The generator is pre-release, so bring it up to this complete spec rather than treating any of it as legacy.

**Cover & basics**

| Form field | From |
| --- | --- |
| Client legal name | Intake / questionnaire (`01`) |
| One-line descriptor (industry · size · location · cloud) | Intake (`01`) |

**Executive summary**

| Form field | From |
| --- | --- |
| Opening summary | Runbook Block 0 (triggering story) |
| At-a-glance card · GO/NO-GO (Proceed / Caution / Pause + blockers) | `01` light readiness screen |
| Track-primary (build / run / both) | `01` / `02`; sets which track carries the finding |
| Run-track n/a flag (build-primary, no agent product) | `02` / field guide §2 (`03-facilitator-field-guide.md`); renders "Run n/a" instead of a fabricated low score |
| At-a-glance card · WHERE YOU STAND (`Build Lx, Run Ly`, or `Run n/a`) | D2 / ladder rubric (field guide §2) |
| At-a-glance card · FIRST BUILD TO START NOW | D8 / selection guide (field guide §7) |
| At-a-glance card · INDICATIVE FIRST ENGAGEMENT (€ · person-days · weeks · run/mo) | Cost basis (field guide §6) |
| Where you stand (prose) | D2 |
| What to do first (prose) | D8 / field guide §7 |
| Gap callout: heading + body | D2 gap statement (field guide §2) |

**Deliverable 01 · Maturity scorecard (7 primitives)**

| Form field | From |
| --- | --- |
| Per primitive: Score 0–5 + one-line note (LLM gateway, Agentic memory, RAG/knowledge, Sandbox/isolation, Identity & access, Observability, Evals) | Scoring rubric (field guide §1) + questionnaire (`01`) |
| The read (one paragraph per bullet, **bold** lead: strong-on-build / weak-on-run / standout gap) | field guide §1 |

**Deliverable 02 · Two-track ladder placement**

| Form field | From |
| --- | --- |
| Build with agents level (L0–L3) · Run agentic systems level (L0–L3) | Ladder rubric (field guide §2) |
| Intro / differentiator; Note under the matrix (optional) | field guide §2 |
| Substrate callout: heading + body | field guide §2 |

**Deliverable 03 · Team & process read**

| Form field | From |
| --- | --- |
| Team types rows (Team type · Status Have/Partial/Gap · Finding) | field guide §3 (current state) |
| Callout: heading + body ("enabling onto a vacuum" / "plumbing per feature") | field guide §3 |

**Deliverable 04 · AWS-native target architecture**

| Form field | From |
| --- | --- |
| The request path (run) · The build path (ship) | field guide §5 |
| Why-managed callout: heading + body | field guide §5 |

**Deliverable 05 · Target operating model**

| Form field | From |
| --- | --- |
| Teams rows (Team · Owns · What changes for them) | field guide §3 (target operating model) |
| Callout: heading + body | field guide §3 |

**Deliverable 06 · Managed vs open source**

| Form field | From |
| --- | --- |
| Capabilities rows (Capability · Recommended · Why) | field guide §4 |
| Rule of thumb (optional) + living-reference pointer to superluminar.io/agentic-stack/ | field guide §4 |

**Deliverable 6b · Gap-to-action**

| Form field | From |
| --- | --- |
| Gap-to-action rows (Gap · Track build/run · Remediation AWS-first · Effort person-days · Priority · Prerequisite/Parallel · Phase) | synthesised off-line (`01`, field guide §§1, 2, 3, 5) |

**Deliverable 6c · Value & success metrics**

| Form field | From |
| --- | --- |
| Expected benefit (prose) · KPI table (metric · baseline · target · when measured) | `02` Block 8 + off-line synthesis, field guide §6 |

**Deliverable 07 · Phased roadmap up the ladder**

| Form field | From |
| --- | --- |
| Phases rows (Tag · Title · Duration/sub · What happens · Gate to clear). **Phase 0 = the selected first build; gates are D6c KPIs clearing their targets where possible.** | Runbook Block 7 + field guide §7 + D6c |

**Deliverable 08 · Recommended first build** *(selected per client via field guide §7)*

| Form field | From |
| --- | --- |
| At-a-glance cards · THE BUILD (field guide §7) · EFFORT + TIMELINE (field guide §6, delivery) · INDICATIVE PRICE (compiled with sales) | field guide §§7, 6; the price card is filled with sales, not from the kit |
| Scope (bullets) · Explicitly out of scope (bullets) · What you get (bullets) | field guide §7 + §5 |
| Decision callout: heading + body | field guide §§6, 5, 7 |

**Off critical path / output options**

| Form field | From |
| --- | --- |
| Architecture diagram upload (PNG/JPG/SVG/WEBP; draw.io export; templates in generator repo `assets/diagram-templates/`) | field guide §5 |
| Mark as EXAMPLE sample (watermark + badge + "illustrative ballparks" disclaimer) | facilitator's call |

---

## Generator field spec (bring the generator up to this)

The generator was built from an earlier, lighter draft of this workshop, before the two-track rebalance and the deepening. **Nothing has shipped, so there is no live form to preserve.** The generator simply needs updating to carry the full set the report now uses. The fields below are what it still needs on top of the map above; together they are the complete spec.

| Field | Where | Source | Type |
|---|---|---|---|
| Go/no-go verdict | Exec summary hero box | `01` light readiness screen | enum (Proceed / Caution / Pause) + blocker list |
| Track-primary | Exec summary, drives the framing | `01` / `02` | enum (build / run / both) |
| Run-track n/a flag | D1 / D2 | field guide §2 | boolean (renders "Run n/a" for a build-primary client) |
| Gap-to-action table | D6b | synthesised off-line | repeatable rows: gap / track / remediation / effort / priority / prerequisite-or-parallel / phase |
| Value & success metrics | D6c | `02` + field guide §6 | expected-benefit prose + KPI table (metric / baseline / target / when). Roadmap gates reference the KPIs. |

This is the full field set, not a patch on a shipped form. Update the generator to it. If the report changes shape later, update this section and the source artifact together.
