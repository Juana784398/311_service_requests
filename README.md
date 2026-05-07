# Winnipeg 311 Service Request Analysis: Operational Demand Dashboard

## Project Overview

This project analyzes over **90,000** records from the `City of Winnipeg's 311 Service Request` dataset to uncover patterns in public service demand. By transforming raw, messy data into two interactive dashboards, this study identifies operational hotspots, peak demand windows, and geographic trends to support effective city resource planning.

## Project Assets
* [**Temporal Demand Trends**](./reports/dashboard1.png) - Operational dashboard for time-series and peak-period analysis.
* [**Geospatial Service Requests**](./reports/dashboard2.png) - Geographic dashboard featuring ward and neighborhood distribution.
* [**Technical Workbook**](./311_Service_Request.xlsx) - Complete Excel workflow: cleaning, engineering, and pivot architecture.

## Tools and Skills
- Software: Microsoft Excel (Advanced)

- Formulas: `XLOOKUP`, `IFS`, `INT`, `TEXT`, `LARGE`, Absolute Referencing (`$`)

- Techniques: Data Cleaning, Feature Engineering, Time-Series Analysis, Dashboard Design

- Visuals: Pivot Tables/Charts, Slicers, Camera Tool, Conditional Formatting (Heatmaps)


## Dataset
The City of Winnipeg 311 Service Request dataset contains over 90,000 records including:

* Combined `Date/Time`
* `Service Area`
* `Service Request Type`
* `Ward`
* `Neighborhood`
* `Location` (geographic coordinates)
* `Point` (alternate coordinate format)


## Part 1: Data Cleaning & Feature Engineering
Before analysis, a dedicated **Working Sheet** was used to transform the raw dataset:

1.  **Temporal Engineering:** Deconstructed combined timestamps into features:
    * **Date & Year:** Extracted via `=INT([@Date/Time])`.
    * **Month & Season:** Mapped using `TEXT()` and `IFS` statements (Winter, Spring, Summer, Fall).
    * **Day & Category:** Grouped 24-hour time into operational blocks: *Morning, Afternoon, Evening, Night, and Overnight*.
2.  **Data Normalization:**
    * **Missing Values:** Replaced `Null` values in Ward and Neighborhood fields with `"Unknown"` to prevent data gaps.
    * **Coordinate Parsing:** Split unstructured `Location` strings into distinct `Latitude` and `Longitude` columns for future mapping.

## Part 2: Dashboard Architecture

### Dashboard 1: Volume & Time Trends
Focused on **when** demand occurs through high-level temporal analysis.
* **Seasonal Trends:** Line charts showing monthly fluctuations.
* **Hourly Distribution:** Histogram-style charts visualizing 24-hour activity.
* **Operational Heatmap:** A "Time vs. Day" matrix highlighting peak periods using Excel's **Camera Tool**.

### Dashboard 2: Geographic Demand Analysis
Focused on **where** demand occurs, utilizing a custom-engineered data structure to ensure accuracy.
* **Ward Rankings:** Horizontal bar chart of total requests by Ward.
* **Top 15 Neighborhoods:** Clustered column chart identifying high-volume areas.
* **Demand Treemap (Heatmap):** A hierarchical visualization of Top 10 Wards and their Top 5 Neighborhoods.
    * **Technical Deep-Dive:** Standard Pivot Table filtering distorted Ward-level totals during hierarchical analysis. To preserve accurate parent-level aggregation, a Helper Table architecture was implemented using separate Pivot Tables, `XLOOKUP`, and Absolute References (`$`). 


## Key Insights
- **Seasonal Demand:** Service requests were highest from January through May, with April recording the single highest monthly volume.
- **Peak Service Hours:** Request activity peaked at 6 PM, while overnight activity (11 PM - 5 AM) remained consistently low.
- **Weekday Demand Pattern:** Weekdays generated substantially more requests than weekends, with elevated activity persisting from 7 AM to 9 PM.
- **Operational Hotspot:** The heatmap identified Monday-Thursday at 6 PM as the highest-demand operational window.
- **Ward Concentration:** Mynarski recorded the highest request volume, exceeding 10,000 requests, while most other wards remained around 6,000.
- **Neighborhood Clustering:** St. John's and William Whyte were the highest-volume neighborhoods and were both located within the Mynarski ward. Chalmers ranked third overall within the Elmwood - East Kildonan ward.




## Conclusion

The analysis reveals strong temporal and geographic demand patterns in Winnipeg's public service system. By transforming large-scale operational data into interactive dashboards, this project demonstrates the ability to clean, structure, and visualize complex datasets to support operational planning and resource allocation.


---


