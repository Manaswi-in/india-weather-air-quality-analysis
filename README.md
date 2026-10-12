# India Weather & Air Quality Analysis

An end-to-end Python data engineering project that combines historical weather data and air-quality estimates for 36 state/UT–city locations across India using the Open-Meteo APIs.

**Dataset:** 3,312 daily records · 14 columns · July 9 – October 8, 2026

## Project Overview

Weather and air pollution are important factors in understanding environmental conditions. This project builds a unified dataset that brings together daily weather variables and air-quality estimates for multiple locations across India.

The data is collected from APIs, processed using Python and Pandas, and combined into a structured dataset suitable for exploratory data analysis and visualization.

## Dataset

The cleaned dataset is available on Kaggle:

**[India Daily Weather and Air Quality Dataset (2026)](https://www.kaggle.com/datasets/manaswika/india-daily-weather-and-air-quality-dataset-2026)**

| Property | Details |
|---|---|
| Records | 3,312 |
| Columns | 14 |
| Geographic coverage | 36 state/UT–city combinations |
| Period | July 9 – October 8, 2026 |
| Time resolution | Daily |
| Format | CSV |

## Features

- Retrieves city coordinates using the Open-Meteo Geocoding API.
- Collects historical weather data for selected locations.
- Retrieves hourly air-quality estimates for six pollutants.
- Aggregates hourly pollution values into daily averages.
- Combines weather and air-quality data by date and location.
- Checks missing values, duplicate records, and dataset dimensions.

## Variables

### Weather

| Column | Description |
|---|---|
| `temperature_mean` | Daily mean temperature (°C) |
| `temperature_max` | Daily maximum temperature (°C) |
| `temperature_min` | Daily minimum temperature (°C) |
| `precipitation_mm` | Daily precipitation total (mm) |
| `wind_speed_max` | Daily maximum wind speed (km/h) |

### Air Quality

| Column | Description |
|---|---|
| `pm2_5` | PM2.5 concentration |
| `pm10` | PM10 concentration |
| `carbon_monoxide` | Carbon monoxide concentration |
| `nitrogen_dioxide` | Nitrogen dioxide concentration |
| `sulphur_dioxide` | Sulphur dioxide concentration |
| `ozone` | Ozone concentration |

Pollutant concentrations are reported using the units provided by the API, typically µg/m³.

### Location and Date

| Column | Description |
|---|---|
| `date` | Date of the record |
| `state_ut` | State or union territory |
| `city` | Selected city associated with the record |

Each row represents one location on one date.

## Methodology

1. **Geocoding:** Retrieve latitude and longitude for each selected city.
2. **Weather collection:** Request historical daily weather variables.
3. **Air-quality collection:** Request hourly pollutant estimates.
4. **Data processing:** Convert timestamps into dates and calculate daily pollutant averages.
5. **Data integration:** Merge the weather and air-quality tables using date, city, and state/UT.
6. **Validation:** Check missing values, duplicates, geographic coverage, and the final dataset shape.
7. **Export:** Save the combined table as a CSV file for publication on Kaggle.

## Technology Stack

- **Python** — data collection and processing
- **Pandas** — data cleaning, aggregation, and merging
- **Requests** — API communication
- **Open-Meteo APIs** — geocoding, historical weather, and air-quality data
- **Google Colab** — development and execution
- **Kaggle** — dataset publication
- **GitHub** — source code and project documentation

## Data Sources and Limitations

- [Open-Meteo Historical Weather API](https://open-meteo.com/en/docs/historical-weather-api)
- [Open-Meteo Air Quality API](https://open-meteo.com/en/docs/air-quality-api)
- [Open-Meteo Terms of Use](https://open-meteo.com/en/terms)

The dataset includes weather reanalysis data and model-based air-quality estimates. These values should not be interpreted as direct measurements from government monitoring stations.

The dataset covers a limited historical period, and the analysis does not establish causal relationships between weather and pollution. Please consult the original data providers' terms for applicable attribution and usage requirements.

## Future Improvements

- Explore relationships between meteorological variables and pollutant concentrations.
- Create charts comparing pollution patterns across locations.
- Investigate seasonal patterns using longer historical periods.
- Develop an interactive dashboard for exploring the dataset.

## Author

Created as a Python data collection and analysis project.

Feedback and suggestions are welcome.
