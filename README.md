# CedarPack LBO Lab

A 120-minute introductory cash-flow LBO lesson in INR crore. CedarPack Industries is fictional. The app uses original explanations organized around the five-stage workflow in Rosenbaum & Pearl, *Investment Banking*, Chapter 5. It does not reproduce the supplied book, proprietary workbook, or book excerpts.

## Student workflow

1. Download `CedarPack-Data.xlsx` from the app.
2. Paste historical inputs and forecast assumptions into the indicated cells.
3. Write formulas, use Fill right, and check each of 12 lessons.
4. Read hints and reveal individual cells when needed.
5. Export current work as CSV, or use `CedarPack-Practice.xlsx` in Excel. The practice workbook includes a worked solution tab.

The browser is a limited spreadsheet teaching surface, not embedded Microsoft Excel. It supports cell references, dollar anchors, arithmetic, parentheses, percentages, SUM, MIN and MAX. Tabs are views into one worksheet with fixed addresses. CSV preserves those addresses and formulas but not formatting. Work is saved locally in the current browser. There are no student accounts or instructor grade records. Validation targets the supplied case and accepts numerically equivalent reference-based formulas; it is a learning check, not a secure examination system.

## Case

Close 31 March 2026; exit 31 March 2031. Entry EBITDA 40; entry EV 320; debt 120 (3.0x); fees 4; sponsor equity 204. Revenue grows 8%; EBITDA margin 20%; D&A 3%; capex 4%; NWC 10% of sales; tax 25% of positive EBT. Interest is 10% of beginning debt. Annual principal repayment is 10% of original principal capped at outstanding debt. No cash sweep, dividends, interest income, tax losses carried forward, financing fee amortization, purchase accounting or full balance sheet. Negative cash is an unfunded shortfall, not an automatic revolver draw.

The base model produces ending debt 60, cash 43.5077708288, MOIC 2.2239840951x and annualized IRR 17.3346643744%. A 7.0x exit produces IRR 14.1236652765%. IRR equals MOIC^(1/5)-1 because there are only two sponsor cash flows separated by exactly five years.

## Development and checks

Use the package manager and pinned dependencies in the lockfile. `pnpm dev` starts the app and `pnpm build` builds it. `node lib/model.test.mjs` checks the model and formula engine. The Excel worked solution was recalculated and reconciled to the engine, and all workbook tabs were rendered for review. Browser UI interaction testing has not been performed. Optional WebMCP support exposes only `read_lbo_progress` where supported.

Original input files from the course are intentionally outside this repository. Only original app content and fictional exercise files are included.
