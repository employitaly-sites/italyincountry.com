# Working hours, overtime and night work in Italy: an FAQ for platform ops teams

> Answers to the working time, overtime and night work questions that EOR and payroll platform ops teams forward from clients hiring in Italy.

Clients of global EOR and payroll platforms ask the same working time questions again and again when they hire in Italy. This FAQ collects them. It gives the structure of the answer and tells you which input your platform needs to capture. It does not give figures, because the figures depend on the contract and the collective agreement that applies. Those must come from a verified source for each case.

## Who sets the rules on working hours?

Three layers apply. National legislation sets the framework. The national collective agreement (CCNL) for the employee's sector fills in most of the detail. The individual contract can add terms, but only in the employee's favour.

The practical point: the same role can have different overtime rules depending on the sector. A software engineer and a warehouse operator hired by the same foreign company may fall under different agreements. Your platform should record the CCNL for each hire before it answers any hours question.

## Can the client set any schedule it wants?

No. The contract states the normal working time. The client can organise the schedule within that, and the CCNL may require notice or agreement for changes. Remote and hybrid arrangements do not remove these limits. Time spent working counts, wherever the employee sits.

Ops teams should ask clients for the intended schedule at onboarding, not after the first payroll run.

## What counts as overtime?

Overtime is work beyond the normal contractual hours. The CCNL defines the threshold, the maximum allowed, and the premium. Some agreements treat overtime as voluntary, others allow the employer to require it within limits. The premium is usually a percentage uplift on the hourly rate, and it often differs for weekday, night and holiday overtime.

Two questions come up constantly:

- **Can overtime be paid as a flat sum?** Not as a way to avoid the statutory or CCNL premium. A flat arrangement only works if it clearly covers at least what the rules would give.
- **Can overtime be replaced by time off?** Some agreements allow a time bank. It needs a written basis. Your platform should not assume it.

## Who is a night worker?

Night work is defined by a time window and by regularity. An employee who regularly works a set share of their hours inside the night window can qualify as a night worker. That status triggers extra obligations, including health checks and limits on the length of the night shift. It also affects pay, since the CCNL usually sets a night premium.

If a client asks whether an occasional late call makes someone a night worker, the answer is usually no. A scheduled rota that regularly includes night hours is different. Capture the rota, not just the contract.

## Are there employees who are exempt from these rules?

Some senior roles with real autonomy over their own time can fall outside parts of the working time rules. This is narrow. A job title does not decide it. The actual autonomy and the CCNL classification do. Do not let clients mark an employee as exempt on their own. Route it to review.

## What about rest and breaks?

Employees are entitled to daily rest, a weekly rest day and breaks during long working days. These are protected rights. A client cannot waive them in the contract. When a client's home-country practice differs, for example on being reachable out of hours, the Italian rules still apply to the Italian employee.

## How are hours recorded?

The employer must be able to show hours actually worked, especially where overtime or night work exists. Payroll needs a reliable feed. Typical gaps we see on platforms:

- No hours data for salaried staff, so overtime is never detected.
- Overtime approved by email but never sent to payroll.
- Shift changes agreed locally and not logged.
- Holiday and leave mixed into worked hours.

The fix is a simple monthly data exchange between the client system, your platform and the local payroll provider.

## What should the platform ask at onboarding?

Use a short checklist:

1. Applicable CCNL and employee level.
2. Contractual normal hours and schedule.
3. Whether overtime is expected, and who approves it.
4. Whether any shifts fall in the night window.
5. Whether the role is claimed to be autonomous in its working time.
6. How hours will be reported each month.

With these six answers, most client questions can be answered without escalation.

## When should a case be escalated?

Escalate when the CCNL is unclear, when a client wants to change the schedule mid-contract, when night work is proposed for an existing employee, or when an exemption is requested. These are the cases where a wrong default creates back-pay exposure.

## Why this matters for partners

Working time errors rarely appear at hire. They appear months later as a payroll correction or a dispute. A clear intake and a clean hours feed prevent most of them. That protects your margin and your client relationship.

Partnership teams can request our data-exchange specification to see how hours, overtime and night work data flow between your platform and ours.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/italy-working-hours-overtime-night-work-faq.html · 2026-10-27
