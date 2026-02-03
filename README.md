# London Bike Hire vs Weather Analysis Using Apache Spark (PySpark)

## Overview
This project studies how London weather affects TfL daily cycle hires.

An end-to-end Apache Spark (PySpark) pipeline was built to clean, join, and analyse weather and bike hire data, followed by visualisation of trends and correlations.

---

## Datasets

- **London Weather (1979–2023)**  
  https://www.kaggle.com/code/zongaobian/london-weather-trends-and-forecasts-1979-2023  

- **TfL Daily Cycle Hires (2010–2025)**  
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

1. Start Spark session and load both CSV files into DataFrames.  
2. Clean weather data: standardise dates and handle **1204 null values**  
   - rainfall & sunshine → 0  
   - humidity → mean  
3. Clean cycle hire data: fix date formats and remove outliers using **mean ± 4×std rule**.  
4. Join datasets on date → final dataset contains **4078 rows**.  
5. Feature engineering:
   - `year`, `month`, `dayofweek`
   - `is_weekend`
   - `rain_flag`
   - `temp_band`
   - `feels_like`
6. Perform correlation analysis and generate Matplotlib visualisations.

---

## Key Results

- Temperature vs hires: **r = 0.648** (positive)  
- Rainfall vs hires: **r = −0.246** (negative)  
- Sunshine vs hires: **r = 0.532** (positive)  
- Humidity vs hires: **r = −0.534** (negative)  

**Conclusion:** warm and dry days increase bike hires, while rainy or humid conditions reduce demand.

---

## Repository Structure

```text
Datasets/                          Datasets used in the pipeline
Cloud_Project_SparkOnly_Final__1_.ipynb   Main Spark notebook (pipeline + analysis)
Cloud_Project_Report_Khushi_Mrinal.pdf    Detailed project report
README.md                          Project documentation
```

## Contributions

| Name | Email | Key Contributions |
|------|------|-------------------|
| Khushi Bijkal | khushi.natrajbijkal2@mail.dcu.ie | Data cleaning, EDA visualisations, feature engineering, interpretation of results, final report |
| Mrinal Vattiprolu | mrinal.vattiprolu2@mail.dcu.ie | Data preparation, dataset integration, Spark pipeline assistance |
