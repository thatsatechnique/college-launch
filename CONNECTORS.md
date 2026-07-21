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

## Notes

- **The knowledge base defaults to local Markdown files** in a folder you choose. Nothing
  external is required to use College Launch. Pick a connected tool only if you want the
  knowledge base to live in a shared workspace.
- The `~~calendar` connector is optional — it's used only when you ask Claude to set
  reminders for deadlines. Without it, deadlines still live in the knowledge base and are
  surfaced during check-ins.
- Recurring "nudge" reminders (e.g., an annual heads-up before an aid renewal window) use
  Cowork's built-in scheduled tasks and need no external connector.
