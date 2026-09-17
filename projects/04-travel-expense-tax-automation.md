# Travel Expense & Monthly Tax Calculation Automation

**Area:** Accounts Payable
**Tools:** Power Query (Excel)

## Objective

Automate the extraction, cleaning, and analysis of travel expense data, and remove the manual effort of calculating applicable taxes each month according to business policy.

## What it does

1. **Multi-source extraction** — a set of Power Query queries pull travel expense data from source exports, standardizing formats and fields across sources into a single clean table.
2. **Data cleaning** — handles inconsistent entries, missing fields, and duplicate or malformed records before they reach the analysis layer.
3. **Automated monthly tax calculation** — applies the business's tax rules and policy logic to the cleaned expense data programmatically within the query, replacing a manual, rule-lookup-by-hand process that had to be repeated every month.

## Impact

- Cut the manual, repetitive work of recalculating month-end travel expense taxes.
- Produced a consistent, auditable expense dataset ready for reporting and analysis.
