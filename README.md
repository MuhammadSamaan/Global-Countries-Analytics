# 🌍 Global Countries Analytics Dashboard

**An interactive 4-page Power BI report that turns raw country statistics into clear, decision-ready insights across 195 countries, covering population, geography, human development, health and digital access.**

![Global Overview](Output%20Images/CA%20Image1.JPG)

---

## 🎯 Business Problem

Policy makers, researchers and analysts need to compare countries quickly, but the data is spread across many indicators and is hard to read in raw tables. This dashboard brings **13 indicators for 195 countries** into one place so a user can:

- Get the global picture in seconds (KPI cards, world map, rankings)
- Drill into any single country with one click
- Test relationships such as *"Does higher human development go with higher internet access?"*

---

## 📊 Dashboard at a Glance

| KPI | Value |
|---|---|
| Countries analysed | **195** |
| World population | **8.03 bn** |
| Average HDI | **0.74** |
| Average population density | **317.4 / km²** |
| Average internet usage | **70.7 %** |
| Average fertility rate | **2.35** |

### Page 1: Global Overview
KPI cards, interactive world map, Top 10 countries by population, highest-HDI countries, and population density vs internet usage.

### Page 2: Population & Geography
Land vs water split, population ranking, largest countries by area, and most densely populated countries.

![Population & Geography](Output%20Images/CA%20Image5.JPG)

### Page 3: Development & Demographics
HDI vs internet usage, highest fertility and mortality rates, and continent-level comparison.

![Development & Demographics](Output%20Images/CA%20Image7.JPG)

### Page 4: Country Explorer
Searchable country table with HDI, population and internet-usage filters, a country profile card, and a Top 10 external-debt chart.

![Country Explorer](Output%20Images/CA%20Image9.JPG)

---

## 🔍 Key Insights

1. **Population is highly concentrated.** India (1.43 bn) and China (1.40 bn) together hold about **35 %** of the world's population.
2. **Development and digital access move together.** HDI and internet usage have a correlation of **+0.86**. Countries with HDI above 0.8 average **91 %** internet usage, while countries below 0.55 average only **28 %**.
3. **Development and fertility move in opposite directions.** HDI and fertility rate have a correlation of **-0.85**. Fertility falls from an average of **4.16** (low-HDI countries) to **1.52** (very-high-HDI countries).
4. **Top of the HDI ranking is Nordic and Alpine.** Iceland (0.972), Norway (0.970) and Switzerland (0.970) lead the index. South Sudan (0.388) is lowest.
5. **Density is driven by city-states.** Monaco (19,429 / km²) and Singapore (8,202 / km²) are far ahead of every large country.
6. **Highest fertility is in Africa.** Chad (5.84), Somalia (5.81) and the Central African Republic (5.69) lead the ranking.
7. **External debt is concentrated in a few economies.** The United States (about 30.2 trillion USD), the United Kingdom and France top the list.

---

## 🧰 Skills Demonstrated

| Area | What was done |
|---|---|
| **Data modelling & cleaning** | Prepared a 195-row, 13-column CSV in Power Query (data types, comma-formatted numbers, missing values) |
| **DAX** | Built measures for averages, area totals, percentages and dynamic selected-country labels |
| **Dashboard design** | Consistent navy theme, left navigation panel, KPI cards, 4 themed pages |
| **Interactivity** | Country slicer that updates every visual, search box, HDI / population / internet filters, cross-highlighting |
| **Visual storytelling** | Right chart for each question: map, ranked bars, scatter plot, doughnut, table |

### Sample DAX Measures

```dax
Average Internet Usage =
DIVIDE(AVERAGE('country_stats'[% of internet users in population]), 100)

Total Area = [Total Land Area] + [Total Water Area]

Selected Country =
SELECTEDVALUE('country_stats'[Country name], "Select a Country")
```

---

## 🖱️ Interactive Country Drill-Down

Selecting a country in the slicer instantly re-computes every KPI, chart and map on the page.

| Pakistan | Germany |
|---|---|
| ![Pakistan](Output%20Images/CA%20Image3.JPG) | ![Germany](Output%20Images/CA%20Image6.JPG) |

---

## 📁 Repository Structure

```text
Global Countries Analysis/
├── Countries Analysis.pbix        # Power BI report (open in Power BI Desktop)
├── country_stats.csv              # Source dataset (195 countries, 13 fields)
├── Output Images/                 # Dashboard screenshots
└── README.md
```

## 🚀 How to Run

1. Download or clone this repository.
2. Open **`Countries Analysis.pbix`** in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).
3. If the data source path differs on your machine: **Home → Transform data → Data source settings → Change source** and point it to `country_stats.csv`, then click **Refresh**.
4. To see the world map, enable it under **File → Options → Security → Use Map and Filled Map visuals**.

---

## 🔮 Next Steps

- Add time-series data for historical trends and year-over-year comparison
- Drill-through country pages and custom tooltips
- Publish to Power BI Service with scheduled refresh

---

## 👤 About the Author

**Muhammad Samaan**: Computer Science graduate (Iqra University, Karachi), Core Interests **Data Analytics, Business Intelligence Tools, Data Enginner, Data Scientist Full-Stack Development**. I'm open to roles, remote or on-site. Would Love to Connect with Professionals and Industry's Giants. Feel free to reach me out even if you are anyone, need assistance and want to ask or discuss something.

📧 mohammadsamaan105@gmail.com
🔗 [LinkedIn](https://linkedin.com/in/muhammad-samaan) · 💻 [GitHub](https://github.com/MuhammadSamaan)

---

*Built with **Power BI · Power Query · DAX · Data Visualization***
