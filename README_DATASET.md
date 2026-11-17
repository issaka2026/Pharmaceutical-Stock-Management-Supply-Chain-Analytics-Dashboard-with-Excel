# Pharmaceutical Supply Chain Analytics — Synthetic Dataset

## Dataset purpose
This dataset is entirely synthetic and was created for an Excel 365 portfolio project on pharmaceutical inventory and supply-chain analytics.
It does not contain real patient, supplier, facility-performance, or confidential operational data.

## Geographic and operational model
The simulated national system is inspired by a generic African public health supply chain. Facility names are fictional.
The hierarchy includes one central warehouse, seven regional depots, district pharmacies, and integrated health centres.

## Reporting period
- Monthly consumption and transactions: November 2025 to October 2026
- Stock snapshot date: 31 October 2026
- Currency: XOF (CFA franc)

## Files
| File | Description |
|---|---|
| PRODUCTS.csv | Product master data |
| FACILITIES.csv | Facility hierarchy and metadata |
| STOCK_DATA.csv | Facility-product stock snapshot |
| TRANSACTIONS.csv | Stock movement records |
| CONSUMPTION.csv | Monthly consumption observations |
| SUPPLY_ORDERS.csv | Replenishment orders and delivery status |
| EXPIRY_TRACKING.csv | Batch-level expiry and remaining quantities |
| DATA_DICTIONARY.csv | Variable definitions and validation rules |

## Important interpretation notes
- All quantities and prices are simulated, not operational facts.
- `Available_Qty` is calculated as on-hand less reserved, damaged and expired quantities, floored at zero.
- `In_Transit_Qty` is not included in available stock.
- Consumption observations are sample records, not a complete census of every product at every facility.
- The stock snapshot and transaction history are separate analytical tables; do not assume the snapshot is a direct sum of all transaction rows.
- Batch identifiers in the transaction table are illustrative references; `EXPIRY_TRACKING` is the dedicated lot-level expiry table.
- Vaccine and insulin storage conditions are flagged for cold-chain monitoring, but no temperature logger data is included.
- For stock status, expiry risk should be assessed independently from quantity status to avoid hiding concurrent risks.

## Suggested Excel workflow
1. Import CSV files using Data > Get Data > From Text/CSV (Power Query).
2. Load each dataset as an Excel Table.
3. Use `Product_ID` and `Facility_ID` as relationship keys.
4. Create PivotTables and slicers for region, facility type, product category and reporting month.
5. Calculate stock coverage, availability, stock-out, order fill rate, on-time delivery and expiry indicators.

## Data quality
Identifiers are unique within their respective master/transaction tables. Some reporting statuses, stock risks, delayed orders and expiry risks are intentionally seeded to support realistic analysis exercises.

## License and use
Portfolio demonstration and educational use. Synthetic data only.