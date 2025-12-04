\# Oregon Air Quality Dashboard (PM2.5 \& Ozone)



This project visualizes both historical and real-time air quality data for Oregon using:



\- EPA AQS (Air Quality System) daily historical data (2020–2024)

\- AirNow API real-time station-level observations (PM2.5 and Ozone)

\- U.S. Census TIGER/Line county boundaries for Oregon

\- Interactive dashboard elements built with Plotly and ipywidgets



The project demonstrates skills in data engineering, API integration, geospatial preprocessing, data visualization, and interactive dashboard design in Jupyter Notebook.



---



\## Features



\### Interactive County-Level AQI Dashboard



The main notebook (`03\_aqi\_dashboard.ipynb`) includes:



\- A time slider to browse historical PM2.5 and Ozone levels by date

\- A pollutant selector (PM2.5 vs. Ozone)

\- Choropleth county-level maps of Oregon using Plotly

\- Summary statistics showing statewide mean and best/worst counties for any selected day



\### Live AirNow Observations



The dashboard also fetches current PM2.5 and Ozone observations from the AirNow API and displays the latest station-level readings on a map.



Set your AirNow API key as an environment variable (PowerShell example): setx AIRNOW\_KEY "your\_real\_key\_here"





Restart Jupyter Notebook afterward.



---



\## Oregon County GeoJSON



The file `data/us\_counties.geojson` was created from the official 2022 U.S. Census Bureau TIGER/Line shapefile:



\- Dataset: 2022 TIGER/Line Shapefiles — Counties  

\- Source: https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.2022.html  

\- ZIP File: `cb\_2022\_us\_county\_500k.zip`



Notebook `01\_prepare\_geojson.ipynb` documents the steps used to:



1\. Download and extract the Census county boundaries

2\. Filter to Oregon counties only (state FIPS code `41`)

3\. Save a smaller, Oregon-specific GeoJSON file used by the dashboard



This ensures the geospatial portion of the project is fully reproducible.



---



\## Installation



Install required packages: pip install -r requirements.txt





Or install using Conda:



conda create -n aqi python=3.11

conda activate aqi

pip install -r requirements.txt





---



\## License and Data Notes



\- The `us\_counties.geojson` and derived files use public domain U.S. Census Bureau data.

\- AirNow and AQS data follow EPA usage guidelines.

\- No personal or sensitive information is stored in this repository.



---



\## Future Improvements



\- Deploy the interactive dashboard using Voila or Binder

\- Add wildfire and smoke plume overlay data

\- Create long-term trend graphs for each county

\- Develop a lightweight API that serves historical county-level AQI data



---



## Live Demo

You can launch the dashboard in your browser (via Binder + Voila) using:

https://mybinder.org/v2/gh/stevenhowley/oregon-aqi-dashboard/main?urlpath=voila/render/notebooks/03_county_aqi_map_clean.ipynb
