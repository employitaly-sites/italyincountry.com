# What a payroll audit of an Italian ICP should cover

> A scope for platform internal audit and SOC teams reviewing an Italian in-country partner: data flows, calculations, payments, filings, access and evidence.

A global EOR or payroll platform that relies on an in-country partner (ICP) in Italy carries the operational risk of that partner. Your customers see your brand. Your auditors will ask what you checked.

This note sets out a scope for internal audit or SOC teams. It is a checklist of areas, not a legal opinion. Adapt the depth to your own control framework.

## Start with the data flow

Map how data moves before you test anything. Draw the path from your platform to the ICP and back.

- Which system is the source of truth for employee master data?
- How do changes arrive: file, API, manual entry?
- Who approves a change before it reaches payroll?
- Where is the evidence stored, and for how long?

Manual re-keying is the main risk to find here. Each re-key is a point where an amount, a tax code or a contract type can change without a trace.

## Contract and collective agreement mapping

Italian payroll depends heavily on the national collective agreement (CCNL) that applies to the employee. It drives minimum pay, extra monthly payments, leave, notice and many allowances.

Audit questions:

- How does the ICP assign a CCNL to each employee, and who signs off?
- Is the assignment recorded with a source and a date?
- What happens when an agreement is renewed and rates change?
- Are the job level and the pay components in the contract consistent with the agreement?

Sample a set of employees and trace each one from contract to payslip. Check that the agreement on file is the one actually applied.

## Gross-to-net calculation

Test the calculation, not just the output. Ask the ICP for the rule set behind it.

- Employer and employee social security contributions.
- Income tax withholding and regional and municipal surcharges.
- Deductions and family-related tax elements.
- Year-end adjustments and tax settlement on the final payslip of the period.
- Severance accrual, which is specific to Italy and often missed by foreign teams.

Re-perform a sample of calculations independently. Where the ICP uses payroll software, ask for the version history and the change log for rate tables. Rate updates should be traceable to an official source.

## Payments and cash control

Payroll in Italy involves several payment streams. Net salaries go to employees. Withholdings and contributions go to the tax and social security bodies, usually through a consolidated payment form.

Audit questions:

- Is there segregation between the person who prepares payments and the person who releases them?
- Do funds for taxes and contributions sit in a segregated account, or are they mixed with the ICP's own money?
- How are payment files checked against the approved payroll?
- What is the reconciliation process, and who reviews it?
- How are rejected or returned payments handled?

Funding is where platform risk concentrates. If you pre-fund the ICP, you need to know how that cash is held and when it is paid out.

## Filings and reporting

The ICP files periodic declarations with the tax and social security authorities. It also handles monthly and annual reporting for each employee.

Check that:

- A filing calendar exists and is owned by a named person.
- Each filing has a submission receipt stored with the payroll run it belongs to.
- Corrections and late filings are logged with a cause.
- The employee's annual tax certificate is issued and matches the payslips.

Ask for the receipts, not a statement that filings are done.

## Starters, leavers and changes

Most errors cluster around events. Test them separately from the regular run.

- Starter notifications and the timing of registration.
- Leaver calculations: unused leave, notice, severance, final tax.
- Mid-month changes in pay, hours or contract.
- Long absences and the split between employer and social security payments.

Trace each event from the request on your platform to the effect on the payslip.

## Access, security and data protection

This is the SOC part of the scope.

- User access review for payroll systems and bank portals.
- Multi-factor authentication on every system that can change pay or release payments.
- Joiner, mover and leaver process for the ICP's own staff.
- Encryption of files in transit and at rest.
- Sub-processors, and where employee data is stored and processed.
- Incident response: how fast you are told, and what you receive.
- Backup and recovery tests, with evidence.

Italian employee data includes sensitive items such as health-related absence information. Confirm that access to it is limited by role.

## Evidence and audit trail

A control that cannot be shown does not exist for audit purposes. Agree up front what evidence the ICP will hand over and in what format.

Useful evidence sets:

- Approved payroll input for each run.
- Calculation reports and variance analysis against the previous run.
- Payment files and bank confirmations.
- Filing receipts.
- Reconciliation sign-offs.
- Change logs for rate tables and employee data.

Variance analysis deserves attention. A good ICP explains every material movement between runs without being asked.

## Service levels and governance

Finally, check how the relationship is managed.

- Are service levels defined for input cut-off, payslip delivery and error correction?
- Who reports breaches, and how often?
- Is there a documented escalation path?
- How are the ICP's own audits and certifications shared with you?
- Is there an exit plan that returns your data in a usable format?

## How to run it

Keep the first review narrow. Pick a small sample of employees across different agreements and event types. Trace each one end to end. Findings from a sample show you where to widen the scope.

Agree a remediation owner and a due date for every finding. Review progress on a fixed rhythm, not only at the next audit.

A structured data exchange makes all of this easier. When inputs, calculation results, payments and filings arrive in a consistent format, your team can test controls on the full population instead of a sample.

Partnership teams that want to see how that exchange can be structured can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/payroll-audit-italian-icp-scope.html · 2026-10-27
