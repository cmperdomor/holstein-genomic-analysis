# Notebook 06 - Technical Statistical Interpretation

**Design.** Cross-sectional distribution analysis of predicted genetic merit by birth-year
cohort in surviving animals, single evaluation date. Not a modelled genetic trend.

**Distribution shift (Part 3).** Percentile regressions (P10/P50/P90 on birth year,
cohorts n>=30) show LPI rising uniformly with the lower tail steeper than the upper
(P10 +83.5 vs P90 +58.1 /yr): compression upward, tail catching up. RI and EI show uniform
negative slopes across all three percentiles, indicating whole-distribution decline rather
than upper-tail-only stagnation.

**Variance change (Part 4).** Brown-Forsythe (median-centred Levene) per subindex across
cohorts, Benjamini-Hochberg FDR over the six-subindex family. RI raw p=0.038 but FDR=0.21;
no subindex survives. Conclusion: dispersion differed across cohorts in the surviving
population but not beyond chance under multiple testing.

**Lower tail (Part 5).** EI P10 = 384 is the deepest and most persistent weak tail. The RI
P10 negative point-slope does not survive sire-clustered bootstrap (95% CI [-12.2, +6.5]),
so the RI lower-tail decline is not statistically robust to family structure.

**Cross-subindex dispersion (Part 6).** Within-animal SD across the six subindexes rises
+3.6/yr; sire-clustered bootstrap 95% CI [+2.08, +4.99] excludes zero. This is the most
robust dispersion finding in the notebook: recent animals are more specialized across
domains. Independent of the mean-level PCA/clustering results in notebook 05.

**Non-independence** handled by resampling sire families in all bootstrap CIs.
Confounding by cohort composition and survivorship is not removed and is stated as a
limitation.
