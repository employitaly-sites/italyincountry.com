# How to sample-test Italian gross-to-net calculations

> A recalculation method for auditors: rebuild Italian gross-to-net from the employee pension contribution, IRPEF brackets and employment tax credit.

Auditors do not need to rerun a whole payroll engine to test it. They need a small, repeatable recalculation that they can run on a sample and compare line by line. This article describes one for Italian gross-to-net.

The method covers the core of the calculation: the employee pension contribution, IRPEF and the employment tax credit. Local surcharges, other contributions and company-specific items are out of scope here. Test them separately.

## Start with the right sample

A random sample is not enough. Pick records so that every branch of the formula is exercised.

- Salaries at or below 15,000 a year.
- Salaries between 15,000 and 28,000.
- Salaries between 28,000 and 50,000.
- Salaries above 50,000.
- At least one salary inside the 25,000 to 35,000 band, where an extra credit applies.
- At least one fixed-term contract at a low salary, because the minimum credit differs.

Most errors sit at the edges. Add records just below and just above each threshold.

## Step: rebuild the employee pension contribution

The IVS rate for the employee is 9.19% of the contribution base. Take the base from the payslip, multiply, and compare with the amount shown.

If the difference is more than a rounding cent, stop. Check whether the base itself is right before you question the rate. A wrong base is more common than a wrong rate.

The IVS rate is one part of the employee contribution. If the payslip shows other employee contributions, test those against their own source. Do not fold them into this check.

## Step: derive the taxable income

Subtract the employee contribution from gross pay. The result is the starting point for IRPEF. Annualise it if you are testing a single month, and note which method the platform uses to do this. Annualisation is where monthly and annual results drift apart.

## Step: apply the brackets

IRPEF is progressive.

- 23% on income up to 28,000.
- 33% on the part between 28,000 and 50,000.
- 43% on the part above 50,000.

The rate applies to the slice, not to the whole income. A frequent defect is a platform applying the top rate it reaches to the full amount. Your recalculation will show it at once, because the gap grows with salary.

## Step: recompute the employment tax credit

This is the line that needs the most care. The credit depends on income and falls as income rises.

- Income up to 15,000: 1,955. The minimum is 690. For a fixed-term contract the figure is 1,380.
- Income from 15,000 to 28,000: 1,910 plus 1,190 times (28,000 minus income) divided by 13,000.
- Income from 28,000 to 50,000: 1,910 times (50,000 minus income) divided by 22,000.
- An extra 65 applies when income is between 25,000 and 35,000.
- Above 50,000 the credit is zero.

Subtract the credit from the gross IRPEF. Check that the result is not negative, and that the platform handles the case where the credit exceeds the tax.

Test the continuity of the formula. At 28,000 both middle formulas should give the same value. If the platform shows a jump at a boundary, the formula or the boundary is wrong.

## Step: close the loop

Net pay is gross minus the employee contribution minus net IRPEF, plus or minus the other items on the slip. Compare your net with the payslip net. Record the difference for each sampled employee.

## What to record

Keep the working simple. For each sampled employee, log:

- the inputs: gross, contract type, period;
- your recalculated contribution, taxable income, gross tax, credit and net;
- the platform values for the same lines;
- the difference and a short reason code.

Reason codes should be few. Rounding, wrong base, wrong bracket, wrong credit band, wrong contract flag. A short list makes patterns visible across the sample.

## Tolerance and escalation

Set the tolerance before you start. Rounding to the cent is acceptable. Anything larger is a finding. If the same reason code appears in more than one record, treat it as a systematic defect and widen the sample around that branch.

## Check your own source data

The parameters above come from secondary sources. Before you sign off an audit, confirm each rate, threshold and formula against the primary legal text for the period you are testing. Record the source and the date you checked. A recalculation is only as good as its parameters.

## Why this works

The method is small on purpose. It uses a few published parameters and plain arithmetic. An auditor can build it in a spreadsheet and run it again next period. Because it targets the branches of the formula, a small sample can still expose a wrong band or a wrong flag.

Partnership teams that want to make this testing easier can request the ItalyInCountry data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/sample-test-italian-gross-to-net-calculations.html · 2026-10-27
