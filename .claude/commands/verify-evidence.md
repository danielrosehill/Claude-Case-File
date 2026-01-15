# Verify Evidence Integrity

You are verifying the integrity of all evidence files in the case repository.

## Process

### Step 1: Locate All Checksums

Find all `.sha256` files in `evidence/checksums/`

### Step 2: Verify Each File

For each checksum file:
1. Read the expected hash
2. Locate the corresponding evidence file
3. Calculate the current SHA-256 hash
4. Compare the hashes

### Step 3: Report Results

Generate a verification report showing:

```
EVIDENCE INTEGRITY VERIFICATION REPORT
======================================
Date: [current date/time]

EXHIBITS:
---------
[✓] EX-001-filename.pdf - VERIFIED
[✓] EX-002-filename.pdf - VERIFIED
[✗] EX-003-filename.pdf - FAILED (hash mismatch)
[?] EX-004-filename.pdf - MISSING (no checksum found)

DIGITAL FORENSICS:
------------------
[✓] DF-001-filename.txt - VERIFIED
[✓] DF-002-filename.mbox - VERIFIED

SUMMARY:
--------
Total files: X
Verified: X
Failed: X
Missing checksum: X
Missing file: X
```

### Step 4: Handle Issues

If any verification fails:
1. **Hash mismatch**: Alert the user immediately - this could indicate tampering or corruption
2. **Missing checksum**: Offer to generate a checksum (but warn that this doesn't verify original integrity)
3. **Missing file**: Alert the user that evidence is missing from the expected location

### Step 5: Update Verification Log

Add an entry to the verification history in `evidence/evidence-log.md`:
- Date of verification
- Who ran the verification
- Result summary
- Any notes about issues found

## Critical Warnings

If any evidence fails verification:
- DO NOT proceed with court submissions until resolved
- Document the discrepancy immediately
- Advise the user to consult with counsel about the implications

## Output

Provide the full verification report and any recommendations for addressing issues.
