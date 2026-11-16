# Eezzebuild's fork of the ERPNext PWAs

Forked 16 Nov 2026 from Zawala/erpnext_overrides (MIT; the original licence stays) as a base of the Eezzebuild staff
app (owner: the free open-source Frappe apps are the base, modified and improved; eezze-erpnext-app
`docs/research/2026-11-16-combine-open-source-frappe-apps.md` §7).

The original is one company's full set of ERPNext changes besides its phone apps. On branch `eezze` only the phone
apps are on: the launcher (`/launcher`) and the sales, HR admin, accounts and admin PWAs, with their routes and APIs.
Commented out in `erp_overrides/hooks.py`: the home-page takeover (our desk lands on Start, eezze-erpnext decision
0050), every `doc_events` hook (ZATCA e-invoicing on Sales Invoice, warehouse fill-ins, three-way match on Payment
Entry, Employee and User rules), the Quotation permission and print overrides, the payroll and letterhead install, the
scheduler (ZATCA sweeps, Zambian tender scrapers, review digests) and the request and job hooks. Its patches are marked
done by Frappe on a fresh install; its own doctypes (tenders, ZATCA, reviews, petty cash) stay empty.

Changed for Eezzebuild's rights:
- the launcher's Sales tile shows to the people who sell (create on Quotation or Sales Order, the rule behind Start's
  "New quotation" and the till), not to everyone who can read a sales document;
- the Sales app's "New quotation", "New lead" and "Start one" show only to those who may create them (quoting is the
  sales team's, eezze-erpnext decision 0050); the server refused them already.

Checked on the staging copy (eezze-erpnext `docs/how-to/erpnext-staging.md`, `scripts/manual/staging-apps-check.mjs`):
the launcher draws per sign-in, "My HR" opens Frappe HR's `/hrms` home in the same session, and every tile's screen
opens; eezze-erpnext's 53 scripted role cases pass with this app installed.

Still to adapt: the tender, ZATCA and review doctypes and screens taken out (they sit empty and their hooks are off),
and each PWA walked against our roles by a person before it is offered to staff.
