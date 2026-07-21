# Connectors

## How tool references work

Plugin files use `~~category` as a placeholder for whatever tool you connect in that
category. The plugin is tool-agnostic — it describes workflows in terms of categories
rather than specific products, so it works the same whether you store things in
Confluence or Notion, or remind yourself via Google or Outlook.

## Connectors for this plugin

| Category         | Placeholder        | Options / notes                                                                 |
| ---------------- | ------------------ | ------------------------------------------------------------------------------- |
| Knowledge base   | `~~knowledge base` | **Local Markdown files (default — no connection needed)**, Confluence, Notion, Google Drive, SharePoint |
| Calendar         | `~~calendar`       | Google Calendar, Outlook/Microsoft 365 (used only for optional reminders)       |

## Complementary connectors (optional)

No skill requires these, but they feed the same workflows from places the student already works — so updates flow in without portal-diving:

- **Canvas LMS** — assignment deadlines, grades, and course schedules feed straight into
  `check-in` and **Deadlines & Milestones**. There's no official Canvas connector in the
  [Claude connectors directory](https://claude.com/connectors) yet, but community MCP
  servers work well — e.g. [vishalsachdev/canvas-mcp](https://github.com/vishalsachdev/canvas-mcp)
  (broad; 80+ tools) or [mbcrosiersamuel/canvas-mcp](https://github.com/mbcrosiersamuel/canvas-mcp)
  (lightweight; assignments and deadlines). Both authenticate with a student-generated
  Canvas API token. If your school uses another LMS (Moodle, Brightspace), search the MCP
  ecosystem for it.
- **Email (Gmail or Outlook)** — award letters, bursar bills, and aid-office notices
  usually arrive by email. With an email connector, "log this" can pull the message or
  attachment directly into `ingest-document` instead of you re-downloading and uploading it.

> Community MCP servers are third-party code. Review what a server does and what scopes
> its API token grants before connecting it to a student account.

## Notes

- **The knowledge base defaults to local Markdown files** in a folder you choose. Nothing
  external is required to use College Launch. Pick a connected tool only if you want the
  knowledge base to live in a shared workspace.
- The `~~calendar` connector is optional — it's used only when you ask Claude to set
  reminders for deadlines. Without it, deadlines still live in the knowledge base and are
  surfaced during check-ins.
- Recurring "nudge" reminders (e.g., an annual heads-up before an aid renewal window) use
  Cowork's built-in scheduled tasks and need no external connector.
