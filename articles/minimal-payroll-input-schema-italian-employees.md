# A minimal payroll input schema for Italian employees

> Field-by-field guide to the data an Italian payroll needs from a global EOR or payroll platform, and why each field matters.

Global platforms often ask what an Italian payroll provider needs to run a month. The honest answer is shorter than most expect, but it is stricter than most expect too. Italian payroll is driven by the national collective agreement, the social security position and the individual's tax situation. If your platform sends clean data for those three areas, the rest is routine.

This article walks through the minimal schema, field by field, and says why each field exists.

## Identity and tax identity

**Legal name, birth date, birth place, sex.** These feed the Italian tax code, the codice fiscale. Italian systems validate the tax code against these fields. A mismatch blocks filings.

**Codice fiscale.** Send it if the employee already has one. If not, flag it as missing. The payroll provider can usually start the process, but the hire cannot be filed cleanly without it.

**Residence address and domicile.** Residence drives local tax treatment. Send both if they differ. Do not send a work address in their place.

**Citizenship and work authorisation status.** Italian filings distinguish between EU and non-EU workers. For non-EU staff, send the permit type and its validity end. The provider needs this to keep the record compliant, not to assess immigration eligibility.

## Contract data

**Start date and end date, if fixed term.** The start date triggers the mandatory employment notification. Late data here creates real exposure, so send it as early as you can.

**Contract type.** Open-ended, fixed-term, apprenticeship and similar. Use a controlled list, not free text.

**Working time.** Full-time or part-time, plus the weekly schedule for part-time staff. Italian payroll calculates many items from the agreed schedule, so a vague "part-time" is not enough.

**Job title and level.** This is the most underestimated field. In Italy the level is not a label. It is a classification inside the collective agreement and it sets minimum pay and many entitlements. Send the level your client believes applies, and expect the provider to confirm it.

**Collective agreement (CCNL).** Send the name of the agreement that applies to the employer's sector. If your client does not know, say so. Do not guess. The wrong agreement changes minimum pay, notice periods, leave and sick pay rules.

## Pay data

**Gross base pay and its period.** State whether the figure is monthly or annual, and in which currency. Italian payroll works from gross.

**Additional monthly payments.** Many agreements provide extra payments beyond the regular months. Do not fold them into an annual total without saying so. The provider needs to know whether your gross figure already includes them or sits on top.

**Recurring allowances and benefits.** Meal vouchers, company car, housing support, phone. Send each as its own line with a type, an amount and a start date. The tax and contribution treatment depends on the type, so a single "benefits" total is not usable.

**Variable pay.** Bonuses, commissions and equity. Send the event, the gross amount and the payment month. Equity needs extra detail, so flag it early rather than at the payment month.

## Monthly variable inputs

After onboarding, the monthly feed should carry only changes.

**Absences.** Type (holiday, sick leave, parental leave, unpaid leave), start, end. Sick leave needs the medical certificate reference. Parental and similar leave types carry their own rules, so keep the types separate.

**Overtime and supplements.** Hours by category, if the agreement pays them.

**One-off payments and deductions.** Each with a reason code.

**Terminations.** Last working day, reason, and whether notice is worked or paid. Also send any outstanding leave balance. Italian final settlement includes accrued items that depend on these facts.

## Tax and family situation

**Dependants and tax allowances.** The employee declares these, and they change withholding. Send the declaration as given and the date it was made.

**Prior employment in the same year.** If the person joined mid-year, the provider needs earlier income and withholding data to calculate correctly.

**Regional and municipal tax location.** Derived from residence, but worth confirming in the feed.

## Payment and delivery

**Bank account in IBAN form.** Account holder must be the employee.

**Payslip language and delivery channel.** Italian payslips are in Italian. Decide in advance whether your platform shows a translation or a link.

## What not to send

Do not send calculated net pay, estimated contributions or your own tax computation. The Italian provider owns those calculations. Send inputs, receive results, and reconcile.

## Practical rules for the feed

Use controlled lists wherever possible. Version every record with an effective date. Send corrections as new records, not overwrites. Return validation errors with a field name and a plain reason. Agree on a cut-off day for monthly changes and keep to it.

A schema this small is enough to run a clean Italian payroll. Most delays come from three fields: the collective agreement, the level and the working schedule. Fix those at onboarding and the monthly cycle becomes predictable.

Partnership teams that want the full field list with formats and validation rules can request our data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/minimal-payroll-input-schema-italian-employees.html · 2026-10-27
