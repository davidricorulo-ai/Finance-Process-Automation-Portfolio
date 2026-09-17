# Cash-in-Transit AR Reconciliation

**Area:** Accounts Receivable
**Tools:** Python (pandas)

## Objective

Reconcile what clients who pay via armored cash-transport (valores) services actually paid against what the sales system said they owed. The two sides frequently disagreed on both **amount** and **day**, and manual reconciliation couldn't reliably tell whether a mismatch was a real payment gap or just a timing artifact.

## The core problem: timezone-shifted sales data

The source sales system logged transactions on its **Berlin server clock**, while the business needed sales grouped by **local business day**. Without correcting for this, a sale made late in the local business day could land on the "wrong" day once viewed in server time — creating false discrepancies against what the armored-transport company reported collecting for that day.

## What it does

1. **Client filtering** — isolates transactions belonging to the specific set of clients that settle via cash-in-transit.
2. **Timezone normalization** — converts Berlin-server timestamps to the correct local time, then applies a day-boundary offset so each sale is bucketed into the correct local business day rather than the server's calendar day.
3. **Daily settlement calculation** — sums daily sales plus applicable commissions per client/day to compute the expected amount owed.
4. **Reconciliation** — compares the computed expected balance against what was actually collected in cash via the armored-transport service, surfacing true variances (not timezone artifacts) for follow-up.

## Impact

- Eliminated false discrepancies caused by timezone misalignment, isolating genuine payment gaps.
- Gave AR a reliable, repeatable daily settlement figure per client instead of a manually reconstructed one.
