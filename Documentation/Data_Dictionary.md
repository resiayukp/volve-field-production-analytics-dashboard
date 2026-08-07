# 📖 Data Dictionary

## Volve Field Production Analytics Dashboard

---

## 1. Overview

This document provides the data dictionary for the **Volve Field Production Analytics Dashboard**.

The Power BI data model consists of:

* **Fact Table:** `Production`
* **Dimension Table:** `Coordinates`
* **Dimension Table:** `Date`

The model is designed to support production performance analysis, well-level analysis, time-series analysis, and spatial visualization.

---

# 2. Data Model

The Power BI model follows a simplified **Star Schema** structure.

```
                    ┌───────────────┐
                    │      Date     │
                    │  Dimension    │
                    └───────────────┘
                            ▲
                            │
                            │
                            ▼
                    ┌───────────────┐
                    │  Production   │
                    │     Fact      │
                    └───────────────┘
                            ▲
                            │
                            │
                            ▼
                    ┌───────────────┐
                    │  Coordinates  │
                    │  Dimension    │
                    └───────────────┘
```

### Model Components

| Table         | Type      | Main Purpose                      |
| ------------- | --------- | --------------------------------- |
| `Production`  | Fact      | Production and well activity data |
| `Date`        | Dimension | Time-based analysis               |
| `Coordinates` | Dimension | Well spatial analysis             |

---

# 3. Fact Table — Production

The `Production` table is the primary fact table in the Power BI model.

It contains production records by well and production date.

## Production Fields

| Field           | Data Type | Unit | Description               | Analytical Purpose         |
| --------------- | --------- | ---- | ------------------------- | -------------------------- |
| `PRDDATE`       | Date      | Date | Production reporting date | Time-series analysis       |
| `WELLBORE_NAME` | Text      | -    | Wellbore name/identifier  | Well-level analysis        |
| `BORE_OIL_VOL`  | Decimal   | Sm³  | Oil production volume     | Oil production KPI         |
| `BORE_GAS_VOL`  | Decimal   | Sm³  | Gas production volume     | Gas production KPI         |
| `BORE_WAT_VOL`  | Decimal   | Sm³  | Produced water volume     | Water production analysis  |
| `BORE_WI_VOL`   | Decimal   | Sm³  | Water injection volume    | Injection analysis         |
| `FLOW_KIND`     | Text      | -    | Flow classification       | Producer/injector analysis |
| `WELL_TYPE`     | Text      | -    | Well classification       | Well activity analysis     |

---

# 4. Dimension Table — Date

The `Date` table is used to support time-based filtering and DAX time intelligence.

## Date Fields

| Field          | Data Type    | Description            | Analytical Purpose |
| -------------- | ------------ | ---------------------- | ------------------ |
| `Date`         | Date         | Calendar date          | Date filtering     |
| `Year`         | Whole Number | Calendar year          | Annual analysis    |
| `Quarter`      | Text         | Calendar quarter       | Quarterly analysis |
| `MonthNo`      | Whole Number | Numeric month          | Month sorting      |
| `Month`        | Text         | Month name             | Monthly analysis   |
| `Year-Month`   | Text         | Year-month combination | Production trends  |

---

## Date Dimension Purpose

The `Date` table enables:

* Date slicers
* Monthly production trends
* Annual production analysis

---

# 5. Dimension Table — Coordinates

The `Coordinates` table is used specifically for well spatial analysis.

It stores surface and bottom-hole coordinate information.

## Coordinate Fields

| Field                   | Data Type | Unit | Description                      | Analytical Purpose           |
| ----------------------- | --------- | ---- | -------------------------------- | ---------------------------- |
| `WELLBORE_NAME`         | Text      | -    | Wellbore identifier              | Connects coordinates to well |
| `Surface Latitude`      | Decimal   | m    | Surface latitude coordinate      | Surface location             |
| `Surface Longitude`     | Decimal   | m    | Surface longitude coordinate     | Surface location             |
| `Bottom Hole Latitude`  | Decimal   | m    | Bottom-hole latitude coordinate  | Subsurface location          |
| `Bottom Hole Longitude` | Decimal   | m    | Bottom-hole longitude coordinate | Subsurface location          |

---

# 6. Coordinate Data

The `Coordinates` dimension supports spatial visualization of wells.

## Surface Coordinates

Surface coordinates represent the location where the well enters the subsurface.

```text
Surface Latitude
Surface Longitude
```

## Bottom-Hole Coordinates

Bottom-hole coordinates represent the subsurface endpoint of the well.

```text
Bottom Hole Latitude
Bottom Hole Longitude
```

### Business Use

Coordinate data can be used to:

* Visualize well locations
* Compare surface and bottom-hole positions
* Display production performance geographically

---

# 7. Production Variables

## Oil Production

**Field:** `BORE_OIL_VOL`

**Unit:** `Sm³`

### Definition

The recorded volume of oil production for a well during a production period.

### Used For

* Total Oil Production
* Production Trend
* Top Performer Well
* Production Contribution

---

## Gas Production

**Field:** `BORE_GAS_VOL`

**Unit:** `Sm³`

### Definition

The recorded volume of gas production for a well during a production period.

### Used For

* Total Gas Production
* Gas Production Trend
* Well Performance Analysis

---

## Water Production

**Field:** `BORE_WAT_VOL`

**Unit:** `Sm³`

### Definition

The recorded volume of produced water during a production period.

### Used For

* Total Water Production
* Water Cut
* Water Production Trend
* High Water Cut Analysis

---

## Water Injection

**Field:** `BORE_WI_VOL`

**Unit:** `Sm³`

### Definition

The recorded volume of water injected during a production period.

### Used For

* Total Water Injection
* Injection Trend
* Reservoir Support Analysis

---

# 8. Units of Measurement

