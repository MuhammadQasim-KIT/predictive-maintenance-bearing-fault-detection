# Predictive Maintenance – Bearing Fault Detection  
### From Raw Vibration Signals to Feature-Based Machine Learning

---

## 📌 Project Overview

Rotating machinery (motors, pumps, gearboxes, etc.) often fails due to bearing faults.  
Unexpected breakdowns lead to:

- Costly **unplanned downtime**
- **Safety risks** for operators
- Increased **maintenance and replacement costs**

This repository implements a **predictive maintenance workflow** for **bearing fault detection** using vibration data:

1. **Raw Vibration Signal Pipeline**  
   - Load raw accelerometer `.mat` files (CWRU-style bearing data)  
   - Segment long time-series into shorter windows  
   - Extract statistical features from each segment  
   - Train & evaluate a machine learning model to classify fault types  

2. **Feature-Based Machine Learning Pipeline**  
   - Use a pre-computed CSV with vibration features  
   - Train and compare multiple classifiers  
   - Visualize confusion matrices and feature importance  

The goal is to show a **complete, end-to-end predictive maintenance solution** using **realistic engineering data** and standard ML techniques.

---

## 🎯 Objectives

- Classify bearing health into categories such as:
  - **Normal (healthy)**  
  - **Ball fault (B)**  
  - **Inner race fault (IR)**  
  - **Outer race fault (OR)**  

- Handle multiple:
  - **Fault severities** (e.g. 0.007, 0.014, 0.021 in)  
  - **Load conditions**  

- Provide:
  - A **raw-signal → feature → ML** workflow  
  - A **quick-start feature-based ML notebook** reusable for other predictive maintenance problems  

---

## 📂 Repository Structure

```
Predictive_Maintenance_Machine_Failure_Prediction_from_Vibration/
│
├── README.md
│
├── data/
│   ├── raw/
│   │   ├── *.mat
│   │   └── feature_from_raw.csv
│   └── processed/
│       ├── feature_from_raw.csv
│       └── feature_time_48k_2048_load_1.csv
│
├── models/
│   ├── raw/
│   │   └── random_forest_predictive_maintenance.joblib
│   └── processed/
│       └── random_forest_predictive_maintenance.joblib
│
├── notebooks/
│   ├── 01_quick_predictive_maintenance.ipynb
│   └── 02_raw_signal_pipeline.ipynb
│
└── results/
    ├── raw/
    ├── processed/
    └── confusion_matrices/
```
---

## 🧩 Data Description

### 🔷 Raw Vibration Data (`data/raw/`)
- MATLAB `.mat` vibration signals  
- CWRU-style naming (B, IR, OR + defect size)

### 🔷 Feature Datasets
Contain common vibration features:
`max, min, mean, std, rms, skewness, kurtosis, crest, fault_raw, fault`

---

## 🛠️ Dependencies

```
numpy
pandas
matplotlib
seaborn
scipy
scikit-learn
xgboost
joblib
```

Install:
```
pip install numpy pandas matplotlib seaborn scipy scikit-learn xgboost joblib
```

---

## 📒 Notebooks

### 1️⃣ `01_quick_predictive_maintenance.ipynb`
Generic CSV → ML predictive maintenance pipeline

### 2️⃣ `02_raw_signal_pipeline.ipynb`
Raw `.mat` → Segments → Features → ML → Results

---

## 📊 Results
Confusion matrices & feature importance saved in `results/`

---

## 🚀 Usage

### Option A – Feature-Based
1️⃣ Open `01_quick_predictive_maintenance.ipynb`  
2️⃣ Set CSV path  
3️⃣ Run all

### Option B – Raw Signal
1️⃣ Open `02_raw_signal_pipeline.ipynb`  
2️⃣ Run pipeline  
3️⃣ View results in `results/`

---

## ✅ Demonstrates
- Real engineering sensor ML workflow
- Signal processing + ML
- End‑to‑end predictive maintenance solution

---

## 📝 Notes
Educational / demonstrative. Extendable for industrial use.
