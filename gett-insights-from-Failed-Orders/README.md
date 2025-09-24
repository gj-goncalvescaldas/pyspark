# Gett_Insights_from_Failed_Orders

## Problem Description

This data project is based on a real take-home assignment used during the recruitment process for data science positions at Gett, a corporate Ground Transportation Management platform. The objective is to analyze unsuccessful ride orders—those in which a client did not end up getting a car after placing a request via the Gett application.

When a client places an order, the system attempts to match it with a relevant driver. However, not all orders succeed. This project focuses on understanding the reasons behind these failures using two datasets: `data_orders` and `data_offers`.

> **Note:** This problem will be solved using **PySpark** in a **Databricks** environment to efficiently handle data processing and analysis.

### Objectives

1. **Categorize Failure Reasons**  
   Create a distribution of failed orders based on:
   - Cancellations before driver assignment
   - Cancellations after driver assignment
   - Order rejections  
   Analyze the resulting distribution and identify which category is most frequent.

2. **Hourly Distribution of Failures**  
   Plot failed orders by hour. Look for time-based patterns or anomalies. Determine:
   - Hours with a higher proportion of specific failure types
   - The time period with the highest failure rates
   - Potential reasons behind these patterns

3. **Cancellation Time Analysis**  
   Analyze average cancellation times (with and without driver assignment) by hour.  
   - Remove any outliers that may distort interpretation  
   - Derive insights from these trends

4. **ETA Analysis**  
   Plot the average Estimated Time of Arrival (ETA) by hour.  
   - Interpret the trends in ETA distribution  
   - Consider implications of the findings

5. **Bonus: Geospatial Analysis Using Hexagons**  
   Using the `h3` and `folium` libraries:
   - Determine how many size-8 hexagons contain 80% of all orders  
   - Visualize these hexagons on a map  
   - Color them by the number of failed orders

### Data Overview

**data_orders.csv**
- `order_datetime`: Timestamp of the order
- `origin_longitude`, `origin_latitude`: Geolocation of the order
- `m_order_eta`: Estimated arrival time
- `order_gk`: Unique order identifier
- `order_status_key`: Order status (4 = cancelled by client, 9 = rejected by system)
- `is_driver_assigned_key`: Indicates if a driver was assigned
- `cancellation_time_in_seconds`: Time elapsed before cancellation

**data_offers.csv**
- `order_gk`: Order identifier (linked with `data_orders`)
- `offer_id`: Identifier for the offer presented to drivers

### Implementation Note

The entire solution will be developed using **PySpark** within **Databricks**, leveraging its distributed computing capabilities to efficiently manipulate and analyze large-scale data. The focus will be on structuring the code logically, ensuring reproducibility, and clearly presenting findings.
