# Validating the Italian codice fiscale before onboarding

> How the Italian codice fiscale is built and how its check character works, so your platform can reject bad IDs before a worker is onboarded.

A wrong codice fiscale causes trouble late. Payroll fails, a registration is rejected, a contract has to be reissued. Most of these errors can be caught at the first form field. The code has a fixed structure and a check character. Both can be tested in your own system before anything is sent on.

This article explains what to test and in what order.

## What the code contains

The codice fiscale is a string of letters and digits. It is built from personal data, not issued at random. Each block has a defined role.

- Surname block: consonants taken from the surname, then vowels if there are too few. Padding is used for very short surnames.
- Given name block: consonants from the given name, with a special rule when there are many consonants. Vowels fill the gap if there are too few.
- Birth year: the last two digits of the year.
- Birth month: a single letter that maps to a month. The mapping is a fixed table.
- Birth day and sex: the day of birth, with a fixed amount added for women. A day value above the normal range of a month therefore signals a female holder.
- Place code: a letter followed by digits. It identifies the Italian municipality of birth, or the foreign state for people born abroad.
- Check character: a final letter computed from everything before it.

This means you can compare the code against the data you already collect. If the form says the worker is male and the day block says female, one of them is wrong.

## Step one: shape check

Start with a pattern test. It is cheap and removes most typos.

- Normalise the input. Remove spaces and convert to upper case.
- Check the length against the expected fixed length.
- Check that each position holds a letter or a digit as the structure requires.
- Check that the month letter belongs to the allowed set.
- Check that the day block falls in a valid range for either sex.

A failed shape check should return a specific message. "The month letter is not valid" helps the user more than "Invalid ID".

## Step two: the check character

The last character is a checksum. It protects against single-character errors and most swaps.

The method is simple. Take the leading characters. Split them by position into two groups: odd positions and even positions, counting from the start. Each character is converted to a number, but the conversion table differs by group. Digits and letters both have entries in each table. For the even group the value is mostly the position of the character in its own set. For the odd group the values come from a fixed lookup table that looks scrambled. You need the official table, so copy it carefully and test it.

Add all the converted values. Divide the total by the size of the alphabet and keep the remainder. Map that remainder to a letter, where zero is the first letter of the alphabet. That letter must equal the final character of the submitted code.

If it does not match, reject the input. Do not try to correct it.

## Step three: cross-check with form data

A code can pass the checksum and still belong to someone else. Use the data you hold to catch that.

- Rebuild the surname and given name blocks from the submitted names and compare.
- Compare the year, month and day blocks with the date of birth.
- Compare the sex implied by the day block with the declared sex.
- Check the place code against your list of municipalities and states.

Treat a mismatch as a warning for review, not always as a hard stop. Names with accents, double surnames and transliterated names from other alphabets can produce legitimate differences. Let a human confirm and log the decision.

## Shared codes and substituted digits

Two people can produce the same base code. Italy resolves this by replacing some digits with letters from a fixed substitution table. The result is still valid and the check character still applies. A strict digit-only pattern will wrongly reject these codes. Your shape test must allow the substituted letters in the numeric positions, and your cross-checks must reverse the substitution before comparing.

This is the most common bug in home-built validators. Test with such a case before release.

## Foreign nationals

Workers who come to Italy from abroad often have a code too. It is built the same way, with a state code in place of a municipality code. It may be issued before the person arrives. Do not assume a holder was born in Italy. Do not require a municipality from the Italian list when the place block points to a foreign state.

## What a valid code does not prove

A code that passes every test is well formed. It is not proof that the code is registered, or that it belongs to the person in front of you. Validation at source reduces bad data. It does not replace identity checks. Keep the two steps separate in your onboarding flow, and record which one failed.

## Practical rules for your platform

- Validate on entry, not at export.
- Store the normalised value only.
- Return a precise reason for each failure.
- Keep the lookup tables in versioned configuration, with a test suite that covers odd cases.
- Log the validation result with the input data version.

Small checks at the form save large corrections later. A clean code on day one means fewer rejected filings and fewer payroll corrections.

Partnership teams that want to align field formats and validation rules with ours can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/validating-italian-codice-fiscale-before-onboarding.html · 2026-10-27
