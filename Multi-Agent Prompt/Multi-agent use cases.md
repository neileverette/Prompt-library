

## Summary

Enterprise AI assistants operate in silos. Users must know which tool has which capability, manually switch contexts, and discover specialized agents on their own.

---

## UX Issues Today

Examples stories below of similar products, though not IBM products
* **Fragmented agents**

  * AWS Q does not integrate its DevOps and Security agents.
  * Users must know these agents exist and manually find them across separate interfaces.

* **Undiscoverable specialized capabilities**

  * ChatGPT provides generic travel advice.
  * The Expedia agent provides real inventory and booking.
  * Users don’t know the Expedia agent exists unless they go looking for it.


Below are use cases under investigation. These use cases include multiple IBM products across portfolios and assumes that each product has their own assistant with available tools and agents.
Note: These use cases are not validated by neither users of the products, nor have they been confirmed or validated by engineering.

---

## Use Case 1: Cross-Product Context Passing

**Scenario**

An SRE in **Instana** sees a predicted resource saturation. They ask the AI assistant to address it. The assistant passes Instana’s context to **Turbonomic**, which returns recommended scaling actions for review and execution—without requiring a tool switch.

**UX Problem**

* Users lose context when switching tools.
* Time-to-action increases due to manual handoffs.

---

## Use Case 2: Intent-Based Capability Routing

**Scenario**

An SRE in **Concert** asks the assistant to “run root cause analysis.” Multiple tools offer RCA. The assistant determines which tool best fits the current context, routes the request, executes it, and explains which tool was used and why.

**UX Problem**

* Similarly named capabilities across tools force users to guess which one to use.

---

## Use Case 3: Cross-Product Capability Invocation

**Scenario**

An SRE in **Guardium** detects a security incident and asks for blast radius analysis. The assistant invokes **Concert’s** impact analysis behind the scenes and returns results inline within Guardium.

**UX Problem**

* Accessing another tool’s capability breaks workflow.
* Users must manually rebuild context in a new tool.

---

## Use Case 4: Specialized Agent Handoff

**Scenario**

An SRE asks the assistant for root cause analysis. The assistant recognizes a specialized agent is better suited, hands off the request, and returns the results in the same conversation—clearly indicating which agent handled it.

**UX Problem**

* Specialized agents exist but are not discoverable from the primary assistant.

---

## Use Case 5: Capability and Agent Discovery

**Scenario**

An SRE asks the assistant what agents or capabilities are available. The assistant lists them, explains when to use each, and recommends relevant ones based on the current context.

**UX Problem**

* Users can’t use capabilities they don’t know exist.

