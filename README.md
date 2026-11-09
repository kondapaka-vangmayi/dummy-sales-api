# Mock Sales API JSON Dataset for ADF

This dataset simulates a paginated sales API using static GitHub Raw JSON files.

## Included
- `sales/sales-page-1.json` through `sales/sales-page-50.json`
- 5,000 orders, 100 orders per page
- 1–5 order items per order
- Unique `ORDERID` values (10001–15000)
- `ORDER_ITEM_ID` is unique within each order
- Customer and product IDs align with the sample master data files
- `UPDATED_DATE_TIME` values simulate updates for incremental extraction practice
- Supporting sample master files: customers, products, manufacturers, countries

## Important
The reference master files are generated from the sample IDs/details used in the conversation. They are not extracted from your on-premises SQL Server. Replace or reconcile the customer reference attributes with your actual source values if needed.

This is static content, not a live API. GitHub Raw does not dynamically apply page query parameters. In ADF, use a pipeline variable such as `PageNumber` to construct the file path `sales/sales-page-<PageNumber>.json` and iterate through the 50 pages.

## Currency
Synthetic unit prices are converted from the sample INR product master prices using approximate rates solely to produce realistic-looking sample values:
- INR: 1.00
- USD: 1 INR / 83
- GBP: 1 INR / 105
- EUR: 1 INR / 90
- AUD: 1 INR / 55

Currency is assigned based on the sample customer's country. These exchange rates are illustrative, not financial data.

## Example path
`https://raw.githubusercontent.com/<github-username>/<repo-name>/main/sales/sales-page-1.json`
