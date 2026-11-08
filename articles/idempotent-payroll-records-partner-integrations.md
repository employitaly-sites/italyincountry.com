# Idempotent payroll records: keeping resubmitted files safe in partner integrations

> How idempotency keys, natural keys and safe upserts stop duplicate payroll records when partners resubmit files to an EOR or payroll platform.

A payroll file will be sent twice. A partner's job times out and retries. An operator uploads the same export again because the confirmation never arrived. A network drop leaves both sides unsure what was received. If your integration treats every submission as new, a retry becomes a duplicate payment or a duplicate employee.

The fix is to design for resubmission from the start. The goal is simple: sending the same data again must leave the system in the same state as sending it once. This is idempotency. Here are the patterns that deliver it.

## Separate the file from the records

A file is a transport unit. A record is a business fact. Mixing them causes most duplicate problems.

Treat the file as an envelope. It has an identifier, a sender, a received time and a status. Treat each row inside it as a record with its own identity. Then you can answer two different questions: has this file been seen before, and has this record been seen before? You need both answers, because a corrected file may contain the same records in a new envelope.

## Use an idempotency key at the submission level

Every submission should carry a key chosen by the sender. The receiver stores the key with the result of the first attempt. If the same key arrives again, the receiver returns the stored result and does nothing else.

Three rules make this work.

- The key belongs to the sender's intent, not to the attempt. A retry reuses the key. A new payroll run gets a new key.
- The key and the outcome are written in the same database transaction. Otherwise a crash can leave work done but no key stored.
- The same key with a different payload is an error. Reject it loudly. Silent acceptance hides bugs on the partner side.

If partners cannot supply a key, derive one from stable fields such as the partner identifier, the pay period and a file sequence number. Do not derive it from a timestamp. Timestamps change on every retry.

## Define a natural key for each record

Submission keys protect against retries. They do not protect against the same employee appearing in two different files. For that you need a natural key per record type.

For a payroll line, a workable natural key combines the partner, the employee reference, the pay period and the component type, such as base pay or a bonus. Two rows with the same natural key describe the same fact. Enforce this with a unique constraint in the database. Application checks alone will fail under concurrent uploads.

Choose the employee reference carefully. Names change and spellings vary. Use an identifier that the partner assigns and keeps stable. Map it to your internal identifier once, at onboarding, and store the mapping.

## Upsert, then compare

When a record arrives with a known natural key, you have three cases.

- The content is identical. Do nothing and report it as unchanged.
- The content differs and the record is still open. Update it and keep the previous version.
- The content differs and the record is already locked, for example after approval or payment. Do not overwrite. Raise an exception for a human to review.

Compare a content hash of the normalised fields, not the raw row. Trim whitespace, fix number formats and standardise date formats before hashing. Otherwise a harmless formatting change looks like a real change.

## Make partial failure safe

Large files fail halfway. Decide in advance what that means.

The simplest approach is all or nothing: validate the whole file, then apply it in one transaction. This is easy to reason about but can block a good file because of one bad row. The alternative is row-level processing with a per-row result. This needs the natural key and upsert logic above, so that a resubmission of the full file only changes the rows that failed before.

Whichever you choose, return a result per row. Partners need to know which rows were created, updated, unchanged or rejected. A single success message invites a blind resend.

## Keep an audit trail

Store the original file, the parsed records and the outcome of each submission. When a partner asks why a payment appears once, or twice, you can show exactly what arrived and what the system did. This also helps operations teams reconcile after an incident without reading logs.

## Test with repeats, not only with errors

Most test suites check that bad input is rejected. Add tests that send good input repeatedly. Send the same file twice in sequence. Send it twice at the same moment. Send a corrected file after the original was approved. Kill the process between the write and the response. These cases find the gaps that production will find otherwise.

## What this means for partnership teams

Idempotency is also a commercial feature. Partners who can retry without fear integrate faster and raise fewer support cases. Operations teams spend less time on manual clean-up. Payroll managers get one record per fact, which is what they expected to begin with.

Partnership teams at EOR and payroll platforms can request the data-exchange specification to see the keys, record identities and error responses in detail.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/idempotent-payroll-records-partner-integrations.html · 2026-10-27
