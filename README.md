# 🏡 U.S. County Housing & Rent Affordability Atlas  
**(Static Web App — Leaflet + Chart.js Edition)**  
**Live App:** https://historical-us-housing-data.onrender.com/  

![Site Example Map & Chart](https://github.com/JonnyMurillo288/Historical-Housing-Data/blob/main/site_screenshot.png)

![County Housing Affordability Map](https://github.com/JonnyMurillo288/Housing-Data/blob/main/HAI_2000_2023_publish_v3_new_color.jpg)

This project provides an interactive, browser-based exploration of **U.S. county-level housing affordability** using a custom-built **JavaScript (Leaflet) web mapping framework**. The goal is to unify and visualize long-term affordability trends using county-level historical Census and modern ACS data.

It is the successor to the earlier Streamlit dashboard and now runs entirely client-side using:

- **Leaflet** for mapping  
- **Chart.js** for time-series charts  
- **Custom JavaScript engine** for color scales, comparison logic, map interactions, and UI state  
- **Static JSON files** for all geographic and metric inputs  

---

## Overview

This is a lightweight, fast, fully client-side spatial tool that lets users:

### **1. View Single-Year Snapshots**
For any selected year, explore:
- Median household income  
- Median home value  
- Median gross rent  
- HAI (Housing Affordability Index)  
- RAI (Rent Affordability Index)  
- Monthly income ratios  
- Geographic patterns across all U.S. counties  

### **2. Compare Two Years**
The comparison mode computes and maps **% change** between user-selected years for:
- Income  
- Home values  
- Median gross rent  
- HAI  
- RAI  

Special diverging color ramps highlight counties where affordability has improved or worsened.

### **3. Inspect Individual Counties**
When comparing two years, users may:
- Select a county  
- View **line charts** for both HAI and RAI over time  
- Visually compare long-term affordability trends  

---

## Core Affordability Metrics

### **Housing Affordability Index (HAI)**  
```
HAI = Median Home Value / Median Household Income
```

### **Rent Affordability Index (RAI)**  
```
RAI = Median Household Income / Median Gross Rent
```

Where:
- Median gross rent includes utilities
- Monthly income is computed as `median_household_income / 12`

These indices offer simple, interpretable comparisons of housing cost burdens across counties and across time.

---

## Data Sources

This project integrates multiple sources:

- **ACS (2000–2023)** — median income, home values, rents  
- **Decennial Census (1980, 1990)** — harmonized fields for historical values  
- **SAIPE (when interpolating older income data)**  
- **Spatial data:** county geometries converted from Shapefiles → Parquet → GeoJSON  

All data is preprocessed into two static assets:

```
data/metrics.json        # Per-county metrics by year
data/counties.geojson    # County geometry
```

These are consumed client-side by the JavaScript application.

---

## Architecture (Current Framework)

### **Static Site — No Backend Required**
The application is rendered entirely via HTML + CSS + JavaScript:

```
project/
  index.html
  css/
    styles.css
  js/
    main.js
  data/
    metrics.json
    counties.geojson
```

---

## Data Processing (To Fill In)
_Add your full preprocessing pipeline here: sources, joins, cleaning logic, imputation, harmonization across years, and how parquet → json → geojson was produced._

---

## Analysis Section (To Fill In)
_Add your interpretation of the results, national patterns, affordability crises, and any state/county case studies you want to document._

---

## Deployment

### Via Render (Static Site)
1. Push this folder structure to GitHub  
2. Create a **Render → Static Site**  
3. Set `staticPublishPath` to the project root  
4. Deploy  

Your app loads entirely client-side and requires no backend.

---

## 📜 License
MIT (or specify your own)
