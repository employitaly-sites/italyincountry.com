# Meal vouchers in Italian payroll: electronic vs paper daily limits

> How Italian meal voucher daily exemption limits differ for electronic and paper vouchers, and how payroll teams should model them in a platform.

Meal vouchers look simple. An employee gets a benefit, and payroll treats part of it as exempt. In Italy the detail sits in the daily limit, and that limit depends on the format of the voucher.

This article is for partnership, operations and payroll managers at global EOR and payroll platforms. It covers how the daily exemption works, where the two formats differ, and what your payroll logic needs to hold.

## Two formats, two daily limits

Italian meal vouchers come in two forms: electronic and paper. Each has its own daily exemption threshold.

- Electronic meal vouchers: EUR 10 per day.
- Paper meal vouchers: EUR 4 per day.

The gap is large. An electronic voucher can carry more than twice the exempt value of a paper one for the same working day. That is a policy choice, and it pushes employers toward electronic formats.

Both figures come from a secondary source, a specialist tax publication that summarises the recent budget law changes. Treat them as working values. Confirm them against the primary legal text before you hard-code them into production rules.

## What "daily exemption" means in payroll

The threshold is a daily amount. It is not a monthly pot that the employee can spend freely. Payroll has to compare the face value of the voucher for each day with the threshold for that format.

There are two outcomes for each voucher day.

- The face value is at or below the threshold. The benefit stays within the exemption.
- The face value is above the threshold. The excess does not benefit from the exemption and must be treated as ordinary taxable remuneration.

The excess is the part that creates errors. A platform that stores only a monthly voucher total cannot see it. It needs the daily face value and the number of days the voucher applies to.

## Why the format changes the calculation

The same face value can give different payroll results depending on the format.

Take a voucher worth EUR 7 per day. As an electronic voucher, it sits under the EUR 10 limit and is fully within the exemption. As a paper voucher, it is above the EUR 4 limit. The part over the limit is not exempt.

So the format is not a cosmetic field. It is an input to the tax and contribution treatment. If your data model drops it, you cannot compute the result correctly.

## What your payroll data model needs

For each employee and each pay period, a platform should hold at least the following.

- The voucher format: electronic or paper.
- The daily face value.
- The number of days for which vouchers were granted.
- The applicable daily threshold for that format.
- The source and the verification status of that threshold.

The last point matters. When a limit changes, you want to know which pay periods used the old value and which used the new one. Store the threshold with its source, not as a constant buried in code.

## Common operational mistakes

**Applying one limit to both formats.** A single flat threshold is the most common shortcut. It will be wrong for one of the two formats.

**Mixing formats inside a company.** Some employers move to electronic vouchers gradually. Employees on the same payroll can hold different formats. Your logic must work per employee, not per client.

**Ignoring the excess.** If the face value is above the threshold, the excess must flow into taxable pay. A silent cap that drops the excess understates remuneration.

**Treating a secondary source as final.** The figures here come from a secondary source. Build a review step so that a payroll specialist confirms the limit against the primary text before it goes live.

## What this means for EOR platforms

An EOR platform that hires in Italy carries the payroll risk for its clients. A wrong voucher treatment is not a client problem alone. It becomes a compliance problem for the platform.

The practical steps are short.

- Add the voucher format as a required field in the benefits record.
- Keep the daily thresholds in a versioned reference table with source and date of verification.
- Calculate the excess per day, then aggregate for the period.
- Show the exempt and taxable parts separately on the payslip preview, so clients and employees can see the split.
- Flag any benefit configuration where the face value exceeds the threshold, before payroll closes.

## Keeping the rules current

Daily thresholds are the kind of value that changes with budget laws. A platform that relies on manual updates will fall behind. A reference table with a clear source, a verification status and a change history lets your team update one record instead of hunting through code.

The current figures are EUR 10 per day for electronic vouchers and EUR 4 per day for paper vouchers. Both are marked as secondary until checked against the primary text.

## Summary

The voucher format decides the daily exemption. Electronic vouchers are exempt up to EUR 10 per day. Paper vouchers are exempt up to EUR 4 per day. Payroll must compare the daily face value to the right threshold and treat any excess as taxable. Store the format, the daily value, the days granted and the source of the threshold.

Partnership teams that want to exchange this data with us in a structured way can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/meal-vouchers-italy-payroll-electronic-vs-paper-limits.html · 2026-10-27
