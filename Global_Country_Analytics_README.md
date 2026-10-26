# 🌍 Global Country Data Analytics Dashboard

An interactive **Power BI dashboard** for exploring country-level
population, geography, human development, and internet-usage data.

## 📊 Dashboard Features

-   **Country Explorer** with searchable country selection
-   Dynamic **Country Profile** showing Country, Continent, Population,
    Total Area, HDI, and Internet Usage
-   **Average Population Density** KPI
-   **Average Internet Usage** KPI
-   **Top 10 Countries by Population**
-   **HDI vs Internet Usage** scatter analysis
-   **Land vs Water** doughnut chart
-   Continent-level analysis
-   Interactive filters and cross-highlighting

## 🛠️ Tools & Technologies

  Tool               Purpose
  ------------------ -----------------------------------
  Power BI Desktop   Dashboard and visualization
  Power Query        Data cleaning and transformation
  DAX                Measures and calculations
  CSV / Excel        Source data
  GitHub             Project hosting and documentation

## 📁 Suggested Repository Structure

``` text
Global-Country-Analytics/
├── README.md
├── PowerBI/
│   └── Global-Country-Analytics.pbix
├── Data/
│   └── country_stats.csv
├── Screenshots/
│   ├── dashboard-overview.png
│   ├── country-profile.png
│   ├── population-ranking.png
│   └── hdi-internet-usage.png
└── Documentation/
    └── data-dictionary.md
```

> Check the dataset license before uploading the raw CSV publicly.

## 📌 Main Dataset Fields

  Field                                Description
  ------------------------------------ ------------------------------------
  Country name                         Country identifier
  Population                           Total population
  Land in km2                          Land area
  Inland water in km2                  Inland water area
  Total in km2                         Total area
  HDI                                  Human Development Index
  \% of internet users in population   Internet usage
  Continent                            Dashboard continent classification

## 🧮 Key DAX Measures

### Average Population Density

``` dax
Average Population Density =
AVERAGE('country_stats'[Population Density])
```

### Average Internet Usage

If the source stores values such as `89.6`:

``` dax
Average Internet Usage =
DIVIDE(
    AVERAGE('country_stats'[% of internet users in population]),
    100
)
```

Format the measure as **Percentage**.

### Total Land Area

``` dax
Total Land Area =
SUM('country_stats'[Land in km2])
```

### Total Water Area

``` dax
Total Water Area =
SUM('country_stats'[Inland water in km2])
```

### Total Area

``` dax
Total Area =
[Total Land Area] + [Total Water Area]
```

### Selected Country

``` dax
Selected Country =
SELECTEDVALUE(
    'country_stats'[Country name],
    "Select a Country"
)
```

### Selected HDI

``` dax
Selected HDI =
SELECTEDVALUE('country_stats'[HDI])
```

## 🎨 Design

The dashboard uses a clean, modern light theme with white cards,
blue/purple accents, rounded containers, consistent typography, clear
KPI hierarchy, interactive filters, and minimal visual clutter.

## 🔄 Data Refresh

For local development:

1.  Update the CSV/Excel source.
2.  Open the `.pbix` file in Power BI Desktop.
3.  Select **Refresh**.
4.  Power BI reloads the updated source data.
5.  Review the dashboard visuals and measures.

Online refresh depends on the source location and Power BI deployment
configuration.

## 🚀 Getting Started

Clone the repository:

``` bash
git clone https://github.com/YOUR-USERNAME/Global-Country-Analytics.git
```

Open:

``` text
PowerBI/Global-Country-Analytics.pbix
```

with Power BI Desktop.

If the source path has changed, use:

**Home → Transform data → Data source settings**

Then update the source location and refresh the report.

## 🌐 Deployment Note

GitHub can host the project's documentation, screenshots, source files,
and project files where licensing permits.

Uploading a `.pbix` file to GitHub does **not** turn it into a fully
interactive web dashboard. For an interactive online Power BI report,
use a supported Power BI publishing/sharing method, or rebuild the
dashboard as a web application using a suitable web/analytics stack.

## 📷 Screenshots

After uploading screenshots to the repository, reference them like:

``` markdown
![Dashboard Overview](Screenshots/dashboard-overview.png)
```

Recommended screenshots:

-   Dashboard overview
-   Country profile
-   Top 10 population
-   HDI vs Internet Usage
-   Land vs Water
-   Country search

## 🔮 Future Improvements

-   Interactive world map
-   Historical trend analysis
-   Year-over-year comparisons
-   Advanced country comparison
-   Drill-through country pages
-   Tooltip pages
-   Automated refresh
-   Data-quality checks
-   Mobile-optimized layout
-   Additional development indicators

## 👤 Author

**Muhammad Samaan**

Built with **Power BI • Power Query • DAX • Data Visualization**

## 📄 License

Add the appropriate license for the project and verify the license of
the underlying dataset before redistributing it.
