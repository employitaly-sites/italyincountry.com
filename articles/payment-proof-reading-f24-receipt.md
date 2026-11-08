# Payment proof: reading an F24 receipt

> What an F24 receipt proves for Italian payroll payments, what it leaves open, and how platforms can reconcile it with their own records.

Every month, a payroll platform asks the same question about Italy. Were the taxes and social contributions actually paid? The usual answer is a PDF called the F24 receipt. It looks final. It is useful. But it proves less than most teams assume.

This article explains what the receipt shows, what it does not show, and how to build a reliable check around it.

## What the F24 is

The F24 is the Italian unified payment form. One form can carry many different charges. Withholding tax, social contributions and regional or local taxes can all sit on the same payment. Each line carries a code that tells the authorities what the money is for, plus the period it refers to.

That structure matters. A single receipt is rarely a single payment obligation. It is a bundle.

## What the receipt proves

A proper receipt, issued after the payment is processed, proves a limited set of facts.

- A payment was submitted and accepted through a bank or an online channel.
- A named taxpayer, identified by tax code, was the payer.
- The total amount was debited.
- Specific lines were paid, each with its own code, period and amount.
- The payment happened on a recorded date.

This is real evidence. If a client asks whether the money left the account, the receipt answers it. If an auditor asks which codes were used, the receipt answers that too.

## What the receipt does not prove

This is where teams get into trouble.

**It does not prove the right amount was paid.** The receipt shows what was paid. It does not show what was due. If the payroll calculation was wrong, the receipt will faithfully record a wrong payment.

**It does not prove the right people were covered.** The form does not list employees. A payment for a whole payroll run looks the same whether it covers every worker or only some of them. The link between the money and the individual payslips lives in your payroll data, not on the receipt.

**It does not prove the right entity paid.** The payer is whoever is named on the form. In a multi-entity setup, a payment made under the wrong tax code can look perfectly valid and still fail to settle the obligation you care about.

**It does not prove the period is correct.** The period reference is typed in by whoever prepared the form. A typo or a wrong reference can send a valid payment to the wrong month. The receipt will not flag it.

**It does not prove the authorities have allocated the money as intended.** Acceptance of a payment and correct allocation to the right position are separate steps. Problems can surface later, through notices or mismatches in the taxpayer's account.

**It does not prove compliance on its own.** Paying is one part of the obligation. Filing and reporting are others. A receipt covers only the payment.

## Common failure patterns

In practice, the gaps above show up in a few repeatable ways.

A receipt is attached to the wrong month. The file name says one period, the codes inside say another.

A payment is split across several forms, and only one receipt reaches the client. The total looks short.

A correction is paid on a new form. Now two receipts relate to the same period, and nobody has linked them.

A scanned or screenshot copy replaces the original. Fields are cut off, and the reviewer cannot read the codes.

## How to read a receipt in a review

A short routine catches most problems.

1. Confirm the payer identity matches the entity that employs the workers.
2. Read the line codes, not just the total. Match each code to an expected obligation.
3. Check the period reference on every line.
4. Compare the line amounts to the figures in the payroll run, line by line.
5. Confirm the payment date and status come from a processed receipt, not from a request or a draft.
6. Store the original file and a structured copy of the fields.

The last step is the one most teams skip. A PDF is evidence for a human. A structured record is evidence for a system.

## From PDF to data

For a global EOR or payroll platform, the receipt should not live as an attachment in a ticket. It should become a record that your systems can test.

A useful record carries the payer, the line codes, the periods, the amounts, the payment date and a reference to the payroll run it is meant to settle. With that, you can automate the checks that people now do by eye. You can flag a missing line. You can flag a period mismatch. You can show an account manager that a client's month is fully paid, or exactly where it is not.

This also changes the client conversation. Instead of sending a PDF and saying it is paid, you can show the receipt, the match to the payroll run, and any open differences. That is a stronger statement, and it holds up better when someone asks a hard question later.

## The practical rule

Treat the receipt as proof of payment, and nothing more. Proof of correctness comes from matching it against the calculation behind it. Proof of coverage comes from linking it to the workers and the period. Do both, and the receipt becomes a reliable part of your audit trail instead of a comfortable assumption.

Partnership teams that want to connect receipt data to their own reconciliation flows can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/payment-proof-reading-f24-receipt.html · 2026-10-27
