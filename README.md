# CapstoneProject2_JCDSAH-023_GalihNurhidayat

NYC TLC Trip Analysis – Revenue Forecasting & Ops Optimization
This repository contains a practical analysis of New York City taxi trips using the NYC TLC trip records.
The goal is to forecast revenue from trip distance, identify peak demand (day & time), and provide operational recommendations that increase revenue and efficiency.

Objectives
1. Model the relationship between trip_distance and fare_amount to forecast revenue.
2. Profile demand by day-of-week and 3-hour intervals to optimize driver allocation.
3. Map demand by drop-off zones (e.g., TLC location IDs).

Key Findings
1. Linear trendline between distance and fare performs best (R² ≈ 0.85).
2. Peak day: Tuesday (~16.5% of requests).
3. Lowest demand: Saturday & Sunday (~12.4% each).
4. Peak window: 12:00–20:00—concentrate supply here.
5. High-demand zones: e.g., Manhattan East Harlem South (DoLocationID 75).

Data Cleaning and Formatting
1. Removed rows with trip_distance <= 0 or fare_amount <= 0.
2. Set infinite ratios (e.g., Fare/distance) to NaN and dropped rows causing infinities.
3. Capped visuals at fare_amount ≤ 175 for readable charts (model tested both on full & capped).
4. Parsed pickup_datetime / dropoff_datetime into separate date & time fields.
5. Created hour groups in 3-hour bins (00–02, 03–05, …, 21–23).

Business Recommendations
1. Forecasting & Pricing: Use the linear model to estimate fares by distance and inform pricing (including targeted surges).
2. Ops Focus: Allocate more drivers Tue and weekdays, especially 12:00–20:00.
3. Zone Strategy: Prioritize high-demand dropoff zones (e.g., East Harlem South) with supply and promotions.
4. Reporting: Track weekly trends of distance mix, fare per mile, and peak-window conversion.
