# Consistency Audit

Every quantitative claim in the README checked against executed outputs on the real
dataset (668 Holstein females, single-date export). Status: PASS (matches output),
FAIL (contradicts output, corrected), UNRESOLVED (cannot verify without re-running).

| Claim | Value | Notebook | n | Type | Status |
|---|---|---|---|---|---|
| Animal count | 668 | all | 668 | descriptive | PASS |
| Described as "cows" | should be "females" | README | 326 GPA are heifers | descriptive | FAIL -> corrected to "females" |
| Column count | 138 vs 139 | README/AUDIT | -- | descriptive | FAIL -> real export has 139 cols; "138 variables" was after dropping an index col. Corrected to 139. |
| "All genomic breeding values" | GPA 326, GEBV 277, SMX PA 36, EBV 16, PA 13 | README | 668 | descriptive | FAIL -> not all genomic; corrected |
| Cohort span | 2013-2026 (13 yrs); analyses filter 2018+ | 04 | -- | descriptive | FAIL -> "8 cohorts / 2018-2026" imprecise; corrected |
| Unique sires | 212, 2 no-sire animals EXCLUDED, models re-run at n=666 | 05 | 666 | descriptive | RESOLVED -> n=666, 212 clusters; results unchanged |
| LPI cohort change | 2,919 to 3,492 | 04 | -- | descriptive | PASS |
| Pro$ cohort change | 658 to 1,609 | 04 | -- | descriptive | PASS |
| Fat cohort change | 11.8 to 61.3 kg | 04 | -- | descriptive | PASS |
| Milk vs %Fat | r = -0.41 (partly structural) | 03 | 668 | association | PASS |
| VIF max %Fat | 961 (production block) | 03 | -- | method-specific | PASS but mis-cited for conformation; corrected |
| Conformation "~10 dimensions" | not a located output | 03 | -- | -- | UNRESOLVED -> reworded, specific figure removed |
| PROD x (GPA/GEBV) interaction | +0.137, CI [-0.07,+0.35], p=0.20 | 05 | 603 | model-based | PASS |
| PCA PCs for 80% | 5 of 6, PC1=24% | 05 | 668 | method-specific | PASS |
| k-means silhouette | max 0.146 | 05 | 668 | method-specific | PASS |
| Balance count | 21 (3.1%) above herd mean all 6 | 05 | 668 | descriptive | PASS |
| Balance Pro$ | 1,887 vs 1,145 | 05 | -- | descriptive | PASS |
| Genomic slope 2021+ | +0.556/yr | 04 | 489 | descriptive | PASS |
| Pedigree slope 2021+ | +0.395/yr | 04 | 489 | descriptive | PASS |
| Gap growth | +0.161/yr, p=0.107 | 04 | 489 | model-based | PASS |
| Paired r | 0.68 (r2=0.47) | 04 | 489 | association | PASS; "explains 47%" reworded |
| 210 animals | below 8% pedigree AND >=8% genomic, of 489 (43%) | 04 | 489 | descriptive | PASS; denominator + direction added |
| Bland-Altman | mean +3.68, LoA [-1.33, 8.69] | 04 | 489 | descriptive | PASS |
| SIZE vs HL/BMR/Pro$ clustered | -2.40 (p=1.4e-17) / -3.09 (p=4.5e-34) / -463.78 (p=5.9e-19) | 05 | 666 | model-based | PASS |
| Body Depth slope | +0.267/yr, p=0.0003 | 04/05 | -- | descriptive | PASS |
| Stature slope | +0.230/yr, p=0.097 (ns) | 04/05 | -- | descriptive | PASS |
| Small vs large Fat/Prot | +19.3 / +10.9 kg | 05 | 387 | descriptive | PASS |
| TOST 0.33 SD | not equivalent, p=0.069 | 05 | 387 | method-specific | PASS |
| TOST 0.5 SD | equivalent, p=0.0009 | 05 | 387 | method-specific | PASS |
| Mediation indirect | +0.225, CI [-0.326,+0.771] includes 0 | 03 | 666 | model-based | PASS |
| Dispersion slope CI | seed=42 locked: approx [+2.32, +5.11] | 06 | 666 | method-specific | RESOLVED -> single value, seed=42, excludes 0 |
| RI P10 CI | seed=42 locked: approx [-12.7, +6.4] | 06 | 666 | method-specific | RESOLVED -> single value, seed=42, includes 0 |
| Dispersion driven by LTI | leave-one-out drops to -0.08 | 06 | 668 | method-specific | PASS |
| Stature cm conversion | 152.65 cm at proof 0, +1.35 cm/5pt (Holstein, Apr 2025) | README | -- | externally sourced | FAIL -> old value 150.31/1.15 corrected |
| Conformation h2 | ranges from 0.04 (Oliveira 2021) | README | -- | externally sourced | PASS |
| Fertility weight on LPI | ~13% (Oliveira 2021) | README | -- | externally sourced | PASS |
| "Timed AI R=0.5, sires re-rank" | NOT in Oliveira 2021 | README | -- | externally sourced | FAIL -> unsupported, removed |
| Lynch et al. 2021 citation | not verifiable | README | -- | externally sourced | FAIL -> removed |
| $63/daughter BMR | derived, not quoted (Lactanet ~$70/5pts/3 lact) | AUDIT | -- | externally sourced | FAIL -> relabelled derived estimate |

## Sample-size key (which n applies where)

| Analysis | n |
|---|---|
| Sire-clustered size models (HL, BMR, Pro$) | 666 (212 sires) |
| Mediation, sire-clustered bootstrap | 666 (212 sires) |
| GPA vs GEBV interaction | 603 (192 sires) |
| PCA of six subindexes | 668 |
| k-means | 668 |
| Above herd mean on all six | 668 |

The missing-sire exclusion applies only to sire-clustered analyses; descriptive and
unsupervised analyses use all 668 animals.

## Points resolved in this pass
- Sire treatment: 2 no-sire animals excluded; models re-run at n=666, 212 clusters; results essentially unchanged.
- Bootstrap CIs: seed=42 locked; dispersion approx [+2.32, +5.11] (excludes 0), RI P10 approx [-12.7,+6.4] (includes 0).

## Remaining note
- The "~10 independent conformation dimensions" figure had no single located output and was removed (not reinstated).
