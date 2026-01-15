# Case Summary

You are generating a comprehensive summary of the current state of the case.

## Arguments

- `$ARGUMENTS` - Optional: "brief" for short summary, "full" for comprehensive, or specific aspect to summarize

## Process

### Step 1: Gather Information

Read all relevant context files:
- `CLAUDE.md` - Case configuration
- `context/case-background.md` - Background
- `context/legal-framework.md` - Legal context
- `timeline/events.md` - Timeline
- `analysis/` - Any existing analyses

Also inventory:
- Number of exhibits in `evidence/exhibits/`
- Number of documents in `documents/` subdirectories
- Any pending items or issues noted

### Step 2: Generate Summary

**For Brief Summary:**

```
CASE SUMMARY (BRIEF)
====================

Case: [Name] | No: [Number]
Court: [Court]
Stage: [Current stage]

PARTIES:
Plaintiff: [Name]
Defendant: [Name]

STATUS: [One sentence current status]

NEXT DEADLINE: [Date] - [Description]

KEY ISSUES:
1. [Issue]
2. [Issue]
```

**For Full Summary:**

```
CASE SUMMARY
============

Generated: [Date]

CASE IDENTIFICATION
-------------------
Case Name: [Name]
Case Number: [Number]
Court: [Court]
Judge: [If assigned]
Your Role: [Role]

PARTIES
-------
Plaintiff(s):
  - [Name] ([Represented by])

Defendant(s):
  - [Name] ([Represented by])

CASE OVERVIEW
-------------
[2-3 paragraph summary of the case, dispute, and key issues]

PROCEDURAL STATUS
-----------------
Current Stage: [Stage]
Filed: [Date]
Last Activity: [Description]

UPCOMING DEADLINES
------------------
| Date | Item | Status |
|------|------|--------|
| [Date] | [Item] | [Pending/Complete] |

KEY TIMELINE
------------
[Condensed timeline of major events]

CLAIMS AND DEFENSES
-------------------
Claims:
1. [Claim] - [Status/Strength assessment]

Defenses:
1. [Defense] - [Status/Strength assessment]

EVIDENCE STATUS
---------------
Total Exhibits: [Count]
Digital Forensics Items: [Count]
Last Verification: [Date] - [Pass/Fail]

Key Evidence:
- [EX-XXX]: [Description and significance]
- [EX-XXX]: [Description and significance]

DOCUMENT STATUS
---------------
Court Filings: [Count]
Discovery Items: [Count]
Correspondence: [Count]

KEY DOCUMENTS:
- [Document]: [Significance]

OUTSTANDING ISSUES
------------------
1. [Issue needing attention]
2. [Issue needing attention]

RISK ASSESSMENT
---------------
Strengths:
- [Strength]

Weaknesses:
- [Weakness]

RECOMMENDED NEXT STEPS
----------------------
1. [Action item]
2. [Action item]
3. [Action item]
```

### Step 3: Save and Output

1. Display the summary to the user
2. Save to `work-product/summaries/[date]-case-summary.md`
3. Ask if they want any section expanded or if there are errors to correct

## Special Sections (If Requested)

Can also generate focused summaries on:
- **Evidence summary**: Just evidence status and inventory
- **Timeline summary**: Expanded timeline with all events
- **Deadline summary**: All pending deadlines and requirements
- **Party summary**: Detailed party and counsel information
- **Document summary**: Inventory of all documents

## Alerts

Always include alerts for:
- Deadlines in the next 14 days
- Evidence verification issues
- Incomplete information in critical fields
- Action items that appear overdue
