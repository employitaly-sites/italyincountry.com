# How TFR accrual works and how to report it to partners

> How monthly TFR accrual, annual revaluation and fund choices work in Italy, and how to structure the data you send to your EOR partner.

TFR is the Italian end-of-service allowance. It is not a bonus and it is not a severance payment triggered by dismissal. Every employee builds it up during employment, and it is paid when the employment ends, whatever the reason. For a global payroll platform, it is a liability that grows on every payslip and has to be visible in your reports.

This article explains how the accrual works, how it is revalued, where it can sit, and what your Italian partner should send you each month.

## Monthly accrual

TFR accrues from pay. Each year, a share of the employee's eligible annual remuneration is set aside. The payroll calculates this share month by month, so the amount appears in every pay cycle even though nobody is paid anything at that moment.

Three points matter for reporting.

- The base is not the same as gross pay. Collective agreements and the law decide which pay elements count. Some items are excluded. Others are included even when they are paid irregularly.
- Unpaid absences can change the accrual. Some absences reduce it. Others, such as statutory leave, keep it running. Your partner should flag these months.
- Accrual is a cost for the employer in the month it arises, even if the cash stays in the company or goes to a fund.

If your platform shows total employment cost, TFR must be in it. A common error is to treat TFR as a leaving cost and book it only at termination. That understates cost during the whole employment and creates a large surprise at the end.

## Revaluation

The balance already accrued is revalued every year. The revaluation has a fixed part and a variable part linked to the national consumer price index. The result is added to the balance. A substitute tax applies to the revaluation, and it reduces the net amount added.

For reporting, keep these items apart:

- opening balance for the period
- new accrual from payroll
- revaluation gross
- substitute tax on the revaluation
- closing balance

Partners often send a single closing balance. That is not enough for audit. You cannot reconcile a balance you cannot rebuild. Ask for the movements, not only the total.

Revaluation is calculated on a year basis, so a mid-year exit gets a pro-rata treatment. Your partner should state the method in the exit report.

## Where the TFR sits: fund options

The employee decides where future accrual goes. There are two main routes.

**Stay with the employer.** The amount accrues on the company books. Depending on the size of the employer, it either stays in the company or is transferred monthly to a public treasury fund managed by the social security institute. In both cases the employee keeps the right to the amount. Only the place where the liability sits changes.

**Move to a pension fund.** The employee can direct the accrual to a supplementary pension scheme. This can be a negotiated fund linked to the collective agreement, an open fund, or an individual pension plan. The employer then pays the accrual to the fund on a regular schedule, and the balance is no longer a company liability.

If the employee makes no choice within the legal window after hire, the law treats this as a tacit choice. The accrual then goes to the pension fund set by the applicable agreement or, failing that, to a default option. This is the point where onboarding errors happen. A missed election form can send contributions to the wrong place for months.

For your platform this means each employee record needs a TFR destination field with a valid status, a start date for the election, and the name of the fund where relevant. When the destination changes, the history must remain readable.

## What to ask your partner to report

A workable monthly data set is short. For each employee and each pay period:

- TFR base for the month
- accrual amount
- destination: company, treasury fund, or named pension fund
- amount paid to the fund in the period, if any
- advances paid to the employee against the balance

Once a year, add the revaluation and tax breakdown listed above, plus the closing balance reconciled to the ledger.

At exit, ask for a final statement. It should show the full balance, any advances already paid, the tax treatment applied, and the amount paid out. Termination payments are the moment when gaps in earlier reporting show up, so this statement is where your finance team will test the whole chain.

## Advances

Employees can ask for an advance on their TFR in defined cases, such as buying a first home or covering medical costs. An advance reduces the balance. If your partner does not report advances, your balance will drift from theirs. Treat advances as their own movement type, with a date and a reason code.

## Practical checks

A few controls prevent most disputes.

- Reconcile the closing balance to opening balance plus movements every year.
- Compare accrual to the base each month. A sudden drop usually means an absence code or a contract change.
- Check that every employee has a recorded destination before the first payroll.
- Keep the applicable collective agreement on each record, since it affects both the base and the default fund.

TFR is predictable once the data is structured. The problems come from totals without movements and from missing election records.

Partnership teams that want a field-level layout for these reports can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/tfr-accrual-reporting-partners.html · 2026-10-27
