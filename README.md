# London Bike Hire vs Weather Pipeline (PySpark)

An end-to-end **Apache Spark (PySpark)** pipeline that combines London weather data with **TfL daily bike hire** records to understand how weather influences cycling demand.

---

## Highlights
- Built a full pipeline: ingestion → cleaning → joining → feature engineering → analysis → visualization
- Engineered features like `rain_flag`, `is_weekend`, `temp_band`, and `feels_like`
- Produced insights using Spark SQL and Matplotlib

---

## Problem
In large cities like London, bike hire usage changes with weather. This project explores how factors such as temperature, rainfall, sunshine, humidity, and wind impact daily bike hires.

---

## Pipeline Overview
1. Ingest CSV datasets into Spark DataFrames  
2. Clean: standardize dates, handle nulls, convert units, remove outliers  
3. Join datasets on date (overlap period **2010–2023**)  
4. Feature engineering:
   - `year`, `month`, `dayofweek`
   - `is_weekend`
   - `rain_flag`
   - `temp_band`
   - `feels_like`
5. Analyze and visualize trends using Spark outputs and charts  

---

## Key Findings
- Mean temperature is strongly positively correlated with hires (**r ≈ 0.65**)
- Sunshine hours show a positive relationship (**r ≈ 0.53**)
- Rainfall has a negative correlation (**r ≈ -0.25**)
- Clear seasonality: colder months show lower hire volumes

---

## Tech Stack
- Apache Spark (PySpark)
- Python
- Spark SQL
- Matplotlib

---

## Repository Structure

```text
data/           Contains dataset instructions or sample files (raw data not included)
notebooks/      PySpark pipeline and analysis notebooks
images/         Visualisations used in the README
reports/        Project report and supporting documents
README.md       Project overview and documentation
requirements.txt
