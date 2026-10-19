# Global COVID-19 Analysis & Trends Dashboard

An interactive Tableau Public project exploring reported COVID-19 cases and deaths over time, across countries, and by WHO region. The dashboard combines KPI cards, monthly trend charts with statistical forecasts, country rankings, regional comparisons, and filled world maps.

## Interactive dashboard
https://public.tableau.com/app/profile/prashant.srivastava4192/viz/Capstone_Project_1_17890294975280/COVID-19Dashboard

## Project objective

The goal is to turn country-level daily COVID-19 reporting data into a concise visual overview that helps users explore:

- How reported new cases and deaths changed month by month.
- Which countries recorded the highest reported new and cumulative totals.
- How reported cases and deaths differ across WHO regions.
- How reported cumulative cases and deaths are geographically distributed.
- What a Tableau time-series forecast projects from the historical pattern, including its uncertainty.

## Dataset

**File:** `data/WHO-COVID-19-global-daily-data.csv`

**Source:** [WHO COVID-19 dashboard data](https://data.who.int/dashboards/covid19/data)

The supplied snapshot contains approximately 526,320 country-date records for 240 countries, across seven WHO regions, covering **4 January 2020 to 4 January 2026**. The source data may be retrospectively revised, and results from a later download can differ.

### Main fields

| Field | Meaning |
|---|---|
| `Date_reported` | Date associated with the report |
| `Country_code` | Country code provided in the source |
| `Country` | Country name |
| `WHO_region` | WHO region classification |
| `New_cases` | Newly reported cases for the reporting period |
| `Cumulative_cases` | Running total of reported cases as of the reporting date |
| `New_deaths` | Newly reported deaths for the reporting period |
| `Cumulative_deaths` | Running total of reported deaths as of the reporting date |

## Dashboard components

1. **KPI summary** — reported new cases, reported new deaths, and distinct countries represented.
2. **Monthly Cases Trend** — monthly aggregation of reported new cases, with Tableau forecast.
3. **Monthly Death Trend** — monthly aggregation of reported new deaths, with Tableau forecast.
4. **Top 10 Countries by Cumulative Cases** — country ranking using a selected cumulative snapshot date.
5. **Top 10 Countries by Cumulative Deaths** — country ranking using a selected cumulative snapshot date.
6. **Top 10 Countries by New Cases** — country ranking by reported new cases over the analysis period.
7. **Top 10 Countries by New Deaths** — country ranking by reported new deaths over the analysis period.
8. **Cases vs Deaths by WHO Region** — regional comparison; separate scales are used so that deaths remain visible beside the much larger case values.
9. **Death % by WHO Region** — each region's share of reported cumulative deaths, not the case-fatality rate.
10. **COVID Cases Map** and **COVID Death Map** — filled maps based on cumulative values from a selected reporting-date snapshot.

## Methodology and data-quality considerations

- Daily new-case and new-death values can be aggregated over a selected period to describe reported activity during that period.
- **Do not sum cumulative values across every date.** Cumulative measures already include prior reports. For country rankings, regional cumulative comparisons, and maps, use one reporting-date snapshot (the final date in this supplied file is **4 January 2026**) or another clearly specified snapshot date.
- Blank values in daily case/death fields have been retained as missing rather than automatically converted to zero. A blank report is not necessarily the same as a confirmed zero.
- WHO notes that reporting frequency, case definitions, detection, testing, and national reporting practices can differ; figures may also be revised retrospectively. See the source above for interpretation guidance.
- Tableau forecasting extrapolates historical patterns and is not a clinical or epidemiological prediction. The forecast does not account for every possible external factor, so the projection and its uncertainty should be interpreted cautiously.

## Tools and skills demonstrated

- **Tableau Public:** calculated fields, dimensions and measures, continuous dates, monthly aggregation, Top N filters, table calculations, geographic roles, filled maps, forecasting, KPI presentation, and dashboard layout.
- **Data analysis:** date-range checks, data-type checks, missing-value review, aggregation choices, geographic comparison, trend interpretation, and validation of cumulative measures.
- **Communication:** presenting multiple analytical perspectives in a single dashboard and explaining limitations to non-technical audiences.

## How to open the project

1. Download the packaged Tableau workbook (`.twbx`) from the repository or use the Tableau Public link above once available.
2. If using Tableau Desktop/Public, open the `.twbx` file. A packaged workbook is preferred because it can include the workbook and a local copy of its data source.
3. If the workbook is not packaged, reconnect it to `data/WHO-COVID-19-global-daily-data.csv` when prompted.
4. Check that cumulative comparison worksheets and maps use a single reporting-date snapshot before interpreting or presenting their values.

> Add your exported packaged workbook to `tableau/` before considering the repository complete. The workbook was built locally; this repository template does not contain the `.twbx` file until you export and add it.

## Suggested repository structure

```text
global-covid19-tableau-dashboard/
├── README.md
├── data/
│   └── WHO-COVID-19-global-daily-data.csv
├── images/
│   └── dashboard-preview.jpg
└── tableau/
    └── Global_COVID19_Dashboard.twbx   # add your packaged workbook
```

## Future improvements

- Add dashboard filters for country, WHO region, and date.
- Add a clearly labeled snapshot-date control for all cumulative comparisons.
- Improve chart tooltips and add a source/limitations note directly to the dashboard.
- Revalidate forecast settings and the data whenever the source file is refreshed.

## Attribution

COVID-19 data source: World Health Organization (WHO), [WHO COVID-19 dashboard data](https://data.who.int/dashboards/covid19/data). Please refer to WHO's current data notes and source guidance when reusing or interpreting the data.
