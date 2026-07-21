---
name: onboard
description: Use when setting up College Launch for the first time, or when the user says "onboard", "set up college planning", "get started with college launch", "start the questionnaire", or "help me plan for college". Runs a guided intake (student, school, term system, funding sources, supporters, where to store things, reminders), then creates a structured knowledge base from templates and populates it with the answers. Makes no assumptions about family structure or aid type.
---

# Onboard a new student

Set up a fresh College Launch knowledge base by interviewing the user, then creating the pages. Work in plain language — never mention file paths, schema fields, or placeholders to the user.

## Operating principles (apply in every College Launch skill)

- **Lead with the BLUF.** One-line bottom line first, then detail. No filler.
- **Read before you answer** anything data-dependent; **update the knowledge base immediately** after learning something new.
- **Surface risks and near deadlines proactively**, especially at the start of a session.
- **Never guess at money or dates** — use confirmed values or clearly label estimates.
- **Log decisions** with their rationale so future sessions inherit the context.
- **Model, don't advise.** Show the trade-offs and the math; let the user decide. This is not financial or legal advice.
- **No assumptions about household or aid.** There may be one supporter or several; any mix of grants, scholarships, loans, savings plans, benefits, work-study, or family money.

## Step 1 — Choose where the knowledge base lives

Ask where they want to keep everything. Default to **local Markdown files** in a folder (no external account needed). Offer `~~knowledge base` connectors (Confluence, Notion, Google Drive, SharePoint) if they prefer a shared workspace. Record the choice; use that destination for every page you create or update from now on. See `references/kb-templates.md` for how each destination maps.

## Step 2 — Run the questionnaire

Interview the user using `references/questionnaire.md`. Ask in small batches (2–4 related questions), not all at once. Skip anything they already told you. It's fine to leave fields as "TBD — confirm" and move on; flag them as data gaps at the end. Do **not** require sensitive numbers (SSNs, full account numbers) — last-4 or a label is enough.

Cover, at minimum: the student and school; the term system (semester/quarter) and expected graduation; **which funding sources apply and their key parameters** (use `references/funding-sources.md`); **supporters/contributors** (zero or more, each with a role and what they've committed); and reminder preferences.

## Step 3 — Seed the knowledge base

Create the standard pages from `references/kb-templates.md`, populated with the answers. At minimum create: **Dashboard**, **Student Profile**, **Funding Plan**, **Semester Funding Plan**, **Academic Plan**, **Degree Progress**, **Deadlines & Milestones**, **Documents & Resources**, and **Notes & Check-ins**. Keep the Dashboard as the authoritative snapshot.

Populate the funding sources and supporters exactly as captured. For any funding source, record what it covers, its cadence, its application/renewal rule, its constraints, and its risks (schema in `references/funding-sources.md`). Leave unknowns as clearly labeled TBDs.

## Step 4 — First funding pass and reminders

Run an initial allocation (see the `funding-plan` skill's logic) so the Dashboard shows a first cut of who covers what and any out-of-pocket. Then offer to set reminders for the nearest hard deadlines (via `~~calendar`) and any recurring windows such as annual aid renewals or benefit re-certifications (via scheduled tasks). Only set reminders the user approves.

## Step 5 — Wrap up

Give a BLUF summary: what was created, the top 3 action items, the nearest deadlines, and the data gaps still to fill. Log an onboarding entry in Notes & Check-ins.

## References

- `references/questionnaire.md` — the full intake question set.
- `references/kb-templates.md` — the knowledge-base page templates and how they map to each storage destination.
- `references/funding-sources.md` — the funding-source schema, the preset library, and the supporter/contributor model.
