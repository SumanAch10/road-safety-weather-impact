# 🚧 Road Safety & Weather Impact Analysis

## Overview
Road traffic accidents are a major public safety concern, claiming thousands of lives every year.  
This project investigates **where fatal road crashes cluster** and **how weather conditions (rain, low visibility, smoke, etc.) influence crash risk**, using a combination of **official U.S. transportation data** and **NASA Earth observation datasets**.

The goal is to move beyond simple crash counts and provide **actionable, data-driven insights** that can inform road safety planning, risk mitigation, and policy decisions.

---

## Problem Statement
**Where do fatal road crashes cluster, and how much do adverse weather conditions increase crash risk?**

This project focuses on:
- Identifying **spatial and temporal hotspots** of fatal crashes
- Quantifying how **weather conditions** correlate with increased crash frequency
- Highlighting **high-risk periods and locations** that may benefit from targeted interventions

---

## Data Sources

### 🚗 Road Accident Data (Core Dataset)
- **NHTSA Fatality Analysis Reporting System (FARS)**
- Coverage: United States (nationwide)
- Years analyzed: **2019–2023**
- Data includes:
  - Crash location (state, county)
  - Time and date
  - Weather and environmental conditions
  - Fatality counts

> FARS is a census of fatal motor vehicle crashes and is widely used in transportation safety research.

---

### 🛰️ Environmental & Weather Context (NASA – Optional Enhancement)
NASA Earth observation data is used as a **contextual layer** to better understand environmental risk factors:
- Precipitation (rain intensity, storms)
- Visibility reduction (fog, smoke proxies)
- Urbanization indicators (night-time lights)

These datasets help explain *why* crashes may spike under certain conditions, rather than only *where* they occur.

---

## Methodology

1. **Data Ingestion**
   - Load annual FARS accident datasets (2020–2023)
   - Standardize columns and append a `YEAR` field
   - Merge into a single consolidated DataFrame

2. **Data Cleaning & Preparation**
   - Handle encoding issues (`cp1252`)
   - Normalize categorical codes (weather, lighting, road conditions)
   - Validate row counts and column consistency across years

3. **Exploratory Analysis**
   - Crash counts by year, state, and weather condition
   - Temporal analysis (hour of day, weekday vs weekend)
   - Identification of high-frequency crash conditions

4. **Risk Analysis**
   - Compare crash frequencies under:
     - Clear vs adverse weather
     - Daylight vs nighttime
   - Highlight weather-associated risk multipliers

5. **Visualization & Insights**
   - Heatmaps of crash density
   - Time-series trends
   - Comparative bar charts for weather conditions

---

## Project Structure

road_safety_weather_impact/
│
├── data/
│ ├── 2020/
│ ├── 2021/
│ ├── 2022/
│ └── 2023/
│
├── notebooks/
│ ├── 01_data_loading.ipynb
│ ├── 02_exploratory_analysis.ipynb
│ └── 03_weather_risk_analysis.ipynb
│
├── src/
│ ├── data_utils.py
│ └── analysis_utils.py
│
├── figures/
│ └── plots_and_maps/
│
├── README.md
└── requirements.txt

---

## Key Insights (Expected)
- Fatal crashes are **not evenly distributed** across space or time.
- Certain weather conditions (e.g., rain, reduced visibility) are **consistently associated with higher crash frequency**.
- Nighttime and adverse weather together represent a **compound risk factor**.
- Some regions experience **persistent risk regardless of year**, indicating structural safety issues.

---

## Tools & Technologies
- **Python**
- **Pandas** – data manipulation and aggregation
- **NumPy** – numerical operations
- **Matplotlib / Seaborn** – visualization
- **Geospatial libraries** (optional): GeoPandas, Folium
- **NASA Earthdata** – environmental context datasets

---

## Limitations
- Satellite-derived weather data is a **proxy**, not a ground sensor measurement.
- Correlation does not imply causation; results are presented as **associations**, not definitive causes.
- Analysis focuses on **fatal crashes only** (non-fatal incidents excluded).

---

## Future Work
- Integrate real-time weather feeds for predictive risk modeling
- Normalize crashes by traffic volume (VMT)
- Build an interactive dashboard for policymakers
- Extend analysis to specific cities or transportation corridors

---

## Why This Matters
Understanding how weather impacts road safety can help:
- Improve early warning systems
- Inform infrastructure design
- Guide public awareness campaigns
- Support data-driven transportation policy

---

## Author
**[Your Name]**  
University Datathon Project  