# ERP GL Migration & Self-Learning Transaction Categorization

**Area:** General Ledger
**Tools:** Python (pandas)

## Objective

Support the JDE-to-NetSuite ERP migration by transforming legacy JDE general ledger extracts into NetSuite's chart-of-accounts structure — and, critically, auto-classifying transactions into the correct expense/revenue type without a person manually tagging every line.

## What it does

1. **Extraction & transformation** — a Python script ingests the raw JDE GL/AP subledger export, splits debit/credit entries, separates records by subsidiary, and remaps them into the target NetSuite chart-of-accounts schema.
2. **Keyword-based categorization with historical learning** — rather than relying on a static keyword list, the script references prior months' already-categorized transactions to build up keyword-to-category associations, then applies that learned mapping to classify new, uncategorized records into the correct expense or revenue type. This reduced the volume of transactions requiring manual review month over month.
3. **Gap analysis** — reconciles resulting balances against the legacy JDE figures and surfaces discrepancies for review before go-live.

## Impact

- Reduced manual categorization effort on recurring transaction types.
- Produced a repeatable transformation process usable across each Latin American business unit's migration wave.
- Gap analysis gave the finance team a clear, explainable list of balance discrepancies to resolve before cutover.
