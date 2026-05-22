# Australia Furniture & Bedding Import Dashboard

Interactive dashboard and supporting Excel workbook for Australian import analysis across selected Furniture & Bedding / AFA product-scope HS codes.

The dashboard is built from UN Comtrade CSV exports reported by Australia for 2020-2025.

## Current Outputs

- `outputs/index.html`  
  Shareable dashboard HTML.

- `outputs/Trade Data Furniture & Bedding 2020-2025.xlsx`  
  Consolidated Excel workbook with one tab per year.

## Product Scope

This project is **not mattress-only**.

The dashboard currently covers these HS codes:

| HS code | Product group |
|---|---|
| 630790 | Made-up textiles |
| 940161 | Upholstered wooden seats |
| 940180 | Other seats |
| 940190 | Seat parts |
| 940290 | Medical furniture |
| 940320 | Metal furniture |
| 940330 | Wooden office furniture |
| 940350 | Wooden bedroom furniture |
| 940370 | Plastic furniture |
| 940390 | Furniture parts |
| 940490 | Bedding and cushions |

Do not apply the old mattress-only headline rule of `940421 + 940429` to this dashboard.

## Data Sources

Expected source files:

```text
Trade Data Furniture & Bedding 2020.csv
Trade Data Furniture & Bedding 2021.csv
Trade Data Furniture & Bedding 2022.csv
Trade Data Furniture & Bedding 2023.csv
Trade Data Furniture & Bedding 2024.csv
Trade Data Furniture & Bedding 2025.csv
HS_SITC_Code_Reference_AFA.pdf
```

The current scripts expect these files under:

```text
/Users/pranjaldube/Downloads/
```

If running on another machine, update the paths in the build scripts.

## Important Quantity Caveat

The selected HS codes do not share one consistent quantity basis.

Some records report units, some report kilograms, some use alternate quantity, and some have no consistent quantity field. For that reason:

- CIF value is the safest cross-category headline.
- Unit counts and kilogram weights are shown separately.
- The dashboard does not imply a single combined unit headline across all selected codes.

## Dashboard Features

The dashboard includes:

- HS code multi-select filter
- Country/origin multi-select filter
- Year range filter
- Metric toggle for CIF, FOB, units, and kg
- KPI cards
- D3/TopoJSON world map with origin bubbles and flows to Australia
- Market share trend
- Annual import trend
- HS contribution chart
- Monthly seasonality chart
- Origin mix and category scope charts
- Average CIF price per reported unit
- Year comparison panel
- Partner and HS detail tables
- Classification notes
- Collapsible raw data table

## Accessibility Notes

The dashboard has been adjusted for older readers:

- darker label colors
- larger small-text labels
- heavier table and chart labels
- higher contrast helper text and notes

## Build The Dashboard

Run:

```bash
python3 build_furniture_bedding_dashboard.py
```

The builder writes:

```text
outputs/furniture_bedding_dashboard.html
```

For GitHub Pages or simple sharing, copy or rename the dashboard to:

```text
outputs/index.html
```

## Build The Excel Workbook

Prepare the workbook data:

```bash
python3 prepare_trade_workbook_data.py
```

Build the Excel workbook:

```bash
node build_trade_excel.mjs
```

Verify the workbook:

```bash
python3 verify_trade_excel.py
```

The workbook verification checks:

- all yearly tabs exist
- row counts match the CSV files
- header counts match
- CIF totals match
- FOB totals match
- primary value totals match

## Sharing Notes

The dashboard embeds the processed data payload, so recipients do **not** need the CSV files to view the dashboard.

However, the world map uses online dependencies:

- D3
- TopoJSON
- `world-atlas@2/countries-110m.json`

Recipients need internet access for the map layer to render fully.

The Excel workbook is self-contained.

## Repository Structure

```text
.
├── README.md
├── build_furniture_bedding_dashboard.py
├── prepare_trade_workbook_data.py
├── build_trade_excel.mjs
├── verify_trade_excel.py
├── dashboard_update_context.md
└── outputs/
    ├── index.html
    ├── Trade Data Furniture & Bedding 2020-2025.xlsx
    └── trade_workbook_data.json
```

## Readiness Status

Latest review found:

- dashboard renders correctly in browser
- country and HS filters work
- raw table is collapsed by default
- Excel workbook reconciles to source CSVs
- no old mattress-only headline logic is present

