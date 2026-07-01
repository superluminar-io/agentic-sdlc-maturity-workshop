# Agentic SDLC Maturity Workshop · Delivery Kit

A self-contained, git-ready kit for delivering superluminar's **Agentic SDLC Maturity Workshop**: a diagnostic for engineering leaders that reads where an organisation stands on *building with agents* and *running agentic systems in production*, designs the AWS-native target, and scopes a first build to start now.

The workshop covers **two co-equal subjects**, never averaged: **building with agents** (engineers using agentic tooling to build software faster, the internal SDLC-productivity track) and **building agentic products** (shipping agentic software to customers, the production track). A client may come for either, or both. A team adopting agentic coding across engineering with **no agent product in sight** is a complete, first-class engagement (a build-primary one), not a precursor to the run track; a team hardening a shipped feature is a run-primary one; a team doing both at once lands on both tracks. The three worked examples, Reimann (run-primary), Aurum Pay (build-primary) and Brightwell (both tracks), show all three shapes end to end.

> Anyone can stand up a working-looking app with AI now. Turning that into software you can ship, run, and trust is the hard part, and so is turning ad hoc agentic coding into a shared, governed capability across engineering.

This is a **diagnostic**, not training. Every engagement ends in a written report and one recommended first build. **No slideware.** The client's next step is a decision, not another workshop. Everything is concrete, written down, and theirs to keep.

> Not a vendor, a sparring partner. You own what we build.

---

## Who runs this, who's in the room

**Who runs it:** two superluminar consultants, both engineers, working together. No fixed split of roles, they share leading the room, capturing, and the architecture and synthesis work, and can swap. The second is the norm, not a luxury.

**Client side (engineering leaders):**
- VP / Director of Engineering or CTO (sponsor, decision-maker)
- Platform / infrastructure team lead
- One or two stream-aligned engineering leads (teams shipping product)
- An AI-guild representative, if one exists
- A security / data-protection contact for the EU-residency and governance questions

This is an **engineering-side** diagnostic. Its business-side peer is the **AI Readiness Workshop** (see *Where this sits* below).

---

## The flow

```
Intake  →  Assessment session  →  Target design  →  Roadmap & first build  →  Report
(pre-work)   (Step 1)              (Step 2)          (Step 3)                  (deliverable)
```

1. **Intake / pre-work.** Send the technical maturity questionnaire ahead of time. Collect what can be answered async; flag what needs the room.
2. **Assessment session (Step 1, Read where you stand).** Score the seven platform primitives, place the client on the two-track ladder, read the org through Team Topologies.
3. **Target design (Step 2, Design the target).** AWS-native target architecture on Bedrock + AgentCore, the operating model to match, managed-vs-open-source decided per capability.
4. **Roadmap & first build (Step 3, Plan the path, scope the first build).** Phased, evidence-gated roadmap up the ladder, and one first build, selected from the diagnostic via the field guide's first-build selection guide (`03-facilitator-field-guide.md`, section 7), scoped in full.
5. **Report.** Write up the 8 deliverables across 3 outcomes, plus the executive summary. Hand over with the editable architecture source.

The customer-facing session is a long half-day to a day. Its job is to **gather depth**, the evidence behind each score, the real stack, the constraints, not to produce the deliverables. The detailed target design, the first-build selection and scoping, and the report itself are built **off-line**, and that is where most of the engagement's effort sits. See the **Engagement shape** and **Off-line: analysis, design & synthesis** sections in `02-facilitator-runbook.md`.

---

## The three steps and three outcomes

| Step | Outcome | Deliverables |
| --- | --- | --- |
| 1. Read where you stand | **01 · Where you are** | D1 Maturity scorecard · D2 Two-track ladder · D3 Team & process read |
| 2. Design the target | **02 · What good looks like** | D4 AWS-native target architecture · D5 Target operating model · D6 Managed vs open source |
| 3. Plan the path, scope the first build | **03 · How to get there** | Gap-to-action (D6b) · Value & KPIs (D6c) · D7 Phased roadmap · D8 Recommended first build |

