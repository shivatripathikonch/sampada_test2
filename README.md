Sampada 2.0 – Bhopal GL Boundary Analytics + Exploratory AI/ML
GitHub Pages files
`index.html` — interactive dashboard
`bhopal_gl_boundary_data.geojson` — 2,881 GL polygons with current GL fields, spatially aggregated evidence, and exploratory ML predictions
Upload both files to the repository root, then enable GitHub Pages: Settings → Pages → Deploy from a branch → `main` → `/(root)`.
Source layers used
GL_bhopal_25_26: 2,881 GL polygons and category-wise guideline rates.
igrs_sales_data_bhopal: 2,503 registry points; 2,502 spatially linked to GL polygons.
LULC_BUILTUP_CHANGE_Bhopal: 7,079 features.
tncp_approved_applications_igrs_geom_bhopal: 20,555 features.
diversion_settlement_bhopal: 16,747 features.
Road_bhopal: 119,766 line features.
AI/ML model included
A Random Forest regression model was trained on 2,450 usable sales records. Target:
`((CONSIDERAT / FINAL_MARK) - 1) * 100`
This is the transaction consideration premium/discount compared with the guideline-assessed transaction value. Features include the relevant GL rate fields, GL-level linked sales activity, built-up change, TNCP, diversion and road intersection counts, coordinates, area type and tehsil. Predictions are written to each GL polygon as `ml_gap_pct`; `ml_evidence` shows a simple evidence band based on linked sales count.
Validation results (spatial GL-group holdout)
MAE: 19.8 percentage points
RMSE: 39.6 percentage points
R²: -0.04
These results show weak predictive performance. The model is experimental and should NOT be used for official guideline revision decisions. The dashboard exposes the model performance and labels its prediction as a transaction premium/discount, not a per-square-metre market rate.
Important data limitation
The Sales layer has transaction consideration and final guideline assessed value but no usable property-area field. It also contains only `AGRICULTURAL LAND` transactions in this supplied extract, so the model is not validated for residential/commercial property types. Therefore this package cannot derive or claim an actual market rate in ₹/Sq. M. It provides an exploratory transaction-to-guideline premium/discount proxy only. To build a reliable ₹/Sq. M. market-rate model, add registered property area (sq. m. or hectare) and a broader, multi-year, multi-property-type transaction dataset.
Separate spatial priority indicator
The dashboard also shows an Indicative Spatial Signal based on weighted percentile ranks: Sales 40%, Built-up Change 20%, TNCP 15%, Diversion 10%, Road intersections 15%. This is a prioritisation index, not a statutory increase recommendation.
Map geometries are simplified for web display. Use original source data for official GIS editing and boundary verification. External Leaflet, OpenStreetMap and Chart.js resources require internet access.
