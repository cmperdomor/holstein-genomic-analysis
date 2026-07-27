# Holstein Genomic Analysis: What 668 Cows Reveal About a Herd's Breeding Strategy

End-to-end analysis of genomic breeding values from a commercial Canadian Holstein herd: 668 animals, 138 variables, 8 birth-year cohorts.

The herd shows strong predicted progress in the traits that increased across recent cohorts, alongside declines in other domains that received less apparent emphasis. Because historical mating goals, sire-selection criteria and applied weights are not available, the analysis describes these patterns rather than attributing them to a documented strategy.

The project answers eight questions:

1. How has the genomic profile of the herd changed over time?
2. How are genomic traits associated?
3. Does Proof Source influence the observed relationships?
4. Are there distinct genomic profiles among cows?
5. Can cows be grouped using unsupervised learning?
6. Which cows show the most balanced genomic profile?
7. How has genomic inbreeding changed over time?
8. Are there redundant genomic indexes?

## Key findings

**1. (Q1) Recent cohorts show higher predicted merit for fat and profit.**
Across cohorts 2018 to 2026, mean genomic merit for Fat yield rose more than fivefold (11.8 to 61.3 kg, r2 = 0.95) and Pro$ rose 144% (658 to 1,609 CAD). Milk EBV and fat percentage show the expected negative association (r = -0.41), although this is partly structural, since component percentage is mathematically related to component yield and milk volume (see the VIF diagnostic in notebook 03), so it is not independent biological evidence of a trade-off. Both the volume and the concentration cohort means rose together. These are cohort means from one herd on a single evaluation date, not a modelled genetic trend.

**2. (Q7) Pedigree and genomic inbreeding disagree at the animal level.**
Computed on the same 489 animals over the same 2021+ period, genomic inbreeding rose numerically faster than pedigree (+0.556 vs +0.395 points per year), but the annual increase in their difference was NOT statistically significant (+0.161/yr, p = 0.107). The two measures correlate r = 0.68 (pedigree explains 47% of genomic variance) and capture related but different quantities: expected inbreeding from known relationships versus realized homozygosity from markers. Bland-Altman shows a mean gap of +3.68 points with wide limits of agreement [-1.33, 8.69], and using an 8% threshold, 210 animals change classification depending on whether pedigree or genomic inbreeding is used.

**3. (Q2) Higher body-size merit shows no milk advantage and less favourable functional evaluations.**
Body size is unrelated to milk yield (r = +0.01, ns) but negatively related to Herd Life (-0.42), Body Maintenance (-0.65), Environmental Impact (-0.45) and Fat yield (-0.21). Larger cows showed no detectable milk advantage: the small-minus-large difference is +94 kg with a 90% CI of [+3, +186] kg. An exploratory equivalence sensitivity analysis (added during review, not pre-registered) found equivalence was NOT established under a stricter 0.33 SD margin (p = 0.069) and held only under a lenient 0.5 SD margin. Neither margin is a validated biological threshold, so the defensible statement is simply that no milk advantage was detected. Smaller cows nonetheless carry +19 kg fat and +11 kg protein, and the associations with longevity, maintenance and profit survive standard errors clustered by sire (213 sires; size vs Herd Life p = 1.4e-15, vs BMR p = 4.1e-38, vs Pro$ p = 1.9e-10). The pattern was consistent across three alternative operational definitions of body size (herd quartiles, breed base, composite index).

**4. (Q4 and Q5, one test answers both) No well-separated clusters were detected.**
K-means across k = 2 to 6 never exceeds a silhouette of 0.146, indicating weak separation. Under this specification (k-means on the six standardized subindexes) the variation is better represented as a continuum than as discrete groups. This does not prove no structure of any kind exists, only that no well-separated clusters were found; it is reported as a negative result rather than dressed up as profiles.