---

## File index

| File | What it is |
| --- | --- |
| `README.md` | This file. What the kit is, the flow, the index, customisation. |
| `01-technical-maturity-questionnaire.md` | Pre-work + assessment questions, grouped by the 7 primitives, separating BUILD from RUN. |
| `02-facilitator-runbook.md` | Agenda, timings, room, session-by-session notes, capture checklists, pitfalls. |
| `03-facilitator-field-guide.md` | The in-room reference to score *against*, in workshop order: scoring rubric, two-track ladder, Team Topologies read, managed vs open source, AWS target architecture patterns, cost basis, and the off-line first-build selection guide (candidates A–H). |
| `04-report-outline.md` | The full 8-deliverable report structure, exec summary, generator field map. |
| `facilitator-deck-outline.md` | A thin on-screen running deck to anchor sessions (NOT a client deliverable). |

---

## File → deliverable map

| Report deliverable | Sourced / supported by |
| --- | --- |
| **D1 · Maturity scorecard** (7 primitives, 0–5) | `01-technical-maturity-questionnaire.md`, `03-facilitator-field-guide.md` (section 1, scoring rubric) |
| **D2 · Two-track ladder placement** (L0–L3) | `03-facilitator-field-guide.md` (section 2, ladder rubric; fed by D1 + questionnaire) |
| **D3 · Team & process read** (Team Topologies) | `03-facilitator-field-guide.md` (section 3, Team Topologies read) |
| **D4 · AWS-native target architecture** | `03-facilitator-field-guide.md` (section 5, architecture patterns) |
| **D5 · Target operating model** | `03-facilitator-field-guide.md` (section 3 target operating model, and section 5) |
| **D6 · Managed vs open source** | `03-facilitator-field-guide.md` (section 4, managed vs open source) |
| **D7 · Phased roadmap** | `02-facilitator-runbook.md` (Step 3), `03-facilitator-field-guide.md` (section 7, first-build selection), `04-report-outline.md` |
| **D8 · Recommended first build** (selected per client) | `03-facilitator-field-guide.md` (sections 7, 6 and 5: selection, cost basis, architecture), `04-report-outline.md` |

`02-facilitator-runbook.md` and `04-report-outline.md` span all deliverables. `04-report-outline.md` also carries the **report generator field map**: the named fields the generator needs and which artifact each comes from.

---

## How to use this kit

1. Read `02-facilitator-runbook.md` end to end before your first delivery.
2. Send `01-technical-maturity-questionnaire.md` as intake pre-work.
3. Run the sessions with the field guide (`03-facilitator-field-guide.md`) open to score against, capturing into the Notion workbook row.
4. Decide the target and managed-vs-open-source with the field guide (`03-facilitator-field-guide.md`, sections 4 and 5); size it with its cost basis (section 6).
5. Assemble the report against `04-report-outline.md`.

Keep the on-screen `facilitator-deck-outline.md` thin. The report is the deliverable, not the deck.

---

## Customisation notes

