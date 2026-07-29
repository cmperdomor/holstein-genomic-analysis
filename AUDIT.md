# Consistency Audit

Every quantitative claim in README_FINAL.md, checked against the executed outputs of the
four notebooks on the real confidential dataset (668 Holstein females, single-date export).
Cell references are the code-cell index within each notebook. States: PASS (README matches
executed output), FAIL (contradiction, corrected this round), UNRESOLVED (cannot verify).
No claim with FAIL or UNRESOLVED status remains in the README.

| Claim | Value | Notebook | Cell | n | Type | State |
|---|---|---|---|---|---|---|
| Animals in export | 668 females | all | load | 668 | descriptive | PASS |
| Proof sources | GPA 326, GEBV 277, SMX PA 36, EBV 16, PA 13 | 05 | c1 | 668 | descriptive | PASS |
| Columns | 139 | all | load | -- | descriptive | PASS |
| Unique sires | 212 (2 animals no sire, excluded from clustered) | 05 | c1 | 666 | descriptive | PASS |
| LPI cohort change | +573 points (2919 to 3492) | 04 | c2 | -- | descriptive | PASS |
| Pro$ cohort change | +951 (658 to 1609) | 04 | c2 | -- | descriptive | PASS |
| Fat cohort change | +49.4 kg (11.8 to 61.3) | 04 | c2 | -- | descriptive | PASS |
| Production-block VIF | %Fat 961, Fat 857, Prot 519, Milk 412 | 03 | c2 | -- | method-specific | PASS |
| Q8 = production-block collinearity only (not conformation) | -- | 03 | c2 | -- | interpretation | FAIL -> corrected (conformation claim removed) |
| Mediation indirect (Stature->Fat via BMR) | +0.225, CI [-0.326,+0.771], includes 0 | 03 | c3 | 666 | model-based | PASS |
| Mediation total effect | -2.510 | 03 | c3 | 666 | model-based | PASS |
| Mediation interpretation | no detectable indirect effect; not "ruled out" | 03 | c3 | 666 | interpretation | FAIL -> corrected |
| Genomic inbreeding slope 2021+ | +0.556/yr, p=0.002 | 04 | c3 | 489 | descriptive | PASS |
| Pedigree inbreeding slope 2021+ | +0.395/yr, p=0.044 | 04 | c3 | 489 | descriptive | PASS |
| Gap growth | +0.161/yr, p=0.107 (ns) | 04 | c3 | 489 | model-based | PASS |
| Paired correlation | r=0.68 (r-squared about 0.47) | 04 | c4 | 489 | association | PASS |
| Discordance 8%, direction A | 210 pedigree<8 & genomic>=8 | 04 | c4 | 489 | descriptive | PASS |
| Discordance 8%, direction B | 2 pedigree>=8 & genomic<8 | 04 | c4 | 489 | descriptive | FAIL -> now computed and added |
| Total discordant | 212 of 489 (43.4%) | 04 | c4 | 489 | descriptive | FAIL -> corrected (was "210") |
| Small vs large stature Milk | +94.3 kg (MWU p=0.13) | 05 | c7 | 387 | unadjusted assoc | PASS |
| Small vs large Fat / Protein | +19.3 / +10.9 kg | 05 | c7 | 387 | unadjusted assoc | PASS |
| TOST 0.33 SD | not equivalent (p_high=0.069) | 05 | c2 | 387 | sensitivity | PASS |
| TOST 0.5 SD | equivalent (p_high=0.0009) | 05 | c2 | 387 | sensitivity | PASS |
| TOST labelling | "not preregistered" (not "not exploratory") | 05 | c2 | -- | interpretation | FAIL -> corrected |
| SIZE vs Milk, adjusted+clustered | -9.6, CI [-83.9,+64.7], p=0.80 (null) | 05 | c8 | 666 | adjusted model | PASS |
| SIZE vs Fat, adjusted+clustered | -13.4, CI [-17.4,-9.4], p=7e-11 | 05 | c8 | 666 | adjusted model | PASS |
| SIZE vs Protein, adjusted+clustered | -7.0, CI [-10.2,-3.8], p=2e-05 | 05 | c8 | 666 | adjusted model | PASS |
| SIZE single-trait (Fat) | Stature -9.2, BodyDepth -5.7, HFE -12.0 all p<0.001; CW -0.27 p=0.87 | 05 | c8 | 666 | sensitivity | PASS |
| SIZE vs HL / BMR / Pro$ clustered | -2.40 (p=1.4e-17) / -3.09 (p=4.5e-34) / -463.78 (p=5.9e-19) | 05 | c3 | 666 | adjusted model | PASS |
| Interaction PROD x (GPA vs GEBV) | +0.137, CI [-0.07,+0.35], p=0.20 | 05 | c4 | 603 | model-based | PASS |
| Interaction: five proof categories, no joint F-test | -- | 05 | c4 | -- | interpretation | FAIL -> corrected |
| Interaction sire handling | SireID built after dropna (no "nan" cluster) | 05 | c4 | 603 | method | FAIL -> corrected |
| PCA subindexes | 5 of 6 PCs for 80%, PC1 about 24% | 05 | c5 | 668 | method-specific | PASS |
| k-means silhouette | max 0.146 (weak separation) | 05 | c5 | 668 | method-specific | PASS |
| Balance count | 21 (3.1%) above herd mean on all six | 05 | c6 | 668 | descriptive | PASS |
| Dependence language | "reduce but do not eliminate" | 05 | c3 | -- | interpretation | FAIL -> corrected |
| LPI percentile slopes | P10 +83.5 > P90 +58.1 | 06 | c3 | 668 | descriptive | PASS |
| RI / EI declined all percentiles | RI P10 -5.3, EI P10 -8.0 | 06 | c3 | 668 | descriptive | PASS |
| Variance change after FDR | none significant (RI raw 0.038, FDR 0.2135) | 06 | c4 | 668 | method-specific | PASS |
| EI lowest tail | latest P10 = 384 | 06 | c5 | 668 | descriptive | PASS |
| RI P10 bootstrap CI | [-11.8, +8.3], includes 0 (seed=42, n>=30 cohorts) | 06 | c5 | 666 | method-specific | PASS |
| Dispersion slope | +4.61/yr, CI [+3.07,+5.99] (seed=42, n>=30) | 06 | c6,c7 | 666 | method-specific | PASS |
| Dispersion drop LTI | +0.21, CI [-1.53,+1.76] includes 0 | 06 | c7 | 666 | method-specific | PASS |
| Dispersion exclude EI / official weights | +5.47 / +5.15 (both exclude 0) | 06 | c7 | 666 | method-specific | PASS |
| Fertility LPI weight | RI 10% x DF 90% = about 9% | README | external | -- | externally sourced | FAIL -> corrected (was 13%) |
| Stature cm conversion | 152.65 cm, +1.35 cm/5pt (Holstein Apr 2025) | README | external | -- | externally sourced | PASS |
| Conformation h2 from 0.04 | Oliveira 2021 | README | external | -- | externally sourced | PASS |
| Timed AI / R=0.5 / re-ranking | not in Oliveira 2021 | README | external | -- | externally sourced | REMOVED |
| $63/daughter BMR | not a located cell | README | -- | -- | derived estimate | REMOVED |
| Log-rank / Cox fertility | exploratory, not headline | README | -- | -- | exploratory | kept only in "could not do" note |

## States used
PASS, FAIL (corrected this round), UNRESOLVED (none remain in README), REMOVED, EXTERNAL.
No "RESOLVED" state is used.

## Sample-size key
Sire-clustered size models and mediation: 666 (212 sires). Interaction: 603 (192 sires).
Stature quartiles / TOST: 387. PCA, k-means, balance, percentiles: 668. Inbreeding: 489.
