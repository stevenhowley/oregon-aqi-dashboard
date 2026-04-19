# Oregon Air Quality Dashboard (PM2.5 \& Ozone)



This project visualizes **historical air quality data for Oregon** using:



- **EPA AQS** (Air Quality System) daily historical data for PM2.5 and Ozone (2020–2024)

- **U.S. Census TIGER/Line** county boundaries for Oregon

- **Interactive dashboard** elements built with Plotly and ipywidgets



The project demonstrates skills in **data engineering**, **API integration**, **geospatial data visualization**, and **interactive dashboard design** in Jupyter Notebook.



---



## Features



### Interactive County-Level AQI Dashboard



The main notebook **`03\_aqi\_dashboard.ipynb`** includes:



- A **time slider** to browse historical PM2.5 and Ozone levels by date

- A **pollutant selector** (PM2.5 vs. Ozone)

- **Choropleth county-level maps** of Oregon using Plotly

- **Summary statistics** showing statewide mean and best/worst counties for any selected day



---



## Oregon County GeoJSON



The file **`data/us\_counties.geojson`** was created from the official **2022 U.S. Census Bureau TIGER/Line** shapefile:



- Dataset: 2022 TIGER/Line Shapefiles — Counties

- Source: https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.2022.html

- ZIP File: `cb\_2022\_us\_county\_500k.zip`



Notebook **`01\_prepare\_geojson.ipynb`** documents the steps to:



1. Download and extract the Census county boundaries  

2. Filter to **Oregon only** (state FIPS code 41)  

3. Save a smaller, Oregon-specific **GeoJSON** file used by the dashboard



The pre-built us_counties.geojson is included in the repo — you don't need to run this notebook to use the dashboard. If you
  want to regenerate the GeoJSON from the raw Census shapefile, you'll need geopandas installed separately.



---



## Installation



### Using pip



```bash

pip install -r requirements.txt

```



### Using Conda



```bash

conda create -n aqi python=3.11

conda activate aqi

pip install -r requirements.txt

```



---



## License and Data Notes



- `us\_counties.geojson` and derived files use public domain U.S. Census Bureau data.

- AQS data follows EPA usage guidelines.

- No personal or sensitive information is stored in this repository.



---



## Future Improvements



- Add wildfire and smoke plume overlay data

- Create long-term trend graphs for each county

- Develop a lightweight API that serves historical county-level AQI data



---



## Live Demo



Launch the dashboard via Binder + Voila:



https://mybinder.org/v2/gh/stevenhowley/oregon-aqi-dashboard/main?urlpath=voila/render/03_county_aqi_map_clean.ipynb



---



## Optional: Live AQI Fetching (AirNow API)



For users with an AirNow API key, the notebook `04\_live\_airnow.ipynb` demonstrates how to fetch the latest station-level hourly AQI observations.



This notebook does not run on Binder because Binder cannot use external environment variables.



