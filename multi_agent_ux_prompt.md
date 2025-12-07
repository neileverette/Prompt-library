# Multi-Agent UX Research Prompt (Markdown Version)

**You are acting as an industry research analyst investigating UX patterns for multi-agent AI assistants.  
Do deep, broad research across the industry with a focus on enterprise-grade AI assistants that support multiple agents.**

---

## 1. Context  
We are dealing with a new, emerging UX pattern: **multi-agent intelligent assistants that allow users to switch between different tools or contexts.**  
There is currently **no industry standard** for how this should work, and we may be defining a new design approach from scratch.

### Concrete Example  
AWS offers *Amazon Q* as its default/generalized assistant. At re:Invent, AWS announced several specialized agents — **Kiro**, a **Security Agent**, and a **DevOps Agent**.  
A user begins in Q’s *default mode*, but may need to **switch modes** to activate one of these specialized agents for a deeper task-specific workflow. After completing that task, the user must be able to **revert back** to the default Q experience seamlessly and without confusion.

This emerging pattern — default assistant → specialized agent → return to default — does **not yet have clear UX conventions**, especially when scaled across multiple products or enterprise suites.

---

## 2. Initial Perceived UX Challenges  
Use these as hypotheses only. You may refine or expand them during research:

1. Users must clearly understand which tool or agent context they are in.  
2. Users must easily discover that agent-switching exists and understand how to use it.  
3. Users must be able to switch to any agent and return to their default context.  
4. The assistant must maintain clear, unambiguous context at all times.  
5. The UX must scale to enterprise complexity:  
   - many agents within a product  
   - many products within a suite  
   - many suites within a company portfolio

---

## 3. Tasks  
Perform an **industry-wide search** for AI assistants that support **multi-agent switching**.

### Inclusion Criteria  
- The AI assistant must offer **multiple agents** (or agent modes).  
- It must be **enterprise-focused**.  
- Evaluate the **UI/UX patterns** of:  
  - agent discovery  
  - agent switching  
  - context visibility  
  - returning to default mode  

---

## 4. Produce a Table  
Columns:

- **Company Name**  
- **Assistant Name**  
- **# of Agents**  
- **How Agent Switching Works (UI/UX summary)**  

---

## 5. Analyze for UX Patterns  
Determine:

- Whether any **industry-standard patterns** exist  
- Whether any **repeatable patterns** emerge  
- Whether the industry is **fragmented**, indicating lack of standardization  

---

## 6. Summary of Findings  
Write a concise summary covering:

- Patterns in the agentic assistant landscape  
- How companies handle agent switching, discoverability, and context clarity  
- Any emerging or proposed UX conventions  
- Overall *maturity level* of this design space  
- Whether this appears to be a **brand-new UX frontier** or whether we can rely on de-facto patterns  

---

## 7. Generate a Cartesian Matrix  
Create a 2-axis matrix that plots each company/assistant:

- **X-Axis:** # of agents (none → few → many)  
- **Y-Axis:** Visibility of agents (highly visible → hidden)  

---

## 8. Identify UX Problems & Pain Points  
Based on your findings, summarize the **key UX challenges** teams will face, especially considering:

- Product-specific workflows (e.g., observability RCA tasks)  
- Switching between general-purpose and specialized agents  
- Jumping across products or suites (e.g., security → APM → observability)  
- Maintaining continuity, clarity, and user mental models  

---

## 9. Provide Guiding Design Principles  
Write a concise set of design principles focusing on:

- clarity of context  
- discoverability  
- reversible mode switching  
- scalability  
- reducing cognitive load  

Keep these principles short, focused, and practical.

