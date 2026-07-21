# Knowledge-base page templates

Create these pages in the chosen destination, populated with the user's answers. Use placeholders like `{student name}` only as prompts — replace them with real values or a clearly labeled "TBD — confirm". Keep the **Dashboard** as the authoritative snapshot; the other pages hold the detail.

## Storage mapping

- **Local Markdown files (default):** one `.md` file per page, in the folder the user chose.
- **`~~knowledge base` connector (Confluence / Notion / Google Drive / SharePoint):** one page/doc per template, created via that tool's connector. Keep the same titles and section structure.

Use identical section headings regardless of destination so pages stay portable.

## Pages

### Dashboard
Authoritative snapshot. Sections:
- **Student overview** — name, school, program, term system, class standing, credits (done / in progress / total), expected graduation, enrollment status.
- **Funding snapshot** — each source with status; current-term balance broken into who-covers-what; out-of-pocket.
- **Action items** — top items with owner, due date, status.
- **Risks** — active risks with severity and mitigation.
- **Upcoming deadlines** — soonest first.
- **Quick links** — to the other pages.

### Student Profile
Personal and identity facts used on forms: names (label legal vs. preferred), IDs, contact, enrollment status, access/records status (e.g., whether a supporter has been granted access), and any sponsor/benefit identity details. Note known-variation quirks (e.g., a name that appears differently on a legacy record) rather than treating them as errors.

### Funding Plan
The full funding strategy. Sections:
- **Funding sources** — the registry (schema from `funding-sources.md`): label, type, covers, cadence, amount, application/renewal, constraints, priority, risks.
- **Allocation strategy** — spend order and rationale.
- **Accounts of record** — where money sits (savings/checking), who controls it, last-4/label only.
- **Finite-benefit tracking** — consumption vs. remaining, projected exhaustion or expiration.

### Semester Funding Plan
Term-by-term model. For each term: cost buckets (tuition, fees, housing, dining, books, transportation, discretionary), which source covers each, out-of-pocket, and payment due dates. Include an **actuals** section when a real bill has been ingested, separate from projections.

### Academic Plan
Program requirements and course plan. Sections: degree/program summary, requirement buckets (general-education/core, major core, electives, milestones), a term-by-term course plan, and notes/advising contacts. Populate from a degree audit when available.

### Degree Progress
Credit and GPA tracking. Credit summary (done / in progress / remaining), progress by requirement category, per-term GPA tracker, and alerts (e.g., enrollment-minimum for a benefit, requirement gaps).

### Deadlines & Milestones
All key dates in one place: aid applications/renewals, registration, payment due dates, benefit certifications, housing, plus recurring ones. Mark which have reminders set.

### Documents & Resources
A document tracker (what's received / needed) and key references: contacts (aid office, benefit administrator, registrar, advisor), links, and identity/account records (labels and last-4 only — never full sensitive numbers). Note where original PDFs are stored.

### Notes & Check-ins
A running log: dated session entries (topic, notes, follow-ups, status), a decisions log with rationale, and the open follow-up list used as the working task list.

## Populating rules

- Fill every field you can from the questionnaire; mark the rest "TBD — confirm" and list them as data gaps.
- Store only labels and last-4 for anything sensitive.
- Keep the Dashboard consistent with the detail pages after every update.
