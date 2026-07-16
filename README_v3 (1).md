# Holstein Genomic Analysis — What 668 Cows Reveal About a Herd's Breeding Strategy

An end-to-end analysis of genomic breeding values from a commercial Canadian Holstein
herd: **668 animals, 138 variables, 8 birth-year cohorts.**

This herd is not failing. It is succeeding at exactly what it selected for — and paying
for it in places nobody was measuring. That is the story this project tells, and the
recommendations at the end follow from it.

The project answers eight questions:

1. How has the genomic profile of the herd changed over time?
2. How are genomic traits associated?
3. Does Proof Source influence the observed relationships?
4. Are there distinct genomic profiles among cows?
5. Can cows be grouped using unsupervised learning?
6. Which cows show the most balanced genomic profile?
7. How has genomic inbreeding changed over time?
8. Are there redundant genomic indexes?

---

## Key findings

**1. (Q1) The breeding programme works — and it beat a known genetic trade-off.**
Across cohorts 2018→2026, genomic merit for **Fat yield rose more than fivefold**
(11.9 → 61.3 kg, r² = 0.95) and **Pro$ rose 144%** (658 → 1,609 CAD). Between animals,
milk volume correlates negatively with fat percentage (r = −0.41 — the classic dilution
antagonism), yet **both volume and concentration rose across cohorts**. That only happens
when selection targets component *yield* rather than volume. Somebody was doing this
right.

**2. (Q7) The pedigree is measuring inbreeding with the wrong instrument.**
Pedigree inbreeding **plateaued and fell** in the last three cohorts (8.77% → 8.54%),
staying below the common 8% threshold. Genomic inbreeding **kept climbing to its highest
value ever** (13.37%). Genomic rises **53% faster** than pedigree (+0.556 vs +0.363
points/year), and pedigree explains only **47%** of it (r = +0.68). **210 animals look
safe on paper and are not.**

**3. (Q2) Size costs everything and buys nothing.**
Body size is **unrelated to milk yield** (r = +0.01, ns) but negatively related to
**Herd Life (−0.42), Body Maintenance (−0.65), Environmental Impact (−0.45)** and **Fat
yield (−0.21)**. Smaller cows deliver **the same milk with +19 kg fat and +11 kg
protein**, live longer and conceive better. Replicated under **three independent size
criteria** (herd quartiles, breed base, composite index).

**4. (Q4 & Q5 — one test answers both) There are no cow "types" — the herd is a continuum.**
K-means across k = 2–6 never exceeds a **silhouette of 0.146**, far below the 0.25
threshold for real structure. Any clusters reported would be **artefacts of the
algorithm, not features of the population**. Reported as a negative result rather than
dressed up as profiles.

**5. (Q8) Redundancy is trait-specific — and the difference explains everything else.**
The **32 conformation traits collapse to ~10 dimensions** (VIF up to **931**), while the
**six functional subindexes are near-independent**: **5 of 6 principal components** are
needed for 80% of variance, none exceeding 24%. PCA splits them into a **functional axis**
(Health, Reproduction, Environment) and a **production–type axis** (PROD, L-TYPE) that
are statistically unrelated. **Selecting hard on one exerts no pull on the other** —
which is precisely why REPRO fell 45.9 points and ENVIRO fell 138.4 while production and
type climbed. The indexes did not fail. They were never connected.

**6. (Q6) Only 3% of cows are complete.**
Just **21 of 668 animals (3.1%)** sit above the herd mean on all six subindexes — and
they average **Pro$ 1,887 against the herd's 1,145 (+65%)**. Balance and profit are not
in conflict. Balance is simply rare.

**7. (Q3) Reliability changes what you see.**
Relationships hold across Proof Source subsets — except one. Pooled, production and
reproduction look unrelated (**r = −0.033, ns**), which supports the reading that
reproduction fell by *omission*. But in the most reliable evaluations (**GEBV**, animals
carrying their own performance records) a real antagonism appears: **r = −0.145
(p = 0.016)**. The dilution trade-off sharpens the same way (−0.405 → **−0.503**).
**Reliability does not just add precision — it exposes relationships the pooled data
hides**, and it forced one of this project's conclusions to be downgraded from "free" to
"costs little".

---

## Recommendations

These are the actions the data supports, in the order I would take them.

### 1. Change the instrument before changing the strategy

