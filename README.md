# Holstein Genomic Analysis: What 668 Holstein Females Reveal About a Herd's Breeding Profile

End-to-end analysis of published genetic evaluations from a single commercial Canadian Holstein herd: 668 Holstein females, 139 variables, from a single-date export spanning birth years 2013 to 2026 (inferential analyses filter to 2018+ where cohort sizes are adequate).

All values analysed are published genetic evaluations representing predicted genetic merit, not measured performance. Most animals carry genomic evaluations (GPA 326, GEBV 277), and the export also includes other proof sources (SMX PA 36, EBV 16, PA 13). Because 326 animals are GPA (typically genotyped heifers without their own production records), the group is described as "females," not "cows." This is a cross-sectional analysis of one herd on one evaluation date; it cannot estimate population genetic parameters or establish causation.

The herd shows strong predicted progress in the traits that increased across recent cohorts, alongside declines in other domains that received less apparent emphasis. Because historical mating goals, sire-selection criteria and applied weights are not available, this analysis describes these patterns rather than attributing them to a documented strategy.



## The eight questions, answered in plain language

Each answer has two layers: first for a producer, then the statistical detail. The notebook that produces each result is named in brackets.

### 1. How has the genetic evaluation profile of the herd changed over time? (notebook 04)

**For the producer.** Females from more recent birth cohorts in this export carry substantially higher predicted merit for production, LPI and profit. Historical mating objectives and selection weights are not available, so an intentional strategy cannot be established from these data.

**Statistical detail.** Descriptive birth-cohort patterns (2018+ cohorts), reported as absolute changes in predicted merit: LPI +573 points (2,919 to 3,492), Pro$ +951 dollars of predicted lifetime profitability (658 to 1,609), Fat merit +49.5 kg (11.8 to 61.3). These are descriptive fits to observed cohort means, not predictive quality, causal proof or national genetic trends; the high r-squared values come from regressions on 8-9 annual means, not on independent observations, so they are not reported as a strength. LPI is an index on a reference base with no natural ratio interpretation, so percentage changes are omitted. Cohort sizes are unequal, the most recent cohort may be incomplete, and older cohorts include only females still present in the export (survivorship).

### 2. How are published genetic evaluations associated? (notebook 03)

**For the producer.** Some traits move together for real biological reasons; others only appear linked because one is built from the other. We separated the two so the real relationships are not mixed up with arithmetic.

**Statistical detail.** Correlations were computed only after excluding composite traits from matrices containing their own components (for example Conf with MS/FL/DS/RU). The milk-to-fat-percentage link (r = -0.41) is partly structural, since a component percentage is mathematically tied to yield and volume; it is not treated as independent biological evidence.

### 3. Does evaluation stage (GPA versus GEBV) modify the PROD-REPRO association? (notebook 05)

**For the producer.** We checked whether the production-reproduction relationship differs between two evaluation stages (GPA, animals evaluated mainly on genomics and pedigree, versus GEBV, animals that also carry their own records). A formal test could not distinguish the two, so we do not claim they differ.

**Statistical detail.** Interaction model REPRO ~ PROD * C(evaluation stage) + BirthYear, standard errors clustered by sire (n = 603, 192 sires): interaction coefficient +0.137, 95% CI [-0.07, +0.35], p = 0.20. The estimated interaction is not statistically distinguishable from zero under this model. This does not prove identical relationships between GPA and GEBV animals, and it is not generalised to other proof sources or to other relationships. Proof source and reliability are related but not identical concepts.

### 4. Is variation across the six subindexes dominated by one dimension or several? (notebook 05)

**For the producer.** The six LPI subindexes capture several dimensions of variation and are not strongly reducible to one or two components in this herd; the herd's variation does not collapse onto a single underlying axis. You cannot summarise an animal with just one number.

**Statistical detail.** PCA on the six standardized subindexes: 5 of 6 principal components are needed to exceed 80% of observed variance, PC1 about 24%. The structure is multidimensional, so the subindexes are not strongly reducible to one or two dimensions in this herd. PCA describes multivariate structure; it does not establish genetic independence, equal economic importance or causation.

### 5. Do animals form well-separated genetic-evaluation profile clusters? (notebook 05)

