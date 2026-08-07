# ⛽ Volve Field Production Analytics Dashboard

> An end-to-end Business Intelligence solution developed with Microsoft Power BI to analyze oil & gas production performance, water injection, well performance, spatial distribution, and business insights using the Volve Field dataset.

---

## 📌 Project Overview

The **Volve Field Production Analytics Dashboard** is an interactive Business Intelligence project designed to transform oil & gas production data into meaningful operational and business insights.

The project demonstrates an end-to-end analytics workflow, starting from data preparation and transformation, followed by data modeling, DAX development, interactive visualization, spatial analysis, and business storytelling.

This project was developed as a portfolio project to demonstrate practical capabilities in:

- Business Intelligence
- Data Analytics
- Power BI Development
- DAX
- Data Modeling
- Data Visualization
- Production Analytics
- Business Storytelling

---

## 🎯 Business Problem

Oil & gas production generates large volumes of operational data across wells and production periods.

Without an integrated analytical dashboard, it can be difficult to:

- Monitor overall field production performance
- Identify top-performing wells
- Detect declining production
- Monitor increasing water production
- Evaluate water injection activities
- Compare well performance
- Understand spatial well distribution
- Translate operational data into actionable business insights

### Business Question

> **How can production and well data be transformed into an interactive BI solution that helps users monitor field performance, identify operational opportunities, and support data-driven decision-making?**

---

## 🎯 Project Objectives

The main objectives of this project are to:

1. Build an executive-level production monitoring dashboard.
2. Analyze oil, gas, water, and water injection performance.
3. Identify high-performing and declining wells.
4. Monitor producer and injector wells.
5. Analyze well locations using surface and bottom-hole coordinates.
6. Develop dynamic KPI calculations using DAX.
7. Generate actionable business insights.
8. Demonstrate an end-to-end Power BI development workflow.

---

# 📊 Dashboard Pages

## 1. Executive Summary

Provides a high-level overview of field performance for management and decision-makers.

### Key KPIs

- Total Oil Production
- Total Gas Production
- Total Water Production
- Total Water Injection
- Average of Daily Oil Production
- Number of Producer Wells
- Number of Injector Wells
- Top Performer Well

### Purpose

The page provides a quick overview of the overall production condition and highlights important performance indicators.

---

## 2. Production & Injection Performance

This page focuses on production and reservoir support performance.

### Analysis

- Oil Production Trend
- Gas Production Trend
- Water Production Trend
- Water Injection Trend
- Top Producing Wells
- Water Cut
- Production Performance

### Purpose

To understand production trends over time and evaluate the relationship between production and injection.

---

## 3. Well Spatial Analysis

This page combines production information with well location data.

### Analysis

- Surface Well Coordinates
- Bottom-Hole Coordinates
- Well Distribution
- Production by Well
- Spatial Well Performance
- Interactive Well Information

### Purpose

To provide a geographical perspective of well performance and support operational surveillance.

---

## 4. Business Insights

This page transforms analytical results into business-oriented insights.

### Analysis

- Top Performing Wells
- Declining Wells
- High Water Cut Wells
- Production Contribution
- Production Opportunity
- Operational Status
- Executive Insights

### Purpose

To move beyond descriptive reporting and provide information that can support operational decision-making.

---

# 🛠️ Tools & Technologies

| Category | Technology |
|---|---|
| Business Intelligence | Microsoft Power BI |
| Data Transformation | Power Query |
| Data Modeling | Star Schema |
| Analytics | DAX |
| Data Source | Volve Field Dataset |
| Visualization | Power BI Custom Visuals |

---

# 🗂️ Data Source

### Dataset

**Volve Field Production Dataset**

### Provider

**Equinor**

### Industry

**Oil & Gas**

The dataset contains production and well-related information that can be used to analyze field production performance.

### Main Data Categories

- Oil Production
- Gas Production
- Water Production
- Water Injection
- Production Date
- Well Information
- Surface Coordinates
- Bottom-Hole Coordinates

---

# 🏗️ Data Architecture

The solution follows an analytical workflow:

```text
Raw Data
   │
   ▼
Power Query
   │
   ├── Data Cleaning
   ├── Data Transformation
   ├── Data Type Validation
   └── Data Preparation
   │
   ▼
Data Model
   │
   └── Star Schema
   │
   ▼
DAX Measures
   │
   ├── KPI Calculations
   ├── Time Intelligence
   └── Business Insights
   │
   ▼
Power BI Visualization
   │
   ├── Executive Summary
   ├── Production & Injection Performance
   ├── Spatial Analysis
   └── Business Insights
