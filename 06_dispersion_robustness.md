# Robustness of the cross-subindex dispersion trend

The original notebook reported cross-subindex dispersion rising +3.6 points/year and
called it "specialization." Four specifications plus a leave-one-domain-out analysis were
run to test whether that label is justified.

## Four specifications (sire-clustered bootstrap 95% CI)

| Specification | Slope (pts/yr) | 95% CI | Robust? |
|---|---|---|---|
| 1. All six, equal weight | +3.62 | [+2.09, +5.03] | yes |
| 2. Excluding EI | +4.77 | [+3.52, +5.88] | yes |
| 3. Excluding EI and RI | +4.52 | [+2.99, +5.80] | yes |
| 4. Official LPI weights (PI 40, LTI 32, HWI 8, RI 10, MI 5, EI 5) | +4.47 | [+3.35, +5.42] | yes |

The trend **survives excluding EI** and **survives the official LPI weighting**, so by the
pre-set criterion it is not an EI artefact and not merely an equal-weighting artefact. If
anything, removing EI makes it slightly larger.

## Leave-one-domain-out (equal weight)

| Removed | Slope | Change vs baseline | CI |
|---|---|---|---|
| baseline (all six) | +3.62 | -- | [+2.09, +5.03] |
| drop PI | +4.16 | +0.53 | [+2.29, +5.94] |
| **drop L-TYPE** | **-0.12** | **-3.75** | **[-1.66, +1.42]** |
| drop HWI | +4.76 | +1.13 | [+3.14, +6.31] |
| drop RI | +3.62 | -0.00 | [+1.90, +5.27] |
| drop MI | +4.32 | +0.69 | [+2.63, +5.77] |
| drop EI | +4.77 | +1.15 | [+3.52, +5.88] |

**Removing L-TYPE collapses the trend to zero** (CI includes zero). No other domain does
this. Removing EI or RI leaves it intact.

## Mechanism

L-TYPE rose +23.9 points/year in cohort means (519 to 696), roughly four times faster than
any other subindex. Its mean absolute gap from each animal's own six-domain average grows
+13.0/year, versus +3.5 or less for every other domain. The rising dispersion is **L-TYPE
separating upward from the other five domains**, driven by strong type selection, not a
broad increase in profile unevenness and not the EI decline.

## Verdict against the four hypotheses

- **A (broad unevenness across multiple domains):** NO. It is concentrated in one domain.
- **B (mainly EI decline):** NO. Removing EI leaves the trend intact.
- **C (mainly EI + RI decline):** NO. Removing both leaves it intact.
- **D (equal-weighting artefact):** NO. It survives official LPI weighting.

The pattern is real and robust, but the precise description is:

> **increasing equal-domain dispersion, driven primarily by L-TYPE rising away from the
> other five domains.**

The word "specialization" is defensible only in the narrow sense that type merit is
pulling ahead of the rest; it is not broad-based specialization across many domains. The
notebook and README wording are updated accordingly.
