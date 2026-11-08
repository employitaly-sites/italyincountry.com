# Pre-cut-off data validation checklist for Italian payroll

> A practical checklist of input validations for Italian payroll, run before cut-off, so most data errors are caught before the run and not after it.

Most Italian payroll corrections do not start in the payroll engine. They start in the input file. A wrong tax code, a missing contract level or a late absence record travels through the whole run and comes back as a rework ticket.

The cheapest fix is a short set of checks, run before cut-off. They are mechanical. They need no judgment. They catch the bulk of input errors before anyone opens a payslip.

This checklist is written for partnership, operations and payroll managers at global EOR and payroll platforms who send data to an Italian payroll provider.

## 1. Identity and registry data

Start with the person. Errors here block everything else.

- **Tax code (codice fiscale).** Check the format and the control character. Check that it matches name, surname, date of birth and place of birth. Foreign workers often have a code issued after arrival, so do not accept a placeholder.
- **Names.** Match the spelling to the identity document. Reject truncated names and special characters your system cannot export cleanly.
- **Residence and domicile.** Both must be present and complete. Tax and local surcharges depend on them.
- **Bank details.** Validate the IBAN structure and country. Confirm the account holder name matches the employee.
- **Duplicates.** Look for the same person under two employee IDs. This happens after rehires and entity transfers.

## 2. Contract and employment data

The contract record drives pay, contributions and leave. Check it field by field.

- **Start and end dates.** The start date cannot be after the end date. Fixed-term contracts must have an end date. Open-ended contracts must not.
- **National collective agreement (CCNL).** Every employee needs one assigned. Reject blanks and free-text labels. Use a controlled list.
- **Job level and category.** The level must exist in the assigned agreement. A level from another agreement is a common silent error.
- **Working time.** Full-time or part-time must be explicit. If part-time, the schedule must be stated.
- **Base pay.** It must be at or above the minimum set by the agreement for that level. Flag anything below it for review.
- **Probation and notice.** Make sure the fields are filled when the contract requires them.

## 3. Variable pay and period movements

This is where most late changes appear. Treat every movement as new data that needs its own check.

- **Period.** Every variable item must carry the payroll period it belongs to. Reject items with no period.
- **Item codes.** Each code must exist in the provider's code list. Unknown codes should fail at import, not during the run.
- **Overtime and allowances.** Check that the agreement allows the item for that level.
- **Bonuses and one-off payments.** Require a clear gross or net flag. Mixing the two is a frequent cause of wrong payslips.
- **Retroactive changes.** Mark them as such. A raise applied late must show the original effective date.
- **Expense reimbursements.** Keep them separate from taxable pay, with the supporting category.

## 4. Absences and leave

Absence data is often the last to arrive and the least structured.

- **Type.** Holiday, sickness, maternity, parental and unpaid leave follow different rules. Do not accept a generic "absence" type.
- **Dates.** No overlaps between absences. No absence outside the contract dates.
- **Sickness.** The medical certificate reference must be present. Without it, the provider cannot report correctly.
- **Balances.** Check that leave taken does not exceed what the system shows as accrued, unless an advance is approved.

## 5. Leavers and joiners

Starts and exits carry deadlines and extra calculations.

- **Joiners.** Confirm the registry and contract data are complete before cut-off, not after. Late joiners create off-cycle work.
- **Leavers.** Require the last working day, the reason for termination and any unused leave. Check the notice period against the agreement.
- **Final pay items.** Make sure severance-related items and leave payouts are listed as separate lines.

## 6. Cross-file consistency

The last layer compares the current file with the previous one.

- **Headcount.** New, changed and removed employees should reconcile with the HR system.
- **Unexpected changes.** Flag any change in base pay, bank account or agreement that has no matching change request.
- **Missing people.** An employee present last period and absent now, without a leaver record, needs an explanation.
- **Entity mapping.** Each employee must map to a valid legal entity or client account.

## How to run it

Run the checks automatically at import. Group failures by severity. Registry and contract errors block the file. Variable pay warnings go to a review list. Send the full result back to the sender the same day, so corrections arrive before cut-off.

Keep the rules versioned. When an agreement or a code list changes, the checklist changes with it. A rule nobody updates becomes a source of false alarms, and teams stop reading the report.

The goal is simple. Fewer surprises on payroll day, fewer corrections after it, and a clear record of who fixed what.

Partnership teams that want to align their exports with these checks can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/pre-cut-off-data-validation-checklist-italian-payroll.html · 2026-10-27
