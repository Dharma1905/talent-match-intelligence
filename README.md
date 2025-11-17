# Talent Intelligence Matching System
Repository for my MagangHub study case submission. Contains Datasets, Project Code, Queries, Insight, and Instructions.

## **Overview**

The Talent Intelligence Matching System is a data-driven pipeline that identifies the behavioral, competency, and psychometric patterns that distinguish top performers, and then compares all employees against those patterns.

### **This project integrates:**

XGBoost Model → Generates the Success Formula using feature importances

DuckDB SQL Engine → Calculates match rates at TV, TGV, and final levels

End-to-End Scoring Pipeline → Produces a unified talent match metric for each employee

**The goal is to turn employee data into an explainable, scalable success prediction engine.**

## 🧠 1. Success Pattern Discovery (XGBoost ML Model)
Model Used: XGBoostClassifier

Input size: 2,100 employees

**Variables:**

10 Competency Pillars (TVs)

26 Psychometric Attributes

Behavioral Strengths

Cognitive Variables

**Output**

XGBoost Feature Importance → Success Formula Weights

Example of your top features:

Feature	Weight

num__pillar_QDD	0.1093

num__pillar_SEA	0.0354

num__pillar_STO	0.0325

num__pillar_VCU	0.0323

num__pillar_IDS	0.0314

num__pillar_LIE	0.0248

num__pillar_CSI	0.0233

cat__disc_DI	0.0232

num__papi_Papi_F_is_missing	0.0198

num__pillar_FTC	0.0184

…	…

These weights form the corporate-level Success Formula.

## 🧮 2. Success Formula

The final formula combines Talent Variables (TV) grouped into Talent Value Groups (TGV):

SuccessScore =
(42.4% × Psychometrics) +
(38.5% × Competency Pillars) +
(12.5% × Behavioral Strengths) +
(6.6% × Cognitive)


This represents the relative influence of each macro category in predicting Rating 5 performance.

## 🗄 3. DuckDB SQL Matching Engine

The SQL engine operationalizes the Success Formula into a matching system that compares every employee to benchmark (Rating 5) performers.