**For the producer.** When we let an algorithm try to sort the females into distinct groups, it did not find clean, well-separated ones. The herd looks like a continuous range rather than a set of separate profiles.

**Statistical detail.** k-means on the six standardized subindexes for k = 2 to 6, silhouette maximum 0.146. No well-separated clusters were detected under this specification; the observed variation is better represented as a continuum. The conclusion is limited to k-means, these six variables and this standardization; it does not prove no structure of any kind exists, and other methods or variables could behave differently.

### 6. Which females show the most balanced genetic-evaluation profile? (notebook 05)

**For the producer.** Very few females are above average in all six breeding areas at once, only about 3 in 100. That small group also carries a much higher predicted-profitability evaluation than the herd average.

**Statistical detail.** 21 of 668 females (3.1%) exceed this herd's mean on all six subindexes. These 21 animals had a substantially higher mean Pro$ evaluation (1,887) than the herd average (1,145). Pro$ is a predicted-profitability evaluation, not observed economic profit. The "balance" criterion is exploratory, relative to this herd's distribution, uses implicitly equal weight across the six subindexes, and other criteria would rank animals differently. (Animals are additionally ranked by their minimum z-score across the six subindexes as a secondary diagnostic.)

### 7. How has genomic inbreeding changed over time? (notebook 04)

**For the producer.** Inbreeding is rising, and the pedigree number and the DNA-based number do not always agree for the same animal. Of the 489 females with both measures, 210 fall below the 8% mark on the pedigree number but at or above it on the DNA-based number. The two measures capture related but different things, so it is worth looking at both when planning matings rather than the pedigree alone.

**Statistical detail.** On the same 489 females over the same 2021+ period, genomic inbreeding rose numerically faster than pedigree (+0.556 vs +0.395 per year), but the annual increase in their difference is not statistically significant (+0.161/yr, p = 0.107). The squared correlation between the two measures is about 0.47, indicating substantial but incomplete linear association. The two are conceptually different quantities: expected inbreeding from the recorded pedigree versus realized marker-based homozygosity. Bland-Altman (an exploratory description of the disagreement between two related measures, not proof that either is correct) gives a mean difference of +3.68 points with limits of agreement [-1.33, 8.69]. At the selected 8% decision threshold, 210 of 489 paired females (43%) fell below the threshold on the pedigree measure but at or above it on the genomic measure; only 2 went the opposite way. Neither measure is treated as an absolute gold standard.

### 8. Are the six subindexes reducible, and how redundant are the conformation traits? (notebooks 03 and 06)

**For the producer.** Many conformation traits within the same body area move together, so tracking every single correlation adds limited information. But traits that move together are not necessarily interchangeable when choosing matings. The six main breeding indexes each tell you something different and are all worth watching.

**Statistical detail.** Within the production block, evaluations are highly collinear (VIF up to 961 for %Fat), because component percentages are mathematical functions of yields and volume; this demonstrates multicollinearity within that block, not that conformation traits repeat one another. For the six functional subindexes, five principal components are required to exceed 80% of observed variance, indicating they are not strongly reducible to one or two dimensions in this herd. PCA describes multivariate structure; it does not establish genetic independence, equal economic importance, or selection response. (A specific "about 10 independent conformation dimensions" figure stated in earlier drafts is not backed by a single located output and has been removed.)

## Additional finding: body size

**For the producer.** The herd is becoming deeper-bodied over time. Within this herd, higher body-size merit shows no detectable advantage in milk-yield merit and goes together with less favourable evaluations for how long females are expected to last, how much feed they need for maintenance, environmental impact, and fat merit.

