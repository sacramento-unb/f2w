# F2W environmental WebGIS study

Streamlit study application that accepts a polygon and GeoTIFF, intersects the
polygon with bundled embargo, PRODES and Indigenous-land layers, renders a
Folium map and estimates areas.

## Run locally

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
streamlit run home.py
```

The repository uses Parquet and shapefile data under `dados/`. No automated
tests or CI are present, and the interactive flow was not run during this audit.

## Current status and limits

This is an untested classroom WebGIS, not a production system. It assumes CRS,
table schemas and valid geometries, uses fixed 900 m² pixels for raster areas,
does not explicitly handle NoData and selects chart columns by fixed positions.
The bundled layers' provenance, update dates, legal basis and redistribution
terms are not documented.

The embargo layer contains identity/contact-related schema markers. The code
drops selected fields after loading, which does not sanitize the repository or
the underlying data object. Keep the project outside a public portfolio until
data rights and minimization are confirmed.

The existing license applies only as stated there and does not grant rights to
third-party datasets.
