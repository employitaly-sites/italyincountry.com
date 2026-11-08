# Reconciling a funding invoice against the payroll register

> A month where the funding invoice and the payroll register disagree, and how a platform operations team can trace the gap line by line.

A funding invoice and a payroll register describe the same month. They should agree. Some months they do not. This article walks through one such month and shows how to trace the gap.

No figures are used here. The method matters more than the amounts.

## The setup

A global EOR platform sends a funding request to its local partner. The request covers net pay, employer contributions, taxes withheld and the partner's fee. The partner runs payroll, files the returns and produces a payroll register.

At month end, the finance contact on the platform side compares the two documents. The invoice is higher than the register total. Nobody has made an obvious error. The task is to find where the difference sits.

## Start with the shape of the gap

Before opening any line, ask what kind of gap it is.

- Is the invoice higher or lower than the register?
- Does the gap sit in one cost category or across all of them?
- Does it affect one employee, a group, or the whole population?

A gap in a single category points to a rule or a rate. A gap spread across all categories points to a headcount or timing issue. A gap tied to one person points to a data change for that person.

In this scenario the gap sits mostly in employer contributions. Net pay lines match. That narrows the search at once.

## Check the basis of each document

The invoice and the register are often built on different cut-off points. Confirm these before looking at individual lines.

- **Period covered.** Does the invoice cover the same pay period as the register?
- **Cut-off for changes.** Joiners, leavers and salary changes entered late may sit in one document and not the other.
- **Currency and rate.** If the platform funds in one currency and the partner pays in another, the conversion date matters.
- **Inclusions.** Some registers show the fee. Some do not. Some invoices bundle one-off items.

Here, the period and currency match. The cut-off for changes does not. The invoice was prepared from the platform's headcount file. The register was produced after a late correction.

## Match employee by employee

Export both documents with a stable employee identifier. Do not match on names. Names are spelled differently across systems.

Then build a simple comparison with these columns:

- employee identifier
- amount on the invoice
- amount on the register
- difference
- reason code

Sort by the absolute difference. The largest items usually explain most of the gap. Work down the list until the remaining items are too small to matter, then group them.

In this scenario a small number of employees account for nearly all of the difference. The rest are rounding.

## Common causes

When funding and actuals diverge, the cause is usually one of these.

**A mid-period change.** A salary increase or a change in contract terms was applied in the register after the invoice was raised. The invoice reflects the older figure.

**A leaver or joiner.** An employee left or started part way through the period. The invoice treats a full period. The register prorates.

**A contribution rule.** A rate, a ceiling or an exemption applies to some employees. The invoice used a general assumption. The register used the individual rule.

**An adjustment from a prior period.** A correction from an earlier run lands in this month's register. It has no matching line on the invoice.

**A timing difference on benefits.** An allowance is paid in one run but accrued in another.

In this scenario the cause is a prior-period correction and a late salary change. Both are real. Neither is an error. They are timing differences.

## Document the result

A reconciliation is only useful if the next person can read it. Record the following for each difference.

- the employee identifier
- the cause
- the document that is correct
- whether a credit note, a supplementary invoice or no action is needed
- who approved the treatment

Then decide how the gap is settled. A timing difference usually reverses in the next period. A genuine overcharge needs a credit. Agree this with the partner in writing.

## Prevent the same gap next month

Most gaps repeat. The fix is upstream.

- Share one cut-off date for changes and keep to it.
- Send changes as structured data, not as emails or spreadsheets.
- Include the reason code in the data, so that the invoice and the register carry the same label.
- Return the register in a format that can be matched to the invoice without manual work.

When both sides use the same identifiers and the same fields, the comparison takes minutes. The team spends its time on the few items that need judgment.

## What good looks like

A clean funding process has few surprises. Differences are explained before the invoice is paid. The register is available when the invoice arrives. Corrections are visible as corrections, not hidden in totals.

This is a data problem more than a finance problem. Better structure removes most of the work.

Partnership teams that want to see how this data can be exchanged between a platform and a local payroll partner can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/reconciling-funding-invoice-payroll-register.html · 2026-10-27
