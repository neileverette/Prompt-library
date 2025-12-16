# Designing for Scalability

## Multi-Agent Experiences for Enterprise

### Why “One Box to Rule Them All” Doesn’t Work

#### The Magic Input Box & Black-Box Routing Problem

---

## Summary

Enterprise AI agents are rapidly evolving—from simple assistants to **autonomous, multi-agent orchestrators** that make and execute decisions across critical systems. This creates a major UX problem: users can see **inputs and outputs**, but not **how decisions were made** or **why specific tools/agents were chosen**.

That’s the **black box problem**.

In consumer tools, some opacity is tolerable. In enterprise contexts—where downtime can be enormously expensive and accountability is real—opacity breaks trust and adoption. (For example, Atlassian cites downtime estimates ranging from **$100,000/hour to over $540,000/hour**.) ([Atlassian][1])

---

## Why Can’t It Just “Magically Pick”?

What works for consumer AI often fails in enterprise systems.

### Why enterprise users reject “magic”

SREs, operators, and security teams need to:

* Understand **why** the system chose a tool/agent/sequence
* Override decisions when domain knowledge matters
* Learn patterns so they can work independently
* Trust the system at **3am during an incident**

BCG explicitly warns that **“decisions made in a black box”** create legal and reputational risk and that governance controls can’t be an afterthought. ([BCG Global][2])

---

## The Core Problem: The Black Box Agent

### What’s happening

* Agents increasingly **route work**, **choose tools**, and **act autonomously**
* Orchestration happens invisibly
* Users can’t easily inspect, validate, or override decisions

### Two kinds of opacity (often conflated)

#### Model opacity

“How did the model reason internally?”

#### Orchestration opacity

“Why **this agent**, **this tool**, and **this sequence of actions**?”

In enterprise UX, **orchestration opacity** is usually the dominant trust failure (not exposing raw LLM reasoning).

### Why this is new

It’s no longer one black box model—it’s a **network of agents** making chained decisions. The real black box becomes the **orchestration layer**, where accountability gets blurry.

---

## Why This Is Enterprise-Specific

(Some regulated “consumer” domains like finance/healthcare behave similarly—this is about **risk profile**, not audience size.)

### Consumer AI (low stakes)

* Wrong answer = annoyance
* Easy recovery
* Minimal legal/operational risk

### Enterprise AI (high stakes)

* Wrong action = outages, breaches, audit failures
* Recovery may be impossible in real time
* Legal, financial, reputational consequences

**Key insight:** Convenience optimizations that work in consumer AI can fail catastrophically in enterprise.

---

## The Magnitude of the Problem

### What we can support with sources

* Downtime costs are commonly estimated in the **hundreds of thousands per hour** range (and higher in some contexts). ([Atlassian][1])
* Industry thought leadership is increasingly framing black-box decisions as a **governance and trust blocker**. ([BCG Global][2])
* IBM’s definition of “black box AI” aligns with the core UX issue: users see inputs/outputs but can’t see what happens inside to produce results. ([ibm.com][3])

### Note on the “~80% hesitate due to trust” stat

I didn’t find a clean, authoritative source matching that exact claim in a quick pass. If you want, I can rewrite that section as either:

* a *hypothesis* (clearly labeled), or
* swap in a specific sourced statistic you prefer.

---

## The “Magic Input Box” Trap

### What designers are tempted to build

* One input
* Invisible routing
* One confident answer

### Why it fails in enterprise

* Users can’t tell which agent/tool was used
* No validation path
* No learning/skill-building
* No audit trail
* Confidence is presented without provenance

### What works better

* Preview the plan before execution
* Reveal which agents/tools will be used
* Explain why a path was chosen
* Allow confirmation or override

---

## Five Enterprise Use Cases

### Use Case 1: Cross-product context passing

**Scenario:** Instana predicts resource saturation → assistant passes context to Turbonomic → returns scaling recommendations inline.
**UX failure avoided:** losing context + increased time-to-action.

### Use Case 2: Intent-based capability routing

**Scenario:** In Concert, user asks “run root cause analysis” → multiple tools could do RCA → assistant selects best fit, runs it, explains why.
**UX failure avoided:** ambiguity across similarly named capabilities.

### Use Case 3: Cross-product capability invocation

**Scenario:** Guardium incident triggers “blast radius” → assistant invokes Concert impact analysis and returns results inline.
**UX failure avoided:** workflow breaks and context rebuilding.

