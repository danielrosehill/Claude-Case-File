# Claude Legal Case File - System Instructions

## Purpose

This repository is a **Claude Space** designed for legal case management. It provides a structured, version-controlled workspace for organizing litigation materials, evidence, correspondence, and legal analysis using Claude Code as an intelligent assistant.

## Case Information

<!-- This section will be populated by the /onboard command -->

**Case Name**: [Not yet configured - run /onboard]
**Case Number**: [Not yet configured]
**Jurisdiction**: [Not yet configured]
**Case Type**: [Not yet configured]
**User Role**: [Plaintiff/Defendant/Counsel/Other]

### Parties

**Your Side**:
- [To be configured]

**Opposing Side**:
- [To be configured]

### Counsel

**Your Counsel**:
- [To be configured]

**Opposing Counsel**:
- [To be configured]

---

## Repository Structure

```
Claude-Case-File/
├── CLAUDE.md                 # This file - case context and instructions
├── .claude/
│   ├── commands/             # Slash commands for legal workflows
│   └── agents/               # Specialized legal task agents
├── context/                  # Background materials and reference docs
├── evidence/
│   ├── exhibits/             # Numbered exhibits for court
│   ├── digital-forensics/    # Digital evidence with chain of custody
│   └── checksums/            # SHA-256 hashes for evidence integrity
├── documents/
│   ├── contracts/            # Relevant contracts and agreements
│   ├── correspondence/       # Letters, emails (non-court)
│   ├── court-filings/        # Documents filed with the court
│   ├── pleadings/            # Complaints, answers, counterclaims
│   ├── discovery/            # Discovery requests and responses
│   └── motions/              # Motions and supporting documents
├── parties/
│   ├── counsel/              # Attorney information and contacts
│   ├── witnesses/            # Witness information and statements
│   └── experts/              # Expert witness information
├── timeline/                 # Chronological case timeline
├── analysis/                 # Legal analysis and research
├── work-product/             # Attorney work product (privileged)
└── templates/                # Document templates
```

## Working with Evidence

### Evidence Integrity Protocol

All evidence files MUST have corresponding SHA-256 checksums stored in `evidence/checksums/`. When adding evidence:

1. Place the file in the appropriate evidence subfolder
2. Generate a checksum: `sha256sum filename > evidence/checksums/filename.sha256`
3. Log the addition in `evidence/evidence-log.md`

### Evidence Numbering Convention

- **Exhibits**: `EX-[NUMBER]-[SHORT_DESCRIPTION].[ext]`
  - Example: `EX-001-contract-signed.pdf`
- **Digital Forensics**: `DF-[NUMBER]-[SOURCE]-[DATE].[ext]`
  - Example: `DF-003-email-export-2024-01-15.mbox`

### Chain of Custody

For digital evidence, maintain chain of custody documentation in `evidence/digital-forensics/custody-log.md`.

## Document Naming Conventions

Use consistent naming for all documents:

- **Court filings**: `[DATE]-[TYPE]-[DESCRIPTION].pdf`
  - Example: `2024-01-15-motion-summary-judgment.pdf`
- **Correspondence**: `[DATE]-[FROM]-[TO]-[SUBJECT].pdf`
  - Example: `2024-01-10-jones-smith-settlement-offer.pdf`
- **Contracts**: `[DATE]-[PARTIES]-[TYPE].pdf`
  - Example: `2023-06-01-acme-user-service-agreement.pdf`

## Key Dates and Deadlines

<!-- Populate this section with critical dates -->

| Date | Event | Status |
|------|-------|--------|
| [TBD] | [Event] | [Pending/Complete] |

## Legal Standards Disclaimer

**IMPORTANT**: Claude is an AI assistant and cannot provide legal advice. All analysis, document preparation, and recommendations should be reviewed by qualified legal counsel before use in any legal proceeding.

This workspace is designed to help organize and analyze materials, not to replace professional legal judgment.

## Confidentiality Notice

This repository may contain privileged attorney-client communications and attorney work product. Unauthorized access, disclosure, or distribution is prohibited.

## Available Commands

Run these slash commands for common workflows:

- `/onboard` - Initial case setup and intake interview
- `/add-evidence` - Add new evidence with proper checksums
- `/verify-evidence` - Verify integrity of all evidence files
- `/legal-analysis` - Request analysis of legal issues
- `/prepare-document` - Prepare documents for legal team
- `/timeline-update` - Add or update timeline events
- `/case-summary` - Generate current case summary
- `/export-bundle` - Create document bundle for counsel

## Working Preferences

When operating in this legal case workspace:

1. **Be meticulous** - Legal work requires precision; double-check all references
2. **Cite sources** - When referencing documents, provide exact locations
3. **Preserve originals** - Never modify original evidence files
4. **Track changes** - Use git commits to document all modifications
5. **Maintain privilege** - Flag potentially privileged materials
6. **Note deadlines** - Highlight any deadline-sensitive matters

## Integration Suggestions

Consider configuring these MCP servers for enhanced functionality:

- **S3 MCP** - Secure cloud backup for evidence
- **Filesystem MCP** - Enhanced file operations
- **Memory MCP** - Persistent case context across sessions
- **PDF MCP** - Document processing and extraction
