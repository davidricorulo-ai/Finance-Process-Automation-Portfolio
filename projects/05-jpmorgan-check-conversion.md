# NetSuite–JPMorgan Check Payment Conversion

**Area:** Accounts Payable
**Tools:** Python (pandas)

## Objective

Eliminate the manual, error-prone process of formatting vendor check payments for JPMorgan Access every week. Payment data lived in NetSuite AP exports, but JPMorgan requires a very specific file layout to print and mail checks, and vendor master data (address, payee name, etc.) needed to be current at the moment of payment — not just at the moment the invoice was entered.

## What it does

1. **Extraction** — pulls the weekly vendor payment batch from the Oracle NetSuite AP export (typically 36+ invoices across 15–30 vendors, run 2–3 times per week).
2. **Master data cross-reference** — matches each payment against the most current vendor master file, so the check reflects up-to-date payee names and mailing addresses rather than whatever was on file when the invoice was created.
3. **JPMorgan Access formatting** — transforms the matched, validated payment data into the exact CSV layout JPMorgan Access requires to issue and mail printed checks.

## Impact

- Cut batch processing time from 2–3 hours down to under 15 minutes per run.
- Removed manual formatting errors that previously risked checks going out with outdated vendor information.
- Made a twice-to-three-times-weekly manual task a repeatable, minutes-long process.
