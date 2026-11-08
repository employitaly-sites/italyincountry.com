# Mandatory pre-start communications for Italian hires: the ops view

> How the Italian hiring notification works for EOR and payroll ops teams: what must be filed before day one, who owns it, and how to keep timing under control.

## The short version

In Italy, an employer must tell the authorities about a new hire before the person starts work. The filing is not optional and it is not a payroll step. It is a legal precondition for day one.

For a global EOR or payroll platform, this changes the order of work. In many countries, payroll set-up can follow the start date. In Italy, the notification comes first. If it is late or wrong, the start date is exposed.

This article explains the flow from the operations side. It does not quote deadlines or amounts. Check the current rule with your Italian provider before you commit to any service level.

## What the notification is

The hiring notification is an electronic filing to the Italian labour authorities. It tells them who is being hired, by which employer, under which contract, and from which start date.

The same system also covers changes. Extensions, conversions, transfers and terminations are reported too. So this is not a single event. It is a chain of filings across the life of the employment.

Once filed, the data is shared with other bodies. That is why errors travel. A wrong contract type or a wrong start date can show up in places you did not expect.

## Who files it

The legal employer is responsible. In an EOR model, that is the local entity or the local partner acting as employer of record.

Your platform may collect the data. Your Italian provider files it. The responsibility stays with the employer, so your process needs a clear record of who submitted what and when.

If the filing is made through a delegated professional, the delegation must be in place before the first filing. Missing delegation is a common cause of delay on the first hire for a new client.

## The data you need before filing

Ops teams should treat the notification as a data-completeness gate. Typical inputs include:

- Employee identity and tax code
- Residence and domicile
- Employer details and the workplace
- Contract type and duration, if fixed term
- Start date
- Collective agreement applied
- Job classification and level
- Working hours and regime

The tax code is the item that blocks most files. Without it, nothing moves. Plan how it is obtained, especially for candidates who live abroad and have never had an Italian tax position.

The collective agreement and the level are the next problem. They affect pay, notice and benefits. They also feed the notification. If sales has promised a role and a level that do not match the agreement, you find out here.

## Timing from the ops side

The legal deadline is tied to the start date. Your internal deadline should be earlier. Build a buffer, because the filing depends on data from the candidate, the client and sometimes a third party.

A workable model has three checkpoints:

- **Data complete.** All required fields are collected and checked against the signed offer.
- **Filed.** The provider submits the notification and returns the receipt.
- **Confirmed.** The receipt is stored against the employee record and matched to the contract.

Do not mark a hire as ready to start until the third checkpoint is done. A start date that moves is cheaper than a start without a valid filing.

## Where start dates go wrong

Three patterns repeat.

**Late offers.** The client signs close to the start date. The data is incomplete. The filing is rushed or missed.

**Changed start dates.** The candidate or client shifts the date after filing. The notification must be corrected. If nobody owns that step, the record stays wrong.

**Non-EU hires.** Work authorisation has its own timeline. The notification cannot be treated as independent from it. Align both before you promise a date.

## Controls worth building

Keep the controls simple.

- A hard rule that no start is confirmed without a filing receipt.
- A change trigger: any change to date, contract or workplace opens a correction task.
- A single owner per hire, on your side, who tracks the three checkpoints.
- Receipts stored in the employee file, searchable by hire.
- A weekly report of hires without a confirmed filing.

These controls cost little. They remove most of the surprises.

## What to ask your Italian provider

Ask how filings are submitted and how fast receipts come back. Ask how corrections are handled and who approves them. Ask what happens when the system is unavailable. Ask for the data fields they need, in the exact format they need them.

Then map those fields to your own onboarding forms. Every field you collect late is a day you lose.

## Integration notes

If you run an API-based platform, treat the notification as a status in the hire workflow, not as a back-office document. Expose its state to your customers. Clients want to know whether a start is safe, and a clear status answers that without a support ticket.

Keep the data model aligned with the filing. Contract type, agreement, level and hours should be structured fields, not free text. Structured fields reduce rework and make corrections traceable.

Partnership teams that want to see how this data can be exchanged between platform and provider can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/italy-mandatory-pre-start-communications-ops-view.html · 2026-10-27