**5. (Q8) Redundancy is trait-specific.**
The 32 conformation traits collapse to about 10 dimensions (VIF up to 961), while the six functional subindexes are not redundant: 5 of 6 principal components are needed for 80% of variance, none exceeding 24%. The subindexes carry largely independent information, in contrast to the highly collinear conformation traits. (PCA describes the multivariate structure of these evaluations; it does not by itself establish genetic independence or predict selection response, which would require genetic correlations or a longitudinal model.) Observed alongside this, REPRO fell 45.9 points and ENVIRO fell 138.4 across cohorts while production and type rose.

**6. (Q6) Only 3.1% are above the herd mean on all six subindexes.**
Just 21 of 668 animals (3.1%) sit above the herd mean on all six subindexes under this exploratory definition, and they average Pro$ 1,887 against the herd's 1,145. High values across all six subindexes and high Pro$ can coexist within this herd, though this descriptive subgroup does not establish the absence of trade-offs, and Pro$ is itself related to some of the subindexes used to define the group.

**7. (Q3) Most relationships are stable across Proof Source.**
LPI vs Pro$ and inbreeding vs merit barely move across subsets. Within the GEBV subset the production-reproduction correlation is significant (r = -0.145, p = 0.016) while pooled it is not (r = -0.033, ns); however, a formal interaction test comparing the two genomically tested groups (REPRO ~ PROD * [GPA vs GEBV] + BirthYear, standard errors clustered by sire) finds the interaction term NOT significant (coef +0.137, 95% CI [-0.07, +0.35], p = 0.20), so the difference between subsets is not established. The honest reading is that the pooled production-reproduction association is near zero, and any subset difference is suggestive at most.

## Recommendations

These are the actions the data supports, in the order I would take them.

### 1. Change the instrument before changing the strategy

Do not rely on pedigree inbreeding alone for mating decisions. Pedigree and genomic estimates disagree substantially at the animal level (limits of agreement [-1.33, 8.69]), and 210 animals classified below 8% on pedigree are at or above 8% on genomic. Both are valid estimates of different quantities; the point is that 210 animals change classification depending on which measure is applied at an 8% threshold.

Nothing else on this list matters if the measurement is wrong. Switch mating decisions to genomic inbreeding, which is already in the export and costs nothing extra to use.

### 2. Evaluate a minimum REPRO threshold before implementing it

REPRO has fallen for eight consecutive cohorts and now sits below the proven-sire base (486 vs 500), with most of the herd below base.

Evaluate a minimum REPRO threshold (for example 500) in the mating program and quantify its expected effects on production, inbreeding and other breeding objectives before implementing it. The pooled production-reproduction correlation is near zero (r = -0.033, ns), which suggests the production cost may be small, and REPRO is positively associated with profit; but a near-zero correlation does not prove selection is economically almost free, and 500 is not shown to be the optimal threshold. This is a hypothesis to test in a selection-index simulation, not a finished recommendation.

The reason to act now is that genetic decline is cumulative and permanent. Management protocols are re-purchased every year and lost the moment you stop paying. The 45.9 points already lost will not come back on their own, and per Lactanet, corrective breeding decisions take roughly five years to reach the bulk tank.

### 3. Avoid further increases in body size unless they serve a defined objective

The herd is getting bigger (Body Depth +0.267 per year, p = 0.0003). Larger size showed no detectable milk advantage and was associated with less favourable evaluations for components, longevity, fertility and feed maintenance. The project did not measure every possible benefit of size or real economic performance, so the recommendation is to avoid continued size increases unless they serve a clearly defined breeding objective, not to treat size as valueless.

Keep selecting for the type traits that pay, such as Locomotion (r = +0.24 with Herd Life) and Front Legs View (r = +0.33 with Pro$), and apply negative or capping pressure on Stature and Body Depth. Using Lactanet's published conversion, the smaller quartile's BMR advantage is worth roughly $63 per daughter over three lactations, estimated without touching the proprietary Pro$ formula.

