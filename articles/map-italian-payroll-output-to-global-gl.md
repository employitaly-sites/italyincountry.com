# How to map Italian payroll output to your global GL

> A double-entry guide to mapping Italian contributions, TFR and surtaxes from payroll output to a partner chart of accounts.

Italian payroll output does not look like payroll output from most other countries. The payslip carries employee and employer contributions, income tax withholding, regional and municipal surtaxes, and a severance accrual called TFR. Your global general ledger expects a short list of accounts. The mapping between the two is where errors start.

This article shows a practical double-entry structure. It is a pattern, not a fixed answer. Adjust account names to your own chart.

## Start from the payroll journal, not the payslip

The payslip is built for the employee. The payroll journal is built for accounting. Map from the journal. Each line should carry a stable code, a sign, an amount and a period. If a line has no code, it cannot be mapped reliably.

Keep three layers separate:

- The source line from the payroll engine.
- The category in your mapping table.
- The GL account in the partner chart.

When the chart changes, you edit the mapping table. The source codes stay the same.

## Gross pay and employer cost

Gross pay is an expense and a liability until it is paid out.

| Debit | Credit |
|---|---|
| Salaries expense | Net pay payable |
| Salaries expense | Employee withholdings payable |

In practice, you post gross to expense and split the credit side into what the employee receives and what is owed to authorities. Do not post net pay as the expense. Net is a settlement amount, not a cost.

## Social contributions

Italian social contributions have two parts. The employee share is taken out of gross pay. The employer share is an additional cost on top of gross.

Employee share:

| Debit | Credit |
|---|---|
| Salaries expense (already booked at gross) | Social security payable, employee share |

Employer share:

| Debit | Credit |
|---|---|
| Employer social charges expense | Social security payable, employer share |

Two points matter here. First, keep the employer expense on its own account. Finance teams compare employer cost across countries, and a blended account hides it. Second, do not merge the employee and employer payables into one balance unless your cash-out is also one payment. If the authority collects them together, you can clear them together, but report them apart.

If the payroll output separates the injury insurance premium from pension and other contributions, map it separately. It behaves like a different cost in many reports.

## Income tax withholding and surtaxes

The employer withholds income tax and pays it to the tax authority. This is a liability, not an expense.

| Debit | Credit |
|---|---|
| Salaries expense (already booked at gross) | Income tax withheld payable |

Regional and municipal surtaxes follow the same logic, but they are usually deducted in instalments and may be settled in a different period from the one that created them. Give each surtax its own payable account, or at least its own sub-ledger tag. The reason is timing. A single tax payable account that mixes current withholding with deferred surtax settlements is hard to reconcile.

When the payroll engine reports an adjustment at year end, post it as a correction to the same payable accounts. Do not route it through expense unless the engine marks it as a true cost change.

## TFR

TFR is the part that most often breaks global mappings. It is a deferred pay obligation that builds up over the employment. It is a cost of the period in which the service is rendered, and a liability until it is paid out or transferred.

The accrual:

| Debit | Credit |
|---|---|
| TFR expense | TFR provision (liability) |

The provision is revalued over time. Post the revaluation as a separate line, so that service cost and revaluation can be reported apart. Many partner charts have one line for "end of service benefits". That works, but only if the sub-ledger keeps the split.

If the employee directs TFR to a pension fund or the employer transfers it elsewhere, the accrual still happens first. Then the liability is cleared against a payable to the fund.

| Debit | Credit |
|---|---|
| TFR provision | Payable to pension fund |

Do not skip the accrual when the money goes straight out. Your cost report will then understate employer cost.

## Settlement entries

Payment is a separate step from accrual. When you pay net salary, debit net pay payable and credit bank. When you remit contributions and taxes, debit each payable and credit bank. Keep one bank entry per payment batch, with a reference you can match to the payroll run.

## Controls that save time

- Check that total debits equal total credits per payroll run before export.
- Reconcile each payable account to zero after settlement, or explain the open item.
- Reject any source code that is missing from the mapping table. Do not default it to a catch-all account.
- Version the mapping table. Reports from last quarter must reproduce with last quarter's mapping.

## What to ask of your Italian provider

Ask for a journal export with stable line codes, signed amounts, period tags and employee-level detail. Ask for separate lines for employer contributions, each surtax, TFR accrual and TFR revaluation. With those, the mapping is a lookup, not a project.

Partnership teams that want to see the full field list can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/map-italian-payroll-output-to-global-gl.html · 2026-10-27
