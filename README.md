# Earthquake Occurrence Rate Modeling – Himalaya & North-Eastern India (GEAR1-based + ETAS Simulation)

## Project Overview

This repository presents a high-resolution earthquake occurrence rate model for the **Himalayan and North-Eastern (NE) regions of India**, combining **smoothed seismicity**, **strain-rate accumulation**, and **ETAS (Epidemic-Type Aftershock Sequence)** simulation to quantify background and aftershock seismic hazard. This forms the basis for long-term seismic hazard assessment, catastrophe risk modeling, and financial risk forecasting.

---

## Objectives

- Model spatially gridded occurrence rates for **M ≥ 4.95** earthquakes using historical seismicity and strain models.
- Apply the **Tapered Gutenberg-Richter (TGR)** magnitude-frequency distribution to forecast magnitude bin rates.
- Simulate **aftershock sequences** using a calibrated **ETAS model** (temporal, spatial, and magnitude kernels).
- Support long-term **risk-informed planning**, **insurance modeling**, and **urban seismic resilience**.

---

##  Features

### Core Occurrence Rate Modeling
- Declustering and magnitude completeness filtering on Indian catalog.
- Smoothed spatial occurrence via **Gaussian and Haversine kernel density estimation**.
- Magnitude binning from **M4.95 to M8.95** in 0.1 intervals with **TGR fitting**.
- Functional smoothing and **log-scaled visualizations** of λ (expected number of events per grid cell).

###  ETAS Aftershock Simulation
- **ETAS Model Parameters** estimated via Maximum Likelihood:
  - **K** (productivity), **α** (magnitude sensitivity), **c**, **p** (temporal), **d**, **q** (spatial).
- Recursive generation of triggered events using:
  - Spatial kernel: \[ f(r) ∝ (r² + d)^{-q} \]
  - Temporal kernel: \[ g(t) ∝ (t + c)^{-p} \]
- Output: Simulated catalogs of aftershock sequences seeded on primary (background) events.

### Visualization
- Gridded heatmaps at **0.1° × 0.1°** and **0.5° × 0.5°**.
- Log-transformed occurrence rate plots for both:
  - Background rates (from smoothed seismicity)
  - Aftershock densities (from ETAS simulations)
- Comparative overlays for visual hazard zonation.

---

## Methodologies Used

- **Statistical Modeling**: TGR fitting, Bayesian filtering, KDE
- **ETAS Simulation**: Recursive Poisson process modeling
- **Functional Data Analysis (FDA)**: For smoothing and temporal trend extraction
- **Geospatial Modeling**: Grid-based binning, vectorized distance calculation

---

##  Applications

- Earthquake hazard assessment and seismic zonation.
- Probabilistic foundation for **parametric insurance schemes** in Indian zones.
- Aftershock-aware **scenario planning** for emergency response authorities.
- Support for India’s NDC goals and **disaster resilience index** computation.

---

## 🛠️ Stack

- **Languages**: Python 3.9+
- **Libraries**: NumPy, pandas, Seaborn, Matplotlib, SciPy, GeoPandas, Scikit-learn
- **ETAS Tools**: Custom vectorized simulation module
- **Distance Engine**: Haversine (vectorized), great-circle kernels



