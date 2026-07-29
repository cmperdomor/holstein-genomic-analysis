# Correction Log

This round applied fourteen corrections. Every notebook change below was made in code or
markdown and the notebook was re-executed on the real dataset; the executed outputs match
the text. Nothing here claims a change that is not present in the delivered files.

| # | File | Location | Before | After | Reason |
|---|---|---|---|---|---|
| 1 | README, AUDIT | Q8 | "Are the six subindexes reducible, and how redundant are the conformation traits? (notebooks 03 and 06)" plus conformation-redundancy claims | "Which apparent trait associations are structurally redundant? (notebook 03)"; conformation removed; points only to production-block VIF | VIF 961 is production-block (Milk/Fat/Prot/%Fat/%Prot), not conformation; no conformation-redundancy analysis exists; subindex PCA is in nb05 (Q4), not nb06 |
| 2 | README, refs, CONSISTENCY | fertility weight | "about 13% weight within LPI"; marked PASS | "Reproduction Index 10%, Daughter Fertility 90% of it, about 9% of total direct LPI weighting"; row marked FAIL-corrected | 13% is the pre-modernization LPI (Oliveira 2021); project uses the modernized April 2025 subindexes |
| 3 | nb04 (c4), README | inbreeding discordance | only 210 computed; README said "210 change classification" | added cell computing 210 + 2 = 212; README says "212 of 489 discordant (210 one direction, 2 the other)" | 210 is one direction only; total discordant is 212 |
| 4 | README | body-size clustered result | "HL p=1.4e-17, , Pro$ coefficient -463.78" (double comma, BMR missing) | "Herd Life -2.40 p=1.4e-17; Body Maintenance -3.09 p=4.5e-34; Pro$ -463.78 p=5.9e-19" | broken edit; all three coefficients now shown |
| 5 | nb05 (c8), README | SIZE sensitivity | "holds under each single trait except Chest Width" (only CW tested singly) | added Stature-only, Body Depth-only, HFE-only cells; claim now backed (all negative significant; CW null) | claim required each single trait; three were missing |
| 6 | nb05 (c2, c4) | TOST wording | "added during review, not exploratory"; "stricter exploratory margin" | "added during review and not preregistered"; "stricter margin" | self-contradiction; analysis is exploratory but not preregistered |
| 7 | nb05 (c4) | interaction sire handling | SireID cast before dropna (kept "nan" cluster) | build SireID after dropna on Sire Reg Number | "nan" string survived dropna, creating a false cluster |
| 8 | nb05 (c4 md) | interaction text | "not all four categories"; "joint F-test"; "subgroups do not differ" | "five categories"; F-test mention removed; "no statistically distinguishable difference detected" | five proof sources exist; no F-test is run; non-significance is not equivalence |
| 9 | nb05 (c3, c7), README | dependence language | "not an artefact of pseudo-replication across half-sib families" | "reduce, but do not eliminate, dependence and confounding from family and cohort structure" | sire clustering does not remove maternal, sire-sire, or full genomic relationships |
| 10 | nb03 (c3), AUDIT | mediation | "BMR as the mediator is ruled out"; "association is real" | "no statistically detectable indirect effect through BMR; indirect effect opposite in sign, CI included zero" | CI includes zero; cannot rule out mediation definitively |
| 11 | README, refs | Pro$ | "body size enters Pro$ through maintenance cost; estimate rebuilt from BMR conversion"; $63 figure | "may partly reflect economic relationships but the unpublished Pro$ formula prevents determining how much is structural"; $63 removed | Pro$ formula unpublished; $63 not a located cell |
| 12 | nb06 (c5, c6, c7) | bootstrap | RI bootstrap used n>=20 while descriptive used n>=30; reps 1500 vs 2000; cohort set varied per replicate | eligible cohorts fixed once at n>=30, same set in observed and every replicate; reps unified to 2000 | estimand must not change between replicates; seed alone did not fix this |
| 13 | nb04 (title, c2 md) | notebook 04 | title "Genomic Trends"; "Mean genomic merit rose"; r2=0.95 in text | "Published Genetic Evaluation Patterns Across Birth Cohorts"; "published genetic evaluations"; r2 removed from text | PA/EBV/SMX PA are not genomic; r2 no longer printed |
| 14 | CONSISTENCY, CORRECTION_LOG, FINAL_SUMMARY | audit docs | claimed corrections not present; 13% marked PASS; Q8 marked done; used "RESOLVED" | rebuilt from scratch against executed outputs with real cell indices and PASS/FAIL/UNRESOLVED/REMOVED only | audit documents must reflect the delivered files |

## Note on the dispersion slope value
Fixing the bootstrap cohort set (point 12) changed the dispersion slope from the earlier
+3.70/yr (which mixed n>=20 and n>=30) to +4.61/yr, CI [+3.07,+5.99]. The conclusion is
unchanged (slope excludes zero; removing L-TYPE collapses it to +0.21 with CI including
zero). All documents now use +4.61 and the matching CIs.
