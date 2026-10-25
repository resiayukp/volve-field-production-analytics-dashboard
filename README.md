# Volve Field Production Analytics Dashboard

Interactive Power BI dashboard that analyses oil, gas and water production and water injection for the Volve field, built on Equinor's open Volve dataset.

!\[Executive Summary](Screenshots/ExecutiveSummary.PNG)

[PDF export](Dashboard.pdf) · [Power BI file](Volve_Field.pbix)

## Key Findings

* Total oil production over the period: **10,037,081 Sm3**, with **F-12 well** producing **45%** of it.
* Production declined **3%** by **year**.
* Water cut ranged from **25%** to **64%**, led by wells **F-14**.
* Water injection of **30M Sm3** against production of **10M Sm3** (injection-to-production ratio **3**).

## Business Problem

Production data is spread across many wells and periods. Without one view it is hard to see which wells drive output, where production is declining, where water production is increasing, and how injection relates to production.

**Question:** how can production and well data be turned into a dashboard that helps users monitor field performance and support decisions?

## Dashboard Pages

|Page|What it answers|
|-|-|
|Executive Summary|How is the field performing overall? KPIs for oil, gas, water, injection, producer and injector counts, top performer well.|
|Production \& Injection Performance|How do production and injection trend over time? Top producing wells, water cut.|
|Well Spatial Analysis|Where are the wells and how do they perform? Surface and bottom-hole coordinates with production by well.|
|Business Insights|Which wells need attention? Top performers, declining wells, high water cut wells, production contribution.|

!\[Business Insights](Screenshots/BusinessInsights.PNG)

!\[Executive Summary](Screenshots/ExecutiveSummary.PNG)

!\[Production \& Injection Performance](Screenshots/Production\&InjectionPerformance.PNG)

!\[Well Spatial Analysis](Screenshots/WellSpatialAnalysis.PNG)

## Data and Model

* **Source:** Volve Field dataset, published by Equinor.
* **Preparation (Power Query):** cleaning, data type validation.
* **Model:** star schema.
* **DAX measures:**

## Repository Structure

```
├── README.md
├── Volve\\\_Field.pbix        # Power BI file (open with Power BI Desktop)
├── Dashboard.pdf           # static export of all pages
├── Screenshots/            # one image per dashboard page
└── Documentation/          # data dictionary and data model
```

## How to Use

1. Download `Volve\\\_Field.pbix` and open it in Power BI Desktop.
2. If prompted, point the data source to [Equinor web page](https://www.equinor.com/energy/volve-data-sharing).
3. Or view the live version through the link at the top.

## Limitations and Next Steps

* Historical data only; no forecasting.
* Next: SQL analysis of the same dataset and a decline-curve analysis in Python.

## Author

**Resiayu Kinasih Pangastuti** — [GitHub](https://github.com/resiayukp) · [LinkedIn](https://linkedin.com/in/resiayu) · [Email](https://mail.google.com/mail/?view=cm&fs=1&to=resiayu.97@gmail.-com)

