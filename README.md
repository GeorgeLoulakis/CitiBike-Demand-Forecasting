

# CitiBike-Demand-Forecasting

Final Project for the DTU course [42577 – Introduction to Business Analytics](https://kurser.dtu.dk/course/42577).

Forecasting bike-sharing demand and extracting operational insights from Citi Bike NYC data using clustering, time-series modeling, graph analytics, and weather-aware analysis.

---

## Overview

This repository contains our project for **42577 – Introduction to Business Analytics** at DTU.

The project focuses on analyzing and forecasting demand in the **Citi Bike New York** bike-sharing system. Using trip-level mobility data, we study station behavior, cluster demand patterns, predict hourly pickups and dropoffs, and estimate repositioning needs for bike rebalancing.

In addition to the prediction task, the project also explores how **weather conditions**, **station connectivity**, and **day-type behavior** influence bike demand.

---

## Objectives

The main goals of the project are:

- cluster bike stations into meaningful spatial groups
- forecast **hourly pickups and dropoffs**
- estimate **overnight bike repositioning needs**
- analyze the system through **graph-based station connectivity**
- study the impact of **weather conditions on demand**
- compare patterns across **weekdays, weekends, and holidays**

---

## Datasets

This project uses the following datasets:

### 1. Citi Bike New York 2018 Dataset
The main dataset contains:

- more than **17 million bike trips**
- more than **900 stations**
- around **14,000 bikes**
- trip-level information such as:
  - start and end stations
  - timestamps
  - trip duration
  - user type
  - gender
  - birth year
  - station coordinates

### 2. Weather Data
To enrich the demand analysis, we also use **hourly weather data for New York City (Central Park)** obtained through **Meteostat**.

Weather-related variables include:

- temperature
- precipitation
- wind
- pressure

This allows us to study how weather affects demand both at the **system level** and at the **cluster level**.

---

## Methods

The project combines multiple analytical and machine learning approaches.

### Data Preprocessing
- missing value handling
- date parsing and feature engineering
- coordinate filtering
- trip duration validation
- outlier removal
- age conversion and filtering
- aggregation to hourly demand

### Clustering
- **K-Means**
- **Mean Shift**
- **DBSCAN**

### Forecasting
- **SARIMAX**
- **LSTM neural networks**

### Graph-Based Analysis
- graph construction from trip connections
- **Node2Vec embeddings**
- PCA-based embedding visualization
- centrality analysis for identifying key stations

### Exploratory Analysis
- weather-demand analysis
- weekday / weekend / holiday demand patterns
- usage intensity grouping
- cluster-level weather sensitivity analysis

---

## Key Insights

Some of the main insights from the project include:

- **K-Means** provided the strongest spatial clustering foundation for the prediction task.
- **LSTM** models generally improved forecasting performance compared to a SARIMAX baseline.
- Net-flow estimation enabled the calculation of **bike repositioning requirements** across clusters.
- Graph analysis revealed **central hubs** and meaningful operational station communities.
- Weather had a strong influence on demand:
  - demand dropped significantly in **cold rainy conditions**
  - demand increased strongly during **warm, dry periods**
- Usage patterns differed clearly by day type:
  - **weekdays** showed commuting-style peaks
  - **weekends and holidays** showed more leisure-oriented demand patterns

---

## Repository Structure

A suggested structure for this repository is:

```text
docs/               # report, figures, documentation
notebooks/          # exploratory and modeling notebooks
scripts/            # reusable Python scripts
data/               # dataset references / processed data instructions
results/            # generated outputs, plots, metrics
README.md           # project overview
