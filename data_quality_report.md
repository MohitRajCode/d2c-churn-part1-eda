# Data Quality Report

## Dataset Overview

The D2C customer churn dataset consists of customer information, orders, support tickets, web activity, campaign history, and churn labels.

## Missing Values

The following columns contain missing values:

* `loyalty_tier`
* `skin_type`
* `rating`

### Handling Strategy

* Missing loyalty tiers can be treated as "No Membership".
* Missing skin types can be categorized as "Unknown".
* Missing ratings may be imputed using median values.

## Duplicate-like Records

During analysis, 12 duplicate-like order IDs with the suffix `_DUP` were identified.

## Outlier Detection

The `gross_amount` variable contains several high-value outliers, as observed in boxplots.

## Leakage Risks

A total of **1872 post-snapshot orders** were detected. Since the snapshot date is **2025-09-30**, these orders must not be used in predictive modeling.

## Data Integration Issues

Duplicate columns appeared due to multiple merges during analysis. These were resolved by retaining a single version of each variable.
