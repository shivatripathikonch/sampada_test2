# Sampada 2.0 – GL Boundary-wise Prediction Dashboard

GitHub Pages-ready interactive prototype.

## Publish
1. Create a GitHub repository, for example `sampada2-gl-prediction`.
2. Upload `index.html` and `README.md` to the repository root.
3. Open **Settings → Pages**.
4. Select **Deploy from a branch**, branch `main`, folder `/(root)`, then Save.
5. GitHub will provide the published website URL after deployment.

## Interactions
- Click a polygon on the map or **View** in the table to select a GL boundary.
- Adjust the policy adoption slider to recalculate suggested increase and proposed GL rate.
- Change map metric, property type, financial year, district and label visibility.

## Data note
All rates, counts, sample polygons and performance indicators are illustrative. Polygon shapes are schematic rectangles around Bhopal, not official GL boundary geometry. The page is not connected to Sampada 2.0 or a trained production ML model. Replace the JavaScript `data` array and schematic map geometry with validated official data before operational use. Departmental approval is required for policy parameters. Leaflet, OpenStreetMap tiles and Chart.js require internet access.
