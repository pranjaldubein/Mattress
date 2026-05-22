Australia Mattress Import Analysis
Interactive dashboard for reviewing Australian mattress import data across HS codes 940410, 940421, and 940429 for the 2020-2025 period.

The dashboard is designed as a shareable stakeholder view for the Australian Furniture Association / FurnitureDNA anti-dumping petition work.

Live Dashboard
Open index.html directly in a browser, or host this repository with GitHub Pages.

The dashboard is self-contained: the processed data is embedded inside the HTML file, so recipients do not need the original CSV files.

What The Dashboard Shows
Annual import volumes and values from 2020 to 2025
Monthly import trends across the selected year range
HS code filters for 940410, 940421, and 940429
Origin filters for China, Viet Nam, Malaysia, and Hong Kong SAR
Metric toggle for units, CIF USD, and FOB USD
Selected-origin share of world imports
CIF / FOB value comparison using import data only
HS code breakdown and year comparison table
Collapsible raw data table
HS Code Scope
HS code	Description	Dashboard note
940410	Mattress supports	Includes bases, slats, supports and related products. Quantity handling can differ from mattress codes.
940421	Mattresses of cellular rubber or plastics	Foam / memory foam / cellular rubber or plastic mattresses.
940429	Mattresses of other materials	Spring, latex, water, air and other-material mattresses.
For clean mattress unit figures, the main petition logic focuses on 940421 + 940429. 940410 is included for visibility, but should be treated carefully because its product scope is broader.

Data Basis
Primary source: UN Comtrade, as reported by Australia via ABF / ABS trade data.

Values are shown in USD:

CIF import value: cost of goods plus insurance and freight to Australia.
FOB import value: value at export point before international freight and insurance.
Units: reported item units where available; 940410 uses item-unit handling where needed because the primary quantity basis can differ.
Methodology Notes
World totals use Comtrade world aggregate rows.
Origin rows are shown for China, Viet Nam, Malaysia, and Hong Kong SAR.
Market share is calculated as selected-origin units divided by world units for the selected HS codes and years.
Volume and market-share views remain unit-based.
CIF / FOB selection affects value, average price, and value split views.
The dashboard uses import data only. Export rows are not included in the dashboard comparison.
GitHub Pages Deployment
Create a public GitHub repository.
Upload index.html and this README.md.
In GitHub, go to Settings → Pages.
Set the source to Deploy from a branch.
Select the main branch and root folder.
The dashboard will be available at:
https://[username].github.io/[repository-name]/
Important Caveat
This dashboard is an analytical support tool, not a final legal determination. Classification, dumping margin, injury analysis, and normal value evidence should be confirmed before formal filing.
