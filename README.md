[![Claude Code Repos Index](https://img.shields.io/badge/Claude%20Code%20Repos-Index-blue?style=flat-square&logo=github)](https://github.com/danielrosehill/Claude-Code-Repos-Index)

# Claude Legal Case File

A **Claude Space** template for managing legal cases using Claude Code as an intelligent workspace assistant.

## Overview

This repository provides a structured, version-controlled workspace for organizing litigation materials, evidence, correspondence, and legal analysis. It leverages Claude Code's capabilities to assist with document management, evidence integrity verification, legal analysis support, and case organization.

Based on the [Claude Spaces Model](https://github.com/danielrosehill/Claude-Spaces-Model) - an approach to using Claude Code workspaces for non-traditional development workflows.

## Features

- **Evidence Management** with SHA-256 checksums and chain of custody tracking
- **Document Organization** by type (contracts, correspondence, court filings, discovery)
- **Timeline Building** with chronological event tracking
- **Legal Analysis Support** through structured analysis frameworks
- **Privilege Review** flagging and logging
- **Document Bundle Preparation** for counsel and court submissions
- **Automated Workflows** via slash commands

## Quick Start

### 1. Clone or Copy This Template

```bash
# Clone the template
git clone https://github.com/yourusername/Claude-Case-File.git my-case-name
cd my-case-name

# Remove git history to start fresh
rm -rf .git
git init
```

### 2. Run the Onboarding Command

Open Claude Code in the repository and run:

```
/onboard
```

This will guide you through setting up the case file with:
- Case name and number
- Party information
- Counsel details
- Jurisdiction
- Key dates

### 3. Start Adding Materials

- Add evidence: `/add-evidence`
- Update timeline: `/timeline-update`
- Generate analysis: `/legal-analysis`

## Directory Structure

```
Claude-Case-File/
├── CLAUDE.md                 # Case context and instructions
├── .claude/
│   ├── commands/             # Slash commands
│   │   ├── onboard.md        # Initial case setup
│   │   ├── add-evidence.md   # Add evidence with checksums
│   │   ├── verify-evidence.md # Verify evidence integrity
│   │   ├── legal-analysis.md # Legal analysis support
│   │   ├── prepare-document.md # Document bundle prep
│   │   ├── timeline-update.md # Timeline management
│   │   ├── case-summary.md   # Generate case summary
│   │   └── export-bundle.md  # Export for counsel
│   └── agents/               # Specialized agents
│       ├── evidence-analyst.md
│       ├── document-drafter.md
│       ├── research-assistant.md
│       ├── timeline-builder.md
│       └── privilege-reviewer.md
├── context/                  # Background materials
├── evidence/
│   ├── exhibits/             # Numbered exhibits
│   ├── digital-forensics/    # Digital evidence
│   └── checksums/            # SHA-256 verification
├── documents/
│   ├── contracts/
│   ├── correspondence/
│   ├── court-filings/
│   ├── pleadings/
│   ├── discovery/
│   └── motions/
├── parties/
│   ├── counsel/
│   ├── witnesses/
│   └── experts/
├── timeline/                 # Case timeline
├── analysis/                 # Legal analysis
├── work-product/             # Privileged materials
├── templates/                # Document templates
└── docs/
    └── recommended-mcps.md   # MCP recommendations
```

## Available Commands

| Command | Description |
|---------|-------------|
| `/onboard` | Initial case setup and intake interview |
| `/add-evidence` | Add evidence with checksums and logging |
| `/verify-evidence` | Verify integrity of all evidence files |
| `/legal-analysis` | Generate legal analysis memoranda |
| `/prepare-document` | Prepare document bundles |
| `/timeline-update` | Add or view timeline events |
| `/case-summary` | Generate case status summary |
| `/export-bundle` | Create export packages |

## Evidence Integrity

All evidence files are tracked with SHA-256 checksums to ensure integrity:

```bash
# Add evidence (via command)
/add-evidence path/to/file.pdf

# Verify all evidence
/verify-evidence

# Manual verification
sha256sum -c evidence/checksums/*.sha256
```

## Recommended MCPs

Enhance functionality with these MCP servers:

- **Filesystem MCP** - Enhanced file operations
- **Memory MCP** - Persistent context
- **S3 MCP** - Secure cloud backup
- **PDF MCP** - Document processing

See [docs/recommended-mcps.md](docs/recommended-mcps.md) for full recommendations.

## Security & Confidentiality

This workspace may contain:
- Attorney-client privileged communications
- Attorney work product
- Sensitive evidence
- Personal information

**Recommendations**:
- Use private repositories
- Enable encryption at rest
- Control access carefully
- Review before any external sharing

## Disclaimer

**This workspace and its tools do not constitute legal advice.**

Claude is an AI assistant that cannot practice law. All analysis, document drafts, and recommendations must be reviewed by qualified legal counsel before use in any legal proceeding.

This template is designed to help organize and analyze materials, not to replace professional legal judgment.

## License

MIT License - See LICENSE file.

## Contributing

Contributions welcome! Please submit issues and pull requests for:
- New slash commands
- Template improvements
- Documentation updates
- Bug fixes

## Acknowledgments

Based on the [Claude Spaces Model](https://github.com/danielrosehill/Claude-Spaces-Model) by Daniel Rosehill.

---

For more Claude Code projects, visit my [Claude Code Repos Index](https://github.com/danielrosehill/Claude-Code-Repos-Index).
