# Cleanup Period & Eligibility Tool

A browser tool for QBL Cleanup (SCU) and Full Service Cleanup. It replaces the Cleanup Period Calculator sheet and the Fiscal Year Product Eligibility Matrix.

Enter the tax year end, the purchase date and the product. The tool shows:

- Which products were available on that purchase date
- The cleanup start date, end date and number of months
- Key SCU dates (onboard by day 60, cleanup at day 120, entitlement ends at day 180)
- For Full Service, the going-to-monthly minimum end date
- An eligibility grid by purchase month for the tax year

Rules come from *2026 Cleanup Front Office Standards & Processes* (Jan 2026). Fiscal-year filers use the calendar rules shifted to their tax year. PY and PY + CY are extended to 9/30 for 2026 purchases only.

The whole tool is one file, `index.html`. It runs in the browser and doesn't save or send any data.

## Updating the rules

The rule logic is in the `<script>` at the bottom of `index.html`:

- `pyMax()` / `PY_EXT_YEAR`: PY and PY + CY cutoff (month 9 for 2026, month 8 otherwise)
- `scu()`: PY, CY and PY + CY sales windows and cleanup periods
- `renderFS()`: Full Service cleanup period and going-to-monthly check

When you change a rule, update the "Rules used by this tool" section in the page too.
