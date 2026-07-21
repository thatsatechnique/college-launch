# Allocation logic and risk checks

## Cost buckets

Normalize every charge into: `tuition`, `fees`, `housing`, `dining`, `books`, `transportation`, `discretionary`. A bill's line items map into these; anything optional/elective (e.g., a sports pass) is `discretionary`.

## Allocation algorithm

1. **Sort** funding sources by `priority` ascending (lower = spend first). Use the user's stated preference; if none, a sensible default order is: benefits/waivers that don't consume a finite resource → grants → scholarships → committed contributions → savings → work-study/income → loans last.
2. **Exclude student-paid income** (stipends, work-study earnings) from covering the school bill — they arrive as payments to the student, not bill credits. Track them on a separate income/savings line.
3. **For each source in order**, apply its available `amount` to the buckets listed in `covers`, in a sensible bucket order (usually tuition → fees → housing → dining → books → transportation → discretionary), but only where the source is eligible and its constraints are satisfied (enrollment minimum met, within remaining finite balance, not past an expiration date, qualified-expense rules for savings plans).
4. **Track consumption** of finite sources (units/months/dollars remaining) as you go.
5. **After all sources**, apply contributor commitments to whatever they've committed to cover.
6. **Remaining = out-of-pocket.** Report the residual per bucket and in total. Distinguish out-of-pocket owed by the family from a separate contributor's obligation (e.g., a supporter covering room & board is a family contribution, not a zero — say so plainly).

Show the allocation as a small table: bucket → amount → source(s). Then the coverage summary: covered by aid/benefits, covered by contributions, out-of-pocket.

## Risk checks

Flag each that applies, with the action that resolves it:

- **Finite benefit runs short or expires unused.** Project consumption against graduation and any delimiting date. Surface both "will run short before graduation" and "months will expire unused" cases.
- **Renewal / reapplication window.** Grants and many scholarships require annual action (e.g., FAFSA); missing it drops the award. Note the window and set a reminder.
- **Benefit certification / verification.** Some benefits need per-term or monthly action or payment pauses. Recurring reminder.
- **Enrollment threshold.** Awards or benefit rates often require a minimum credit load (commonly full-time). Flag if the schedule is near or below it, and note that dropping below mid-term can create a repayment debt.
- **Payment due date.** A term balance is due on a date; a benefit hold may protect the tuition portion but not contributions or discretionary items. Call out what must be paid by when.
- **Contributor validation due.** A commitment that needs periodic re-confirmation is approaching its checkpoint; note the backstop if it lapses.
- **Savings misuse.** A savings-plan withdrawal for a non-qualified expense may trigger tax/penalty — flag before it happens.

## Projections

For future terms, apply a stated inflation assumption to costs (label it) and keep contributions/aid at known values unless the user gives escalators. Never present an estimate as a confirmed figure.

## Boundary

Present preserve-vs-use and borrow-vs-pay trade-offs with the math. Do **not** recommend a specific loan, investment, or tax action. Add: "This models the options; confirm consequential decisions with the aid office, benefit administrator, or a qualified advisor."
