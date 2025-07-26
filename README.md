# 📊 Power BI Report – CBR Report

## 📝 Overview
The **CBR Report** is a Power BI dashboard that presents a comprehensive analysis of population and birth-related statistics by continent and country. The report leverages advanced Power BI features such as **Drillthrough**, **Bookmarks**, **Page Navigation**, **Custom Tooltips**, and **DAX Measures** to enhance interactivity and analytical power.

---

## 🖼️ Dashboard Preview

![CBR Report Dashboard](.<img width="1333" height="743" alt="Ekran şəkli 2025-07-26 111638" src="https://github.com/user-attachments/assets/da68bb2e-3dc8-4bd4-bee6-6c16ee3e2a55" />
)

---

## 🚀 Features

### 1. 🔍 Drillthrough
- Right-click on visuals like population or CBR bars to drill into detailed data by:
  - Country
  - Continent

### 2. 📑 Bookmarks
- Bookmarks are used to:
  - Switch between main views
  - Reset visuals and filters
  - Highlight key demographic insights

### 3. 🧭 Page Navigation
- Sidebar buttons allow navigation between:
  - Overview
  - Map Analysis
  - Country-level Details

### 4. 💡 Custom Tooltips
- Tooltip pages are configured to show:
  - Hover insights on CBR values
  - Additional detail for bubble and bar charts

### 5. 📊 Parameters
- **What-If Parameters** for:
  - Population projection years
  - Continent-level filtering
  - Time series analysis from 1960–2023

---

## 🔢 Key Metrics Displayed

- **Avg Population**: 25.3M  
- **Avg Density**: 460.3  
- **Avg CBR**: 27.9  
- **Avg Birthrate per 1000**: 1.18  
- **Total Birthrate**: 15.7K  
- **Total CBR**: 461.8K  
- **Total Density**: 99K  
- **Total Population**: 347B  
- **Total Annual Births**: 8B  

---

## 📈 Visuals Included

| Visual | Description |
|--------|-------------|
| **CBR % by Continent** | Donut chart showing % share by continent |
| **Total Population by Continent** | Horizontal bar chart with % scale |
| **Total Annual Births** | Bar chart with birth numbers per continent |
| **Geo Map** | Map showing country-level data by continent |
| **CBR by Continent** | Bar chart for total CBR figures |
| **CBR vs Population** | Scatter plot with time-based slider |

---

## 🧠 DAX Functions Used

The report uses several DAX functions to compute metrics and dynamic interactivity:

- `CALCULATE()`
- `FILTER()`
- `ALLSELECTED()`
- `SELECTEDVALUE()`
- `SAMEPERIODLASTYEAR()`
- `DIVIDE()`
- `RANKX()`
- `ISINSCOPE()`
- `SWITCH()`
- `IF()`
- `VAR` / `RETURN`

---

## 📐 Sample Measures

```DAX
Total Population = SUM('Demographics'[Population])

Total CBR = SUM('Demographics'[CBR])

CBR per 1000 = DIVIDE([Total CBR], [Total Population]) * 1000

Population Rank = 
RANKX(
  ALLSELECTED('Demographics'[Country]),
  [Total Population],
  ,
  DESC
)
