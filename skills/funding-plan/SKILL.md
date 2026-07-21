---
name: funding-plan
description: Use to build or refresh how a term is paid for, or to check cost coverage and shortfall risk — "update the funding plan", "how is next semester paid for", "what's our out-of-pocket", "are we going to run short", "who's covering what". Allocates the student's funding sources across each term's cost buckets, computes out-of-pocket, and flags risks (a finite benefit running out, a missed renewal window, a credit-load threshold, a payment due date). Models trade-offs; does not give financial advice.
---

# Build or refresh the funding plan

Allocate funding sources to costs for a term (or the whole plan) and surface the money picture. Read the current Funding Plan and Semester Funding Plan first.

## Step 1 — Gather inputs

- The term's **cost buckets** and amounts — from an ingested bill if available (actuals), otherwise the Cost of Attendance or estimates (label them).
- The **funding sources** with their schema fields — especially `covers`, `amount`, `cadence`, `priority`, and `constraints`.
- The **contributors** and what each covers.

## Step 2 — Allocate

Follow `references/allocation.md`. In short: order sources by `priority`, and for each, apply its `amount` to the buckets it `covers`, respecting constraints, until costs are covered or sources are exhausted. Keep student-paid items (stipends, work-study) out of the bill allocation — track them as separate income/savings.

Produce, for the term: each bucket, the source(s) covering it, and the **remaining balance / out-of-pocket** after all sources and contributions.

## Step 3 — Run the risk checks

From `references/allocation.md`, flag any that apply: a finite benefit projected to run short or expire unused before graduation; an aid/scholarship renewal or benefit certification window; an enrollment/credit-load threshold that affects an award; a payment due date; a contributor commitment due for validation; a savings plan drawn for a non-qualified purpose.

## Step 4 — Update and report

Update the Semester Funding Plan and the Dashboard funding snapshot and risks. BLUF the result: who covers what, the out-of-pocket number, and the top risks with the action that resolves each. State assumptions and mark estimates.

> **Model, don't advise.** Show the numbers and trade-offs (including preserve-vs-use decisions for finite benefits) and let the user choose. Add the standard reminder that this isn't financial or legal advice for consequential decisions.
