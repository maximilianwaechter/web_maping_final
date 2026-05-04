# Philadelphia Food Accessibility Map

An interactive web map showing how easily Philadelphians can reach a grocery store or farmers market on foot, by bike, or by car. Built with Mapbox GL JS, Turf.js, and the U.S. Census ACS API.

## Features

- Travel-time isochrones (5 / 10 / 15 minutes) for walking, cycling, and driving
- Drop a pin anywhere or click a store/market for instant accessibility analysis
- Citywide accessibility surfaces across all groceries and/or farmers markets
- Population & poverty estimates from ACS census tract data
- Five recommended grocery store sites scored by population gain, poverty weighting, and isolation from existing stores
- CSV / GeoJSON export of current results

## Running locally

The page expects three GeoJSON files in the same directory:

- `City_Limits.geojson`
- `grocery_stores.geojson`
- `Farmers_Markets.geojson`

Serve the folder over HTTP (the Mapbox isochrone API requires a real origin):

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Tech stack

- Mapbox GL JS v3.20 (basemap + isochrone API)
- Turf.js v6 (spatial union / difference / intersect / hex grid)
- U.S. Census TIGERweb + ACS 5-year (2024) for tract geometries and demographics
