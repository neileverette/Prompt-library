# Updated Summarization Prompt Instructions

Use this prompt whenever you want ChatGPT to generate a **bolded first line** followed by a **short explanatory paragraph**, based on source text you provide.

---

## Example of Input Text (for LLM context)

This demonstrates the type of long-form NotebookLM-style content the model will receive:

```
The documents primarily showcase the versatile technological offerings and market applications of the Confluent Platform, emphasizing its role in enabling a contextual, event-driven business strategy. This proprietary system offers a wide array of pipeline solutions tailored to enterprise needs, including supporting real-time analytics via streaming ETL, offering Database Offload solutions, and facilitating complex Microservices Integration. These uses are illustrated through specific examples such as streamlining MiFID II compliance for banks and managing vast sensor data for car manufacturers like Audi. Furthermore, the platform is presented as a critical enabler for modernizing infrastructure through Mainframe Augmentation and providing robust data synchronization capabilities for Hybrid Cloud deployments. A concluding excerpt reveals a significant corporate event, with the CEO commenting on the company's future after announcing its acquisition by IBM.
```

---

## Example of Expected Final Output


The expected output example should include
Max 400-character explanation
Human-readable summary (no “the input text says…” phrasing)
Written assuming the user knows nothing about the topic

**Confluent Platform for Enterprise Event-Driven Systems**

The input text explains how Confluent enables real-time, event-driven architectures through streaming pipelines, database offload, microservices integration, and hybrid cloud data sync. It highlights enterprise use cases—from financial compliance to automotive sensor processing—and positions Confluent as a modern infrastructure layer strengthened further by its acquisition by IBM.

[Playbook with summary video, podcast, other goodies](https://notebooklm.google.com/notebook/1ada452b-e824-4e17-97a5-0dfbfc170fc1)

---

# Instructions to ChatGPT

When using this prompt, ChatGPT must follow these exact steps:

1. **Use the provided input text** as the sole source material. Do *not* visit external links or add information not found in the provided text.

2. If a **Subject** is not explicitly given, extract the primary technology, topic, or theme from the input text and use it as the **bolded first line**.

3. The **bolded first line** must be a concise, standalone statement of the topic. Do **not** label it (no "title:" or "topic:").

4. The explanatory paragraph must briefly describe:

   * what the topic is,
   * what the content covers,
   * and how it fits into the user's broader solution or context.

5. **Do NOT** use the words "headline," "title," "summary," "description," or "link" anywhere in the output.

6. End with this exact text as a hyperlink (or plain text if no URL is provided):
   **[Playbook with summary video, podcast, other goodies](https://notebooklm.google.com/notebook/1ada452b-e824-4e17-97a5-0dfbfc170fc1)**

7. Output **MUST** follow this structure:

   * **Line 1:** Bolded text (the topic)
   * **Line 2+:** A short explanatory paragraph
   * **Final line:** "[Playbook with summary video, podcast, other goodies](https://notebooklm.google.com/notebook/1ada452b-e824-4e17-97a5-0dfbfc170fc1)" (hyperlinked if a URL is available)

---

This updated prompt includes context, examples, and stricter guidance so the LLM consistently produces the desired format.
