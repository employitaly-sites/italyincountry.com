# Access control and security checklist for ICP integrations

> A practical checklist for platform teams connecting to an in-country partner: credentials, logging and least privilege, with what to ask and verify.

An integration with an in-country partner (ICP) moves sensitive data. It carries identity documents, salary details, bank data and tax identifiers. Security for that link is not a one-time review. It is a set of controls you can test, and a set of habits you keep.

This checklist is written for partnership, operations and payroll managers at global EOR and payroll platforms. It focuses on three areas: credentials, logs and least privilege. Use it when you set up an integration with ItalyInCountry, and again at each renewal of the working agreement.

## Start with a data map

Before you open any access, list what flows in each direction. For each field, write down who needs it, why, and for how long.

- Which fields does the partner need to run onboarding, payroll inputs and statutory filings?
- Which fields does your platform need back?
- Which fields are never needed by either side?

The last question matters most. Data that is never sent cannot leak. If a field has no named purpose, remove it from the exchange.

## Credentials

Most integration incidents start with a credential that lived too long or was shared too widely.

**Issue one credential per integration and per environment.** Test and production must never share keys. A leaked test key should never open production.

**Use service accounts, not personal ones.** If an integration runs on a named employee's login, it breaks when they leave and nobody knows who is acting. A service account has an owner, a purpose and a clear record.

**Prefer short-lived tokens.** Where the interface supports it, use tokens that expire and refresh automatically. Static keys should be the exception, and each one needs an owner and a rotation routine.

**Store secrets in a secrets manager.** Never keep them in source code, tickets, chat messages or shared spreadsheets. If a secret was ever pasted somewhere it should not be, treat it as exposed and replace it.

**Agree a rotation and revocation process in writing.** Both sides should know who can revoke a credential, how fast, and how the other side is told. Test the process before you need it.

**Restrict where credentials work.** If possible, limit use to known network ranges or to mutually authenticated connections. A stolen key then has less value.

## Least privilege

Least privilege means each account can do only what its job requires. In an integration this is easy to say and easy to forget.

**Separate read from write.** A reporting job that pulls payslip status does not need to create or change employee records.

**Scope by function.** Onboarding, payroll inputs, document exchange and reporting are different jobs. Give each its own permissions instead of one broad role.

**Scope by entity.** If you serve many customers, make sure an integration credential cannot see data of customers it does not handle. Ask the partner how tenant separation is enforced and how it is tested.

**Limit human access.** People on both sides who can see personal data should be few, named and reviewed on a schedule. Support staff should see the minimum needed to resolve a case. Where possible, mask sensitive fields such as bank details and tax identifiers by default.

**Review access on a fixed rhythm.** Put it in the calendar. At each review, remove accounts that are unused, belong to people who changed role, or were created for a project that has ended.

**Remove access at the end of the relationship.** Offboarding the partner, or a customer, should include a defined step to revoke credentials and confirm deletion or return of data.

## Logs

Logs let you answer a simple question after something goes wrong: who did what, to which record, and when.

**Log every access and every change.** For each event, record the account, the action, the record affected, the time and the source. Include failed attempts, not only successes.

**Keep personal data out of the logs.** Log record identifiers, not names, tax identifiers or bank details. A log that holds full payloads becomes a second copy of the data you are trying to protect.

**Protect the logs.** Limit who can read them, and make them hard to alter. A log that an administrator can quietly edit proves little.

**Agree retention and sharing.** Decide how long logs are kept and how each side can request an extract during an incident or audit. Decide this before you need it.

**Set alerts for unusual behaviour.** Examples include bulk exports, access outside normal hours, repeated failures and use of a credential from a new location. An alert nobody reads is noise, so name who receives it.

## Incidents

Agree the incident path in advance.

- Who is the named contact on each side?
- How is the other side told, and how quickly?
- Who decides whether to suspend the integration?
- Who talks to affected customers and, where needed, to the authorities?

Run a short exercise at least once. A rehearsal finds gaps that a document does not.

## Questions to ask any ICP

- How are credentials issued, stored, rotated and revoked?
- How do you separate customers from each other?
- Who inside your company can see our employee data, and how is that access reviewed?
- What do you log, for how long, and can we get an extract?
- How do you handle a suspected breach, and how will we hear about it?
- What happens to our data when the relationship ends?

Good partners answer these without hesitation and in writing. Vague answers are information too.

Partnership teams can request the data-exchange specification from ItalyInCountry.

{{< compare-table compact="true" >}}


---
Source: https://italyincountry.com/articles/icp-integration-access-control-security-checklist.html · 2026-10-27
