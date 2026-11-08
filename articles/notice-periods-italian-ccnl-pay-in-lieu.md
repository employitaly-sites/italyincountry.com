# Notice periods under Italian CCNLs: how notice is set and paid in lieu

> How Italian CCNLs set notice periods, who must give notice, and how pay in lieu works. A guide for EOR and payroll platform partnership and operations teams.

Notice is one of the first questions a global payroll platform asks when it works with Italy. The answer is not in one statute with a single table. It sits mostly in the national collective agreement, the CCNL, that applies to the employee. This article explains how notice is set and how pay in lieu works, so your teams know what data they need before they quote or process a termination.

## Where the rule comes from

Italian law sets the principle. A party who ends an open-ended contract must give notice. The length of that notice is left largely to collective agreements, custom and, where they exist, individual terms that are not worse for the employee.

In practice, the CCNL is the working source. It states the notice period and how it is calculated. You cannot read the notice period from the country alone. You need the agreement.

## Which CCNL applies

The sector and the employer's activity usually decide which CCNL applies. The contract of employment normally names it. Payslips and the employer's registrations also point to it.

Two employees in the same city can have different notice rules because they sit under different agreements. For a platform with many clients, this means notice cannot be a country-level default. It has to be a field linked to the agreement and the employee's classification.

## What drives the length of notice

Most CCNLs build notice from the same few inputs:

- The employee's classification level (inquadramento). Higher levels usually carry longer notice.
- Length of service with the employer. Notice usually grows as seniority grows. Agreements often use bands of service.
- Who ends the contract. Many agreements set a different period for resignation than for dismissal by the employer. The employee's period is often shorter.
- The type of role. Managers (dirigenti) follow their own agreements, with their own rules and often their own protections.

The agreement states these in tables or articles. Your system should store the table, not a summary. Summaries lose the bands and the exceptions.

## How notice is counted

The CCNL also says when notice starts and how the period is measured. Some agreements count in calendar units and start the period from a fixed point, such as the start of the next month or the next half-month. Others count from the day after the written notice is received. The difference changes the last working day.

Notice must be in writing. For resignation, Italy also has a digital procedure for validating the employee's resignation. Operations teams should treat the date of valid communication as the key date and record it with evidence.

## Working the notice period

By default, the employee keeps working during notice. The employment relationship continues in full. Salary, contributions and accrual of leave and other rights go on as normal. Holiday cannot be freely used by the employer to shorten notice unless the parties agree.

## Pay in lieu of notice

If the party ending the contract does not want the notice to be worked, or cannot give it, the law and the CCNL provide for an indemnity in place of notice (indennità sostitutiva del preavviso).

Points that matter for payroll:

- The indemnity is owed by the party who fails to give or work the notice. An employer who ends the contract with immediate effect owes it to the employee. An employee who leaves without working notice can owe it to the employer, and the employer can deduct it where the rules allow.
- The amount is based on the pay the employee would have received during the missing notice. The CCNL defines which pay elements count. This often includes more than base salary, such as regular additional pay items. Check the agreement for the exact list.
- The period used is the notice period the agreement would have required. That is why the length rules above must be correct first.
- The indemnity is generally treated as remuneration for contribution and tax purposes. It also affects the calculation of the end-of-service payment (TFR) and related items in the way the rules and the CCNL provide. Do not assume it is a flat, untaxed sum.

A dismissal for just cause is a separate case. Where the cause is so serious that the relationship cannot continue, notice is not due. The label used in the termination letter and the facts behind it matter, and an error can turn into a dispute.

## Final settlement items

On exit, the final payslip normally brings together several items: pay up to the last day, unused leave, accrued additional monthly pay, TFR and any indemnity in lieu. Notice is only one line, but it often sets the last day that all other lines depend on. A wrong notice date moves everything.

## What platforms should collect

To calculate notice and pay in lieu without manual research, a platform needs structured data per employee:

- The applicable CCNL and its version
- Classification level
- Start date and service history, including any recognised prior service
- Who ends the contract and the reason
- Date of valid written communication
- The pay elements the CCNL includes in the indemnity base
- Any individual terms more favourable than the CCNL

With these fields, notice becomes a lookup and a calculation. Without them, it becomes a case-by-case legal question each time.

## Practical advice

Keep the CCNL tables as versioned data with the source and the date checked. Agreements are renewed, and notice terms can change at renewal. Show the user which version produced a figure.

Flag edge cases for review rather than guessing. These include managers, mixed pay structures, long service and disputes over cause.

Partnership teams that want to exchange this data with us in a structured way can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/notice-periods-italian-ccnl-pay-in-lieu.html · 2026-10-27
