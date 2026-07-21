# Funding sources — schema, presets, and supporters

The funding model is a small registry. Every source — grant, scholarship, loan, savings plan, benefit, job, or family money — is described with the **same fields**, so the allocation logic can treat them uniformly.

## Funding-source schema

Capture each source with:

- **label** — human name ("Pell Grant", "Grandma's contribution", "Ch. 35 DEA").
- **type** — one of: `grant`, `scholarship`, `savings`, `benefit`, `loan`, `contribution`, `employment`.
- **covers** — which cost buckets it can pay: any of `tuition`, `fees`, `housing`, `dining`, `books`, `transportation`, `discretionary`, or `any`.
- **cadence** — `per-term`, `annual`, `monthly`, or `one-time`.
- **amount** — per-cadence amount or balance (confirmed value, or a labeled estimate).
- **application** — is action required each term/year? deadline rule? form or link? (e.g., "FAFSA each year", "re-certify each semester").
- **constraints** — any of: finite total (units/months/dollars), enrollment minimum (e.g., ≥12 credits), GPA minimum, income limits, age limit, delimiting/expiration date, tax treatment, refund/return rules.
- **priority** — integer allocation order (lower = spend first). Set from the user's preferred order.
- **risks** — what to watch (runs out, renewal missed, threshold slips, penalty on misuse).
- **notes** — anything else, including who controls/administers it.

## Preset library

Use these as starting points; confirm the specifics with the user or their documents.

| Preset | type | typical covers | cadence | key constraints / risks |
|--------|------|----------------|---------|-------------------------|
| Federal Pell Grant | grant | tuition, fees, any | annual | need-based; FAFSA each year; enrollment intensity affects amount |
| State grant | grant | tuition, fees | annual | residency + need; annual application; funds can be limited/first-come |
| Institutional / need grant | grant | tuition, fees | per-term/annual | set by school; may require FAFSA/CSS; renewal terms |
| Merit / departmental scholarship | scholarship | tuition, fees, any | annual | GPA/credit renewal conditions; may be fixed number of years |
| External / private scholarship | scholarship | any | one-time/annual | often one-time; may be paid to school or student; reapply |
| 529 plan | savings | tuition, fees, housing, books | flexible | qualified-expense rules; non-qualified withdrawal = tax + penalty |
| Coverdell ESA | savings | tuition, fees, books | flexible | contribution/age limits; qualified-expense rules |
| GI Bill (Post-9/11, Ch. 33) | benefit | tuition, housing allowance, books | per-term | finite months; certify each term; possible delimiting date |
| Dependents' assistance (Ch. 35 DEA) | benefit | stipend paid to student | monthly | finite months; monthly enrollment verification; enrollment-rate tiers |
| State veteran tuition waiver | benefit | tuition, fees | per-term | eligibility rules; apply each term; no retroactive grants |
| Federal subsidized loan | loan | any | per-term/annual | borrowing limits; interest terms; repayment obligation |
| Federal unsubsidized / PLUS loan | loan | any | per-term/annual | interest accrues; credit check (PLUS); repayment |
| Private loan | loan | any | as arranged | rates/terms vary; cosigner; repayment |
| Work-study | employment | discretionary | monthly | award cap; hours; earnings arrive as paychecks, not a bill credit |
| Family / supporter contribution | contribution | as committed | per-term/annual/monthly | commitment can lapse — validate on a cadence |

> Presets are a floor, not a ceiling. Add any source the user names, using the schema.

## Benefit-specific cautions (when applicable)

- **Finite benefits** (GI Bill months, capped scholarships): track consumption and project when they run out relative to graduation. Flag if they'll expire unused or run short.
- **Certification / verification**: some benefits require action every term or month; a miss pauses payment. Put these on a recurring reminder.
- **Delimiting / expiration dates**: some benefits expire on a hard date regardless of remaining balance. Calendar it.
- **Direct-to-student vs. bill credit**: stipends and work-study pay the student, not the school bill — don't count them against tuition/fees in the allocation; track them separately (e.g., a savings or living-expense line).

## Supporter / contributor model

Contributors are `0..n`, each independent. Capture:

- **role** — free label (parent, guardian, grandparent, sponsor, student, other). No relationship between contributors is assumed.
- **commitment** — what they cover (a bucket like "room & board", a fixed amount, or "the gap after aid").
- **mechanism** — direct to school, reimbursement, shared account.
- **validation cadence** — when to re-confirm (e.g., each spring). A lapsed commitment is a funding risk — note the backstop if one exists.

Never encode assumptions about marital status, number of parents, or who pays. A single contributor, several, or none are all valid configurations.
