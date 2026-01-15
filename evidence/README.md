# Evidence Directory

This directory contains all evidence materials for the case with proper integrity verification.

## Structure

```
evidence/
├── exhibits/           # Numbered exhibits for court submission
├── digital-forensics/  # Digital evidence with chain of custody
└── checksums/          # SHA-256 verification hashes
```

## Evidence Integrity Protocol

### Adding New Evidence

1. **Place the file** in the appropriate subdirectory
2. **Generate checksum**:
   ```bash
   sha256sum evidence/exhibits/EX-001-filename.pdf > evidence/checksums/EX-001-filename.pdf.sha256
   ```
3. **Log the addition** in `evidence-log.md`
4. **Commit with descriptive message**

### Verifying Evidence

Run the `/verify-evidence` command or manually:
```bash
cd evidence && sha256sum -c checksums/*.sha256
```

## Naming Conventions

### Exhibits
Format: `EX-[NUMBER]-[SHORT_DESCRIPTION].[ext]`

Examples:
- `EX-001-signed-contract.pdf`
- `EX-002-email-thread-jan2024.pdf`
- `EX-003-photo-damage.jpg`

### Digital Forensics
Format: `DF-[NUMBER]-[SOURCE]-[DATE].[ext]`

Examples:
- `DF-001-server-logs-2024-01-15.txt`
- `DF-002-email-export-2024-02-01.mbox`
- `DF-003-database-snapshot-2024-01-20.sql`

## Chain of Custody

For digital evidence, document the chain of custody in `digital-forensics/custody-log.md`:

- Who collected the evidence
- When it was collected
- How it was preserved
- Any transformations or copies made
- Hash verification at each step

## Best Practices

1. **Never modify original files** - Work with copies if processing is needed
2. **Document everything** - Every action should be logged
3. **Verify regularly** - Run checksum verification before any court submission
4. **Secure storage** - Consider encrypted backups for sensitive evidence
5. **Metadata preservation** - Maintain original file metadata when possible
