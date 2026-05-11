# Winnipeg 311 Service Request Analysis - Operational Demand Dashboard

## Project Overview  
This project analyzes over **90,000 service requests** from the City of Winnipeg's 311 system to uncover patterns in public service demand across time and geography.

The goal is to transform raw municipal data into interactive dashboards that reveal operational hotspots, peak demand periods, and geographic distribution of citizen service requests.

## Key Insights

- Weekdays consistently generated higher service demand than weekends, indicating work-week driven reporting behavior.  
- Peak activity occurs around 6:00 PM, suggesting citizens submit requests after work hours.  
- Tuesday at 6:00 PM recorded the highest single-hour demand across the dataset. 
- Service requests are lowest between 11:00 PM and 5:00 AM, showing clear overnight inactivity.   
- Late Winter to early spring months show slightly elevated demand compared to other seasons.
- Certain wards (e.g., Mynarski, Elmwood, Point Douglas) consistently dominate request volume, indicating geographic concentration of issues. 
- Mynarski recorded the highest overall request volume, exceeding 10,000 requests, while most other wards remained near 6,000.  
- St. John's and William Whyte were the highest-volume neighborhoods and were both located within the Mynarski ward.


## Tools & Skills

- Microsoft Excel (Advanced)
- Data Cleaning & Transformation
- Feature Engineering (Time & Seasonal Categorization)
- Time-Series Analysis
- Pivot Tables & Pivot Charts
- Interactive Dashboard Design
- Heatmap Analysis (Conditional Formatting)
- Slicers & Dynamic Filtering
- Data Visualization & Storytelling

## Dataset

The City of Winnipeg 311 Service Request dataset contains over **90,000** records including:

- Combined `Date/Time`
- `Service Area`
- `Service Request Type`
- `Ward`
- `Neighborhood`
- `Location` (geographic coordinates)
- `Point` (alternate coordinate format) 


## Data Preparation & Feature Engineering

### 1. Temporal Feature Engineering
- Split combined Date/Time into separate components  
- Extracted Year, Month, Day, and Hour  
- Grouped months into Seasons (Winter, Spring, Summer, Fall)  
- Categorized time into operational periods (Morning, Afternoon, Evening, Night, Overnight) 


### 2. Data Cleaning
- Replaced missing values in Ward and Neighborhood with "Unknown" 
- Standardized inconsistent geographic fields  
- Parsed coordinate strings into structured Latitude and Longitude fields  

## Dashboard Structure

### Dashboard 1: Time-Based Demand Analysis
- Seasonal trend line chart (monthly volume patterns)  
- Hourly distribution chart (simulated histogram)  
- Heatmap (Time of Day vs Day of Week) using conditional formatting  


### Dashboard 2: Geographic Demand Analysis
- Ward-level ranking (horitzontal bar chart)  
- Top 15 neighborhoods by request volume (column chart)
- Heatmap-style treemap (Ward --> Neighborhood hierarchy)  


## Technical Highlights

- Built multi-layer pivot table architecture for time + geography analysis  
- Used Excel Camera Tool for dynamic dashboard embedding  
- Implemented slicers for Year and Service Area filtering  
- Created helper tables to preserve hierarchical accuracy in aggregations  
- Designed reusable feature engineering logic for time-based categorization  

## Project Assets
* [**Temporal Demand Trends**](./reports/dashboard1.png)
* [**Geospatial Service Requests Trends**](./reports/dashboard2.png)
* [**Technical Workbook**](./311_Service_Request.xlsx)

## Outcome

This project converts large-scale municipal service data into an interactive analytical dashboard that supports operational planning and resource allocation.

It demonstrates the ability to:
- Clean and structure large real-world datasets  
- Engineer meaningful analytical features  
- Build executive-level dashboards in Excel  
- Extract actionable operational insights from public data  