**Statistical detail.** The composite body-size merit score is a within-herd construct: the equal-weight average of z-scores for Stature, Body Depth, Height at Front End and Chest Width. It is not measured body weight, is not in kg, is not an externally validated scale, one unit equals one within-herd standard deviation, and the four traits do not necessarily contribute equally to physiological size. Sensitivity check: the negative Fat association holds under each single trait except Chest Width alone (which is null), and under every leave-one-out composite, so the result is not driven by any single component; Chest Width contributes least. Of the four traits, two rose significantly across cohorts: Body Depth (+0.267/year, p = 0.0003) and Height at Front End (+0.241/year, p = 0.022); Stature rose but not significantly (+0.230/year, p = 0.097) and Chest Width was flat (p = 0.36). The composite shows no detectable milk-merit association (r = +0.01, ns) and unfavourable associations with Herd Life (-0.42), Body Maintenance (-0.65), Environmental Impact (-0.45) and Fat merit (-0.21). Several of these are partly structural rather than independent biological findings: Body Maintenance is built from weight-linked maintenance requirements, Environmental Impact includes Body Maintenance, and Pro$ incorporates maintenance-related costs, so size-BMR, size-ENVIRO and size-Pro$ are not fully independent of how the indexes are constructed. The size-Herd Life, Body Maintenance and Pro$ associations survive standard errors clustered by sire with birth year and proof source as covariates (HL p=1.4e-17, , Pro$ coefficient -463.78, p=5.9e-19; n=666 after excluding 2 animals with no recorded sire, 212 sire clusters). Clustering by sire reduces dependence from paternal half-sib groups but does not account for the full relationship structure. In adjusted models (trait ~ SIZE + birth year + Proof Source, sire-clustered SE, n=666), the composite is unrelated to Milk merit (coef -9.6, 95% CI [-83.9, +64.7], p = 0.80) and negatively related to Fat merit (coef -13.4, 95% CI [-17.4, -9.4], p = 7e-11) and Protein merit (coef -7.0, 95% CI [-10.2, -3.8], p = 2e-05). The quartile comparison (smaller quartile +19.3 kg fat, +10.9 kg protein merit) is shown for communication only; the adjusted models are the primary evidence. No detectable Milk-merit advantage was found for the larger group; strict equivalence was not established under the 0.33 SD margin (p = 0.069) and held only under the wider 0.5 SD margin, so the practical conclusion depends on the margin, which is a sensitivity analysis, not a validated biological threshold.

## Recommendations

These are the actions the data supports, framed as hypotheses to test, not finished prescriptions.

### 1. Do not rely on pedigree inbreeding alone for mating decisions

Pedigree and genomic estimates disagree substantially at the animal level (limits of agreement [-1.33, 8.69]), and 210 animals classified below 8% on pedigree are at or above 8% on genomic. Both are valid estimates of different quantities; at the 8% threshold, 210 of 489 paired females change classification between the two measures. The genomic measure is already available in this herd's export, so no additional testing is required to use it in the current mating workflow.

### 2. Evaluate a minimum REPRO threshold before implementing it

REPRO has fallen across cohorts and the herd mean (486) sits below the proven-sire base of 500. Evaluate a minimum REPRO threshold (for example 500) in a selection-index simulation and quantify its effects on production, inbreeding and other objectives before implementing it. The pooled production-reproduction correlation is near zero (r = -0.033, ns), so the production cost may be small, and REPRO is positively associated with profit; but a near-zero correlation does not prove selection is economically almost free, and 500 is not shown to be the optimal threshold.

### 3. Avoid further increases in body size unless they serve a defined objective

Body Depth and Height at Front End rose significantly (see the body-size section). Larger body-size merit showed no detectable milk association and unfavourable associations with longevity, feed maintenance and fat merit. Avoid continued increases in these traits unless they serve a clearly defined breeding objective; this does not mean size is valueless, only that the project measured no benefit to offset the costs.

### 4. Maintain production and type gains while testing more emphasis on the functional domains

Recent cohorts show greater separation among the six subindexes, driven primarily by the much faster increase in LTI; this does not necessarily indicate intentional specialization. Rather than pushing production and type harder (the herd has already advanced strongly there), maintain those gains while simulating greater emphasis on Environmental Impact and Reproduction, to test whether functional weaknesses can be reduced without materially sacrificing overall merit.

### 5. Record reproductive management

Fertility phenotypes depend on management that is not recorded in this export. This dataset has no reproductive-protocol field. Recording reproductive management protocols would improve interpretation of fertility phenotypes and the quality of data contributed to genetic evaluation systems. (Fertility traits are low-heritability, and the weight on fertility traits within LPI is about 13%; Oliveira et al., 2021.)

