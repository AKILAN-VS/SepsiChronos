# 🩺 SepsiChronos

### A Hybrid Machine Learning Framework for Early Sepsis Prediction

SepsiChronos is a machine learning-based early warning framework designed to predict the onset of sepsis in ICU patients using continuously collected vital signs, laboratory measurements, and demographic information.

The project explores the progression from **classical machine learning to Quantum Machine Learning (QML)** for clinical risk prediction.

---

## 📌 Problem Statement

Sepsis is a life-threatening response to infection where early intervention is critical.

In intensive care units, patient vitals and laboratory measurements are continuously collected. These measurements contain temporal patterns that may indicate deterioration before sepsis becomes clinically apparent.

**SepsiChronos aims to learn these patterns and predict whether an ICU patient will develop sepsis within the upcoming hours.**

Unlike simple sepsis detection, the focus of this project is **early prediction**.

---

## 🎯 Objectives

- Perform exploratory data analysis on ICU clinical data.
- Develop an effective preprocessing and missing-value handling strategy.
- Extract meaningful temporal and clinical features.
- Train and compare multiple classical machine learning algorithms.
- Identify the best-performing model using appropriate clinical evaluation metrics.
- Perform feature selection/extraction to reduce dimensionality.
- Prepare a reduced dataset suitable for Quantum Machine Learning.
- Develop and evaluate a Quantum Machine Learning model.
- Compare classical ML and QML performance.

---

## 📊 Dataset

The project uses the:

**PhysioNet / Computing in Cardiology Challenge 2019 — Early Prediction of Sepsis from Clinical Data**

The dataset contains approximately **40,000 ICU patients**, represented as hourly time-series clinical observations.

### Feature Categories

| Category | Examples |
|---|---|
| Vitals | Heart rate, oxygen saturation, temperature, blood pressure, respiratory rate |
| Laboratory | Lactate, WBC count, creatinine, bilirubin, platelets, etc. |
| Demographics | Age, gender, ICU information, admission-related information |
| Target | `SepsisLabel` |

The dataset is characterized by substantial clinical missingness, particularly in laboratory measurements.

> **Note:** The dataset is credentialed-access data. Raw patient data is not included in this repository.

---

## 🏗️ Project Pipeline

```text
                    ┌─────────────────────┐
                    │   PhysioNet Data    │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │        EDA          │
                    │  Distribution /     │
                    │  Missingness /      │
                    │  Correlation        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Data Preprocessing  │
                    │ Imputation /        │
                    │ Encoding / Scaling  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Feature Engineering │
                    │ Rolling Statistics  │
                    │ Rate of Change      │
                    │ Shock Index / SIRS   │
                    └──────────┬──────────┘
                               │
                               ▼
                 ┌───────────────────────────┐
                 │ Classical ML Models       │
                 │ KNN / RF / XGBoost /      │
                 │ SVM / DT / Logistic Reg. │
                 └────────────┬──────────────┘
                              │
                              ▼
                 ┌───────────────────────────┐
                 │ Model Comparison &        │
                 │ Hyperparameter Tuning     │
                 └────────────┬──────────────┘
                              │
                              ▼
                 ┌───────────────────────────┐
                 │ Feature Selection /       │
                 │ Dimensionality Reduction  │
                 └────────────┬──────────────┘
                              │
                              ▼
                 ┌───────────────────────────┐
                 │ Quantum Data Preparation  │
                 └────────────┬──────────────┘
                              │
                              ▼
                 ┌───────────────────────────┐
                 │ Quantum Machine Learning  │
                 └────────────┬──────────────┘
                              │
                              ▼
                 ┌───────────────────────────┐
                 │ Classical ML vs QML       │
                 │ Performance Comparison    │
                 └───────────────────────────┘
