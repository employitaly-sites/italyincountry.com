# How to build an Italian deadline feed into your platform

> Turn the Italian compliance calendar into machine-readable alerts. A practical data model for EOR and payroll platforms, with real 2026 examples.

Your Italian clients ask the same question every year. What is due, and by when? Most platforms answer with a PDF or a help-centre page. That does not scale, and it does not trigger anything inside your product.

A better answer is a feed. Each deadline becomes a structured record. Your platform reads the records and creates alerts, tasks and reminders. This article explains how to design that feed.

## Start with a deadline record

Keep the record small. Every deadline needs the same few fields.

- **id**: a stable key, so updates replace old versions.
- **obligation**: what must be done, for example the annual employee tax certificate.
- **audience**: who must act. Employees, self-employed payees or exempt cases are different audiences.
- **due_date**: a calendar date, not free text.
- **adjusted_due_date**: the date after any weekend or holiday shift.
- **source_url**: where the rule or the date was verified.
- **status**: whether the date is confirmed by a primary source or reported by a secondary one.
- **verified_on**: when someone last checked it.

The last three fields matter most. They let your users trust the alert. They also let your team see which dates need a second check.

## Use real 2026 examples

Three deadlines show why the model needs these fields.

The first is the annual certificate for employees. The date is 2026-03-16. The same date applies to sending the certificates to the tax authority.

The second shows why audience matters. For the tax authority submission, the date differs by case. Self-employed payees are due on 30/04. Exempt cases are due on 31/10. One obligation, three dates. If you store a single date per obligation, you will send wrong alerts. Store one record per audience instead.

The third is the annual withholding return known as Modello 770. Its nominal date is 2026-10-31. That day is a Saturday, so the effective date moves to 2026-11-02. This is why you need both `due_date` and `adjusted_due_date`. Your alert logic should always run on the adjusted date. Show both to the user so nobody is confused when the calendar and the alert disagree.

## Treat the status field seriously

The dates above come from a secondary source, a publication that summarises the calendar. They are not copied from the official text. Your feed should say so. Mark them as secondary and keep the link.

This is not a formality. A secondary date is good enough to schedule an internal reminder. It is not good enough to promise a client that a filing is safe. Let your product show the difference. A small label on the alert is enough.

When a primary source confirms the date, change the status and update `verified_on`. Do not overwrite history. Keep the earlier version so you can explain why an alert changed.

## Turn records into alerts

Once the records exist, the alert logic is simple. Build it in three layers.

**Lead time.** Create alerts at several points before the adjusted date. Early alerts give payroll teams time to collect data. Late alerts are a final check. Let each client choose their own schedule.

**Scope.** Match the record's audience to the client's workers. A client with no self-employed payees should not receive the self-employed date. Fewer alerts means fewer ignored alerts.

**Ownership.** Assign each alert to a role, not a person. In an EOR setup, some tasks belong to the provider and some to the client. Your feed should say which. A deadline nobody owns is a deadline someone misses.

## Handle change without breaking clients

Dates move. A holiday shift, a decree or a new circular can change a record. Design for this from the start.

- Version every record. Send changes as updates to the same id.
- Add a `changed_on` field and a short reason.
- Notify users only when a change affects an open alert.
- Never delete a past deadline. Mark it as closed.

Pull the feed on a schedule and compare it with what you already hold. Diff the records. Only the differences should create work.

## Delivery format

Keep the transport boring. A JSON endpoint with a modified-since filter covers most needs. A calendar export helps teams that live in their own calendars. A webhook for changes helps platforms that want to react at once. Pick the one your engineers already know.

## What to check before you launch

- Does every record have a source and a status?
- Do you store the adjusted date separately?
- Does one obligation produce one record per audience?
- Can a user see why an alert changed?
- Can your team correct a wrong date in one place?

If the answer to all five is yes, your Italian calendar stops being a document. It becomes part of the product.

Partnership teams that want to integrate this feed can request the data-exchange specification.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/italian-deadline-feed-platform-integration.html · 2026-10-27
