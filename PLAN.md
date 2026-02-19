# Analysis of Ascombe data

## Goal

Analyze data set and visualize it, and see what we want to do next with it.

## Implication

- Obtain and analyze data from anscombe_quartet.tsv
- First, look at the data and generate descriptive statistics.
- Second, create a Jupyter Light notebook in which you will generate plots.
- Propose the types of plots that you would like to generate.
- Save this proposal to the end of this file and let me look at it.
- I will need to approve this plan and tell you to go ahead before we actually do anything. Plase append te plan to the end of this file.

---

## Descriptive Statistics

All four datasets share nearly identical summary statistics — this is the defining property of Anscombe's Quartet.

| Dataset | var | n  | mean   | stdev  | min   | max   | median |
|---------|-----|----|--------|--------|-------|-------|--------|
| I       | x   | 11 | 9.0000 | 3.3166 | 4.00  | 14.00 | 9.0000 |
| I       | y   | 11 | 7.5009 | 2.0316 | 4.26  | 10.84 | 7.5800 |
| II      | x   | 11 | 9.0000 | 3.3166 | 4.00  | 14.00 | 9.0000 |
| II      | y   | 11 | 7.5009 | 2.0317 | 3.10  | 9.26  | 8.1400 |
| III     | x   | 11 | 9.0000 | 3.3166 | 4.00  | 14.00 | 9.0000 |
| III     | y   | 11 | 7.5000 | 2.0304 | 5.39  | 12.74 | 7.1100 |
| IV      | x   | 11 | 9.0000 | 3.3166 | 8.00  | 19.00 | 8.0000 |
| IV      | y   | 11 | 7.5009 | 2.0306 | 5.25  | 12.50 | 7.0400 |

OLS regression line (virtually identical across all four):

| Dataset | Intercept | Slope  | Pearson r |
|---------|-----------|--------|-----------|
| I       | 3.0001    | 0.5001 | 0.8164    |
| II      | 3.0009    | 0.5000 | 0.8162    |
| III     | 3.0025    | 0.4997 | 0.8163    |
| IV      | 3.0017    | 0.4999 | 0.8165    |

---

## Proposed Plots

### Plot 1 — 2×2 Scatter Plot Grid with Regression Lines (canonical)
**Rationale:** The classic Anscombe's Quartet visualization. Each subplot shows one dataset's (x, y) scatter points overlaid with the fitted OLS regression line. Despite identical summary statistics, the structural differences become immediately apparent:
- Dataset I: roughly linear with random scatter
- Dataset II: a clear curve (quadratic relationship)
- Dataset III: a perfect line with one high-leverage outlier
- Dataset IV: a vertical cluster at x=8 with a single outlier at x=19

### Plot 2 — Box Plots of y per Dataset
**Rationale:** Side-by-side box plots of the y variable across all four datasets. Highlights distributional differences (spread, skew, outliers) that are hidden in the equal means and standard deviations. Useful to show that equal variance does not imply similar distribution shape.

### Plot 3 — Residual Plots (residuals vs. fitted values)
**Rationale:** After fitting the OLS line to each dataset, plot residuals against fitted values in a 2×2 grid. Residual structure directly reveals model adequacy:
- Dataset I: random scatter (good fit)
- Dataset II: systematic curve (quadratic pattern missed)
- Dataset III: one extreme residual (influential outlier)
- Dataset IV: all residuals at one x-value except one (near-degenerate x)

## Interation 1

- go ahead and execute your plan.
- save it all in a Jupyter Notebook that I can start in this VS Code instance.
- explain to me how to start a Jupyter Notebook so I can validate your results.

## Interation 2

- Make the first plot blue-themed, the second plot purple-themed, the third plot green-themed.
- Make the fit line a black, dash line. 