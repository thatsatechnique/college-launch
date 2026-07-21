---
name: ingest-document
description: Use when the user shares a college document and wants it captured — an aid or scholarship award letter, a tuition or student-account bill, a veteran/benefit certificate of eligibility, a degree audit or academic-requirements report, or a class schedule. Also triggers on "log this bill", "here's their award letter", "update from this degree audit", "add this schedule", "capture this". Parses the document, extracts the relevant facts, updates the knowledge base and funding plan, and surfaces any new to-dos.
---

# Ingest a college document

Turn a document into knowledge-base updates. Read the document first; never guess values that aren't in it.

## Step 1 — Identify the document type

Common types and the fields that matter:

- **Aid / scholarship award letter** — source name, amount, period covered, what it applies to, conditions (GPA, credits), renewal/reapplication rule, whether paid to school or student.
- **Tuition / student-account bill** — each line item and amount, total, credits/anticipated aid, balance, and **due date(s)**. Separate charges into cost buckets (tuition, fees, housing, dining, books, transportation, discretionary).
- **Benefit certificate / eligibility letter** — benefit type, entitlement (months/amount), effective date, any delimiting/expiration date, payment method (to school vs. to student), verification cadence, and any file/reference number (record last-4 or label).
- **Degree audit / academic-requirements report** — program/major, requirement buckets and their status, which courses satisfy which requirement, credits earned/in-progress, and outstanding milestones.
- **Class schedule** — each course (code, title, credits, grading basis), meeting times, and the term dates; compute total credits and whether it meets the full-time / benefit threshold.

If the type is ambiguous, state your best read and confirm briefly before writing.

## Step 2 — Extract and reconcile

Pull the fields above. Cross-check against what's already in the knowledge base:

- Confirm or correct existing values (balances, dates, names). Flag genuine discrepancies rather than silently overwriting; if a mismatch has an innocent explanation (e.g., a legacy record variation), record it as a note, not an error.
- For a bill, map each line to a funding bucket and note which source is expected to cover it. **Remember stipends/work-study pay the student, not the bill** — don't net them against tuition.
- For a benefit certificate, record finite months, verification cadence, and any expiration date as tracked risks with reminders.

## Step 3 — Update the knowledge base

Update every affected page (see the onboarding `kb-templates.md` for structure), then reconcile the Dashboard:

- Award letter / benefit → **Funding Plan**, **Documents & Resources**, and the funding snapshot on the Dashboard.
- Bill → **Semester Funding Plan** (actuals), payment deadline into **Deadlines & Milestones**, Dashboard balance.
- Degree audit → **Academic Plan** and **Degree Progress** (map every course and requirement).
- Schedule → **Degree Progress** / **Academic Plan** and confirm the credit total meets any enrollment threshold.

Then re-run the allocation (see the `funding-plan` skill) so out-of-pocket and risks reflect the new facts. Log a dated entry in **Notes & Check-ins**.

## Step 4 — Report

BLUF: what changed, any new action items (with owners and due dates), any new risks, and any data still missing. Keep sensitive numbers to last-4 or labels.
