# 🌍📡 Planet API – Agronomic & Environmental Data Analysis Examples

This repository contains **hands-on, production-oriented Jupyter notebooks** demonstrating how to **access, process, and analyze Planet satellite data** using **Python**, with a strong focus on **agronomic intelligence, environmental monitoring, and geospatial analytics**.

These notebooks go beyond basic API usage. They reflect **real-world workflows**, including **data quality handling, spectral index computation, and time series analysis**, as commonly required in **precision agriculture, ESG projects, and environmental decision support systems**.

---

## 📂 Repository Contents

### 🛰️ `api-planet-imagery.ipynb`

Notebook focused on **PlanetScope multispectral imagery**, covering the **full analytical workflow** from data acquisition to vegetation index analysis.

#### 🔑 What this notebook demonstrates

**Data access & ordering**

* 🔐 Secure authentication with the Planet API
* 🗺️ AOI definition using GeoJSON (including AOIs derived from shapefiles)
* 🔎 Image search by:

  * Temporal range
  * Product type (`PSScene`)
  * Asset type (`AnalyticMS_SR_8b`)
* 📦 Order creation with:

  * AOI clipping
  * Surface Reflectance products
  * Automated asset download

**Understanding Planet imagery products**

* 🧠 Clear interpretation of Planet file nomenclature:

  * `AnalyticMS_SR_8b` → 8-band Surface Reflectance imagery
  * `udm2` → pixel-level quality and usability mask
* 🧪 Validation of band count and band semantics:

  * Coastal Blue, Blue, Green, Yellow, Red, Red Edge, NIR

**Data quality handling**

* 🛡️ Proper use of **UDM2 masks** to:

  * Remove clouds, shadows, invalid pixels
  * Ensure agronomically reliable indices
* ✅ Construction of a valid pixel mask for analysis

**Spectral index processing**

* 🌱 NDVI computation (Normalized Difference Vegetation Index)
* 🌾 NDRE computation (Normalized Difference Red Edge Index)
* 📐 Correct band selection and scaling
* ✂️ Safe clipping of index values **only for visualization**

**Visualization & analysis**

* 🗺️ Agronomically appropriate color palettes:

  * NDVI → brown → yellow → green
  * NDRE → yellow → orange → dark green
* 📊 Distribution analysis using:

  * Histograms
  * Kernel Density Estimation (KDE)
* 📈 Interpretation of pixel distributions for crop vigor and stress analysis

#### 🚜 Practical agronomic applications

* Crop vigor mapping
* Early detection of water or nitrogen stress
* Field heterogeneity analysis
* Support for variable-rate management
* Pre-processing for machine learning models

---

### 🌱 `api-planet-planetary-variables.ipynb`

Notebook dedicated to **Planetary Variables (L4)** — **ready-to-use, derived products** optimized for **time series and large-scale analysis**.

#### 🌍 Special focus on

* 💧 **Soil Water Content (SWC)**
* 🌡️ Land Surface Temperature (LST)
* 🌾 Biomass Proxy

#### 📡 What this notebook demonstrates

* 🔍 Automatic discovery of **products available to the organization**
* 🧾 Inspection of enabled `resource_ids`
* 🧩 Understanding product families and quotas
* 📑 Creation of **Subscriptions** (no raster delivery required)
* 📈 Consumption of **time series via the `/results` endpoint**
* 📊 Parsing of returned statistics:

  * Mean values over AOI
  * Valid data percentage
  * Acquisition timestamps (UTC and solar time)

#### 🚀 Why this approach matters

* ❌ No need to download large raster files
* 💸 Lower storage and processing costs
* 🔄 Ideal for:

  * Dashboards
  * Data pipelines
  * Monitoring systems
  * ESG indicators
  * Predictive analytics

---

## 🚜🌎 Why This Repository Matters for Agronomy & Environment

### 🌾 Precision Agriculture

* Monitoring **vegetation vigor and variability**
* Detecting **water and nitrogen stress**
* Supporting irrigation and fertilization decisions
* Field-level temporal analysis

### 🌦️ Environmental & Climate Monitoring

* Tracking hydric and thermal stress
* Supporting climate impact assessments
* Monitoring sensitive or regulated areas

### 📊 Data Science & Analytics

* Seamless integration with Pandas, NumPy, Rasterio, and Seaborn
* Transformation of satellite data into **structured analytical datasets**
* Solid base for ML models and decision-support systems

### 🛰️ Modern Geospatial Workflows

* GeoJSON-first design
* Shapefile-to-AOI conversion
* API-driven, cloud-native geoprocessing

---

## ⚠️ Important Notes

* 🔑 Valid Planet API credentials are required
* 📜 Product access depends on your organization’s contract
* 📦 Some products consume quota
* 📐 Very large AOIs may be subject to limits

---

## 🧠 Target Audience

This repository is ideal for:

* Agronomists working with remote sensing
* Environmental and climate data scientists
* ESG and sustainability analysts
* GIS and GeoAnalytics developers
* Researchers and consultants in agriculture and environmental domains
