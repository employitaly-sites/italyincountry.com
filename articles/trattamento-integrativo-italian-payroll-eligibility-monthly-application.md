# Trattamento integrativo: when Italian payroll adds it

> How Italian payroll applies the trattamento integrativo: who may get it, what operators must check each month, and what to pass between platforms.

The trattamento integrativo is a small payment that Italian payroll can add to an employee's net pay. It is easy to miss. It is also easy to apply when it should not apply. For a global EOR or payroll platform, both errors reach the employee and the employer. This article looks at it from the operator's side: who qualifies, how the monthly run handles it, and what your platform needs to hand over.

## What it is

The trattamento integrativo is a benefit for employees with low income. The reference figure we use is up to 1,200 EUR per year, for employees with income up to 15,000 EUR, and subject to conditions. That is the whole headline. The details sit in the conditions.

The source for these figures is a secondary one. Treat the figures as a guide for planning and confirm them against the current official rules before you build logic around them.

## Why the operator cares

The payment is not a request from the employee. Payroll is expected to look at the position and apply it when the conditions are met. If payroll skips it, the employee loses money during the year. If payroll applies it and the conditions were not met, the amount may have to be recovered later. Neither outcome is good for a service whose value is that payroll just works.

For a foreign company hiring in Italy, this is a typical surprise. Their home payroll has no equivalent. The employee earns a modest salary, sees an extra line on the payslip, and the client asks what it is.

## Eligibility from the operator's view

The test is about the employee's income level and their tax position. Three things matter in practice.

**Expected annual income.** The ceiling is 15,000 EUR. Payroll has to estimate income for the year, not just look at one month. A part-time contract, an unpaid leave period or a mid-year start all change that estimate.

**Tax position.** The payment is linked to the employee's income tax situation. An employee with no tax due in the year is treated differently from one with tax due. Your payroll provider's rules decide how this is read. You should not guess it from the gross salary alone.

**Other income.** An employee may have more than one employer, or other income, during the year. Payroll sees only its own employment unless told otherwise. This is the main source of wrong results.

Because the figure is conditional, a simple salary threshold is not enough. Do not build a rule in your platform that says: salary below the ceiling, so the benefit applies. Let the Italian payroll engine decide, and make sure it has the facts it needs.

## Monthly application

The benefit is applied through the monthly payroll run. The yearly maximum is the cap. The monthly amount is a share of what the employee is expected to receive over the year, adjusted as the year goes on.

What this means for your process:

- Each run should recalculate the position, not copy the previous month.
- A change in contract hours, pay or start date can change the monthly amount.
- At year end, payroll compares what was paid with what was due. A difference can show up as an adjustment.

Operators should expect the line to appear, disappear and change size during the year. That is normal behaviour, not an error. The error is when nobody can explain why.

## What can go wrong

**Mid-year hires.** The employee joins and payroll has no income history. The estimate rests on the new contract alone. If the employee had income earlier in the year, the estimate is too low.

**Unreported second jobs.** Payroll applies the benefit. The employee's total income is above the ceiling. The mismatch appears later.

**Variable pay.** Bonuses and overtime push income up. A benefit applied in earlier months may no longer fit. Payroll must be told about expected variable pay as early as possible.

**Gross-to-net quotes.** If you quote net salary to a client or candidate, state clearly whether the quote includes the benefit. A quote that includes it can be wrong later if the conditions stop being met.

## What to pass between platforms

If your platform sits in front of Italian payroll, the data you send decides the outcome. At minimum, send:

- contract start date and end date
- working hours and gross pay
- expected variable pay
- a declaration from the employee about other employment or income in the year
- any change to these items, with its effective date

Also agree on what comes back. Payroll should return whether the benefit was applied, the amount for the period, and the amount to date. That lets your support team answer questions without opening a ticket with the payroll provider.

## A practical checklist

- Do not hard-code the 1,200 EUR figure or the 15,000 EUR ceiling. Keep them as data with a source and a review date.
- Show the line on the payslip preview, with a short plain explanation for the client.
- Flag employees near the income ceiling. These are the cases most likely to change during the year.
- Ask new hires about other income at onboarding, and again when pay changes.
- Keep an audit trail of what was told to payroll and when.

The trattamento integrativo is small compared with other payroll items. It still generates many questions, because it is conditional and because it moves during the year. A clean data flow removes most of them.

Partnership teams that want to align on this can request our data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/trattamento-integrativo-italian-payroll-eligibility-monthly-application.html · 2026-10-27
