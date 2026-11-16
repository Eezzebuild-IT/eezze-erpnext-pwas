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

Still to adapt: the launcher's tiles to the rights Start uses (`eezze_erp_theme.landing.tiles`), and each PWA checked
against our roles before it is offered to staff.
