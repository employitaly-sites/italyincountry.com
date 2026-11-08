# Absence data checklist: sick leave, parental leave and permits

> Which fields your platform must send for each absence type so Italian payroll calculates pay correctly: sick leave, parental leave and permits.

Absence data is where most Italian payroll errors start. A missing field does not cause a rejected file. It causes a wrong payslip, and the fix arrives a month later.

This checklist lists what an EOR or payroll platform should send for each absence type. Use it to review your own payloads before they reach Italian payroll.

## Fields every absence needs

Send these for every record, whatever the type.

- Employee identifier that matches the payroll master record.
- Absence type code from an agreed list.
- Start date and end date, or an open end flag if the end is not known yet.
- Full-day or partial-day indicator. For partial days, send hours.
- Record status: new, changed or cancelled.
- Source and timestamp of the entry.

Two rules help here. Never overwrite a record silently. Send a change with a reference to the original. And never reuse one type code for different cases. Pay rules depend on the code.

## Sick leave

Sick leave pay depends on the medical certificate, the contract and the collective agreement. The employer and the social security institute each pay part of it, and who pays what changes by case.

Required fields:

- Certificate protocol number issued for the electronic certificate.
- First day of illness and last day of the prognosis.
- Whether the record is an initial certificate, a continuation or a relapse.
- Link to the previous episode when it is a continuation. Pay rules treat linked episodes differently from new ones.
- Hospital stay flag, if applicable.
- Work accident or occupational disease flag. These follow a different payment route and must never be sent as plain sickness.
- Collective agreement and employee level, so the correct employer top-up can be applied.

Common errors: sending a new episode when it is a continuation, missing the protocol number, and mixing up accident leave and sickness.

## Parental leave

This category covers several different entitlements. Maternity and paternity leave are separate from optional parental leave, and each has its own pay logic.

Required fields:

- Leave subtype: compulsory maternity, paternity, or optional parental leave.
- Child's date of birth, or expected date of birth for leave before the birth.
- Which parent takes the leave.
- Whether the leave is taken in full days or in hours.
- Reference to the application filed with the social security institute, where one is needed.
- Running total of optional leave already used by this parent for this child, including leave taken with a previous employer if known.
- Any special circumstance flags, such as a single parent or a child with a disability.

Common errors: no child date of birth, which blocks the entitlement check. Another is hourly leave sent without hours. A third is a missing running total, which leads to leave being paid beyond the entitlement.

## Permits

Permits are short authorised absences. The pay effect depends on the type.

Required fields:

- Permit type: paid permit under the collective agreement, unpaid permit, statutory permit for family reasons, medical visit, study permit, union permit, or accrued time-off bank.
- Hours or days taken.
- Which balance to draw from, if the type uses one.
- Supporting document reference where the rule requires proof.
- Approval status and approver.

For time-off banks, send the opening balance and the movement. Do not send only the new balance. Payroll needs to see the movement to reconcile accruals.

Common errors: a generic "leave" code with no reason, and permits sent as full days when the employee worked part of the day.

## Quality checks before you send

Run these checks on your side first.

1. Does every record have a valid type code from the shared list?
2. Do dates sit inside the employment period?
3. Do overlapping records make sense? A sick leave overlapping a permit usually means one is wrong.
4. Are cancelled records marked as cancelled, not deleted?
5. Is the cut-off for late changes known to both sides?

Late changes matter most. If a certificate arrives after the payroll run, payroll needs the change flagged as retroactive so it can adjust the next period correctly.

## Why the structure matters

Italian pay for absences depends on the type, the collective agreement and the employee's history. A free-text note cannot carry that. Structured fields with fixed codes can. Agree the code list once, version it, and treat changes as a controlled process.

This also reduces support work. When a payslip looks wrong, you can trace it to a field instead of reading emails.

Partnership teams that want to align their absence payloads with Italian payroll can request our data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/absence-data-checklist-italy-sick-parental-permits.html · 2026-10-27