The scale of this matters: the gap between the small and large stature quartiles is approximately 2 cm. Two centimetres separate a group with +19 kg fat, +11 kg protein and +3.6 Herd Life points from one without them, with no detectable milk advantage for the larger group.

### 4. Breed from the herd's own best animals

The solution does not need to be imported. 45 animals (6.7%) already combine top-quartile production, REPRO greater than or equal to 500 and below-average size, and they are worth Pro$ 2,146 vs the herd's 1,145. A further 21 animals (3.1%) are above the herd mean on all six subindexes.

These are not compromise animals; they are among the most profitable in the herd. Their existence shows the favourable combination is achievable within this herd. It does not prove the absence of any genetic or biological antagonism, only that the combination exists and can be selected for.

### 5. Record reproductive management

Fertility phenotypes are only as good as their context. Published work shows breeding values for heat detection and Timed AI correlate at R = 0.5 (p = 0.002), causing sires to re-rank depending on the reproductive management of the herds recording their daughters (Oliveira et al., 2021; Lynch et al., 2021).

This dataset has no reproductive-protocol field: Current group records semen type, not protocol. Recording it costs nothing and improves every fertility evaluation the herd contributes to and receives.

## How these findings were validated

Genomic evaluations are constructed values. Several of the relationships in this dataset are arithmetic rather than biological, and the analysis was built to separate them.

| | |
|---|---|
| **Index components were excluded before interpreting correlations** | PROD correlates +0.96 with Protein yield and Conf +0.86 with Mammary System, because each is built from the other. Diagnostics caught a further dependency that visual inspection missed: %Fat had VIF = 961, since component percentages are functions of yield and volume. Composites are never reported as independent evidence alongside their own components. |
| **The profit result was checked against the index that produces it** | Small cows show +617 CAD of Pro$. Lactanet does not publish the Pro$ formula but confirms that body size modifies its maintenance-cost term, so that result is partly structural. The economic estimate is therefore rebuilt from BMR's published conversion (about $63 per daughter over three lactations), and the size conclusion rests on fat, protein and Herd Life, which are independent evaluations. |
| **Mechanisms were tested, not assumed** | The intuitive explanation for finding 3, that smaller cows redirect saved maintenance energy into fat, was tested by cluster-bootstrap mediation (resampling sire families, adjusting for birth year). The indirect effect through BMR is +0.225 with a 95% CI of [-0.324, +0.800], which includes zero: the data do not support BMR as the mediator. This does not refute energy-partitioning physiology in general; it shows BMR does not account for the association here. |

Sensitivity checks by Proof Source, effect sizes with confidence intervals, minimum detectable effects for every underpowered test, and Bonferroni correction across trait families are reported throughout.

## A note on what this project could not do

I attempted to validate the genomic fertility evaluation against the herd's real service records. It did not work, and the reason is worth more than the result would have been.

Mean services fall monotonically across DF quartiles (2.56 to 1.90), but no assumption-valid test reaches significance: the log-rank test gives p = 0.536, and a Cox model returned p = 0.011 while violating proportional hazards (p = 0.003), making it unreportable.

This is arithmetic, not failure. Fertility heritability is low (h2 about 0.02 to 0.05), so the correlation between an evaluation and an animal's own phenotype cannot exceed about 0.22 even for a perfect evaluation. Detecting an effect that small requires about 344 cows at 80% power; this herd offers 278.

A single 668-animal herd is structurally too small to validate a low-heritability evaluation. That does not weaken recommendation 2: the herd's own 45.9-point REPRO decline is the demonstration that low-heritability traits accumulate, measured on the genetic trend rather than on an individual-cow prediction.

## Repository structure

