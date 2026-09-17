# Automated Invoice Aging & Collections Reminder Flow

**Area:** Accounts Receivable
**Tools:** Power Query (Excel), Power Automate Desktop (PAD)

## Objective

Replace a manual, spreadsheet-driven aging process with a self-refreshing report that always reflects the current state of open invoices, and automatically nudge clients with overdue balances — without a person having to build the list by hand every day.

## What it does

1. **Power Query aging engine** — pulls the open-invoice ledger, calculates days-outstanding per invoice against the current date, and buckets balances into standard aging tiers (e.g. current, 1–30, 31–60, 61–90, 90+ days). The query refreshes on demand or on a schedule, so the aging position is always current rather than a snapshot from whenever someone last updated it.
2. **PAD reminder flow** — a Power Automate Desktop robot reads the aging output, filters for clients with invoices past the reminder threshold, and sends a templated reminder email per client (or per invoice) with the relevant balance and due date detail pulled directly from the aging table.

## Impact

- Removed the manual rebuild of the aging report, saving recurring analyst time.
- Standardized when and how overdue clients get contacted, instead of ad hoc follow-up.
- Gave collections and AR leadership an always-current view of exposure by aging bucket.
