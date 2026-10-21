# Volve Field Production Analytics Dashboard

Interactive Power BI dashboard that analyses oil, gas and water production and water injection for the Volve field, built on Equinor's open Volve dataset.

!\[Executive Summary](Screenshots/executive-summary.png)

[**View the live dashboard**](add-power-bi-publish-to-web-link) · [PDF export](Dashboard.pdf) · [Power BI file](Volve_Field.pbix)

## Key Findings

> Replace each line with a real number from your dashboard. Findings are what recruiters read first.

* Total oil production over the period: **10,037,081 Sm3**, with **F-12 well** producing **45%** of it.
* Production peaked in **\[month/year]** and declined **3%** by **year**.
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

Add one screenshot per page in `Screenshots/` and link them here.

## Data and Model

* **Source:** Volve Field dataset, published by Equinor. \[add link and licence terms from the Volve data page]
* **Preparation (Power Query):** cleaning, data type validation, \[list your main steps].
* **Model:** star schema with \[fact table name] and \[dimension table names].
* **DAX measures:** For example:

```DAX
Water Cut % =
DIVIDE ( \\\[Total Water Production], \\\[Total Oil Production] + \\\[Total Water Production] )
```

Replace the example with your own measure definitions.

## Repository Structure

```
├── README.md
├── Volve\\\_Field.pbix        # Power BI file (open with Power BI Desktop)
├── Dashboard.pdf           # static export of all pages
├── Screenshots/            # one image per dashboard page
└── Documentation/          # \\\[describe what is in here]
```

## How to Use

1. Download `Volve\\\_Field.pbix` and open it in Power BI Desktop (\[version]).
2. If prompted, point the data source to \[describe where the data file should be].
3. Or view the live version through the link at the top.

## Limitations and Next Steps

* Historical data only; no forecasting.
* Next: SQL analysis of the same dataset and a decline-curve analysis in Python.

## Author

**Resiayu Kinasih Pangastuti** — [GitHub](https://github.com/resiayukp) · [LinkedIn](https://linkedin.com/in/resiayu) · [Email](https://mail.google.com/mail/?view=cm&fs=1&to=resiayu.97@gmail.-com)

