# How to Set Up Regional and Municipal Surtaxes for a Distributed Italian Workforce

> Residence data decides which regional and municipal surtax applies to each Italian employee. Here is how to model it in your payroll platform.

Italian payroll does not stop at national income tax. Each employee also owes a regional surtax and a municipal surtax. Both depend on where the employee lives. For a distributed workforce, residence data is therefore a payroll input, not an HR detail.

This article explains how to set it up so that withholding is right in every city.

## Why residence drives the calculation

The employer withholds the surtaxes from salary. The rate comes from the employee's municipality of residence and the region it belongs to. The work location does not set the rate. Two colleagues on the same team can pay different amounts because they live in different cities.

This matters for global platforms because remote and hybrid teams rarely sit in one place. A company with staff in Milan, Rome, Turin, Bologna and Naples has five different municipal setups before regional rules are counted.

## What the municipal rates look like

Municipal rules differ in two ways: the rate and the exemption threshold. The figures below come from a published comparison of main city rules. They are a secondary source. Check each against the municipal resolution before you load it.

| City | Rate | Exemption threshold |
|---|---|---|
| Milan | 0.8% flat | EUR 23,000 |
| Rome | 0.9% flat | EUR 14,000 |
| Turin | 0.8% / 0.8% / 1.1% / 1.2% (4 brackets) | EUR 11,790 |
| Bologna | 0.8% flat | EUR 15,000 |
| Naples | 1% flat | EUR 12,000 |

Three things stand out.

First, the rates are close, but the thresholds are not. Milan sits at EUR 23,000 and Turin at EUR 11,790. An employee at a given income can owe nothing in one city and a real amount in another.

Second, most cities use one flat rate. Turin uses four brackets. Your engine must support both a single rate and a bracket table.

Third, the table shows the headline rule only. The rate for a given employee still depends on how each city applies its threshold to that person's income. Store that logic as data, not as code.

## Regional surtax

The regional surtax follows the same principle. The region of residence sets the rule, and rules differ between regions. This article gives no regional figures, because none are in the verified data used here. Load them from each region's official publication and record the source and date.

## How to model it

Treat the surtaxes as a lookup keyed on residence, not as a field typed into payroll.

1. **Capture residence as structured data.** Store the municipality by its official code, not as free text. "Milano", "Milan" and "MI" must resolve to one record.
2. **Link municipality to region.** Derive the region from the municipality. Do not ask for it separately. Two inputs can disagree. One derived value cannot.
3. **Keep a rate table per municipality.** Each record holds the rate type (flat or bracketed), the rates, the bracket limits where they exist, and the exemption threshold.
4. **Version every rule.** Each row carries its source link and the date you checked it. When a city changes a rate, you add a row. You do not overwrite the old one.
5. **Resolve the rate at calculation time.** The payroll run reads the employee's current residence and the rule in force for that period.

## Handling changes of residence

Employees move. A change of address is a payroll event. It should trigger a new lookup and, where needed, a recalculation. Build a flag that fires when the residence record changes. Without it, the old city's rate keeps applying and you find the error at year end.

Ask employees to confirm residence at onboarding and whenever their address changes. Keep the confirmation date on file.

## Controls worth adding

- **Missing residence.** Block the payroll run, or fall back to a clearly marked default, until the field is filled.
- **Unknown municipality.** Reject codes that are not in your table. Do not guess.
- **Bracket tables.** Test Turin-style rules with incomes on each side of every bracket limit.
- **Threshold cases.** Test incomes just below and just above each exemption threshold.
- **Source audit.** Report every rule whose source check is older than your review cycle.

## What partnership teams should agree on

If you run an EOR or payroll platform and work with a local provider, define the data contract early. Agree on these points:

- The residence fields you send and their format.
- Who owns the rate table and who updates it.
- How a residence change is notified.
- How rule sources and check dates are shared.

A clear contract keeps city-level withholding correct as headcount spreads across Italy. It also makes errors traceable. When a payslip is questioned, you can show the residence on record, the rule applied and the source behind it.

Partnership teams can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/regional-municipal-surtaxes-distributed-italian-workforce.html · 2026-10-27
