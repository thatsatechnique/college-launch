# Example: a fully fictional student

This is synthetic sample data — **not a real person** — to show what a populated College Launch knowledge base looks like. It deliberately uses a different shape from any one family: a **single guardian**, a **quarter-system** school, and a **mixed aid stack** (grant + scholarship + savings + work-study + one contributor), with **no veteran benefits**. Any funding mix and any household size works the same way.

## Onboarding answers (what the questionnaire captured)

- **Student:** Alex Rivera. School: Riverbend State University. Program: Environmental Science (BS).
- **Term system:** quarters (fall/winter/spring funded; ~15 credits/term target, full-time).
- **Start / graduation:** Fall 2026 → Spring 2030.
- **Housing:** on-campus, standard meal plan.
- **Storage:** local Markdown files in a folder.
- **Reminders:** Google Calendar; guardian receives them.

## Funding sources

| Label | type | covers | cadence | amount | application | constraints / risks | priority |
|-------|------|--------|---------|--------|-------------|---------------------|----------|
| Federal Pell Grant | grant | tuition, fees | annual | ~$4,000/yr | FAFSA each year | need-based; enrollment intensity affects amount; **renew via FAFSA** | 1 |
| Riverbend Merit Scholarship | scholarship | tuition | annual | $6,000/yr | auto-renew | requires **3.0 GPA + full-time**; 4-year cap | 2 |
| Rivera 529 plan | savings | tuition, fees, housing, books | flexible | ~$22,000 balance | — | qualified-expense rules; non-qualified withdrawal = tax + penalty | 4 |
| Federal Work-Study | employment | discretionary | monthly | up to $2,500/yr | accept award; find campus job | **paid to student, not the bill**; hours-capped | — |
| Guardian contribution | contribution | housing, dining (gap after aid) | per-term | committed | — | validate each spring; single guardian — no backstop noted yet | 3 |

**Allocation preference:** grants → scholarship → guardian gap → 529 last; keep work-study as student income.

## Contributors

- **Guardian (parent).** Commits to the housing + dining gap after aid. Paid directly to the school. Validate each spring before the housing deadline. *(Single contributor — flag as a funding risk with no secondary backstop; revisit if circumstances change.)*

## What a first funding pass looks like (illustrative Fall 2026 quarter)

| Bucket | Amount | Covered by |
|--------|--------|-----------|
| Tuition | $3,300 | Pell + Merit Scholarship |
| Mandatory fees | $450 | Pell (remainder) → 529 |
| Housing | $3,600 | Guardian contribution |
| Dining | $1,500 | Guardian contribution |
| Books/supplies | $400 | 529 |
| **Out-of-pocket (family)** | **~$0** | Guardian's gap is a contribution, not zero — it is a real, separate obligation |

Work-study (~$275/mo) is tracked as **student income**, not applied to the bill.

## Risks flagged

- **FAFSA renewal** each year — miss it and Pell drops. → annual reminder.
- **Scholarship condition:** 3.0 GPA + full-time. → watch GPA and credit load each term.
- **Single-contributor dependency:** the guardian's gap has no secondary backstop. → note; revisit if income changes.
- **529 qualified-use:** keep withdrawals to qualified expenses to avoid tax/penalty.

## Deadlines seeded

- Fall term payment due — before term start.
- FAFSA opens (annual) — recurring reminder.
- Housing renewal / contribution validation — each spring.

> Replace all of the above with real onboarding answers via the `onboard` skill. This file exists only so the plugin demonstrates end-to-end with zero setup and zero personal data.