### Use Case 4: Specialized agent handoff

**Scenario:** User asks for RCA → handoff to specialized agent → UI clearly indicates which agent handled it.
**UX failure avoided:** invisible specialization.

### Use Case 5: Capability and agent discovery

**Scenario:** User asks what agents are available → system lists agents, explains when to use each, recommends based on context.
**UX failure avoided:** undiscoverable functionality.

---

## Why Users Reject Black Boxes in Enterprise

### Historical patterns

* Unexplained recommendations get rejected
* Mission-critical systems require reversible action
* Bias and failure modes often surface only after external investigation

### Behavior under pressure

* Experts trust their judgment over opaque systems
* Confidence drops fast after one unexplained failure
* Time pressure amplifies distrust (incidents, breaches, audits)

**Design takeaway:** Accuracy alone doesn’t create trust—especially under time compression.

---

## Principles for Trustworthy Agentic Systems

These are **non-optional** above defined risk thresholds.

### 1) Observability

Make the *why* visible.

* Show intent, agent selection, and planned actions *before execution*

### 2) Intervenability

Keep humans in control.

* Approval gates for high-risk actions
* Editable parameters
* Emergency stop

### 3) Auditability

Create a system of record.

* Human-readable decision logs
* Rationale + outcome captured
* Traceability across agents

BCG’s framing strongly supports this direction: governance controls must be embedded early, not retrofitted. ([BCG Global][2])

---

## From Black Box to Transparent UX

### Design shift required

* Hidden automation → **visible orchestration**
* AI authority → **AI partnership**
* Outcome explanation → **plan explanation**

**Designers aren’t simplifying AI—they’re governing it.**

---

## Guidance for Design Teams

### Questions to ask in reviews

* Can a user explain why this action happened?
* Can they override it?
* Can an auditor reconstruct it later?
* Would you trust this at 3am during an incident?

### Common anti-patterns

* Explanations shown only after execution
* Logs exist but aren’t human-readable
* Confidence without provenance

### Where to start

* Map the agent ecosystem
* Identify mission-critical junctions
* Prototype observability first

---

## Reference Resources

### Business implications

* BCG — *How Agentic AI is Transforming Enterprise Platforms* (black-box decisions → legal/reputational risk) ([BCG Global][2])
* IBM — *What Is Black Box AI and How Does It Work?* (inputs/outputs visible, internals opaque) ([ibm.com][3])

### Downtime framing

* Atlassian — *Cost of downtime* (estimates $100k/hour to $540k+/hour) ([Atlassian][1])

(You also listed WEF, Microsoft, Fuselab, Emerge Haus, Google Gems—if you want, I can convert those into a consistent “annotated bibliography” format next.)

---

## Where Engineering Will Push Back (and How to Respond)

### “This will slow us down”

* Previews/approvals add latency
* **Response:** uncontrolled failures create far more drag and rework

### “We can’t explain model reasoning”

* Often a misunderstanding
* **Clarification:** goal is operational transparency, not raw LLM internals

### “Logging everything is expensive”

* True at scale
* **Trade-off:** selective logging at risk boundaries, not everywhere

### “Users don’t want more UI”

* Users don’t want noise
* They *do* want clarity when stakes are high

### “We’ll add it later”

* Retrofitting trust is harder
* Governance must be designed in from day one ([BCG Global][2])

---

## Sample Architecture Diagram

### Passing Context, Intent, and Agent Routing (Text Description)

**User action → Intent detection → Agent selection → Tool plan preview → Execution across tools → Trace log + outcome**

Key elements to show in UX alongside this flow:

* Active agent identity
* Planned tools + permissions
* Context being passed (what’s included/excluded)
* Checkpoints for approval
* Human-readable trace for audit and debugging

---


[1]: https://www.atlassian.com/incident-management/kpis/cost-of-downtime?utm_source=chatgpt.com "Calculating the cost of downtime | Atlassian"
[2]: https://www.bcg.com/publications/2025/how-agentic-ai-is-transforming-enterprise-platforms?utm_source=chatgpt.com "How Agentic AI is Transforming Enterprise Platforms | BCG"
[3]: https://www.ibm.com/think/topics/black-box-ai?utm_source=chatgpt.com "What Is Black Box AI and How Does It Work? | IBM"
