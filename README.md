# College Launch

An AI copilot for the operational and financial chaos of a student's **first year of college** — and the years after.

It gives a student and the people supporting them one place to answer: *What's due? What's it going to cost? Who's paying which part? What did we decide, and what's coming next?* Claude runs an onboarding questionnaire, reads the documents you drop in (aid award letters, tuition bills, benefit certificates, degree audits, class schedules), keeps a structured knowledge base up to date, and surfaces deadlines and risks before they bite.

It is **aid-agnostic** (grants, scholarships, loans, 529/ESA, veteran benefits, work-study, family contributions — any mix), **household-agnostic** (one supporter or several; no assumptions about family structure), and **tool-agnostic** for storage (plain Markdown files by default, or Confluence / Notion / Google Drive / SharePoint).

## What it does

- **Onboards** a new student in a guided questionnaire and seeds a knowledge base from templates.
- **Ingests documents** — parses an aid letter, a bill, a benefit certificate, a degree audit, or a class schedule and updates the plan.
- **Builds a funding plan** — allocates whatever aid and contributions you have across each term's costs, computes out-of-pocket, and flags risks (a finite benefit running out, a scholarship renewal window, a credit-load threshold, a payment due date).
- **Runs check-ins** — surfaces the top action items and nearest deadlines, and offers to set calendar reminders and recurring nudges.

## Skills

| Skill | Use it when |
|-------|-------------|
| `onboard` | Setting things up for the first time — a guided intake that creates the knowledge base. |
| `ingest-document` | You have a college document (award letter, bill, benefit certificate, degree audit, schedule) to capture. |
| `funding-plan` | You want to build or refresh how a term is paid for, or check out-of-pocket / shortfall risk. |
| `check-in` | A quick "what's due / where are we / anything I'm missing," with optional reminders. |

## Quickstart

1. Install the plugin in Cowork.
2. Say **"onboard"** (or "set up college planning"). Claude will ask a short set of questions and build your knowledge base.
3. As things arrive, drop documents into the chat and say **"log this"** — the plan stays current.
4. Say **"college check-in"** any time for status and upcoming deadlines.

By default, everything is stored as Markdown files in a folder you choose. If you'd rather keep it in Confluence, Notion, Google Drive, or SharePoint, tell Claude during onboarding and connect that tool — see `CONNECTORS.md`.

## Privacy

This plugin ships with **no personal data** — only templates, schemas, and one fully fictional example student. Your real information lives only in your chosen knowledge base, never in the plugin itself.

## Not financial or legal advice

College Launch models and surfaces trade-offs so you can decide with the full picture in front of you. It does not recommend specific loans, investments, or tax moves. For decisions with financial or legal consequences, confirm with the aid office, benefit administrator, or a qualified advisor.

## License

MIT — see [LICENSE](LICENSE). Contributions welcome, especially new funding-source presets and knowledge-base adapters.
