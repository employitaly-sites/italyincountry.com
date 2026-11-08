# Why Italian payroll runs on a thirteenth and sometimes fourteenth month

> How Italian additional monthly payments work, why they are an accrual and not a bonus, and what platforms must model so pricing matches real payroll cost.

Many global payroll platforms quote Italy as a simple monthly salary. Then the first year closes and the real cost does not match the quote. The reason is the additional monthly payments, known in Italy as the thirteenth and, in many sectors, the fourteenth month.

This article explains how they work, so your pricing and accruals can reflect them from the first payslip.

## What they are

The thirteenth and fourteenth month are not bonuses. They are part of the annual pay of the employee. Italian pay is often described as annual compensation split into more installments than calendar months. A gross annual figure agreed with a candidate is therefore not divided by the number of months in a year. It is divided by the number of installments the contract and the collective agreement provide.

This is the first point where platforms go wrong. If the offer letter says annual gross, the monthly figure on the payslip is lower than a simple monthly split would suggest. If the offer says monthly gross, the annual cost is higher than a simple multiplication would suggest. Both are valid. They must not be mixed.

## Where the rules come from

The thirteenth month is established by law and by national collective agreements. The fourteenth month is different. It does not apply to every employee. It comes from the national collective agreement (CCNL) that covers the employee's sector and, in some cases, from company-level agreements or individual contracts.

So you cannot answer the question "does this employee get a fourteenth month" at country level. You answer it per agreement, per job level, and sometimes per employer. Your data model needs the applicable agreement as an input, not as a note.

## How the installments accrue

Each additional payment accrues month by month during the reference period. The employee earns a share of it for each month worked. The payment itself is made later, at the time the agreement sets.

This has three consequences for finance and operations teams.

- **Cost is incurred monthly, cash leaves later.** If you book the cost only when the payment is made, your monthly margin looks better than it is, and the payment month looks worse. Accrue monthly.
- **Partial periods are pro rata.** An employee who joins or leaves part way through the reference period earns only the accrued share. Your engine needs a clear rule for part months.
- **Termination settles the balance.** When employment ends, any accrued but unpaid share is paid out in the final settlement. A client who offboards an employee early still owes it.

## Contributions follow the payment

The additional installments are part of taxable and contributory pay. Employer social contributions apply to them, as they do to ordinary salary. When you price the employer cost of an Italian hire, the contribution base includes all installments, not only the twelve ordinary monthly payments.

A quote that applies the employer contribution rate to twelve payments, and then adds the extra installments without contributions, understates cost. Apply the contribution base to the full annual pay.

## Absence, leave and unpaid periods

Periods of absence can reduce or change the accrual, depending on the type of absence and the agreement. Some absences are covered by social security or by the employer for accrual purposes. Others reduce the share earned. Do not assume one treatment for all. Map absence types to accrual effect per agreement, and keep the mapping versioned.

## What platforms should model

A practical data model for Italy needs the following fields.

- The applicable national collective agreement and the job level.
- The number of installments per year under that agreement.
- The payment timing of each additional installment.
- The accrual rule for partial periods and for absences.
- The contribution base, which includes all installments.
- A clear flag on whether the client's offer is stated as annual or as monthly gross.

With these fields, the quote, the payslip, the accrual ledger and the final settlement all use the same logic. Without them, each system makes its own assumption and the differences surface at year end.

## Common mismatches we see

- Quote built on a monthly split, payroll run on the contractual installments.
- Accrual booked at payment instead of monthly.
- Fourteenth month assumed for everyone, or for no one.
- Employer contributions calculated on ordinary pay only.
- Final settlement missing the accrued share.

Each of these is easy to fix once the agreement and installment count are captured as data. None is easy to fix after clients have signed on a wrong number.

## The practical point

Italian payroll is not complicated because of one rule. It is complicated because the rule depends on the agreement. Treat the agreement as a primary key, accrue monthly, apply contributions to the full annual pay, and your Italian pricing will match what payroll actually costs.

Partnership teams that want to align their models with ours can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/italian-payroll-thirteenth-fourteenth-month.html · 2026-10-27