| Variable                | Unit               | Description           |
| ----------------------- | ------------------ | --------------------- |
| Oil Production          | Sm³                | Standard cubic metres |
| Gas Production          | Sm³                | Standard cubic metres |
| Water Production        | Sm³                | Standard cubic metres |
| Water Injection         | Sm³                | Standard cubic metres |
| Surface Latitude        | Decimal Degrees    | Coordinate value      |
| Surface Longitude       | Decimal Degrees    | Coordinate value      |
| Bottom Hole Latitude    | Decimal Degrees    | Coordinate value      |
| Bottom Hole Longitude   | Decimal Degrees    | Coordinate value      |
| Production Date         | Date               | Reporting date        |

### Dashboard Display

Large production values may be displayed using abbreviated units.

```text
1,000 Sm³      → 1.00 KSm³
1,000,000 Sm³  → 1.00 MSm³
```

---

# 9. Well Classification

## Producer

A well associated with hydrocarbon production activity.

### Analytical Use

* Producer count
* Oil production
* Gas production
* Production contribution

---

## Injector

A well associated with water injection activity.

### Analytical Use

* Injector count
* Water injection
* Injection performance
* Reservoir support monitoring

---

# 10. Key Business Metrics

## Water Cut

Water Cut measures the proportion of produced water relative to total liquid production.

```text
Water Cut =
Water Production
-------------------------------
Oil Production + Water Production
```

### Business Interpretation

A higher water cut indicates a greater proportion of water in total liquid production and can be used as a well surveillance indicator.

---

## Production Contribution

Production Contribution measures the percentage of total field oil production contributed by an individual well.

```text
Production Contribution =
Well Oil Production
--------------------
Total Oil Production
```

### Business Interpretation

This metric helps identify wells that have a significant contribution to total field production.

---

## Production Decline

Production decline represents a reduction in production over a defined period.

### Analytical Use

Used to identify wells requiring further production surveillance.

---

# 11. Table Relationships

The model contains relationships between the fact and dimension tables.

| From Table    | To Table     | Relationship | Purpose                                |
| ------------- | ------------ | ------------ | -------------------------------------- |
| `Date`        | `Production` | One-to-Many  | Filter production by date              |
| `Coordinates` | `Production` | One-to-Many  | Connect well coordinates to production |

### Model Direction

The recommended filtering approach is:

```
Date
  ▲
  │
  ▼
Production
  ▲
  │
  ▼
Coordinates

```

# 12. DAX Measures Supported by the Model

The data model supports analytical measures such as:

## Production KPIs

* Total Oil Production
* Total Gas Production
* Total Water Production
* Total Water Injection

## Well Performance

* Producer Wells
* Injector Wells
* Top Performer Well

## Production Quality

* Water Cut
* Gas Cut
* Oil-to-Water Ratio
* Average Daily Oil Rate

## Time Intelligence

* Running Total Production

## Business Insights

* Declining Wells
* High Water Cut Wells
* Production Opportunity
* Executive Insight

---

# 13. Data Quality & Preparation

Data preparation is performed through **Power Query** before the data is loaded into the Power BI model.

Typical preparation activities include:

* Data type validation
* Date conversion
* Numeric field validation
* Missing-value handling
* Duplicate checking
* Column standardization
* Unnecessary-column removal
* Coordinate validation
* Relationship preparation

---

# 14. Report Pages Supported

| Report Page             | Main Tables Used                |
| ----------------------- | ------------------------------- |
| Executive Summary       | Production + Date               |
| Production Performance  | Production + Date               |
| Well Spatial Analysis   | Production + Date + Coordinates |
| Business Insights       | Production + Date               |

---

# 15. Data Flow

The overall data flow can be represented as:

```

Volve Field Dataset
        │
        ▼
   Power Query
        │
        ├───────────────┐
        │               │
        ▼               ▼
   Production      Coordinates
        │               │
        └───────┬───────┘
                │
                ▼
             Date
                │
                ▼
          Power BI Model
                │
                ▼
           DAX Measures
                │
                ▼
         Dashboard Pages
                │
                ▼
       Business Insights
```

# 16. Data Governance

| Attribute           | Description                    |
| ------------------- | ------------------------------ |
| Dataset             | Volve Field Production Dataset |
| Data Provider       | Equinor                        |
| BI Platform         | Microsoft Power BI             |
| Transformation      | Power Query                    |
| Analytical Language | DAX                            |
| Intended Use        | Educational & Portfolio        |
| Data Classification | Public Dataset                 |

```
```

# 17. Repository Documentation

This document is part of the project documentation.

```
Volve-Production-Analytics/
│
├── README.md
│
├── Documentation/
│   ├── Data_Dictionary.md
│   └── Data_Model.png
│
├── Screenshots/
│   ├── ExecutiveSummary.png
│   ├── Production&InjectionPerformance.png
│   ├── WellSpatialAnalysis.png
│   └── BusinessInsights.png
│
├── Volve_Field.pbix
└── Dashboard.pdf
```

---

# 18. Summary

The **Volve Field Production Analytics Dashboard** uses a simplified analytical model consisting of:

```text
┌──────────────┐
│     Date     │
│  Dimension   │
└──────────────┘
       ▲
       │
       ▼
┌──────────────┐
│  Production  │
│     Fact     │
└──────────────┘
       ▲
       │
       ▼
┌──────────────┐
│ Coordinates  │
│  Dimension   │
└──────────────┘
```

This structure focuses the model on three key analytical requirements:

1. **Production analysis** through the `Production` fact table.
2. **Time-based analysis** through the `Date` dimension.
3. **Spatial well analysis** through the `Coordinates` dimension.

The model provides the foundation for production surveillance, well performance analysis, time-series reporting, spatial visualization, and business insight generation in Power BI.
