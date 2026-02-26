# katrinahooper.github.io

Personal portfolio and project showcase, hosted via GitHub Pages at [katrinahooper.github.io](https://katrinahooper.github.io).

## About

I'm a data and ML engineer with a focus on logistics, transit, and geospatial systems. This site collects my active projects — each one is either a live interactive demo or a reusable open-source library.

My work tends to sit at the intersection of messy real-world data and practical engineering: building pipelines that actually run in production, optimisation algorithms grounded in physical constraints, and ML models that produce calibrated, actionable outputs rather than just benchmark numbers.

## Projects

### [Port Disruption Risk Predictor](https://github.com/kjhooper/port_disruption_risk_predictor)
A 72-hour weather-driven disruption risk scorer for major global shipping ports. Ingests live meteorological and marine data from Open-Meteo and NOAA NDBC buoys, runs automated quality checks, engineers risk features (wind severity, wave height, pressure gradients), and serves everything through a Streamlit dashboard. The ML layer uses XGBoost for risk scoring and Prophet for forecast decomposition. Currently tracking Rotterdam, Houston, and Singapore.

### [Cargo Ship Loader](https://github.com/kjhooper/cargo_ship_loader)
A greedy optimisation algorithm for loading 20ft and 40ft ISO containers into a Panamax-class ship's hull. The algorithm respects the ship's expanding hull geometry (the hull widens from keel to full beam), places containers to minimise centre-of-gravity shift, and maintains port/starboard and fore/aft weight balance throughout the loading sequence. Includes a matplotlib animation that plays back the loading order visually. Wrapped in a Streamlit app so you can define a cargo manifest and watch the optimiser run in your browser.

### [Toronto OD Data Ingestor](https://github.com/kjhooper/toronto_od_data_ingestor)
A reusable Python library for ingesting any Toronto Open Data (CKAN) package into PostgreSQL. Built as the data layer for a TTC delay prediction project, but designed to be dataset-agnostic. Handles both datastore-backed resources (CSV dump via CKAN API) and raw file downloads (CSV, Excel), and supports replace and append modes with optional deduplication. Works out of the box with Supabase for database hosting. Install with `pip install toronto-od-ingest`.

## Stack

- **Portfolio site:** Plain HTML + CSS, no framework — fast, zero dependencies, easy to maintain
- **Interactive demos:** [Streamlit Community Cloud](https://streamlit.io/cloud) (free tier, auto-deploys on push)
- **Hosting:** GitHub Pages (auto-deploys on push to `main`)
- **CI:** GitHub Actions — tests must pass before any deploy

## Local Development

The site is a single HTML file with a linked stylesheet — no build step needed.

```bash
# Just open it in a browser
open index.html
```

To preview with live reload, any static file server works:

```bash
python -m http.server 8000
# then open http://localhost:8000
```
