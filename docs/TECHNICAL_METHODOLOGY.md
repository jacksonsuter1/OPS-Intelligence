# Technical methodology

## Scope
Five Power BI pages using 5,000 synthetic 2025 work orders across Production, Assembly, Quality Control, Packaging, and Maintenance.

## Reporting-date logic
```dax
Reporting Date =
MIN(MAX('Calendar'[Date]), DATE(2025, 12, 31))
```

## Historical backlog definition
An order is outstanding as of a selected reporting date when its created date is on or before that date and its completed date is blank or after that date. An outstanding order is overdue when its due date is populated and strictly before the reporting date. Historical snapshot measures remove Calendar filters after capturing the reporting date, retaining other applicable filters such as department.

## Average completion time
```dax
Average Completion Time =
CALCULATE(
    AVERAGEX(
        FILTER(
            'Work Orders',
            NOT ISBLANK('Work Orders'[Start Date]) &&
            NOT ISBLANK('Work Orders'[Completed Date]) &&
            'Work Orders'[Completed Date] >= 'Work Orders'[Start Date]
        ),
        DATEDIFF('Work Orders'[Start Date], 'Work Orders'[Completed Date], DAY)
    ),
    USERELATIONSHIP('Work Orders'[Completed Date], 'Calendar'[Date]),
    KEEPFILTERS('Work Orders'[Status] = "Completed")
)
```
This counts calendar day boundaries. It is not an exact elapsed-hours average.

## Key modeling concepts
- Calendar date filtering and inactive completion-date relationship activated with `USERELATIONSHIP`.
- Snapshot backlog measures using `REMOVEFILTERS('Calendar')` and date-based conditions.
- Disconnected categories for backlog status and completion timeliness; disconnected aging buckets for overdue analysis.
- Department slicers and month slicers used for analysis and validation.

## Limitations
The PBIX and source workbook are included. This document is a selective technical overview, not a full relationship diagram or exhaustive measure inventory. Source refresh may require updating a local file path in Power Query.
