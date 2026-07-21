# Contributing to College Launch

Thanks for helping other families get through the first-year-of-college chaos. The two highest-value contributions are **funding-source presets** (so more aid types work out of the box) and **knowledge-base adapters** (so more storage tools work). Both are designed to be added without touching the core skills.

## Ground rules

1. **No personal data, ever.** The repo ships templates, schemas, and one fully fictional example (`examples/synthetic-student.md`). Never commit a real name, ID, account number, balance, or document. `.gitignore` blocks the common cases — don't work around it.
2. **Model, don't advise.** Contributions may compute and surface trade-offs (preserve-vs-use, borrow-vs-pay) but must not recommend a specific loan, investment, or tax action. Keep the not-financial-advice framing intact.
3. **No household assumptions.** Contributors are `0..n` generic roles. Don't add logic that assumes two parents, a marital status, or who pays.
4. **Tool-agnostic language.** Reference external tools by category with the `~~` placeholder (`~~knowledge base`, `~~calendar`), not by product name, so the plugin stays portable. Update `CONNECTORS.md` if you add a category.

## Repo layout

```
college-launch/
├── .claude-plugin/plugin.json     # manifest
├── skills/                        # onboard, ingest-document, funding-plan, check-in
│   └── <skill>/SKILL.md (+ references/)
├── examples/                      # fictional sample data only
├── docs/                          # contributor guides (adapter authoring, etc.)
├── README.md  CONNECTORS.md  CONTRIBUTING.md  .gitignore
```

## Adding a funding-source preset

Funding sources all share one schema (see `skills/onboard/references/funding-sources.md`). To add a preset:

1. Add a row to the preset table with: `label`, `type`, `covers`, `cadence`, `application`, `constraints/risks`, and a sensible default `priority`.
2. If it introduces a new constraint the allocator should honor (a new threshold, a new expiration rule), document the check in `skills/funding-plan/references/allocation.md`.
3. Keep it descriptive and general — a category (e.g., "state grant"), not one state's exact program, unless the specificity is genuinely reusable.
4. If it changes how the money reaches the student (bill credit vs. paid-to-student), say so — the allocator treats those differently.

## Adding a knowledge-base adapter

See `docs/adapter-authoring.md`. In short: the skills read/write a small set of standard pages by title and section; an "adapter" is just the mapping of those operations onto a storage backend (local files or a `~~knowledge base` connector). You usually don't write code — you extend the storage-mapping notes so Claude knows how to create and update pages in that tool.

## Skill conventions

- Frontmatter `description` is third-person and names the trigger phrases users would actually say.
- Skill bodies are **instructions for Claude**, written imperatively — not documentation for the end user.
- Keep `SKILL.md` lean (under ~3,000 words); put detail in `references/`.
- Don't rename existing skills or the plugin.

## Testing a change

Run the plugin locally with `claude --plugin-dir .` from your clone (after edits, `/reload-plugins` picks them up without restarting), and exercise it against `examples/synthetic-student.md`:

- `onboard` should produce a full knowledge base from the example answers.
- `ingest-document` should update it from a (fictional) bill or award letter.
- `funding-plan` should allocate the example's mixed stack and flag its risks (FAFSA renewal, GPA/full-time condition, single-contributor dependency).
- `check-in` should surface the seeded deadlines.

If your change touches allocation or risk logic, confirm the example's flags still fire correctly.

## Submitting

Open a PR describing what you added and which of the four skills (if any) it affects. Small, focused PRs — one preset or one adapter at a time — are easiest to review.
