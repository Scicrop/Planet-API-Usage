# 🌍📡 Planet API – Advanced Agronomic & Environmental Intelligence Workflows

This repository contains **production-grade Jupyter notebooks** demonstrating how to **acquire, process, validate, analyze, and interpret Planet satellite data** using Python.

The workflows implemented here are designed for **real-world agronomic intelligence, environmental monitoring, ESG analytics, and geospatial data science**.

This is not just API usage — it is an **end-to-end analytical framework** for remote sensing applications.

---

# 📂 Repository Structure

## 🛰️ `api-planet-imagery.ipynb`

Complete workflow for **PlanetScope Surface Reflectance (8-band) imagery**.

---

## 🔐 Data Acquisition & Ordering

* Secure authentication
* AOI definition (GeoJSON or Shapefile → GeoJSON conversion)
* Search by:

  * Temporal range
  * `PSScene`
  * `AnalyticMS_SR_8b`
* Order creation with:

  * AOI clipping
  * Surface Reflectance products
  * Automated download

---

## 🧠 Understanding Planet Assets

Example:

```
20250515_133533_10_2506_3B_AnalyticMS_SR_8b_clip.tif
```

Breakdown:

* `3B` → Level 3B (orthorectified)
* `AnalyticMS_SR` → Surface Reflectance
* `8b` → 8 spectral bands
* `udm2` → pixel usability mask

Bands confirmed programmatically:

```
coastal_blue
blue
green_i
green
yellow
red
rededge
nir
```

---

## 🛡️ Data Quality & Masking (UDM2)

New functionality includes:

* Automatic detection of matching UDM2 mask
* Valid pixel mask generation
* Cloud/shadow/no-data removal
* Safe masking before index calculation

This ensures agronomically reliable outputs.

---

## 🌱 Spectral Index Processing (Modular Functions)

### `process_ndvi(tif_path)`

* Uses Red & NIR bands
* Applies valid mask
* Returns masked NDVI array

### `process_ndre(tif_path)`

* Uses RedEdge & NIR
* Sensitive to nitrogen & canopy structure
* Mask-aware implementation

---

## 🎨 Visualization & Distribution Analysis

### `show_ndvi(path)`

### `show_ndre(path)`

Each function:

* Displays index map with agronomically meaningful palette

  * NDVI → brown → yellow → green
  * NDRE → yellow → orange → dark green
* Generates Seaborn distribution plot (histogram + KDE)
* Uses clipping **only for visualization**, not for computation

Also explains:

* Why density ranges vary
* Why index values are clipped for display
* Interpretation of pixel distributions

---

## 🚜 Agronomic Applications (Imagery Notebook)

* Crop vigor mapping
* Early stress detection
* Irrigation performance assessment
* Field heterogeneity detection
* Support for variable-rate application
* Input for ML models

---

# 🌱 `api-planet-planetary-variables.ipynb`

Advanced workflow for **Planetary Variables (L4)** — derived products optimized for time-series monitoring.

---

## 📡 Product Discovery & Quota Inspection

New additions:

* Query available products via:

```
GET /my/subscriptions/products
```

* Inspect:

  * `resource_ids`
  * `quota_total`
  * `quota_used`
  * `quota_units`
  * `supports_reservation`

Helps prevent accidental overconsumption.

---

## 🧾 Subscription-Based Time Series

Instead of downloading rasters:

* Create subscription
* Consume `/results`
* Parse returned statistics
* Build Pandas DataFrame

Robust handling added for:

```python
statistics = None
```

Prevents runtime failures.

---

## 📊 Supported Planetary Variables

### 💧 Soil Water Content (SWC)

* Unit: volumetric fraction (m³/m³)
* Example: `0.13` → 13% soil volumetric water content

---

### 🌡️ Land Surface Temperature (LST)

* Unit: Kelvin
* Example:

  * `288.82 K` → 15.67 °C
  * `301.40 K` → 28.25 °C

Converted interpretation implemented.

---

### 🌾 Biomass Proxy

* Dimensionless proxy index (0–1 scale typical)
* Example:

  * `0.523` → moderate-to-high canopy biomass

---

## 📈 DataFrame Construction Pipeline

Converts raw results:

```json
{
  "statistics": [{"name":"mean","value":0.274}]
}
```

Into structured dataset:

| datetime_utc | mean_swc | valid_percent | source_id |
| ------------ | -------- | ------------- | --------- |

Sorted, typed, ready for:

* Trend analysis
* Anomaly detection
* Dashboarding
* Predictive modeling

---

# 🔬 Agronomic Interpretation Layer

The notebooks now include interpretation logic for:

* SWC in irrigated systems
* LST thermal stress thresholds
* Biomass proxy vigor inference
* NDVI vs NDRE canopy stage differentiation
* Early nitrogen stress detection

Designed specifically for crops such as:

* Tobacco (irrigated)
* Soybean
* Corn
* Perennial crops
* ESG-monitored areas

---

# 🚀 Why This Repository Is Different

This project integrates:

* API engineering
* Raster processing
* Pixel masking
* Spectral analysis
* Time series modeling
* Agronomic interpretation
* Cost-awareness (quota monitoring)

It is a **remote sensing intelligence stack**, not just a demo.

---

# ⚠️ Important Notes

* Valid Planet API credentials required
* Product access depends on contract
* Large AOIs may be restricted
* Always monitor quota before large batch operations

---

# 🎯 Target Audience

* Precision agriculture professionals
* Environmental monitoring specialists
* ESG analytics teams
* Remote sensing engineers
* Data scientists working with geospatial data
* Consultants building agronomic intelligence systems

---

# 🌍 Final Perspective

These notebooks demonstrate how to transform:

Satellite data → Clean raster → Valid pixels → Spectral indices → Structured time series → Agronomic insight → Decision support.

This is the bridge between **remote sensing and actionable intelligence**.
