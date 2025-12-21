# Router Prompt + Pause/Resume Checkpoints — Competitive Market Analysis Controller
## Topic: Observability-Driven Development (ODD)

You are an LLM tasked with producing a **competitive market analysis** using a strict, multi-phase workflow with **pause/resume checkpoints**.

Before executing any phase, select the execution mode that best matches your native strengths:

- Choose **MODE_GPT** if you excel at structured, guardrail-heavy, stepwise execution
- Choose **MODE_CLAUDE** if you excel at careful reasoning, ambiguity preservation, and neutral narrative clarity
- Choose **MODE_GEMINI** if you excel at taxonomies, tables, and analytical decomposition

Once a mode is selected:
- Do not mention the mode in the output
- Do not switch modes mid-process
- Follow the Canonical Procedure exactly
- Use the Pause/Resume Checkpoint System

---

## MODE_GPT — Execution Rules
- Execute one phase per response
- Never combine phases
- Use explicit headings and bullet lists
- Label absence of evidence explicitly

## MODE_CLAUDE — Execution Rules
- Preserve ambiguity where evidence conflicts
- Prefer careful explanation over compression
- Avoid persuasive or definitive language

## MODE_GEMINI — Execution Rules
- Prefer structured tables and taxonomies
- Maintain consistent categorical labels
- Avoid narrative expansion

---

# Pause/Resume Checkpoint System (Required)

## Checkpoint Object (Write at End of Every Phase Output)
At the end of every phase output, include a single section titled:

## CHECKPOINT

Inside it, output a compact checkpoint object in plain text with these fields:

- Phase: <0-9>
- Status: COMPLETE | IN_PROGRESS | BLOCKED
- Role: <role name used>
- Inputs Used: <artifact names only>
- Outputs Produced: <artifact names only>
- Evidence Required Next: YES | NO
- Next Phase: <phase number and name>
- Open Issues: <none or short bullets>
- Resume Instruction: <one sentence telling the next LLM exactly what to do next>

## Resume Protocol
When resuming from a checkpoint:
1. Read the latest CHECKPOINT object.
2. Continue with the Next Phase only.
3. Do not restate prior work except for a 1–2 line reminder of purpose and constraints.
4. If Status is BLOCKED, only do the minimum work to unblock, then write a new CHECKPOINT.

## Pause Rules
- If a phase requires evidence not provided yet, mark BLOCKED and specify what evidence is missing.
- Never “fill in” missing evidence by guessing.
- Never progress to the next phase without producing the checkpoint.

---

# Canonical Procedure
## Competitive Market Analysis — Observability-Driven Development

## Global Rules
- One phase at a time
- No phase may assume outputs from a later phase
- Evidence must precede synthesis
- Absence of evidence = absence of capability
- Findings must remain directional
- No rankings, no scoring, no prescriptions

---

## Phase 0 — Grounding & Guardrails
**Role:** Aggregator / Synthesizer

Task:
- Produce a Research Charter defining:
  - Purpose
  - Audience
  - Research focus
  - Explicit out-of-scope items
  - Confidence level

Rules:
- No competitors
- No solutions
- No predictions

Output:
- Research Charter only

Checkpoint:
- Phase 0 COMPLETE

---

## Phase 1 — Market Framing
**Role:** Subject Matter Expert (Observability / DevEx)

Task:
- Define Observability-Driven Development as a practice
- Contrast against:
  - Traditional observability
  - APM / NPM
  - Testing and CI alone

Rules:
- No vendors
- No feature comparisons

Output:
- ODD framing section

Checkpoint:
- Phase 1 COMPLETE

---

## Phase 2 — Developer Workflow Model
**Role:** User Researcher

Task:
- Define the canonical developer workflow:
  - IDE / local development
  - Pre-commit & code review
  - CI pipelines
  - CD / release gates
  - Post-deploy observability
  - Feedback loops back into development

Rules:
- Tool-agnostic
- No implied solutions

Output:
- Workflow model (primary comparison axis)

Checkpoint:
- Phase 2 COMPLETE

---

## Phase 3 — Competitive Set Definition
**Role:** Product Manager

Task:
- Define:
  - Inclusion criteria
  - Exclusion criteria

Rules:
- Enterprise observability vendors only
- Must have documented workflow integration
- No rankings

Output:
- Approved competitor list with categorical tags

Checkpoint:
- Phase 3 COMPLETE

---

## Phase 4 — Evidence Collection (Loop Per Competitor)
**Role:** Research Assistant

FOR EACH competitor:
- Collect evidence from:
  - Product documentation
  - Case studies
  - Public claims (label as claims)
  - User-reported feedback
  - Analyst reports

Evidence Packet Schema:
- Source type
- Source date
- Exact quote (≤25 words)
- Paraphrase (neutral)
- Reference
- Confidence level (High / Medium / Low)
- Notes (what this evidence supports)

Rules:
- Prefer sources from last 18 months
- Conflicting evidence must be retained

Output:
- One evidence packet per competitor

Checkpoint:
- Mark COMPLETE only when all competitors have packets meeting minimum evidence requirements
- Otherwise IN_PROGRESS, with list of remaining competitors

---

## Phase 5 — Workflow Mapping
**Role:** Aggregator / Synthesizer

Task:
- Map documented capabilities to:
  - Workflow stages
  - Developer-facing UX
  - Feedback loop presence
  - Technology anchors (OpenTelemetry, IDE plugins, CI/CD, AI/ML)

Rules:
- Every mapping must cite evidence
- Label claims explicitly
- Mark unclear areas as unclear

Output:
- Workflow mapping tables organized by workflow stage

Checkpoint:
- Mark COMPLETE only when all competitors are mapped across all workflow stages (even if “no evidence/unclear”)

---

## Phase 6 — Gap Identification
**Role:** User Researcher

Task:
- Identify gaps by comparing:
  - Workflow model
  - Workflow mappings

Gap categories:
- Missing coverage
- Delayed feedback
- Role misalignment
- Fragmented feedback
- Broken loops

Rules:
- Evidence-derived only
- No solutions

Output:
- Gap list tied to workflow stages

Checkpoint:
- Phase 6 COMPLETE

---

## Phase 7 — Innovation Signals
**Role:** Subject Matter Expert (ODD)

Task:
- Identify innovation signals based on:
  - Pre-production impact
  - Defect or incident prevention
  - Feedback loop acceleration into development

Rules:
- MTTR improvement alone does not qualify
- Evidence required
- No scoring or ranking

Output:
- Directional innovation map

Checkpoint:
- Phase 7 COMPLETE

---

## Phase 8 — Synthesis for Discovery
**Role:** Product Manager

Task:
- Translate gaps and innovation signals into:
  - Opportunity areas
  - Testable hypotheses
  - Discovery priorities

Hypothesis format:
“If developers had visibility into ___ at ___ stage, then they could ___, reducing ___.”

Rules:
- No solution design
- No roadmap commitments

Output:
- Discovery inputs section

Checkpoint:
- Phase 8 COMPLETE

---

## Phase 9 — Quality Control
**Role:** Content Editor

Task:
- Validate:
  - Evidence traceability
  - Scope adherence
  - Language discipline
  - Directional confidence

Rules:
- No new evidence
- No new insights

Output:
- Final, shareable Competitive Market Analysis

Checkpoint:
- Phase 9 COMPLETE
- Include any remaining open issues as non-blocking notes

---

## End Condition
Stop when:
- All phases are complete
- All claims trace back to evidence
- Findings remain directional and discovery-focused
- The final CHECKPOINT exists and is Phase 9 COMPLETE
