# Data

## The real dataset is not published

The analysis in this repository was performed on a **commercial genomic export from a
private Canadian Holstein herd** (668 animals × 138 variables, Semex
evaluations, July 2026). That file contains identifiable farm and animal records and is
**not included here**.

Every figure, statistic, p-value and conclusion in the notebooks was computed on the
**real data**.

## What `sample_synthetic.csv` is

A **structural stand-in**: 60 rows × 138 columns, with the same column names, data
types, value ranges and missing-data pattern as the real export. It exists so the
notebook code **runs end to end** for anyone cloning the repository.

- Animal identifiers are obviously fake (`SYN0000`, `SYNTHETIC_ANIMAL_001`)
- Sire names and registration numbers are synthetic (`SYNTH_SIRE_00`, `SYNTHM00000000`)
- No real animal, sire, farm or registration number appears in this file

## Important: findings will NOT reproduce on this file

Columns were generated **independently** of one another, matched to the real marginal
distributions (mean, SD, range, missingness) but **carrying none of the real
correlation structure**.

This means:

| | |
|---|---|
| ye, The code executes without errors | loading, cleaning, grouping, plotting, testing all work |
| yes Distributions look plausible | LPI ≈ 3,253 vs 3,243 real; Fat ≈ 42.9 vs 42.5 real |
| no **Correlations are absent** | e.g. `r(Stature, Milk)` = −0.07 (ns) here vs the real dataset's structure |
| no **Trends are absent** | cohort slopes will be flat and non-significant |
| no **No conclusion in the README can be re-derived from this file** | by design |

This is deliberate. A synthetic file that reproduced the real correlation structure
would effectively republish the confidential dataset's information content.

## To reproduce the actual results

The real export is proprietary to the farm. Anyone with an equivalent
Semex/Lactanet Holstein genomic export can run the notebooks unchanged by pointing the
load cell at their own file — the column names are standard to that export format.

## How it was generated

`sample_synthetic.csv` was produced by sampling each column independently from a
distribution matched to the real column (normal for numeric, clipped to the observed
range; uniform draw from observed categories for text), then re-applying the real
missing-data rate per column and overwriting all identifier fields with synthetic
values. Seed: 42.
