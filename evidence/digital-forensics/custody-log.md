# Chain of Custody Log

This document maintains the chain of custody for all digital evidence.

## Purpose

Chain of custody documentation establishes that evidence has been properly collected, preserved, and handled to maintain its integrity and admissibility.

---

## Custody Entries

### Template Entry

```
## [Evidence ID]: [Brief Description]

**Original Collection**
- Collected by: [Name]
- Date/Time: [YYYY-MM-DD HH:MM]
- Location/Source: [Where collected from]
- Method: [How collected]
- Tool(s) used: [Software/hardware used]

**Original Hash**
- Algorithm: SHA-256
- Hash: [hash value]
- Verification date: [date]

**Storage Location**
- Current location: [path/location]
- Backup location: [if applicable]
- Access restrictions: [who can access]

**Handling History**
| Date | Action | By | Hash Verified | Notes |
|------|--------|-----|---------------|-------|
| [date] | [action] | [name] | [✓/✗] | [notes] |

**Notes**
[Any additional relevant information]

---
```

---

## Entries

<!-- Add custody entries below -->

---

## Verification Procedures

When verifying custody:

1. Confirm file location matches documented location
2. Verify SHA-256 hash matches original
3. Document verification in handling history
4. Note any discrepancies immediately

## Custody Transfer Protocol

When transferring evidence:

1. Verify hash before transfer
2. Document transfer method (encrypted USB, secure upload, etc.)
3. Verify hash after transfer
4. Both parties sign off on transfer
5. Update this log with transfer details
