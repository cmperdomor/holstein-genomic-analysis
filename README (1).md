# Correction Log

Each row: file, section, previous text (abbreviated), corrected text (abbreviated), reason.

| File | Section | Before | After | Reason |
|---|---|---|---|---|
| README | Title | "668 Cows" | "668 Holstein Females" | 326 are GPA (genotyped heifers, no own records); productive state not assumable |
| README | Intro | "genomic breeding values; 138 variables, 8 birth-year cohorts" | "published genetic evaluations; 139 variables; export spans 2013-2026" | Not all genomic (GPA/GEBV/SMX PA/EBV/PA); real column count 139; span is 13 years, analyses filter 2018+ |
| README | Intro | "All values are genomic breeding values" | "published genetic evaluations; most genomic, other proof sources present" | Mixed proof sources, verified counts |
| README | Q1 producer | "Your breeding is working where you pushed hardest... quintupled... doubled" | "more recent cohorts carry higher predicted merit... strategy cannot be established" | Removed causal/promotional framing; ratio-scale over-interpretation |
| README | Q1 stats | "+20%, +144%, r2" as primary | absolute changes (573 pts, $951, 49 kg) primary, % secondary | EBV/index are not ratio scales; absolute change is the defensible interpretation |
| README | Q3 title | "Does Proof Source influence the observed relationships?" | "Does evaluation stage (GPA vs GEBV) modify the PROD-REPRO association?" | Scope was too broad; only GPA/GEBV tested |
| README | Q3 | "more/less reliable"; "do not differ significantly" | "evaluation stage"; "not distinguishable from zero; does not prove identical" | Proof source is not reliability; non-significance is not equivalence |
| README | Q4/Q5 | near-duplicate; "no natural types of cow" | Q4 = PCA dimensionality; Q5 = k-means separation; limited to specification | Differentiated the two; removed absolute "no types" claim |
| README | Q6 | "those few are also the most profitable" | "higher mean Pro$ evaluation than herd average" | Pro$ is predicted profitability, not observed profit; balance definition clarified |
| README | Q7 | "pedigree explains 47% of genomic variance" | "squared correlation about 0.47, substantial but incomplete" | Avoids treating one measure as dependent/gold standard |
| README | Q7 | "210 animals change classification" | "210 of 489 (43%) below 8% on pedigree but >=8% on genomic; 2 opposite" | Added denominator and exact direction (verified) |
| README | Q7 | "genomic costs nothing extra" | "already in export, no additional testing required" | Precise, non-promotional |
| README | Q8 ref | "notebooks 03 and 08" | "notebooks 03 and 06" | No notebook 08 exists |
| README | Q8 | "32 traits carry about 10 independent dimensions" | removed; reworded | No single located output supports the figure |
| README | Q8 | production VIF implies conformation redundancy | "demonstrates multicollinearity within production block, not conformation" | VIF was production-block, mis-applied to conformation |
| README | Body size | "SIZE"; "Bigger is not paying" | "within-herd composite body-size merit score"; neutral wording | Named construct; removed evaluative claim |
| README | Body size | size-BMR/ENVIRO/Pro$ as independent findings | flagged partly structural | BMR/ENVIRO/Pro$ share construction with size |
| README | Body size | sire clustering removes dependence | "reduces dependence from half-sib groups, not full structure" | Accurate scope of clustered SE |
| README | Rec 5 | "improves every evaluation the herd contributes to and receives"; Timed AI R=0.5 | "improves interpretation and data quality"; Timed AI removed | Oliveira 2021 does not contain Timed AI / R=0.5 / re-ranking |
| README | References | "Lynch et al. 2021: Timed AI" | removed | Not verifiable; Lynch is a co-author of Oliveira 2021, not a separate supporting source |
| README | References | stature 150.31 cm, 1.15 cm/5pt | 152.65 cm, 1.35 cm/5pt (Holstein, Apr 2025) | Corrected to actual Lactanet April 2025 table |
| AUDIT | sires | 213 | 212 (2 animals missing sire) | Verified unique count |
| AUDIT | $63 BMR | "quoted from Lactanet" | "derived estimate applying Lactanet ~$70/5pts to observed herd difference" | A published conversion is not a quoted figure |
| Notebooks 03-06 | markdown | causal/scope wording as above | matched to corrected README | Consistency; outputs unchanged (real data) |
| README | Limitations | "Every figure reports genomic breeding values" | "published genetic evaluations... PA/SMX PA/EBV also present" | Not all records genomic |
| README | Q1/Q2/Q5 titles | "genomic profile/traits" | "genetic evaluation profile / published genetic evaluations" | Mixed proof sources |
| README/AUDIT | sires | 212 / 668 with 2 missing | 2 no-sire animals EXCLUDED; n=666, 212 clusters, models re-run | Two animals are not half-sibs; must not share a "missing" cluster |
| README/AUDIT | dispersion CI | [+2.08,+4.99] vs [+2.32,+5.11] | single value approx [+2.32, +5.11], seed=42 | One reproducible figure |
| README/AUDIT | RI P10 CI | [-12.2,+6.5] vs [-12.6,+6.5] | single value approx [-12.7,+6.4], seed=42 | One reproducible figure |
| README | Rec 4 | "the herd is becoming more specialized" | "greater separation driven primarily by LTI; not necessarily intentional" | Matches leave-one-out result |
| README | Validation | "used throughout" | "used where relevant to the corresponding question" | Not every method in every analysis |
| README | Q6 heading | "Which cows show the most balanced genomic profile" | "Which females show the most balanced genetic-evaluation profile" | Terminology |
| README | Q4 producer | "each carry their own information" | "not strongly reducible to one or two components" | PCA shows non-reducibility, not full uniqueness |
