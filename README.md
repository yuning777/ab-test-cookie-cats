# A/B Test: Cookie Cats Gate Placement

A practice project on A/B testing using a public dataset. I tested whether moving the first gate in the mobile game Cookie Cats from level 30 to level 40 changes player retention.

## Question
Does moving the gate from level 30 (`gate_30`) to level 40 (`gate_40`) change 1-day or 7-day retention?

## Data
- Cookie Cats A/B testing dataset from Kaggle (90,189 players).
- Columns: `userid`, `version`, `sum_gamerounds`, `retention_1`, `retention_7`.

## Methods
- Data checks: duplicates, missing values, outliers (one extreme outlier removed).
- Two-proportion z-test for 1-day and 7-day retention.
- Bootstrap (2,000 resamples) as a second check for 7-day retention.
- Tools: Python (pandas, numpy, matplotlib, statsmodels).

## Key Results
| Metric | Difference (gate_30 − gate_40) | p-value |
|---|---|---|
| 1-day retention | 0.59 pp | 0.074 (not significant) |
| 7-day retention | 0.82 pp | 0.0016 (significant) |

The bootstrap 95% CI for the 7-day difference is [0.33, 1.28] pp.

**Recommendation:** Keep the gate at level 30.

## Files
- `ab_test.ipynb`: full analysis
- `data/cookie_cats.csv`: dataset

## Note
This is a learning project using a public dataset, not work from a company.