```
notebooks/
  01_Data_Cleaning.ipynb        audit, completeness, marker-coding verification
  02_EDA.ipynb                  population, markers, sire diversity
  03_Correlation_Analysis.ipynb corrected matrix, VIF, redundancy
  04_Genomic_Trends.ipynb       indexes, production, conformation, inbreeding
  05_Genomic_Profiles.ipynb     proof-source sensitivity, PCA, clustering, balance
data/
  README.md                     data provenance and synthetic-sample limits
  sample_synthetic.csv          synthetic sample, real data is confidential
outputs/                        generated figures and tables
requirements.txt
README.md
```

Start here: 04_Genomic_Trends.ipynb, the pedigree vs genomic inbreeding divergence.

## Data availability

The original dataset is a commercial genomic export from a private Canadian Holstein farm and is not published. All figures, statistics and conclusions in this repository were computed on that real data.

data/sample_synthetic.csv (60 x 138) reproduces the column names, types, ranges and missing-data pattern so the code runs end to end. Its columns were generated independently, so it deliberately carries none of the real correlation structure: the code executes, but the findings will not reproduce on it. A synthetic file that preserved those correlations would effectively republish the confidential dataset. See data/README.md.

## Methods

* Descriptive: completeness audit, IQR outlier screening, distribution profiling
* Inferential: Pearson correlation, Mann-Whitney U, OLS regression implemented from scratch with numpy.linalg.lstsq (coefficients, standard errors, t, p and R2), partial correlation, mediation testing, log-rank and Cox proportional hazards
* Non-independence: standard errors clustered by sire for the central size associations (213 sires); formal interaction tests before claiming a relationship differs between subgroups
* Equivalence: two one-sided tests (TOST) before claiming two groups are equivalent rather than merely not significantly different
* Effect sizes: Cohen's d with 95% confidence intervals; minimum detectable effect reported for every underpowered test
* Multiple testing: Bonferroni correction across trait families
* Diagnostics: Variance Inflation Factors, proportional-hazards tests
* Unsupervised: PCA (dimensionality), k-means with silhouette validation

## Setup

```bash
git clone https://github.com/cmperdomor/holstein-genomic-analysis
cd holstein-genomic-analysis
pip install -r requirements.txt
jupyter notebook
```

## Limitations

Every figure reports genomic breeding values, not measured performance. All animals were evaluated on the same date, so cohort comparisons describe the merit of animals born in each year: they are not population genetic trends estimated with a genetic model, and not longitudinal measurements. Early cohorts are small (2018: n = 13) and subject to survivorship, since culled animals are absent. Correlations describe association within one herd (n = 668) and are not causal.

Additional statistical caveats, stated plainly:

* Non-independence. The 668 cows are not independent: many share sires (213 sires in total). The central size associations are re-tested with standard errors clustered by sire and survive (size vs Herd Life p = 1.4e-15), but not every reported p-value has been clustered, so uncorrected intervals elsewhere may be optimistic. A sire random-effects model would be the fuller treatment.
* Cohort trends are not causal. Higher recent-cohort merit for fat and Pro$ is a description; it does not establish that a specific intentional strategy produced it.
* PCA describes structure, not selection response. The independence of the subindex axes is a multivariate description, not evidence of genetic correlations or of how the herd would respond to selection.
* Clustering is specification-dependent. "No well-separated clusters" holds for k-means on these six variables; other methods or variables could behave differently.

## Domain references

* Lactanet, The Modernized LPI (April 2025): subindexes standardized so the average proven sire = 500, SD = 100
* Lactanet, Pro$: formula details are not published
* Lactanet, Body Maintenance Requirements: +5 RBV points is about $70 saved in maintenance feed per daughter over three lactations
* Lactanet, Interpreting Sire Proofs for Linear Type Traits: Holstein conformation EBVs standardized to base 0, SD 5; each 5 stature points is about 1.15 cm in daughters
* Oliveira et al. (2021); Lynch et al. (2021): unrecorded Timed AI and sire re-ranking

## Author

Claudia Perdomo
LinkedIn: https://www.linkedin.com/in/claudia-perdomo-803340325
Email: cmperdomor14@gmail.com
