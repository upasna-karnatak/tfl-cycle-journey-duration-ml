TfL Santander Cycle Journey Duration Prediction

## Project Overview
A distributed machine learning pipeline predicting TfL Santander Cycle hire journey 
durations across 561,830 records (Feb–Mar 2023), comparing scikit-learn and Apache 
Spark (PySpark) implementations in terms of accuracy, efficiency, and scalability.

Completed as part of MSc Data Science & Analytics — CS5811 Distributed Data Analysis  
Brunel University London | 2025–2026 


## Research Question
 *"To what extent can the duration of Santander Cycle hire journeys in London be 
predicted from temporal and meteorological features, and how does a distributed 
Apache Spark ML pipeline compare to scikit-learn in predictive accuracy, computational 
efficiency, and scalability?"*

---

## Dataset
| Source | Details |
|--------|---------|
| TfL Open Data | 561,830 journey records, Feb–Mar 2023 |
| Open-Meteo Weather API | Hourly meteorological data (ERA5) |
| Final merged dataset | 561,830 rows × 31 columns |

---

## Key Steps
- **Data Cleaning:** Removed outliers (<2 min, >180 min journeys) — 1.88% of records
- **Feature Engineering:** 14 features including temporal, operational and weather variables
- **EDA:** 9 visualisations including bimodal demand analysis, temperature anomaly discovery, K-Means clustering (K=4)
- **ML Models:** Linear Regression (baseline), Random Forest (scikit-learn), Log-transformed RF
- **HPC Pipeline:** Apache Spark Random Forest with scalability experiment across 5 data volumes

---

## Results Summary
| Model | RMSE (mins) | MAE (mins) | R² |
|-------|------------|-----------|-----|
| Linear Regression | 13.65 | 8.78 | 0.015 |
| Random Forest (sklearn) | 13.56 | 8.69 | 0.027 |
| Random Forest (Spark) | 13.53 | 8.67 | 0.030 |

---

## Key Findings
- **day_of_week** was the dominant predictor at **33.6% feature importance** — ahead of hour (9.6%), a counter-intuitive finding
- Weekend journeys averaged **18.2 mins vs 15.1 mins** on weekdays across 561,830 records
- A **−1°C temperature anomaly** was identified: mean duration rose to 17.6 mins vs 14.5 mins at 0°C — only discoverable through heterogeneous data merging
- Spark training time grew only **2.9x** vs sklearn's **14.9x** across a 10x data volume increase — crossover advantage projected at ~1.5–2 million rows
- K-Means clustering (K=4) independently confirmed behavioural segmentation without prior labelling

---

## Tech Stack
![Python](https://img.shields.io/badge/Python-3.x-blue)
![Spark](https://img.shields.io/badge/Apache%20Spark-PySpark-orange)
![sklearn](https://img.shields.io/badge/scikit--learn-ML-green)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-lightblue)

- Python, Pandas, NumPy
- scikit-learn (Random Forest, Linear Regression, K-Means)
- PySpark 4.1.1 (Apache Spark)
- Matplotlib, Seaborn
- Open-Meteo Historical Weather API

---

## Repository Structure
├── notebook.ipynb          # Full pipeline: data collection, EDA, ML, HPC

├── README.md               # Project documentation



## Author
Upasna Karnatak  
MSc Data Science & Analytics — Brunel University London  
[LinkedIn](https://www.linkedin.com/in/upasna-karnatak-2226653a6/)
MSc Data Science & Analytics — Brunel University London  
[LinkedIn](https://www.linkedin.com/in/upasna-karnatak-2226653a6/)
