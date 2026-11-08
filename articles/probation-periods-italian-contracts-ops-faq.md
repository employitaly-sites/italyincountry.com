# Probation Periods in Italian Contracts: An Ops FAQ

> How probation length depends on the CCNL and job level in Italy, and how payroll and partnership ops teams can track end dates without missing them.

Probation in Italy looks simple until you run it at scale. The length is not a global default. It depends on the collective agreement (CCNL) that applies to the employee, and often on the job level inside that agreement. This FAQ covers what ops teams ask most.

## Who sets the probation length?

The applicable CCNL sets the maximum. The individual contract then states the actual period. The contract value can be shorter than the CCNL maximum. It cannot be longer.

The period must be agreed in writing before the employee starts work. If it is missing from the signed contract, there is no probation. This is the most common gap we see in contracts that arrive from foreign templates.

## Why do durations differ by CCNL?

Each CCNL was negotiated by a different sector and a different set of parties. Commerce, metalworking, IT services and hospitality each define their own scale. Within one CCNL, the period usually grows with seniority. A junior role gets a shorter period. A manager gets a longer one.

So you cannot store a single country-level value. You need a lookup keyed on at least two fields: the CCNL and the job level. Some agreements also distinguish between categories of staff, so keep that field open.

## What data do we need to compute the end date?

Keep these fields for every employee:

- CCNL name and version in force
- Job level as written in the contract
- Start date
- Probation length stated in the contract
- Unit of the length (days, weeks or months)
- Whether the CCNL counts calendar days or working days

The last two fields cause most errors. A period in months and a period in working days give different end dates. Store the unit with the value, never a bare number.

## How do we calculate the end date?

Take the start date and add the contractual period in the unit the CCNL uses. If the CCNL counts working days, you need an Italian holiday calendar and a rule for weekends. Check how the agreement treats public holidays and days of absence before you automate anything.

Write the rule per CCNL, not per employee. Then test it against a sample of real contracts that your Italian payroll team has already confirmed by hand.

## Does sickness or leave pause probation?

It can. Some agreements suspend or extend the period when the employee is absent for certain reasons. Others do not. This is a CCNL-level rule and it must be in your lookup table as a flag, with a note on the source clause.

If your system only stores a fixed end date, an absence will silently make that date wrong. Store the original end date and a recalculated end date as two separate fields. Show both to ops.

## What happens at the end of probation?

During probation, either side can usually end the contract with much lighter notice rules than normal. After it ends without a decision, the employment continues as a standard contract and the employee keeps the time already served for seniority.

This matters for your calendar. A decision to confirm or end the role has to be taken before the end date, not after. Waiting for the date to pass is a decision, and a costly one.

## How early should alerts fire?

Set more than one alert. A first alert gives the client time to run a review. A second alert is a final reminder to the account owner and the payroll lead. Choose the lead time per client, since review cycles differ. Send alerts to a shared queue, not to one person's inbox.

## What should partnership teams ask us?

When you integrate with an Italian EOR, ask for these items in writing:

- The CCNL and level for every employee, as structured fields
- The contractual probation length and unit
- The computed end date and the rule used
- A flag for any suspension or extension event
- A change log when the end date moves

If a provider can only send a PDF of the contract, your team will re-key dates by hand. That is where mistakes start.

## What are the common failure points?

- Using a default length when the CCNL was not captured
- Mixing calendar days and working days
- Treating the contract template as proof of probation, when the signed copy has no clause
- Ignoring absences that move the end date
- Alerting after the date instead of before it
- Updating a CCNL table without versioning, so old contracts are recalculated under new rules

Each of these is a data problem, not a legal puzzle. Clean fields and versioned rules remove most of them.

## A practical setup

Build one table of CCNL, level, maximum period, unit, counting rule and suspension rule. Add a source reference and a review date to every row. Link each employee record to a row by key, not by free text. Recalculate on any change and keep the history.

Then reconcile monthly. Compare your computed end dates with the ones the Italian payroll team holds. Investigate every mismatch. After a few cycles the mismatches should be rare, and the ones left will point to real gaps in the contract data.

Partnership teams that want to exchange these fields automatically can request the data-exchange specification from us.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/probation-periods-italian-contracts-ops-faq.html · 2026-10-27
