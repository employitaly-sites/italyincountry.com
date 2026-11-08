# Daily contribution minimum: part-time payroll FAQ

> What the Italian daily contribution minimum is, how it is derived, and how it affects part-time payroll. A short FAQ for EOR and payroll platform teams.

Part-time contracts raise the same questions again and again in Italian payroll. One of them is the daily contribution minimum. This FAQ answers the questions that operations and payroll teams ask most often.

## What is the daily contribution minimum?

It is the lowest daily amount of pay on which social security contributions are calculated. The figure we use is EUR 58.13 per day. It is expressed as 9.5% of a reference amount of EUR 611.85.

The figure comes from a secondary source, a specialist tax publication. Treat it as a working value. Confirm it against the official INPS circular before you load it into a production payroll engine.

## How is the figure derived?

The calculation is simple. Take 9.5% of 611.85. The result is 58.13.

This matters for your data model. Do not store only the final daily amount. Store the reference amount and the percentage as well. When the reference amount changes, you can recompute the minimum and keep an audit trail.

## Why does the minimum exist?

Contributions must be paid on a pay base that is at least the minimum. If the contractual pay is lower than the minimum, the minimum is used for the contribution calculation. The employee's social security record is protected, and the contribution base never falls below a floor.

For a platform, this means the contribution base is not always the gross pay. A payroll run needs a comparison step. It checks actual pay against the minimum and uses the higher value.

## Why is it expressed per day?

The rule is built around days worked, not around monthly salary. This is the key point for part-time work. The minimum is tied to the working days in the period, so the number of days drives the result.

A monthly view hides this. Two employees can have the same monthly pay and a different number of working days. The check against the minimum can then give different results.

## How does part-time change the calculation?

There are two effects to keep in mind.

**Fewer working days.** A part-time employee who works fewer days in the month has fewer daily minimums to compare against. The floor for the month is lower than for a full-time employee.

**Lower pay per day.** A part-time employee who works every day but fewer hours earns less per day. Their daily pay can come close to the minimum, or fall below it. When it falls below, the minimum replaces the actual pay as the contribution base for that day.

The second case is the one that surprises teams. The employer pays contributions on more than the actual pay. The cost per euro of salary is higher than in a full-time contract.

## What should a platform check on a part-time contract?

Run these checks at onboarding and at every payroll cycle:

- Is the contract's working pattern recorded as days, hours, or both?
- Is the daily pay above or below the minimum?
- Does the number of working days match the days used in the calculation?
- Is the minimum used by the engine the current value, with a source and a date?

If the engine cannot answer these, the cost estimate you show to the client may be wrong.

## How does this affect cost quotes?

A quote for a part-time hire often uses a simple ratio. The full-time cost is scaled down by the part-time share. This is not always correct. When daily pay is near the minimum, the contribution cost does not scale down in the same way.

Give clients a cost estimate that includes the minimum check. A flat ratio is acceptable only when daily pay is clearly above the floor.

## What about changes over time?

The reference amount is updated periodically. When it changes, the daily minimum changes with it. Every stored value should carry a source and a date. A payroll engine that uses a hard-coded number will drift out of date without anyone noticing.

Plan for a small, versioned table of reference values. Each row holds the amount, the percentage, the derived daily minimum, the source, and the date it was checked. Payroll reads the row that applies to the period.

## What are the common errors?

- Using monthly pay to test against a daily floor.
- Counting calendar days instead of working days.
- Applying the full-time minimum to a part-time contract without checking the pattern.
- Rounding the percentage early. Compute from the reference amount and round only the final value.
- Keeping the figure without its source.

## What should you do next?

Start with the data. List the contracts in your portfolio that are part-time. For each one, record the working pattern and compare the daily pay with the minimum. The contracts near the floor are the ones where your cost estimates are most likely to be off.

Then check the process. Make sure the engine stores the reference amount, the percentage and the source. Make sure it compares pay with the minimum on every run.

Partnership teams that want to exchange these values in a structured way can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/daily-contribution-minimum-part-time-payroll-faq.html · 2026-10-27
