# INPS contribution statement reconciliation: matching declared contributions to payroll

> How EOR and payroll platforms can reconcile INPS declared contributions with Italian payroll, and which checks catch differences early.

## Why reconciliation matters

Every Italian payroll run produces contributions. Some are withheld from the employee. Some are paid by the employer. Both are declared to INPS and paid on schedule. The declaration and the payroll should tell the same story. When they do not, someone has to find out why.

For a global EOR or payroll platform, this is a recurring operational task. You depend on a local partner for the Italian side. Your finance team needs numbers it can trust. Your customers expect clean records. Reconciliation is how you get there.

This article describes a practical way to match declared contributions to payroll. It is written for partnership, operations and payroll managers.

## Start with the contribution base

Contributions are calculated on a taxable base. The base is the starting point of every check. If the base differs between payroll and the declaration, every contribution derived from it will differ too.

So compare the base first. Do it per employee and per period. Do not compare totals only. Totals hide offsetting errors.

Common causes of a base mismatch:

- A pay element treated as contributory in payroll but not in the declaration, or the reverse.
- A retroactive change applied in payroll but declared in a later period.
- A bonus or allowance mapped to the wrong code.
- A part-period employee, for example a new hire or a leaver, where the base was prorated differently.

Fix the base mismatch before you look at anything else.

## Recalculate the main contribution

The core pension contribution, known as IVS, is a good control point. It is a fixed share of the taxable base.

According to a secondary source, the employee share is 9.19% of the taxable base. The employer share is 23.81% of the taxable base. These figures come from a secondary source and should be confirmed against the official INPS circular before you hard-code them into any control.

The check is simple:

1. Take the base from the payroll.
2. Apply the employee rate. Compare the result with the amount withheld on the payslip.
3. Apply the employer rate. Compare the result with the employer cost in the payroll.
4. Compare both results with the amounts in the declaration.

If all three agree, the IVS line is clean. If not, the difference points to the base, a rate, or a rounding rule.

Note that some employees fall under different rules or ceilings. Treat these as exceptions with their own flag. Do not force them through the standard check.

## Separate the types of difference

Not every difference is an error. Sort differences into groups before you escalate.

**Timing differences.** The payroll recorded a cost in one period. The declaration reflects it in another. These resolve themselves, but you must track them until they do.

**Rounding differences.** Small amounts caused by rounding at line level versus total level. Agree a tolerance with your partner and write it down.

**Mapping differences.** A pay element sits under the wrong contribution treatment. These repeat every period until someone fixes the mapping.

**True errors.** A wrong base, a wrong rate, a missing employee, a duplicated line. These need correction and, in some cases, a corrective declaration.

A clear category makes the next step obvious. It also lets you report on root causes instead of single cases.

## Match employees, not only amounts

A reconciliation that only compares amounts misses a whole class of problems. Check the population too.

- Is every active employee in the payroll also in the declaration?
- Is anyone in the declaration who is not in the payroll?
- Do start and end dates agree?
- Does the contract and inquadramento data agree on both sides?

Missing or extra employees are rare but costly. They are easy to find with a simple key match on a stable employee identifier.

## Build a repeatable routine

Reconciliation works best as a fixed routine, not as a reaction to complaints.

- Run it every period, soon after the declaration is prepared.
- Use the same checks each time, in the same order.
- Store the result with the period, the data version and the rates used.
- Keep a list of known, accepted differences and review it regularly.
- Record who resolved each difference and how.

This gives you an audit trail. It also shows trends. If the same mapping error appears again and again, you fix the process, not the case.

## What to ask your Italian partner

Before you rely on the numbers, agree a few things with your partner:

- Which fields are exchanged: base, employee contribution, employer contribution, period, employee identifier.
- In what format and how often.
- Who owns each correction.
- How rate changes are communicated and applied.
- What tolerance applies to rounding.

Without these points, each period turns into a negotiation. With them, it becomes a check.

## Keep rates under control

Rates and ceilings change. A control that uses an old rate will flag correct payroll as wrong. A control that is never updated will stop being trusted.

Keep rates in one place, with a source and a date. Update that place when the official source changes. Every check should read from it. Do not repeat rates in spreadsheets or scripts.

## Summary

Reconcile the base first. Recalculate the main contribution from the base. Sort differences by cause. Match the employee population. Run the routine every period and keep the record.

The work is not complicated. It needs discipline and a shared data format between you and your partner.

Partnership teams can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/inps-contribution-statement-reconciliation-partners.html · 2026-10-27