**Stop managing matings on pedigree inbreeding.** This is the cheapest fix in the list
and the most urgent. The pedigree currently reports a herd that has stabilised below the
8% threshold; the genome reports the most inbred cohort in the herd's history. **210
animals are classified as safe when they are not.**

Nothing else on this list matters if the measurement is wrong. Switch mating decisions to
`Genomic Inb. %` — the data is already in the export and costs nothing extra to use.

### 2. Put a floor under reproduction — it is nearly free

REPRO has fallen for eight consecutive cohorts and now sits **below the proven-sire base
(486 vs 500)**, with **56% of the herd below base**.

Add a **REPRO ≥ 500 threshold** when filtering sires. The cost is small and quantified:
production explains only **2%** of reproduction variance (r = −0.145 in the most reliable
subset). This is a real cost, not zero — but it is close to it, and **REPRO is positively
associated with profit (r = +0.28)**.

The reason to act now is that genetic decline is **cumulative and permanent**. Management
protocols are re-purchased every year and lost the moment you stop paying. The 45.9
points already lost will not come back on their own, and per Lactanet, corrective
breeding decisions take roughly **five years** to reach the bulk tank.

### 3. Cap body size — stop paying for a trait that returns nothing

The herd is getting bigger (Body Depth **+0.27/yr, p = 0.0003**) as a **by-product** of
type selection, not a goal. Size delivers **no additional milk** while costing
components, longevity, fertility and feed.

Keep selecting for the type traits that pay — **Locomotion (r = +0.24 with Herd Life)**,
**Front Legs View (r = +0.33 with Pro$)** — and apply **negative or capping pressure on
Stature and Body Depth**. Using Lactanet's published conversion, the smaller quartile's
BMR advantage is worth roughly **$63 per daughter over three lactations**, estimated
without touching the proprietary Pro$ formula.

**The scale of this matters:** the gap between the small and large stature quartiles is
approximately **2 cm**. Two centimetres separate a group with +19 kg fat, +11 kg protein
and +3.6 Herd Life points from one without them, at identical milk yield.

### 4. Breed from the herd's own best animals

The solution does not need to be imported. **45 animals (6.7%)** already combine
top-quartile production, REPRO ≥ 500 and below-average size — and they are worth
**Pro$ 2,146 vs the herd's 1,145**. A further **21 animals (3.1%)** are above the herd
mean on all six subindexes.

**These are not compromise animals.** They are the most profitable animals in the herd.
Their existence is the proof that the trade-off is **a selection choice, not a biological
constraint**.

### 5. Record reproductive management

Fertility phenotypes are only as good as their context. Published work shows breeding
values for heat detection and Timed AI correlate at **R = 0.5 (p = 0.002)**, causing
**sires to re-rank** depending on the reproductive management of the herds recording
their daughters (Oliveira et al., 2021; Lynch et al., 2021).

This dataset has **no reproductive-protocol field** — `Current group` records semen type,
not protocol. Recording it costs nothing and improves every fertility evaluation the herd
contributes to and receives.

---

## A note on what this project could not do

I attempted to validate the genomic fertility evaluation against the herd's real service
records. **It did not work, and the reason is worth more than the result would have
been.**

Mean services fall monotonically across DF quartiles (**2.56 → 2.41 → 2.17 → 1.90**), but
no assumption-valid test reaches significance: the log-rank test gives **p = 0.536**, and
a Cox model returned p = 0.011 while **violating proportional hazards (p = 0.003)**,
making it unreportable.

This is arithmetic, not failure. Fertility heritability is low (h² ≈ 0.02–0.05), so
`cor(EBV, own phenotype) = accuracy × √h² ≤ 0.22` — **even a perfect evaluation could not
exceed ~0.22**. Detecting an effect that small requires **~344 cows at 80% power**; this
herd offers 278.

**A single 668-animal herd is structurally too small to validate a low-heritability
evaluation.** That does not weaken recommendation #2 — the herd's own −45.9-point REPRO
decline is the demonstration that low-heritability traits accumulate, measured on the
genetic trend rather than on an individual-cow prediction.

---

## What this project demonstrates

The analytical decisions are the point, not the plotting:

