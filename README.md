# Spark Bike Hire–Weather Pipeline (London)

## Overview
This project studies how London weather affects TFL daily cycle hires.  
We built an end-to-end Apache Spark (PySpark) pipeline to clean, join, and analyse weather and bike hire data, and then visualised the trends.

---

## Datasets
- **London Weather (1979–2023):**  
  https://www.kaggle.com/code/zongaobian/london-weather-trends-and-forecasts-1979-2023  

- **TFL Daily Cycle Hires (2010–2025):**  
  https://www.kaggle.com/datasets/belayethossainds/tfl-daily-cycle-hires-data  

**Overlap used for analysis:** 2010–2023 (weather data ends in 2023).

---

## Tools Used
- Apache Spark (PySpark)  
- Spark DataFrames / Spark SQL  
- Matplotlib  
- Jupyter Notebook  

---

## Pipeline Summary
1. Start Spark session and load both CSVs into DataFrames.  
2. Clean weather data: fix dates, convert units, handle **1204 nulls**  
   - rain & sunshine → 0  
   - humidity → mean  
3. Clean cycle hire data: fix dates, remove outliers using **mean ± 4×std rule**.  
4. Join datasets on date → final dataset **4078 rows**.  
5. Feature engineering: `year`, `month`, `dayofweek`, `is_weekend`, `rain_flag`, `temp_band`, `feels_like`.  
6. Correlation analysis + Matplotlib visualisations.

---

## Key Results
- Temp vs hires: **r = 0.648** (positive)  
- Rain vs hires: **r = −0.246** (negative)  
- Sunshine vs hires: **r = 0.532** (positive)  
- Humidity vs hires: **r = −0.534** (negative)  

**Conclusion:** warm/dry days increase hires; rainy/humid days reduce hires.

---

## How to Run
```bash
git clone https://gitlab.computing.dcu.ie/khushi.natrajbijkal2/spark-bike-hire-weather-pipeline.git
cd spark-bike-hire-weather-pipeline
