# Data dictionary — verified fields and documentation template

The field names below are confirmed by the project roadmap, measures, or visible register. **Data types, allowed values, and business rules should be verified in Power BI before publishing as a definitive dictionary.**

| Table | Field | Purpose |
| --- | --- | --- |
| Work Orders | Work Order ID | Unique work-order identifier |
| Work Orders | Department | Department assignment |
| Work Orders | Order Type | Work-order category |
| Work Orders | Priority | Work-order priority |
| Work Orders | Status | Work-order status |
| Work Orders | Shift | Work shift |
| Work Orders | Created Date | Order creation date |
| Work Orders | Start Date | Work start date |
| Work Orders | Due Date | Due date |
| Work Orders | Completed Date | Completion date |
| Work Orders | Est. Cost | Estimated cost (display name; verify source field) |
| Work Orders | Actual Cost | Actual cost (display name; verify source field) |
| Work Orders | Delay Reason | Delay description |
| Calendar | Date | Reporting-date calendar |
| Overdue Aging Buckets | Aging Bucket | Overdue-age category |
| Overdue Aging Buckets | Min Days / Max Days / Sort Order | Aging bucket bounds and order |

**To finish:** export actual Power Query field types, relationship cardinalities, permitted values, null-handling rules, dataset-generation method, and source-file descriptions from the final PBIX.
