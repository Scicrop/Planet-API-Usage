# 🌍📡 Planet API – Agronomic & Environmental Data Analysis Examples

This repository contains **practical and functional Jupyter notebooks** demonstrating **how to access, query, and analyze Planet data** using **Python**, with a focus on **agronomic, environmental, and territorial monitoring applications**.

The examples provided here are **not generic tutorials**: they reflect **real-world use cases**, designed for professionals working with **geospatial analysis, remote sensing, data science, ESG, agriculture, and environmental monitoring**.

---

## 📂 Repository Contents

### 🛰️ `api-planet-imagery.ipynb`

Notebook focused on **traditional Planet imagery products**.

**Key topics covered:**

* 🔐 Secure authentication with the Planet API
* 🗺️ Definition of AOI (Area of Interest) using GeoJSON
* 🔎 Image search by:

  * Temporal range
  * Sensor / product type
  * Spatial coverage
* 📦 Creation of **Orders** for:

  * AOI clipping
  * Automated download
* 📥 Organization and consumption of returned assets

**Practical applications:**

* Crop and field monitoring
* Visual assessment of climate-related events
* Land use and land cover analysis
* Environmental and operational audits

---

### 🌱 `api-planet-planetary-variables.ipynb`

Notebook dedicated to **Planetary Variables (L4)** — derived products ready for quantitative analysis.

**Special focus on:**

* 💧 **Soil Water Content (SWC)**
* 🌡️ Land Surface Temperature (LST)
* 🌾 Biomass Proxy

**What this notebook demonstrates:**

* 📡 Automatic discovery of products available to the organization
* 🔍 Identification of enabled `resource_ids`
* 🧾 Creation of **Subscriptions** (without physical delivery)
* 📈 Consumption of **time series directly via the `/results` endpoint**
* 📊 Extraction of statistics such as:

  * Spatial mean
  * Valid data percentage
  * Solar and UTC timestamps

**Why this matters:**

* Eliminates the need to download raster files
* Reduces computational and storage costs
* Simplifies integration with data pipelines, BI tools, and analytical models

---

## 🚜🌎 Importance for Agronomic and Environmental Analysis

These notebooks are particularly useful for:

### 🌾 Precision Agriculture

* Monitoring **soil moisture dynamics**
* Assessing water stress during critical periods
* Supporting irrigation and crop management decisions

### 🌦️ Climate and Environmental Monitoring

* Detecting hydric and thermal stress
* Supporting climate impact studies
* Monitoring sensitive areas and environmental degradation

### 📊 Data Science & Analytics

* Direct integration with Pandas, NumPy, and analytical pipelines
* Use of geospatial data as **structured time series**
* Solid foundation for predictive models and ESG indicators

### 🛰️ Modern Geoprocessing

* Practical use of GeoJSON
* AOIs derived from shapefiles
* API-first, cloud-native data consumption

---

## ⚠️ Important Notes

* 🔑 Valid Planet API credentials are required
* 📜 Product access depends on the organization’s contract
* 📦 Some products require active quota
* 📐 Very large AOIs may be subject to area limits

---

## 🧠 Target Audience

This repository is ideal for:

* Agronomists with a data-driven focus
* Environmental data scientists
* ESG and sustainability analysts
* GIS / GeoAnalytics developers
* Researchers and consultants in agriculture and environmental domains
