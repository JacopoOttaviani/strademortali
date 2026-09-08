# StradeMortali — Road Accidents in Rome

An interactive open data dashboard visualizing 31,615 road accidents recorded in Rome between March 2021 and March 2022. A civic technology project by [Jacopo Ottaviani](https://www.linkedin.com/in/jacopo-ottaviani/), built to spark debate on the release and use of open data and to raise public awareness of road safety.

## Features

- **Accident map** — Leaflet map with marker clustering of all geolocated accidents, with popups showing date, location, accident type, and severity.
- **Filters** — filter by severity, accident type, weather, road condition, traffic, and hour range.
- **Day/hour heatmap** — distribution of accidents by day of week and hour of day.
- **Killer intersections** — ranking of the most dangerous intersections, scored by accidents, injuries, and deaths (see `classifica_incroci.csv`).
- **Data table** — sortable, filterable table of the underlying records with export.
- **Bilingual** — Italian (`/it/`, default at root) and English (`/en/`) versions with a language switcher.

## Project structure

```
index.html                  Italian version (root)
it/index.html               Italian version
en/index.html               English version
data.js                     Shared embedded dataset (31,615 records)
classifica_incroci.csv      Intersection ranking (accidents, deaths, injuries, score)
Dataset incidenti Roma.xlsx Original source dataset
```

The site is fully static: no build step, no backend. All data is embedded in `data.js` as a single `EMBEDDED` array. Each record contains: ID, datetime, street (and cross street), accident type, weather, lighting, road surface, traffic, deaths, injuries (reserved field), coordinates, vehicle types, and a severity flag.

## Running locally

Serve the folder with any static server (opening `index.html` directly also works):

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

External dependencies are loaded from CDNs: [Leaflet](https://leafletjs.com) with MarkerCluster, Chart.js, and Google Fonts. The basemap uses the free [OpenStreetMap](https://www.openstreetmap.org/copyright) standard tiles, which need no API key.

## Data source

Accident data from **Comune di Roma** (Rome open data), covering March 2021 through March 2022, up to the latest available update.

## Credits

Made by Jacopo Ottaviani. Special thanks to [Leaflet](https://leafletjs.com). If you find the project useful, you can [buy me a coffee](https://ko-fi.com/jacopoottaviani).
