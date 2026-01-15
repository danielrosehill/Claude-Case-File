# Export Document Bundle

You are creating a comprehensive export bundle for sharing with counsel or for case archive purposes.

## Arguments

- `$ARGUMENTS` - Optional: Type of export ("counsel", "archive", "discovery", "court")

## Process

### Step 1: Determine Export Type

If not specified, ask the user what type of export they need:

1. **Counsel Bundle**: Complete materials for legal team
2. **Archive Bundle**: Full case archive for records
3. **Discovery Bundle**: Documents for discovery production
4. **Court Bundle**: Exhibits and filings for court submission

### Step 2: Pre-Export Verification

Before creating any export:

1. **Verify all evidence checksums**
   - Run full verification
   - Report any failures
   - Do not include unverified evidence in exports

2. **Check for completeness**
   - Verify CLAUDE.md has case information
   - Check that key context files are populated
   - Identify any missing critical documents

3. **Privilege review reminder**
   - Alert user that exports may contain privileged material
   - Recommend privilege review before external sharing
   - Flag any documents marked as privileged

### Step 3: Create Export Structure

Create export in `work-product/exports/[date]-[type]/`:

**Counsel Bundle:**
```
export/
├── 00-INDEX.md
├── 01-case-summary/
│   ├── case-summary.md
│   └── timeline.md
├── 02-context/
│   ├── case-background.md
│   └── legal-framework.md
├── 03-evidence/
│   ├── exhibits/
│   ├── digital-forensics/
│   └── verification-report.md
├── 04-documents/
│   ├── contracts/
│   ├── correspondence/
│   ├── court-filings/
│   └── discovery/
├── 05-analysis/
│   └── [analysis files]
├── 06-parties/
│   ├── counsel-info.md
│   └── party-info.md
└── MANIFEST.md
```

**Archive Bundle:**
- Full copy of entire repository structure
- Git history export
- Complete verification report

**Discovery Bundle:**
- Only producible documents
- Bates numbering log
- Privilege log for withheld docs

**Court Bundle:**
- Numbered exhibits
- Proposed orders/filings
- Verification certificates

### Step 4: Generate Manifest

Create `MANIFEST.md` with:

```markdown
# Export Manifest

## Export Information
- Type: [Bundle type]
- Created: [Date/Time]
- Created by: [User or Claude]
- Case: [Case name and number]

## Contents Summary
- Total files: [Count]
- Total size: [Size]
- Evidence items: [Count]
- Documents: [Count]

## Verification Status
- Evidence verification: [PASSED/FAILED]
- Last verified: [Date]
- Failed items: [List if any]

## File List
[Complete list of all files in export]

## Notes
[Any special notes about this export]

## Confidentiality Notice
This export contains confidential and potentially privileged
materials. Unauthorized distribution is prohibited.
```

### Step 5: Export Options

Ask about export preferences:
- **Format**: Directory structure, ZIP archive, or both
- **Checksums**: Include verification files
- **Redactions**: Any documents needing redaction
- **Password protection**: For sensitive exports

### Step 6: Create Export

1. Create the export directory structure
2. Copy all relevant files
3. Generate the index and manifest
4. Verify copied files
5. Create ZIP if requested
6. Generate final report

### Step 7: Post-Export

Provide:
- Location of export bundle
- Summary of contents
- Verification status
- Recommendations for sharing/transmitting
- Reminder about confidentiality

## Security Reminders

- Recommend encrypted transmission for sensitive exports
- Suggest password protection for ZIP archives
- Remind about secure deletion after transmission
- Note any cloud upload considerations
