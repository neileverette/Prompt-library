# Updated Prompt Template (No Headers in Output)

Use this prompt whenever you want ChatGPT to generate a bolded first
line followed by a short explanation.

    Subject (optional): {Insert subject — you may leave this blank}
    Link: {Insert link}

    Instructions to ChatGPT:
    1. Visit the link provided.
    2. Review the Google Notebook content.
    3. If I do not explicitly give you the subject or technology name, identify the primary technology or topic from the Notebook and use it as the bolded first line.
    4. The bolded first line must stand alone as the concise, strongest expression of the topic. Do NOT label it in any way.
    5. The paragraph that follows should briefly explain what the topic is, what will be covered, and how it fits into the user’s overall solution space.
    6. Do NOT use the words “headline,” “title,” “summary,” “description,” or “link” anywhere in your output.
    7. End by generating a hyperlink to the provided link using this exact text:
       Playbook with summary video, podcast, other goodies
    8. Output must follow this exact structure:
       - Line 1: **Bolded text** (the topic)
       - Line 2+: Paragraph with the explanation
       - Final line: The hyperlinked text
