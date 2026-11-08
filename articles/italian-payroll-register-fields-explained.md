# Italian payroll register fields explained for non-Italian finance teams

> A column-by-column guide to the Italian payroll register, so finance teams at EOR and payroll platforms can reconcile it with their own ledgers.

An Italian payroll register does not look like a payslip from other countries. The labels are Italian. The contribution lines are split by fund. Some columns have no equivalent in your ledger.

This guide goes through the register column by column. The goal is reconciliation: matching each Italian field to a line in your platform.

## Identity and contract columns

The register starts with the worker's tax code (codice fiscale). This is the key for every filing. Use it as the primary match field, not the name.

Next come the contract level (livello) and the collective agreement (CCNL). Both drive the minimum pay and many of the other columns. If your platform stores only a job title, you will not be able to explain a pay difference. Store the agreement and the level as separate fields.

The hire date and the contract type also sit here. They decide which contribution rules apply.

## Pay elements

The gross side is made of several lines, not one salary figure.

- **Minimo tabellare**: the minimum base pay set by the collective agreement for the level.
- **Scatti di anzianità**: seniority increments, where the agreement provides them.
- **Superminimo**: any amount agreed above the minimum. It is contractual and can usually be absorbed in later increases.
- **Straordinari and maggiorazioni**: overtime and premiums, shown as separate lines.
- **Indennità**: allowances, such as for travel or role.

For reconciliation, map each line to its own account. Do not collapse them into base salary. Auditors and local advisers will ask for the split.

## Contribution columns

Social security is paid to INPS. The register shows two sides: the share withheld from the worker and the share paid by the employer.

The main fund line is IVS, which covers invalidity, old age and survivors. In our verified data, the employee share is 9.19% of the taxable base (quota imponibile). The employer share is 23.81% of the same base. Both figures come from a secondary source, so confirm them against the current INPS circular before you hard-code them.

Two points matter for your ledger.

- The employee share is a deduction from gross pay. The employer share is an extra cost on top of gross pay. Post them in different places.
- The register can show more contribution lines than IVS. Sector, company size and contract type add lines. A single combined rate in your system will not match the register.

## Occupational injury insurance

INAIL covers workplace injury and occupational disease. It is an employer cost. It appears in the register as a premium line or in the employer cost summary, depending on the software.

The tariff in force is the 2019 tariff (DI 27/02/2019). The rules on how it is applied were changed by DM 02/04/2026, published on 03/06/2026. If you model INAIL cost, check that your application logic reflects the new method. A rate table alone is not enough.

## Taxable base and withholding

The register shows the taxable base for income tax after the employee contributions are deducted. From it the employer calculates the income tax withheld at source (IRPEF), plus regional and municipal surtaxes where they apply.

The order matters. Gross pay, then employee contributions, then taxable base, then tax, then net. If your platform computes tax on gross, the register will not match.

Many registers also show adjustments from the annual reconciliation (conguaglio). These can raise or lower net pay in a given month. Treat them as a separate reconciling item and not as an error.

## Deferred pay and severance

The register tracks accruals that have no cash effect in the month. The main one is TFR, the Italian severance fund. An amount accrues each period and is paid out when employment ends, or is transferred to a pension fund if the worker chose that.

Platforms often miss this line because no cash moves. It is still a liability. Book it as an accrual and keep the running balance per worker.

Leave and permit balances are shown the same way. They are balances, not payments.

## Net pay and payment

The last columns give net pay, the payment date and the bank reference. Net pay is the result of every line above. Match it last, after the gross, contribution and tax lines agree.

A good order for reconciliation:

1. Match workers by tax code.
2. Match contract level and agreement.
3. Match each gross pay line.
4. Match employee and employer contribution lines separately.
5. Match the taxable base and the withholding.
6. Match accruals.
7. Match net pay.

If a step fails, stop and fix it before moving on. Errors in early steps carry into every later one.

## What to ask your Italian provider

Ask for the register in a structured format, not only as a PDF. Ask for the field dictionary. Ask which contribution codes appear and how they map to funds. Ask how the provider handles rate changes during the year.

These answers decide whether your reconciliation can run automatically or needs a person each month.

Partnership teams are welcome to request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/italian-payroll-register-fields-explained.html · 2026-10-27
