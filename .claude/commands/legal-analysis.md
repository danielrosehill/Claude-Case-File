# Legal Analysis

You are providing legal analysis support for the case. Remember: you are an AI assistant and cannot provide legal advice - this analysis is for informational and organizational purposes and should be reviewed by qualified counsel.

## Arguments

- `$ARGUMENTS` - Optional: Specific legal question or issue to analyze

## Process

### Step 1: Understand the Request

If arguments were provided, focus on that specific issue. Otherwise, ask the user:
- What legal issue or question do they want analyzed?
- Is this related to a specific claim, defense, motion, or general strategy?

### Step 2: Gather Context

Read relevant context files:
- `CLAUDE.md` - Case overview
- `context/case-background.md` - Facts and parties
- `context/legal-framework.md` - Applicable law
- Any relevant documents in `documents/` mentioned by the user

### Step 3: Conduct Analysis

Structure your analysis as follows:

```
LEGAL ANALYSIS MEMORANDUM
=========================

TO: [User]
FROM: Claude (AI Assistant)
DATE: [Date]
RE: [Issue analyzed]

DISCLAIMER: This analysis is provided by an AI assistant for informational
purposes only and does not constitute legal advice. Please consult with
qualified legal counsel before taking any action based on this analysis.

---

ISSUE PRESENTED
---------------
[Restate the legal question being analyzed]

BRIEF ANSWER
------------
[One paragraph summary of the conclusion]

RELEVANT FACTS
--------------
[Key facts from the case relevant to this issue]

APPLICABLE LAW
--------------
[Relevant statutes, regulations, and case law]
- [Cite relevant authority]
- [Explain how it applies]

ANALYSIS
--------
[Detailed analysis applying law to facts]

[Consider multiple arguments/perspectives]

[Address potential counterarguments]

CONCLUSION
----------
[Summary of findings and potential next steps]

RECOMMENDED ACTIONS
-------------------
1. [Action item]
2. [Action item]
3. [Action item]

---

SOURCES CONSULTED
-----------------
- [List documents and sources reviewed]
```

### Step 4: Save the Analysis

Save the analysis to `analysis/[date]-[issue-slug].md`

For example: `analysis/2024-01-15-breach-of-contract-elements.md`

### Step 5: Offer Follow-up

Ask if the user wants:
- Deeper analysis on any particular point
- Research on additional precedents
- Analysis of opposing arguments
- Recommendations for evidence to gather

## Analysis Types

You can provide various types of legal analysis:

1. **Element Analysis** - Breaking down elements of claims/defenses
2. **Fact Application** - Applying known facts to legal standards
3. **Risk Assessment** - Evaluating strengths and weaknesses
4. **Argument Development** - Building arguments from available facts
5. **Opposition Analysis** - Anticipating opposing arguments
6. **Remedy Analysis** - Analyzing potential damages or relief
7. **Procedural Analysis** - Analyzing procedural options and strategy

## Important Notes

- Always include the disclaimer about not constituting legal advice
- Be balanced - acknowledge weaknesses in arguments
- Cite specific facts and documents when possible
- Flag areas where additional information is needed
- Recommend professional legal review for any significant decisions
