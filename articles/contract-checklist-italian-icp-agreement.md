# Contract checklist for a new Italian ICP agreement

> A practical checklist for EOR and payroll platforms signing an in-country partner in Italy: data, liability, SLA and exit clauses to settle before go-live.

A global EOR or payroll platform that adds an in-country partner (ICP) in Italy is handing over live payroll, employee records and compliance filings. The contract has to describe how that works day to day. Most disputes later come from vague wording, not bad faith.

This checklist covers four areas: data, liability, service levels and exit. Use it before you sign, and again when you renew.

## Data

Start with roles. State who is controller and who is processor for each data category. Payroll inputs, payslips, tax and social security filings, and employee contact details may not all sit in the same role. Write it down per category.

Then cover these points:

- **Scope of processing.** List the data fields exchanged, the purpose of each, and the systems that hold them.
- **Format and channel.** Define the file or API format, the field names, the encoding and the transfer method. Ambiguity here causes most payroll errors.
- **Location and transfers.** Name where data is stored and which sub-processors can touch it. Require notice before any change.
- **Security measures.** Reference concrete controls such as access rights, encryption and logging. Avoid the phrase "industry standard" on its own.
- **Breach notification.** Set a clear internal deadline for the ICP to tell you, so you can meet your own duties to the authority and to the client.
- **Retention and deletion.** Say how long records are kept, who keeps the legal archive, and how deletion is confirmed.
- **Audit rights.** Allow reasonable audits or the delivery of independent reports, with a defined process.

Also decide who owns the master data. Your platform should remain the system of record for the employee profile. The ICP should hold only what it needs to act.

## Liability

Payroll mistakes have a cost that is easy to name: wrong net pay, late filings, interest and penalties. Decide in advance who bears which part.

Split errors into types. An error caused by wrong input from your platform sits with you. An error in calculation, filing or deadline handling by the ICP sits with the ICP. Mixed causes need a rule, not a debate.

Check these clauses:

- **Indemnity for penalties and interest.** The party at fault covers them, including the cost of correcting the filing.
- **Cap on liability.** Caps are normal. Make sure the cap does not swallow the cases that matter most, such as data breach, wilful misconduct and gross negligence.
- **Pass-through to the end client.** Your client contract will have its own terms. Align the two so you are not left with a gap between what you promise and what the ICP covers.
- **Insurance.** Ask for professional indemnity and cyber cover, and request proof of it.
- **Correction duty.** The ICP should fix its own errors at its own cost and within a stated time.

Do not forget conduct. The ICP deals with authorities and employees on your behalf. Set out what it may and may not say, and who approves communication with institutions.

## SLA

An SLA that says "timely" is not an SLA. Tie each service to a measurable target and a consequence.

Cover the full monthly cycle: receipt of inputs, payroll calculation, your approval, payment instructions, payslip delivery and filings. For each step, define the cut-off and the owner.

Include:

- **Input cut-offs.** What happens to late changes from your side. Agree whether they roll into the next cycle or trigger an off-cycle run, and who pays for it.
- **Response and resolution times.** Separate urgent payroll issues from routine questions.
- **Onboarding and offboarding.** Time to set up a new employee and to process a leaver.
- **Language and support hours.** Say which languages and which hours are covered, including cover during holidays.
- **Reporting.** Monthly service reports with agreed measures, and a review meeting.
- **Service credits and termination triggers.** Repeated failure should lead to credits first, then a right to terminate.
- **Change control.** Regulatory updates will arrive. Define how the ICP tells you, how fast it updates its process, and who pays for system changes.

## Exit

Exit is the clause teams skip and later regret. Write it as if the relationship will end badly.

Ask for:

- **Termination rights.** For convenience with notice, for cause, and on change of control.
- **Transition assistance.** The ICP keeps running payroll while you migrate, at agreed rates, until handover is complete.
- **Data return.** Full export of employee records, payroll history, filings and open items in a documented format, with confirmation of deletion afterward.
- **Open obligations.** Who finishes pending filings, year-end statements and corrections after the exit date.
- **Employee continuity.** Employees must see no gap in pay or in contact points during the switch.
- **Non-solicitation and exclusivity.** Check that the ICP cannot contact your clients or employees directly, and that you are not locked in against your will.
- **Survival.** Confidentiality, liability and audit clauses should continue after the contract ends.

## Before you sign

Run a short dry test. Send a sample data set through the agreed format, check the output, and log the problems. A contract tells you what should happen. A test shows what will.

Then assign an owner on each side for the data, the SLA and the exit plan. Clauses only protect you if someone reads the reports and acts on them.

Partnership teams that want to align their integration with the contract can request the data-exchange specification from ItalyInCountry.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/contract-checklist-italian-icp-agreement.html · 2026-10-27
