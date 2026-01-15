# Prepare Document Bundle

You are preparing documents for the legal team by compiling, organizing, and formatting materials from the case file.

## Arguments

- `$ARGUMENTS` - Optional: Type of bundle to prepare (e.g., "discovery response", "motion support", "counsel briefing")

## Process

### Step 1: Understand the Purpose

If arguments were provided, use that context. Otherwise, ask the user:
- What is this document bundle for?
  - Sending to counsel
  - Discovery response
  - Motion support
  - Court filing
  - Settlement negotiation
  - Client meeting
- Who is the intended audience?
- Are there specific documents to include?

### Step 2: Gather Materials

Based on the purpose, identify relevant materials:

**For Discovery Response:**
- Relevant documents from `documents/`
- Evidence from `evidence/exhibits/`
- Privilege log if applicable

**For Motion Support:**
- Relevant exhibits
- Supporting evidence
- Legal analysis from `analysis/`
- Relevant correspondence

**For Counsel Briefing:**
- Case background from `context/`
- Current status
- Key documents
- Timeline
- Outstanding issues

**For Court Filing:**
- Exhibits with proper numbering
- Evidence with verified checksums
- Supporting declarations

### Step 3: Create Document Index

Generate an index of included materials:

```
DOCUMENT BUNDLE INDEX
=====================

Prepared: [Date]
Purpose: [Purpose of bundle]
Prepared by: [User name or Claude]

CONTENTS:
---------

Tab A: Background Documents
    A-1: Case Background Summary
    A-2: Timeline of Events
    A-3: Party Information

Tab B: Evidence
    B-1: EX-001 - [Description]
    B-2: EX-002 - [Description]
    [etc.]

Tab C: Legal Analysis
    C-1: Analysis of [Issue]
    C-2: Analysis of [Issue]

Tab D: Correspondence
    D-1: [Date] - [Description]
    D-2: [Date] - [Description]

VERIFICATION:
-------------
All evidence files verified against checksums: [YES/NO]
Verification date: [Date]
```

### Step 4: Compile the Bundle

Create a compilation in `work-product/bundles/`:

1. Create a directory: `work-product/bundles/[date]-[purpose]/`
2. Copy relevant files (maintaining directory structure)
3. Generate the index as `INDEX.md`
4. Create a cover memo if appropriate

### Step 5: Generate Cover Memo (Optional)

If appropriate, create a cover memorandum:

```
MEMORANDUM
==========

TO: [Recipient]
FROM: [User]
DATE: [Date]
RE: Document Bundle - [Case Name]

Enclosed please find the following documents in connection with [purpose]:

[Summary of contents]

If you have any questions about these materials, please contact [user].

Attachments: See Index
```

### Step 6: Format Considerations

Ask about output format preferences:
- PDF compilation (single file)
- Individual files with index
- Specific formatting requirements
- Bates numbering needs
- Redaction requirements

### Step 7: Final Output

Provide:
- Location of the prepared bundle
- Summary of what was included
- Any items that were requested but not found
- Recommendations for additional materials to gather

## Special Considerations

### Privilege Review
- Flag any documents that may be privileged
- Do not include privileged materials without explicit confirmation
- Recommend privilege review before production

### Redaction
- Ask about redaction requirements
- Note any sensitive information that may need redaction
- Do not automatically redact - leave for human decision

### Evidence Integrity
- Always verify checksums before including evidence
- Note verification status in the index
- Alert if any evidence verification fails
