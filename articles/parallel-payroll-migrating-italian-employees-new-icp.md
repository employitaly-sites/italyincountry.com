# How to Run a Parallel Payroll When Migrating Italian Employees to a New ICP

> A step-by-step plan for running parallel payroll when you move Italian employees to a new ICP, without double payments or broken TFR balances.

Moving Italian employees from one in-country provider (ICP) to another is a payroll project first and a contract project second. The risks are easy to name. An employee is paid twice. An employee is paid by nobody. The TFR balance arrives wrong, or does not arrive at all. A parallel run is the control that catches these before they reach a payslip.

This plan is written for partnership, operations and payroll managers at EOR and payroll platforms who own the relationship with both providers.

## Decide what a parallel run means

A parallel run does not mean paying twice. It means the new ICP calculates the full payroll in a test environment while the old ICP still pays. You compare results. Nobody receives money from the new provider until you sign off.

Write this down before you start. Teams that skip this step end up with two live payrolls and a recovery exercise.

## Step one: freeze the employee master data

Export the full employee record from the outgoing ICP. Include tax code, contract type, national collective agreement (CCNL), job level, seniority date, working hours, and every recurring pay element.

Also collect the employee's choices on TFR. In Italy, each employee decides whether TFR stays with the employer or goes to a pension fund. That choice must carry over exactly. If it is lost in the migration, the accruals go to the wrong place.

Agree one owner for the master data on each side. Changes during migration go through that owner only.

## Step two: agree the cut-over point

Choose a clean payroll period boundary for the switch. Never switch mid-period. A split period creates partial payslips, partial contributions and an almost certain reconciliation error.

Name the last period paid by the old ICP and the first period paid by the new one. Put both in writing, signed by both providers.

## Step three: load the year-to-date balances

The new ICP needs the cumulative figures, not just the current salary. That means gross pay to date, tax withheld to date, contributions to date, and any leave and bonus accruals. Without them, progressive tax and annual conguaglio calculations will be wrong at year end.

Ask the outgoing ICP for these balances in a structured file, not a PDF. Reconcile every line against the last payslip before you load anything.

## Step four: transfer the TFR balance explicitly

TFR is the field most likely to break. Treat it as its own workstream.

First, confirm with Italian counsel how the employment relationship moves. If the contract is assigned to a new employer, the accrued TFR normally follows the employee. If the old contract ends and a new one starts, the old employer settles TFR at termination. These are different payroll events with different cash flows.

Second, get the opening TFR balance per employee from the outgoing ICP. Include the revaluation already applied and any advances already paid. Load it as an opening balance with a clear source reference.

Third, run the new ICP's accrual calculation on the same pay history and compare. Any difference needs an explanation before go-live, not after.

## Step five: run the parallel calculation

Run the new payroll in test mode for the same period the old ICP is paying. Compare per employee: gross pay, net pay, tax, employee and employer contributions, and TFR accrual.

Sort differences into three groups. Data errors are fixed in the load. Rule differences, such as rounding or a CCNL interpretation, need a decision from you. Timing differences are documented and accepted.

Repeat until the differences are explained for every employee. One clean run is better than several rushed ones.

## Step six: lock out double payment

This is the control that matters most. Before the first live payroll, do all of the following:

- Confirm in writing that the old ICP will not issue any payment for periods after the cut-over.
- Cancel or suspend scheduled bank transfers at the old ICP.
- Check that final settlements, such as unused leave, are paid by one provider only.
- Compare the bank payment file against the employee list before release.

A named person at each provider should confirm each point by message. Verbal agreement is not enough.

## Step seven: go live and reconcile

Release the first payroll from the new ICP. After payment, compare the results with the parallel run. Check that tax and social contribution filings come from the new provider only, and that the old provider has filed everything for its last period.

Keep the old ICP engaged until the final filings and the TFR position are confirmed on both sides. Closing the relationship early is the usual cause of unresolved queries.

## What to put in the migration agreement

Keep it short. It should cover the cut-over period, the data files and their format, the owner of each step, the sign-off criteria for the parallel run, and the handling of corrections after go-live.

Most migration failures are not calculation failures. They are handover failures. A clear data exchange and a named owner for each step prevent most of them.

Partnership teams that want to standardise this handover can request our data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/parallel-payroll-migrating-italian-employees-new-icp.html · 2026-10-27