| | |
|---|---|
| **A hypothesis of mine was tested and rejected** | I proposed that smaller cows redirect saved maintenance energy into fat. A mediation test **rejected it**: BMR — the direct measure of maintenance requirement — has **zero association with fat yield** (r = +0.022, p = 0.57), and controlling for BMR *strengthened* rather than weakened the size→fat link. The association is real; **the mechanism is unknown**, and the notebook says so. |
| **A finding of mine was flagged as partly circular** | Small cows show +617 CAD of Pro$. But Lactanet does not publish the Pro$ formula while confirming that **body size modifies its maintenance-cost term**. That result is reported as *consistent with*, not *independent evidence of*, an economic penalty — and the economic estimate is rebuilt from **BMR's published conversion instead**. |
| **I corrected my own error, and the correction found a bigger one** | My correlation matrix mixed `Conf` with its own components (`Conf & MS` = +0.86 — arithmetic, not biology). Removing it barely moved the diagnostics, because **%Fat had VIF = 931**. **The visible error hid a larger invisible one.** |
| **A conclusion was revised when a subset contradicted it** | See finding 7. Having written that selecting for reproduction was *"free"*, I ran the sensitivity check anyway — and it disagreed with me. Rather than keep the cleaner claim and the pooled number that supported it, the conclusion was **downgraded to "costs little"** and the 2%-of-variance figure was published alongside it. **A sensitivity analysis is only worth running if you are willing to lose.** |
| **A negative result is reported as a result** | K-means returns clusters whenever asked. Silhouette shows this herd has none (≤ 0.146 at every k). The notebook reports **no structure** rather than manufacturing three profiles. |
| **The data's own coding was verified, not assumed** | The glossary defines BLAD/CVM/HH1–HH6 as **carrier probability (0 = free, 99 = carrier)**, not binary flags. Treating them as 0/1 would invert the entire defect screen. |

---

## Repository structure

```
├── notebooks/
│   ├── 01_Data_Cleaning.ipynb        # audit, completeness, marker-coding verification
│   ├── 02_EDA.ipynb                  # population, markers, sire diversity
│   ├── 03_Correlation_Analysis.ipynb # corrected matrix, VIF, redundancy
│   ├── 04_Genomic_Trends.ipynb       # indexes, production, conformation, inbreeding
│   └── 05_Genomic_Profiles.ipynb     # proof-source sensitivity, PCA, clustering, balance
├── data/
│   ├── README.md                     # data provenance and synthetic-sample limits
│   └── sample_synthetic.csv          # synthetic sample — real data is confidential
├── outputs/                          # generated figures and tables
├── src/
│   └── portfolio_style.py            # reusable plotting style
├── requirements.txt
└── README.md
```

**Start here:** [`04_Genomic_Trends.ipynb`](notebooks/04_Genomic_Trends.ipynb) — the
pedigree/genomic inbreeding divergence.

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
  partial correlation, mediation testing, log-rank and Cox proportional hazards
- **Effect sizes:** Cohen's d with 95% confidence intervals; minimum detectable effect
  reported for every underpowered test
- **Multiple testing:** Bonferroni correction across trait families
- **Diagnostics:** Variance Inflation Factors, proportional-hazards tests
- **Unsupervised:** PCA (dimensionality), k-means with silhouette validation

## Setup

```bash
git clone https://github.com/<user>/holstein-genomic-analysis.git
cd holstein-genomic-analysis
pip install -r requirements.txt
jupyter notebook
```

## Limitations

Every figure reports **genomic breeding values, not measured performance**. All animals
were evaluated on the same date, so cohort comparisons describe the merit of animals
*born* in each year — they are **not** population genetic trends estimated with a genetic
model, and not longitudinal measurements. Early cohorts are small (2018: n = 13) and
subject to survivorship: culled animals are absent. Correlations describe association
within one herd (n = 668) and are not causal.

## Domain references

- Lactanet — *The Modernized LPI* (April 2025): subindexes standardized so the average
  proven sire = 500, SD = 100
- Lactanet — *Pro$*: formula details are not published
- Lactanet — *Body Maintenance Requirements*: +5 RBV points ≈ $70 saved in maintenance
  feed per daughter over three lactations
- Lactanet — *Interpreting Sire Proofs for Linear Type Traits*: Holstein conformation
  EBVs standardized to base 0, SD 5; each 5 stature points ≈ 1.15 cm in daughters
- Oliveira et al. (2021); Lynch et al. (2021) — unrecorded Timed AI and sire re-ranking

---

**Claudia Perdomo**
[LinkedIn](https://www.linkedin.com/in/claudia-perdomo-803340325) · cmperdomor14@gmail.com
