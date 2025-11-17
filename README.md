# Talent Intelligence Matching System
Repository for my MagangHub study case submission. Contains datasets, project code, queries, insights, and instructions.

---

## 📌 Overview
The **Talent Intelligence Matching System** is a data-driven scoring and analytics pipeline designed to identify the behavioral, competency, and psychometric patterns that differentiate top performers—then match all employees against these success patterns.

### Core Components
- **XGBoost Model** → Extracts the Success Formula via feature importances  
- **DuckDB SQL Engine** → Computes match rates across TV, TGV, and final formula levels  
- **End-to-End Scoring Pipeline** → Produces a unified Talent Match Score  

**Goal:** Transform employee data into an *explainable, scalable success prediction engine.*

---

## 🧠 1. Success Pattern Discovery (XGBoost)
**Model Used:** `XGBoostClassifier`  
**Dataset Size:** 2,100 employees

### Input Variables
- 10 Competency Pillars (TVs)  
- 26 Psychometric Attributes  
- Behavioral Strengths  
- Cognitive Indicators  

### Output: Feature Importance (Success Formula Weights)
Example of top features:

| Feature | Weight |
|--------|--------|
| num__pillar_QDD | 0.1093 |
| num__pillar_SEA | 0.0354 |
| num__pillar_STO | 0.0325 |
| num__pillar_VCU | 0.0323 |
| num__pillar_IDS | 0.0314 |
| num__pillar_LIE | 0.0248 |
| num__pillar_CSI | 0.0233 |
| cat__disc_DI | 0.0232 |
| num__papi_Papi_F_is_missing | 0.0198 |
| num__pillar_FTC | 0.0184 |
| … | … |

These weights form the **corporate-level Success Formula.**

---

## 🧮 2. Success Formula
The final Talent Match Score is generated using weighted macro-categories:

SuccessScore =
(42.4% × Psychometrics) +
(38.5% × Competency Pillars) +
(12.5% × Behavioral Strengths) +
(6.6% × Cognitive)


These weights reflect each category’s predictive power in identifying **Rating 5 performers.**

---

## 🗄 3. DuckDB SQL Matching Engine
The DuckDB SQL Engine operationalizes the weighted Success Formula by:

- Benchmarking each employee against Rating 5 top performers  
- Calculating Talent Variable (TV) match rates  
- Aggregating TV values into Talent Value Group (TGV) scores  
- Producing the final Talent Match Score  

This design ensures fast, explainable, and scalable scoring across the organization.

---

## 📁 Repository Structure
📦 Talent-Intelligence-Matching-System

├── data/ # Raw & processed datasets

├── notebooks/ # EDA, XGBoost model, feature importance

├── sql/ # queries

├── main report/ # Final results

└── README.md
