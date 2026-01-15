# Timeline Update

You are managing the case timeline - adding, updating, or reviewing chronological events.

## Arguments

- `$ARGUMENTS` - Optional: "add", "review", or specific event to add

## Process

### Step 1: Determine Action

Based on arguments or user request:
- **Add**: Adding a new event to the timeline
- **Review**: Reviewing and displaying the current timeline
- **Update**: Modifying an existing event
- **Import**: Importing events from a document

### Step 2: Timeline Structure

The timeline is stored in `timeline/events.md` using this format:

```markdown
# Case Timeline

## [Year]

### [Month]

| Date | Event | Category | Source | Notes |
|------|-------|----------|--------|-------|
| YYYY-MM-DD | Description | [category] | [source doc] | [notes] |
```

**Categories:**
- `key-fact` - Important factual events
- `contract` - Contract-related events
- `communication` - Key communications
- `court` - Court dates and filings
- `discovery` - Discovery events
- `deadline` - Upcoming deadlines
- `other` - Other events

### Step 3: For Adding Events

Ask the user for:
- **Date**: When did this occur? (exact or approximate)
- **Description**: What happened?
- **Category**: What type of event is this?
- **Source**: Is this documented somewhere? (reference the document)
- **Notes**: Any additional context?

Then add to the appropriate section in `timeline/events.md`, maintaining chronological order.

### Step 4: For Reviewing Timeline

Generate a formatted view of the timeline:

```
CASE TIMELINE
=============

[Case Name]
Generated: [Date]

UPCOMING DEADLINES
------------------
⚠️  2024-02-15 - Discovery deadline
⚠️  2024-03-01 - Motion filing deadline

KEY EVENTS
----------
2023-01-15    Contract signed between parties
2023-06-20    First breach alleged
2023-08-10    Demand letter sent
2023-10-05    Complaint filed
2024-01-10    Answer filed

COURT DATES
-----------
2024-04-15    Status conference
2024-07-20    Trial date (tentative)
```

### Step 5: For Importing Events

If the user wants to import events from a document:
1. Read the specified document
2. Extract date-based events
3. Propose additions to the timeline
4. Confirm with user before adding

### Step 6: Visual Timeline (Optional)

Offer to generate a visual timeline in ASCII:

```
2023                                      2024
|                                         |
|--Jan-15: Contract signed                |
|                                         |
|--Jun-20: Breach alleged                 |
|                                         |
|--Aug-10: Demand letter                  |
|                                         |
|--Oct-05: Complaint filed                |
|                                         |--Jan-10: Answer filed
|                                         |
|                                         |--Feb-15: Discovery due ⚠️
|                                         |
|                                         |--Apr-15: Status conference
```

### Step 7: Deadline Alerts

When reviewing or updating, always check for:
- Deadlines in the next 30 days
- Overdue items
- Items without specific dates

Alert the user about any upcoming deadlines.

## Output

After any timeline operation:
1. Show the updated/relevant portion of the timeline
2. Note any upcoming deadlines
3. Offer to commit the changes if modifications were made
