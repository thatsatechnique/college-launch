---
name: check-in
description: Use for a status check on the college plan — "college check-in", "what's due", "where are we", "anything I'm missing", "what's coming up". Reads the knowledge base and surfaces the top action items, the nearest deadlines, and any data gaps, then offers to set calendar reminders and recurring nudges for time-sensitive items. Good as a session opener.
---

# Run a check-in

Give a fast, current status from the knowledge base. Read the Dashboard, Deadlines & Milestones, and Notes & Check-ins first.

## Step 1 — Surface the state

BLUF, then:

- **Top 3 action items** — owner, what, due.
- **Nearest deadlines** — soonest first, with how close they are.
- **Data gaps** — anything marked "TBD — confirm" that's now blocking or overdue.
- **Active risks** worth re-flagging (a finite benefit, a renewal window, a payment date).

Keep it tight. Don't dump every field — highlight what needs attention.

## Step 2 — Offer reminders

For time-sensitive items without a reminder, offer to set them:

- **Fixed dates** (payment due, application deadline, registration) → a `~~calendar` event with advance alerts.
- **Recurring windows** (annual aid renewal, benefit re-certification, monthly enrollment verification, an annual permit or contribution validation) → a recurring scheduled task that fires ahead of time. For windows whose exact date shifts year to year, schedule the nudge early and have it confirm the current date from the source before reminding.

Only set what the user approves. Record which items have reminders in Deadlines & Milestones.

## Step 3 — Log

Add a dated check-in entry to Notes & Check-ins noting what was surfaced and any reminders set. Update the Dashboard if anything changed.
