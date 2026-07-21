# Authoring a knowledge-base adapter

College Launch keeps its data in a **knowledge base** — a small, fixed set of pages. The skills never assume a particular storage tool; they work against a tiny logical interface. An "adapter" is the mapping of that interface onto one backend (local Markdown files, or a `~~knowledge base` connector like Confluence, Notion, Google Drive, or SharePoint).

You usually don't write code. You add a short storage-mapping note so Claude knows how to perform each operation in that tool.

## The logical interface

Every backend must support three operations:

| Operation | Meaning |
|-----------|---------|
| **list** | Enumerate the College Launch pages that exist. |
| **read(page)** | Return the current contents of a page by its standard title. |
| **write(page, content)** | Create the page if missing, or replace its contents if it exists. |

That's it. The skills read a page, change it, and write it back. There is no partial-patch requirement — replace-in-place is fine.

## The standard pages

Adapters must be able to create and update these page titles (structure in `skills/onboard/references/kb-templates.md`):

- Dashboard
- Student Profile
- Funding Plan
- Semester Funding Plan
- Academic Plan
- Degree Progress
- Deadlines & Milestones
- Documents & Resources
- Notes & Check-ins

Use the **same titles and section headings** across every backend so a family can move from one to another without losing structure.

## Reference adapter: local Markdown (the default)

- **list** → the `.md` files in the chosen folder.
- **read** → read the matching `.md` file.
- **write** → write/overwrite the matching `.md` file (`Dashboard.md`, `Funding Plan.md`, …).

No connector, no account. This is the baseline every other adapter should match in behavior.

## Adding a connector-backed adapter

For a `~~knowledge base` connector, document, in a short section (here or in `CONNECTORS.md`):

1. **Locating the space/parent.** How Claude finds or creates the container for these pages (a Confluence space + parent page, a Notion database/page, a Drive folder, a SharePoint site/library).
2. **Create vs. update.** Which connector tools create a new page and which replace an existing page's body. Note any ID that must be captured on create and reused on update.
3. **Formatting.** How the standard Markdown sections map to that tool's format (Confluence storage/ADF, Notion blocks, a Google Doc, a SharePoint page). Tables and headings must survive the round-trip.
4. **Titles.** Confirm the tool allows the standard page titles; if it forces a naming scheme, document the mapping.
5. **Idempotency.** Re-running `write` on an existing page must replace, not duplicate.

Keep the note short and operational — enough for Claude to perform list/read/write reliably in that tool.

## Checklist for a new adapter

- [ ] Can create all nine standard pages with the standard section headings.
- [ ] `read` then `write` round-trips content without losing tables or headings.
- [ ] `write` on an existing page replaces it (no duplicates).
- [ ] Sensitive values stay as labels / last-4 (never full account or ID numbers).
- [ ] Documented how to locate/create the container and how create-vs-update works.
- [ ] Verified against `examples/synthetic-student.md` end-to-end.

## Design notes

- Prefer **replace-in-place** semantics; the skills already reconcile the Dashboard against detail pages after each change.
- Don't invent extra pages — the nine standard titles are the contract. If a backend needs an index page, that's an implementation detail, not a new logical page.
- The `~~calendar` and scheduled-task reminders are **not** part of the knowledge-base adapter — they're separate and optional.