## A note on what this project could not do

Validating the genomic fertility evaluation against real service records did not succeed, and the reason is quantifiable. Mean services fall monotonically across DF quartiles (2.56 to 1.90), but no assumption-valid test reaches significance (log-rank p = 0.536; a Cox model gave p = 0.011 but violated proportional hazards, p = 0.003). Fertility heritability is low (about 0.02 to 0.05), so the correlation between an evaluation and an animal's own phenotype is bounded low (roughly 0.2 or less, from cor(EBV, phenotype) = accuracy times the square root of heritability, with heritability about 0.02 to 0.05). The available sample has limited power to validate a low-heritability evaluation against the individual phenotype. (A specific required-sample figure quoted in earlier drafts could not be reconstructed from documented assumptions and has been removed.)

## How these findings were validated

Genomic evaluations are constructed values, and several relationships in this dataset are arithmetic rather than biological. The analysis was built to separate them: composite traits were excluded from correlation matrices containing their own components; the profit result was checked against the index that produces it (body size enters Pro$ through maintenance cost, so that result is partly structural and the economic estimate is rebuilt from BMR's published conversion); mechanisms were tested formally rather than assumed (cluster-bootstrap mediation shows BMR does not account for the size-fat association, indirect effect CI [-0.326, +0.771] includes zero). Sire-clustered standard errors, effect sizes, confidence intervals, equivalence testing, minimum detectable effects and FDR correction were used where relevant to the corresponding statistical question, not in every analysis.

## Repository structure

```
notebooks/
  03_Correlation_Analysis.ipynb          traits association, VIF, mediation (Q2, Q8)
  04_Genomic_Trends.ipynb                cohort trends, inbreeding (Q1, Q7)
  05_Genomic_Profiles.ipynb              proof source, PCA, clustering, balance (Q3-Q6)
  06_Trait_Variability_and_Selection_Room.ipynb   distribution and selection room
data/
  README.md                              data provenance and synthetic-sample limits
  sample_synthetic.csv                   synthetic sample, real data is confidential
outputs/                                 generated figures
AUDIT.md                                 claim-to-code audit table
requirements.txt
README.md
```

Notebooks 01 (data cleaning) and 02 (EDA) provide descriptive population figures and are kept locally; they carry no headline inferential claim.

## Data availability

The original dataset is a commercial genomic export from a private Canadian Holstein farm and is not published. All figures and statistics were computed on that real data. `data/sample_synthetic.csv` reproduces column names, types, ranges and missing-data pattern so the code runs end to end, but its columns were generated independently and carry none of the real correlation structure: the code executes, but the findings will not reproduce on it. See `data/README.md`.

## Setup

```bash
git clone https://github.com/cmperdomor/holstein-genomic-analysis
cd holstein-genomic-analysis
pip install -r requirements.txt
jupyter notebook
```

## Limitations

Every figure reports published genetic evaluations, not measured performance. Most records are genomic evaluations, but PA, SMX PA and EBV proof sources are also present. Cohort comparisons describe animals born in each year, evaluated on one date; they are not population genetic trends and not longitudinal measurements. Early cohorts are small (2018: n = 13) and subject to survivorship. Correlations describe association within one herd (n = 668) and are not causal.

## Domain references

* Lactanet, The Modernized LPI (April 2025): subindexes standardized so the average proven sire = 500, SD = 100
* Lactanet, Pro$: formula details are not published
* Lactanet, Body Maintenance Requirements: about $70 saved in maintenance feed per +5 RBV points per daughter over three lactations
* Lactanet, Sire Proof Interpretation Table for Linear Type Traits (April 2025): for Holstein, daughters of a proof-0 sire average 152.65 cm stature, increasing about 1.35 cm per 5-point proof increase
* Oliveira Junior et al. (2021), J. Dairy Sci.: genetic parameters for Canadian Holstein traits; fertility traits are low-heritability and carry about 13% weight within LPI. (The previously cited "Timed AI, R=0.5, sire re-ranking" claim is not supported by this source and has been removed.)

## Author

Claudia Perdomo
LinkedIn: https://www.linkedin.com/in/claudia-perdomo-803340325
Email: cmperdomor14@gmail.com
