# Holstein Genomic Analysis — What 668 Cows Reveal About a Herd's Breeding Strategy

An end-to-end analysis of genomic breeding values from a commercial Canadian Holstein herd
herd: **668 animals, 138 variables, 8 birth-year cohorts.**

This project asks a single question — **where has this herd moved genetically, **  and answers it with descriptive statistics, hypothesis testing, effect
sizes and multicollinearity diagnostics.

---

## Key findings

**1. The breeding programme works, and it beat a known genetic trade-off.**
Across cohorts 2018→2026, genomic merit for **Fat yield rose more than fivefold**
(11.9 → 61.3 kg, r² = 0.95) and **Pro$ rose 144%** (658 → 1,609 CAD). Between animals,
milk volume is negatively correlated with fat percentage (r = −0.41, the classic
dilution antagonism), yet **both volume and concentration rose across cohorts** — only
possible because selection targeted component *yield*, not volume.

**2. The pedigree is measuring inbreeding with the wrong instrument.**
Pedigree inbreeding **plateaued and fell** in the last three cohorts (8.77% → 8.54%),
staying below the common 8% management threshold. Genomic inbreeding **kept climbing to
its highest value ever** (13.37%). Genomic inbreeding rises **53% faster** than pedigree
(+0.556 vs +0.363 points/year), and pedigree explains only **47%** of it (r = +0.68).
**210 animals look safe on paper and are not.**

**3. Good conformation does not mean good production.**
A widely held industry assumption, tested and **rejected**. Overall Conformation
correlates ~zero with production (Milk r = +0.06, Protein r = −0.00, both ns). The top
conformation quartile shows **no significant production advantage** (p = 0.34) — but a
large LPI advantage (+337, p ≈ 7×10⁻²⁷), because conformation is *inside* the LPI
formula. Conformation buys index points, not milk.

**4. Size costs everything and buys nothing.**
Body size (composite of Stature, Body Depth, Height at Front End, Chest Width) is
**unrelated to milk yield** (r = +0.01, ns) but negatively related to **Herd Life
(−0.42), Body Maintenance (−0.65), Environmental Impact (−0.45)** and **Fat yield
(−0.21)**. Replicated under three independent criteria (herd quartiles, breed base,
composite index).

---

## What this project demonstrates

This is not a notebook that loads a dataset and prints a heatmap. The analytical
decisions are the point:

| | |
|---|---|
| **A hypothesis of mine was tested and rejected** | I proposed that smaller cows redirect saved maintenance energy into fat. A mediation test **rejected it**: BMR — the direct measure of maintenance requirement — has **zero association with fat yield** (r = +0.022, p = 0.57), and controlling for BMR *strengthened* rather than weakened the size→fat link. The association is real; **the mechanism is unknown**, and the notebook says so. |
| **A finding of mine was flagged as partly circular** | Small cows show +617 CAD of Pro$. But Lactanet does not publish the Pro$ formula while confirming that **body size modifies its maintenance-cost term**. That result is therefore reported as *consistent with*, not *independent evidence of*, an economic penalty — and the economic estimate is rebuilt from **BMR's published conversion instead** (~$63/daughter over three lactations). |
| **I corrected my own error, and the correction found a bigger one** | My correlation matrix mixed `Conf` with its own components (`Conf & MS` = +0.86 — arithmetic, not biology). Removing it barely moved the diagnostics, because **%Fat had VIF = 931**: component percentages are near-linearly dependent on yields and volume. **The visible error hid a larger invisible one.** |
| **The data's own coding was verified, not assumed** | The glossary defines BLAD/CVM/HH1–HH6 as **carrier probability (0 = free, 99 = carrier)**, not binary flags. Treating them as 0/1 would invert the entire defect screen. |
| **Redundancy was measured, not eyeballed** | PCA shows the **32 conformation traits carry ~10 dimensions**: 10 components explain 80% of variance, 15 explain 90%. |

---

## Repository structure

```
├── notebooks/
│   ├── 01_Data_Cleaning.ipynb      # audit, completeness, marker-coding verification
│   ├── 02_EDA.ipynb                # population, markers, sire diversity
│   ├── 03_Correlation_Analysis.ipynb  # corrected matrix, VIF, redundancy, PCA
│   └── 04_Genomic_Trends.ipynb     # indexes, production, conformation, inbreeding
├── data/
│   └── sample_synthetic.csv        # synthetic sample — real data is confidential
├── outputs/                        # generated figures and tables
├── src/
│   └── portfolio_style.py          # reusable plotting style
├── requirements.txt
└── README.md
```

## Data availability

The original dataset is a **commercial genomic export from a private Canadian Holstein
farm** and is **not published**. All figures, statistics and conclusions in this
repository were computed on that real data.

`data/sample_synthetic.csv` (60 × 138) reproduces the column names, types, ranges and
missing-data pattern so the code **runs end to end**. Its columns were generated
**independently**, so it deliberately carries **none of the real correlation
structure** — the code executes, but **the findings will not reproduce on it**. A
synthetic file that preserved those correlations would effectively republish the
confidential dataset. See [`data/README.md`](data/README.md).

## Methods

- **Descriptive:** completeness audit, IQR outlier screening, distribution profiling
- **Inferential:** Pearson correlation, Mann-Whitney U, OLS regression (implemented from
  scratch with `numpy.linalg.lstsq` — coefficients, standard errors, t, p and R²),
  partial correlation, mediation testing
- **Effect sizes:** Cohen's d with 95% confidence intervals; minimum detectable effect
  reported (d = 0.285 at 80% power)
- **Multiple testing:** Bonferroni correction across trait families
- **Diagnostics:** Variance Inflation Factors, PCA dimensionality

## Setup

```bash
git clone https://github.com/<cmperdomor>/holstein-genomic-analysis.git
cd holstein-genomic-analysis
pip install -r requirements.txt
jupyter notebook
```

## Limitations

Every figure reports **genomic breeding values, not measured performance**. All animals
were evaluated on the same date, so cohort comparisons describe the merit of animals
*born* in each year — they are **not** population genetic trends estimated with a
genetic model, and not longitudinal measurements. Early cohorts are small (2018: n = 13)
and subject to survivorship: culled animals are absent. Correlations describe
association within one herd (n = 668) and are not causal.

## Domain references

- Lactanet — *The Modernized LPI* (April 2025): subindexes standardized so the average
  proven sire = 500, SD = 100
- Lactanet — *Pro$*: formula details are not published
- Lactanet — *Body Maintenance Requirements*: +5 RBV points ≈ $70 saved in maintenance
  feed per daughter over three lactations
- Lactanet — *Interpreting Sire Proofs for Linear Type Traits*: Holstein conformation
  EBVs standardized to base 0, SD 5; each 5 stature points ≈ 1.15 cm in daughters

---

**Author:** [Claudia Perdomo] · [www.linkedin.com/in/claudia-perdomo-803340325

] · [cmperdomor14@gmail.com]
