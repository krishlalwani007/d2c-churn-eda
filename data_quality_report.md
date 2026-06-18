# Data Quality Report

## Datasets Audited

* customers.csv (2400 rows)
* orders.csv (10009 rows)
* support_tickets.csv (1921 rows)
* web_events_snapshot.csv (2400 rows)
* intervention_history.csv (2400 rows)
* churn_labels.csv (2400 rows)
* rfm_modeling_snapshot.csv (2400 rows)

## Missing Values

Minor missing values may exist in demographic and engagement fields. Missing values should be imputed or handled before modeling.

## Duplicate Records

No major duplicate issues were observed in customer-level datasets.

## Outliers

The following fields contain outliers:

* monetary_180d
* recency_days
* sessions_30d
* return_rate_180d

These should be analyzed carefully before modeling.

## Join Consistency

All datasets use `customer_id` as the primary key. Snapshot-based joins should ensure dates align correctly.

## Leakage Risks

Future information after `snapshot_date` must not be used.

The following fields require caution:

* churn_next_60d (target variable)
* future orders
* future support tickets
* post-snapshot interventions

## Recommendation

Use only information available on or before the snapshot date when building models.
