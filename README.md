# Thailand Rainfall Intensity Viewer

This project provides a lightweight, client-side tool to explore rainfall intensity-duration-frequency (IDF) data for Thailand. The map loads a cropped subset of the BURGER dataset and lets you interactively inspect grid values, visualize different duration/return-period combinations, and analyze return-period profiles at individual locations.

## Features
- Interactive Leaflet map with 0.1° grid coverage over Thailand.
- Duration and return-period selectors with instant updates across 80 IDF layers.
- NOAA reflectivity-inspired colour ramp with adjustable opacity.
- Searchable lat/lon lookup and grid-cell highlighting.
- Popup details showing the selected intensity and a chart of all return-period values for the chosen duration.

## Data
The map consumes the pre-generated NetCDF subset and accompanying JSON export located in the same directory:
- `BURGER_1.0_thailand.json`

These files contain sub-daily rainfall intensities (1–24 hour durations, 2–10,000 year return periods) over Thailand at 0.1° resolution.

### Citation
Hoch, J. (2025) “BURGER - A bottom-up regionalization approach for global sub-daily intensity-duration-frequency data”, *Water Resources Research*. Zenodo. [https://doi.org/10.5281/zenodo.15473689](https://doi.org/10.5281/zenodo.15473689)

### Licensing
The dataset is distributed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). Please review the license before commercial use.

## Usage
1. Ensure `index.html`, `BURGER_1.0_thailand.json` reside in the same folder.
2. Serve the directory (e.g. `python -m http.server`) and visit `http://localhost:8000/`.
3. Select a rainfall duration and return period; hover or click on the map to inspect values.
4. Use the opacity slider, search box, and chart popups for deeper analysis.

## Dependencies
The UI is entirely client-side and references CDN-hosted libraries:
- Leaflet for mapping
- Chart.js for popup charts
- Chroma.js for colour scaling

No build tooling is required; simply serve the folder and explore.
