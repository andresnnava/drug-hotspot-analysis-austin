# Predicting Emerging Drug Hotspots in Austin
**Tools:** Python · Scikit-Learn · Pandas · Matplotlib · Seaborn · Time-Series Modeling  
**Course:** CS 329E — Elements of Data Science, The University of Texas at Austin  
**Date:** Fall 2025

---

## Overview
Built a time-series classification model to predict emerging drug-related crime hotspots across Austin Police Department (APD) districts using over 20 years of public crime data. The goal was to identify which districts were trending toward becoming hotspots before they peaked — enabling proactive resource allocation.

---

## Problem Statement
Can we predict which APD districts are *emerging* drug crime hotspots not just which ones are currently high using historical monthly crime trends?

---

## Project Structure
```
drug-hotspot-austin/
├── README.md
├── notebooks/
│   └── drug_hotspot_analysis.ipynb
├── data/
│   └── README.md
├── outputs/
│   ├── roc_curve.png
│   ├── confusion_matrix.png
│   └── district_heatmap.png
└── requirements.txt
```

---

## Data
| Detail | Value |
|---|---|
| Source | Austin Open Data Portal — Crime Reports dataset |
| Time range | 20+ years of crime records |
| Records | 20,000+ incidents |
| Key fields | District, offense type, date, location coordinates |

---

## Methodology

### 1. Data Cleaning & Filtering
- Filtered for drug-related offense categories
- Aggregated incidents by APD district and month
- Handled missing district labels and date formatting inconsistencies

### 2. Feature Engineering
- Calculated **monthly growth rate** per district: `(current_month - prior_month) / prior_month`
- Defined **emergence labels**: districts with sustained upward growth over a rolling window were labeled as emerging hotspots
- Created lag features to capture multi-month trend momentum

### 3. Modeling
- Trained a time-series classification model using Scikit-Learn
- Applied cross-validation to prevent data leakage across time periods
- Used feature selection to identify the most predictive growth-based signals

---

---

## Key Findings
- Monthly growth rate was the strongest predictor of emerging hotspot status
- Several APD districts showed consistent lead indicators 2–3 months before peak crime periods
- Model outperformed a naive baseline on AUC

---

## How to Run
```bash
git clone https://github.com/andresnnava/drug-hotspot-austin.git
cd drug-hotspot-austin
pip install -r requirements.txt
jupyter notebook notebooks/drug_hotspot_analysis.ipynb
```

---

## Requirements
```
pandas
numpy
scikit-learn
matplotlib
seaborn
jupyter
```

---

## Skills Demonstrated
`Python` `Pandas` `NumPy` `Scikit-Learn` `Time-Series Classification` `Feature Engineering` `Cross-Validation` `ROC-AUC` `Confusion Matrix` `Matplotlib` `Seaborn` `Data Cleaning` `Predictive Modeling`