- **The kit does not set a rate or a price.** Delivery sizes the effort (person-days) in the field guide's cost basis (`03-facilitator-field-guide.md`, section 6) and estimates the AWS run cost there (AWS's pricing, from the Pricing Calculator, not a number we set). The day rate and the engagement price are owned by sales and compiled with them when the report is built. The ~€39k / ~28 person-day / ~€600–1,400/mo figures are from the published example report, an illustration of order of magnitude, not a quote.
- **Three worked examples run through the kit**, one per shape, so none is treated as the default. **Reimann Software GmbH** (Karlsruhe B2B SaaS, ~280 engineers, finding "Build L2, Run L1") is the run-primary example: a shipped feature that got hard, landing on first build A (platform foundation). **Aurum Pay GmbH** (Berlin B2B fintech, ~140 engineers, PCI-DSS scope, finding "Build L1, Run L0 n/a") is the build-primary example: adopting agentic coding across engineering with no agent product, landing on first build D (internal golden path). **Brightwell GmbH** (Hamburg B2B SaaS analytics, ~200 engineers, finding "Build L1, Run L1") is the both-tracks example: shipping a customer-facing agentic assistant *and* adopting agentic coding, both emerging, landing on a composite first build A (shared platform substrate serving both tracks). Replace with the real client. Keep the example blocks as a reference for shape, not content.
- **EU data realities are first-class, not a footnote.** GDPR, the EU AI Act, data residency and sovereignty, and `eu-central-1` (Frankfurt) belong in the target and the first build. Sovereignty is matched to the actual bar: in-region AWS, the AWS European Sovereign Cloud (more cases, but service-limited and not a drop-in), or an EU-native provider (Scaleway, STACKIT) for the strictest requirements, where an AgentCore-style managed stack may not exist and the target itself changes. Confirm the client's residency and sovereignty line early.
- **Managed by default.** Reach for open source only where a concrete requirement (portability, a bespoke metric, a cost cliff) pays for the extra operational load. Keep the field guide's managed-vs-open-source section (`03-facilitator-field-guide.md`, section 4) aligned with the living capability map at <https://superluminar.io/agentic-stack/>.
- **The recommended first build is selected per client, never fixed.** Use the field guide's first-build selection guide (`03-facilitator-field-guide.md`, section 7) to derive it from the diagnostic (the weaker track, the binding primitive, technical-vs-org blocker, the live pain). The platform foundation is the right call for *some* clients; build-weak or org-gap clients get a different build. A workshop that recommends the same build every time is a sales pitch, not a diagnostic.
- **A light readiness screen gates the engagement.** A fast yes/no go/no-go at the top of `01-technical-maturity-questionnaire.md`, confirmed at the open of the session and finalised off-line, tallying blocker flags to Proceed / Proceed with caution / Pause. A clear no early beats an expensive maybe. Engineering-leader framing: a sponsor with authority, budget or intent, a team to build and operate (or a partner-reliance plan), baseline cloud/Bedrock access, a real codebase/feature to work with, a security contact, no hard regulatory block, a realistic timeline, and appetite to act.
- **Value is light and honest, no ROI model.** For the recommended first build, state the expected benefit (order of magnitude) and 1 to 3 KPIs (metric, baseline, target, when measured) that the roadmap gates measure, so value is proven, not promised. Build-track KPIs look like "a stream-aligned team ships an agentic feature on the golden path without rebuilding plumbing" or "adoption / cycle-time on a pilot team"; run-track ones like "an eval gate blocks a regressing change in CI" or "per-session isolation verified". We do not manufacture an NPV or payback model; the business case is the client's to own.
- **The gap-to-action mapping turns the diagnosis into a plan.** An off-line synthesis table mapping each primitive/org gap to a remediation (AWS-first, OSS or another cloud where it earns its place), effort in person-days, priority, prerequisite-or-parallel, and the phase it lands in.
- **Capability transfer is the model.** superluminar embeds and hands over. Phase 0 is the selected first build; all phases are evidence-gated.

---

## Report generator

The report is produced by superluminar's report generator, live at `https://a2hmr6fzsm.eu-central-1.awsapprunner.com/` (route `/new/agentic`; access password is in the shared 1Password). It also runs locally on `:8000` for development. Fill the form from `04-report-outline.md`, which ends with the field spec the generator is built to.

## Where this sits beside the other workshops

- **AI Readiness Workshop** is the **business-side peer**. For exec teams: where the business stands on AI, the use cases worth building, what to build first. The two fit together: AI Readiness answers *what's worth building*; this workshop answers *can you build and run it, and what's the platform*. When both run, share findings so the recommended first build and the prioritised use cases line up.
- **AI Kickstart** is the short, hands-on entry point for teams not yet ready for a full diagnostic. A natural feeder into this workshop once a team wants the deeper engineering read.

---

*superluminar GmbH · AWS Advanced Consulting Partner · Hamburg · Völckersstraße 14–20, 22765 Hamburg.*
