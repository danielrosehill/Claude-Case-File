# Add Evidence

You are helping the user add evidence to the case file with proper integrity verification.

## Arguments

- `$ARGUMENTS` - Optional: Path to the file to add, or leave blank for interactive mode

## Process

### Step 1: Identify the Evidence

If a file path was provided in arguments, use that. Otherwise, ask the user:
- What file do they want to add as evidence?
- Where is the file currently located?

### Step 2: Classify the Evidence

Ask the user:
- **Type**: Is this an exhibit for court submission or digital forensic evidence?
  - Exhibits go in `evidence/exhibits/`
  - Digital forensics go in `evidence/digital-forensics/`
- **Description**: Brief description for the filename

### Step 3: Determine the Next Number

Check the appropriate directory for existing files and determine the next sequential number:
- For exhibits: `EX-[NEXT_NUMBER]`
- For digital forensics: `DF-[NEXT_NUMBER]`

### Step 4: Copy and Rename

Copy the file to the appropriate location with the proper naming convention:
- Exhibits: `EX-[NUMBER]-[description].[ext]`
- Digital forensics: `DF-[NUMBER]-[source]-[date].[ext]`

### Step 5: Generate Checksum

Generate a SHA-256 checksum for the evidence file:
```bash
sha256sum evidence/[type]/[filename] > evidence/checksums/[filename].sha256
```

### Step 6: Update Evidence Log

Add an entry to `evidence/evidence-log.md` with:
- ID
- Filename
- Date added (today)
- Source (ask user)
- SHA-256 Verified: ✓
- Added by (ask user or use "Claude")
- Notes (any relevant notes)

### Step 7: Chain of Custody (Digital Forensics Only)

If this is digital forensic evidence, prompt the user for chain of custody information and add an entry to `evidence/digital-forensics/custody-log.md`:
- Who collected it
- When and where
- How it was collected
- Any handling history

### Step 8: Confirm and Commit

- Show the user a summary of what was added
- Verify the checksum
- Offer to commit the changes to git with an appropriate message

## Important Reminders

- Never modify original evidence files
- Always verify checksums after copying
- Document the source of all evidence
- Treat all evidence as potentially discoverable
