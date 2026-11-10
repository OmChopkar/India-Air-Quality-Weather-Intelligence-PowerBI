# 🌬️ India Air Quality & Weather Intelligence (4-Stage Power BI Analytics)

An end-to-end, multi-page Power BI analytics framework designed to analyze, diagnose, forecast, and mitigate air quality hazards across major Indian cities using historical atmospheric and meteorological data.

---

## 📌 Executive Summary

This project implements a complete 4-tier business intelligence workflow (**Descriptive, Diagnostic, Predictive, and Prescriptive**) evaluating over 77,000 daily atmospheric observations. The dashboard provides public health officials and urban planners with interactive decision support—moving from baseline tracking to predictive risk modeling and dynamic policy scenario simulation without relying on external Python environments.

---

## 📊 Dashboard Architecture & Page Overview

### Page 1: Descriptive Analytics — Historical Baseline & Spatial Profiling
* **Objective:** Answers *"What has happened?"* by establishing regional air quality baselines.
* **Key Visuals & Metrics:**
  * **Executive KPIs:** Average AQI (146), $\text{PM}_{2.5}$ ($35.5\,\mu\text{g/m}^3$), $\text{PM}_{10}$ ($56.3\,\mu\text{g/m}^3$), Ambient Temp ($24.3^\circ\text{C}$), Humidity ($68.0\%$), and Wind Speed ($14.6\,\text{km/h}$).
  * **Air Quality Trend Line:** Multi-year chronological trajectory tracking particulate fluctuations.
  * **Top 5 Most Polluted Cities:** Bar chart profiling regional pollution hotspots (Delhi, Agra, Amritsar, Patna, Ludhiana).
  * **AQI Category Distribution:** Donut chart segmenting recorded days by severity (Good to Severe).
  * **Geographic AQI Heatmap:** Geospatial mapping of monitoring stations across India.

### Page 2: Diagnostic Analytics — Root-Cause & Weather Correlation Analysis
* **Objective:** Answers *"Why did it happen?"* by isolating atmospheric drivers of severe AQI spikes.
* **Key Visuals & Metrics:**
  * **Extreme Benchmarks:** Highest AQI (500 Peak), Largest Increase (+307.51%), Largest Decrease (-74.14%).
  * **$\text{PM}_{2.5}$ vs. Temperature Scatter Plot:** Demonstrates inverse thermal correlation ($r = -0.58$), confirming winter boundary-layer inversion effects.
  * **City-Wise Monthly Heatmap:** Matrix grid categorizing high-risk months (red) versus clean months (green) across municipalities.
  * **Delhi Case Study Line Chart:** Tracks atmospheric stagnation patterns (low wind speed + dropping temperatures driving winter pollution surges).

### Page 3: Predictive Analytics — Machine Learning Forecasting & Driver Modeling
* **Objective:** Answers *"What will happen next?"* to provide early warnings for municipal authorities.
* **Key Visuals & Metrics:**
  * **7-Day AQI Forecast:** Native Exponential Smoothing (ETS) time-series line chart with a 95% Confidence Interval band.
  * **Predicted Category Breakdown:** Donut chart projecting upcoming risk windows (**66.67% Poor** vs. **33.33% Moderate**).
  * **Key Influencers (AI Visual):** Machine learning regression panel measuring exact pollutant impacts ($\text{PM}_{2.5}$ and $\text{PM}_{10}$) driving daily AQI spikes.

### Page 4: Prescriptive Analytics — Scenario Simulation & Emergency Action Planning
* **Objective:** Answers *"What actions should we take?"* by quantifying policy intervention ROI.
* **Key Visuals & Metrics:**
  * **What-If Policy Slicer:** Interactive parameter allowing decision-makers to simulate 0%–50% emission reduction targets.
  * **Gauge Chart:** Speedometer visual comparing Baseline Predicted AQI (254.57) against Target Mitigated AQI (216.38) on a 0–500 index scale.
  * **Dynamic GRAP Action Trigger:** Automated DAX calculation initiating Stage II alert protocols based on predicted severity.
  * **GRAP Protocol Matrix:** Structured action matrix linking policy thresholds to mandatory municipal directives (mechanized sweeping, anti-dust sprinkling, public transit frequency boosts).

---

## 🛠️ Data Model & Technical Architecture

* **Data Sources:** `air_quality_daily.csv`, `weather_daily.csv`, `cities.csv`
* **Modeling Schema:** Extended Star Schema linked via `city`, `date`, and a dedicated `Dim_Date` table.
* **Calculations:** 100% native DAX measures for dynamic aggregations, time-series offsets, conditional threshold evaluation, and scenario modeling.
* **Platform:** Power BI Desktop

---

## 💡 Key Findings

1. **Particulate Sensitivity:** Fine particulate matter ($\text{PM}_{2.5}$) serves as the single largest contributor to daily AQI escalations, accounting for over 40% of predictive weight.
2. **Thermal Inversion:** Dropping ambient temperatures during Q4 significantly increase air density and reduce mixing height, trapping surface pollution across northern urban corridors.
3. **Policy Mitigation ROI:** Simulating a **15% reduction in traffic and industrial emissions** mitigates **38.19 AQI points**, pulling projected air quality out of severe risk zones and demonstrating measurable policy efficacy.

---

## 🚀 How to View This Dashboard

1. Clone or download this repository.
2. Install [Power BI Desktop](https://powerbi.microsoft.com/).
3. Open `AQI_PBI.pbix` to explore the interactive report.