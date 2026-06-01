 # Uber Trip Fare Analysis 🚖📊

An end-to-end **Exploratory Data Analysis (EDA)** on a dataset of **200,000 Uber rides** to identify the key spatial and temporal factors influencing ride-hailing dynamic pricing. This project investigates how physical distances, city traffic congestion, and daily time cycles predict and alter fare progression.

---

## 📈 Executive Summary & Research Framework

Traditional taxi pricing relies on rigid meters that fail to adapt to real-time urban contexts. This repository features a structured analysis to validate modern dynamic pricing principles based on academic literature.

### 📌 Core Hypotheses Tested
1. **Distance vs. Price:** The physical distance of a trip and the specific time it takes place will directly predict the ride's `fare_amount` *(Reference: Muhammad, A. R., 2025)*.
2. **Traffic Congestion Charges:** Trips taken during peak traffic hours (weekday rush hours) generate a significantly higher `fare_amount` per mile than off-peak trips.
3. **Late-Night Valuations:** Fares requested during late-night cycles (12:00 AM – 5:00 AM) experience lower localized demand and yield lower relative fares *(Reference: The Economic Times / ET Infra)*.

---

## 🛠️ Tech Stack & Libraries Used

* **Language:** Python 3.x
* **Data Manipulation:** `pandas`, `numpy`
* **Data Visualization:** `matplotlib`, `seaborn`

---

## 🧹 Data Pipeline & Data Cleaning

The raw dataset containing 200,000 records underwent a rigorous data preparation pipeline to ensure statistical integrity:

* **Feature Dropping:** Discarded arbitrary identifier columns (`Unnamed: 0`, `key`).
* **Financial Filtering:** Isolated realistic entries by eliminating non-positive fares (`fare_amount <= 0`) and capping extreme outliers (`fare_amount < $200`).
* **Temporal Conversion:** Cast object timestamps into proper `datetime` variables for seamless feature extraction.
* **Geospatial Integrity:** Bound pickup and drop-off coordinates to strict regional borders (New York Metropolitan area: Latitude `[40, 42]`, Longitude `[-74, -72]`) to strip out corrupt/invalid GPS points.

---

## 📊 Key Insights & Visualizations

### 💵 1. Fare Amount Distribution
The univariate distribution of pricing reveals that the majority of Uber rides are budget-friendly, highly concentrated between **$5 and $15**. Long-distance or high-tariff rides diminish sharply.
<img width="1063" height="695" alt="image" src="https://github.com/user-attachments/assets/bd11b563-94a3-41e7-88d5-6849f4c42fe2" />


| Metric | Detail |
| :--- | :--- |
| **Data Rows Analysed** | ~199,970 (Post-cleaning) |
| **Primary Fare Range** | $5.00 – $15.00 |
| **Geographic Core** | NYC Coordinates (~40.75° N, ~73.98° W) |

---

## 💡 Key Takeaways

* **Distance vs. Price:** Physical trip distance is the strongest factor driving `fare_amount`, but traffic conditions heavily distort this relationship during peak times.
* **Peak Hour Surge:** Weekday rush hours (8 AM - 10 AM and 4 PM - 7 PM) see a noticeable spike in price-per-mile, confirming how Uber's pricing adapts to city congestion.
* **Late-Night Demand:** Average fares actually dip between 1 AM and 4 AM on weekdays due to lower overall demand, debunking the myth that late-night rides are always more expensive.

---

## 🏁 Conclusion

This analysis successfully validated the core dynamics of ride-hailing pricing models using a 200,000-trip dataset. The findings confirm that while physical distance serves as the foundational baseline for predicting `fare_amount`, urban variables introduce significant variations.

* **Congestion Multipliers:** High-traffic weekday windows drastically increase the fare-per-mile ratio, proving that time-spent-in-traffic heavily influences dynamic pricing algorithms.
* **The Off-Peak Myth:** Late-night hours do not inherently guarantee premium rates; a steep drop in baseline weekday demand between 1 AM and 4 AM actually results in lower average fares compared to mid-day travel.

Ultimately, the data shows that Uber's pricing model functions less like a rigid taxi meter and more like a real-time reflection of urban supply, demand, and traffic density.
