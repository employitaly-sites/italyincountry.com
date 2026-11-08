# How to model the full Italian employment cost for client quotes

> A practical way to build an Italian employment cost quote by combining gross salary, employer contributions and accruals in separate, auditable layers.

A client asks for a quote to hire one person in Italy. The number they expect is the full cost to the employer. The gross salary is only the start.

If your quote engine treats salary plus a flat uplift as the answer, you will misprice. Some quotes will be too low and you will absorb the gap. Others will be too high and you will lose the deal. A better approach is to model the cost in separate layers, each with its own source and its own review date.

## Layer one: gross salary

Start with the contractual gross pay. In Italy this is not only a negotiated figure. The national collective agreement (CCNL) for the sector sets minimum pay by job level. It also defines how many monthly payments the employee receives in a year, and which allowances apply.

Your model should store the CCNL, the job level and the number of payments as explicit inputs. Do not hard-code them. Two roles with the same headline salary can produce different total costs because the CCNL structure differs.

## Layer two: employer contributions

Employer social contributions are calculated on the taxable base. They are not a single rate. They are a set of components, each with its own rule.

The largest component is the IVS contribution, which covers invalidity, old age and survivors. Our current figure for the employer share of IVS is 23.81% of the taxable base. This comes from a secondary source, so treat it as a working value. Confirm it against the official social security circular before you publish a quote that depends on it.

Other components exist on top of IVS. Their rates depend on company size, sector and the specific CCNL. Keep each one as its own line in the model. A single blended rate hides errors and makes it hard to explain a quote to a client's finance team.

## Layer three: workplace injury insurance

Insurance against workplace accidents and occupational disease is handled by INAIL. The premium depends on the risk classification of the work performed, not on the company in general. An office role and a warehouse role in the same company carry different rates.

The tariffs set by the Interministerial Decree of 27/02/2019 for 2019 remain in force. The way they are applied was changed by a ministerial decree dated 02/04/2026, published on 03/06/2026. For a quote, this means two things. First, you need the correct risk classification for each role. Second, you should check whether the new application rules change the premium for that classification, for example through reductions linked to the company's track record.

Do not carry a single INAIL rate across all roles. Model it per classification, and record the decree reference next to the rate.

## Layer four: accruals

Some costs are not paid in the month they arise. They build up and are paid later. A quote that ignores them looks cheap and then fails at the first payroll close.

The main accruals are:

- Severance pay (TFR), set aside every month and paid when employment ends.
- Paid leave and holiday entitlement that the employee earns over time.
- Additional monthly payments, where the CCNL provides for them.

Each accrual also carries its own contributions where the law applies them. Model the accrual and the related charge together, so the monthly view and the annual view reconcile.

For the client, make the accrual visible. Show it as a separate line, labelled as a provision. A client who sees it up front is less likely to question it later.

## Keep sources and dates attached to every rate

Each rate in the model should carry three fields: the value, the source and the date it was last checked. When a rule changes, as the INAIL application rules did, you can find every quote that depends on it.

Mark the status of each source. A value from a secondary source should be flagged until it is confirmed against the primary one. This costs little and protects you when a client challenges a number.

## Build the quote from the layers

A clean quote follows the same order as the model:

- Gross salary and the CCNL inputs behind it.
- Employer contributions, shown by component.
- Injury insurance, shown by risk classification.
- Accruals, shown as provisions.
- The total, with the date the rates were last verified.

This structure makes the quote easy to audit. It also makes updates cheap. When one rate changes, you change one line, not the whole formula.

## What to avoid

Avoid a flat percentage on top of salary. It is quick, but it cannot tell a client why the number changed after a rule update. Avoid mixing paid and accrued costs in one figure. Avoid rates without a source.

The goal is a quote you can defend line by line. For partnership and operations teams, that is what keeps a margin intact and a client relationship calm.

Partnership teams that want to plug this cost model into their own quoting flow can request our data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/model-full-italian-employment-cost-client-quotes.html · 2026-10-27
