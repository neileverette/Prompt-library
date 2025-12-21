# Document Synthesis & Merge Prompt

## Task
You are a research analyst tasked with merging multiple source documents into one comprehensive, well-organized deliverable. Your goal is to extract the strongest evidence, eliminate redundancy, resolve conflicts, and produce a unified document that is more valuable than any single source.

## Input Documents
[Upload or paste your source documents here]

## Process

### Step 1: Document Overview
Read all source documents completely. For each, provide:
- Document length and structure
- Primary focus/angle
- Key strengths
- Notable gaps or limitations

### Step 2: Comparative Analysis
Based on the content you found in the documents, identify the relevant dimensions for comparison. These might include (but are not limited to):
- Research structure or framing
- Depth vs. breadth of coverage
- Quantified evidence (statistics, metrics, data)
- Direct quotes or testimonials
- Specific examples, scenarios, or case studies
- Number and quality of citations
- Vendor/competitor coverage
- Actionable recommendations
- Recency of information

Create a comparison matrix using the dimensions most relevant to these specific documents:

| Dimension | Document 1 | Document 2 | Best Source |
|-----------|------------|------------|-------------|
| [AI determines relevant dimensions] | | | |

For each dimension, briefly note what each document offers and which source is stronger.

### Step 3: Content Extraction
Identify what to preserve from each document:

**From Document 1, keep:**
- [List specific sections, data points, frameworks worth preserving]

**From Document 2, keep:**
- [List specific sections, data points, frameworks worth preserving]

**Conflicts to resolve:**
- [List any contradictions between sources and state your resolution approach—favor more specific evidence, more recent data, or better-cited claims]

**Gaps in both:**
- [List any missing elements neither document addresses adequately]

### Step 4: Proposed Merged Structure
Based on your analysis, propose a reorganized structure that:
- Leads with the strongest framing from either source
- Groups related content logically
- Eliminates redundancy
- Preserves all unique valuable content

Outline format:
1. [Section name] — Source: [which document(s)]
2. [Section name] — Source: [which document(s)]
3. ...

Present this outline and confirm with the user before proceeding, OR proceed directly if user has specified to complete in one pass.

### Step 5: Create Merged Document
Produce the final merged document following these rules:

**Content rules:**
- Use the strongest version of any duplicated content
- Preserve all unique valuable content from both sources
- Maintain consistent voice and terminology throughout
- When sources conflict, favor: (1) more specific/cited evidence, (2) more recent data, (3) primary sources over secondary

**Citation rules:**
- Add inline citation numbers [1], [2], etc. for all:
  - Statistics, metrics, and quantified claims
  - Direct quotes from people or organizations
  - Specific vendor/product claims
  - Research findings or study results
- Create a "Key Statistics Reference" table at the end summarizing major data points and their sources
- Include a numbered references section with full URLs where available

**Formatting rules:**
- Use consistent heading hierarchy (H1 for title, H2 for major sections, H3 for subsections)
- Standardize all table formats
- Ensure all lists use parallel structure
- Use consistent terminology (create a terminology decision if sources use different terms for same concept)

## Output Format
[Specify: Markdown for Notion, Word document (.docx), PDF, or other]

## Quality Checklist
Before delivering, verify:
- [ ] All statistics and quantified claims have inline citations
- [ ] All citations map to numbered references at the end
- [ ] No valuable content from either source was lost
- [ ] Consistent terminology throughout
- [ ] No redundant or repeated sections
- [ ] Logical flow between sections
- [ ] Executive summary (if present) reflects the merged content accurately

## Optional Context
[Add any additional context that may help, such as:]
- Target audience for the merged document
- Intended use (internal strategy, executive presentation, published research, etc.)
- Any specific sections or topics to prioritize
- Content to explicitly exclude