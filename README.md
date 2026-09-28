# Blog Post 3: Education as a Buffer Against Joblessness

This repository contains the reproducible analysis for Blog Post 3 in AEDS 6400. It uses IPUMS Current Population Survey monthly basic microdata and the person-level final weight (`WTFINL`) to examine how unemployment and employment outcomes differ by education among adults ages 25–64.

Published article: <https://haozhuo22.github.io/myweb/blog/posts/post3/>

## Research design

- Samples: May basic monthly CPS, 2000–2025
- Population: civilian adults ages 25–64 represented by the selected CPS samples
- Variables: `YEAR`, `MONTH`, `AGE`, `EDUC`, `EMPSTAT`, and `WTFINL`
- Weight: `WTFINL`
- Education groups: less than high school, high school, some college/associate, and bachelor's degree or higher

The project produces three connected visualizations:

1. Weighted unemployment rates by education over time.
2. Changes during the Great Recession and COVID-19 labor-market shock.
3. Weighted employment-status composition by education in 2025.

`R/01_analysis.R` performs the complete cleaning, weighting, aggregation, and plotting workflow. Releasable weighted aggregate tables are stored in `derived/`; publication-ready charts are stored in `figures/`. `index.qmd` contains the article and can be rendered in RStudio after the licensed raw extract is placed in `data/`.

## Data access

IPUMS CPS microdata require a free IPUMS account and acceptance of the IPUMS terms of use. The raw extract is intentionally excluded from Git. To reproduce the analysis, create an IPUMS CPS extract with the samples and variables listed above, then place the downloaded `.dat.gz` file and its DDI `.xml` file in `data/`.

## Reproduce

```r
install.packages(c("ipumsr", "dplyr", "tidyr", "ggplot2", "readr", "scales", "haven"))
source("R/01_analysis.R")
```

Then render `index.qmd` in RStudio or run:

```bash
quarto render index.qmd
```

Raw IPUMS microdata are not redistributed in this repository. The repository contains only code, documentation, weighted aggregate results, and exported figures.

## Citation

Sarah Flood, Miriam King, Renae Rodgers, Steven Ruggles, J. Robert Warren, Daniel Backman, Etienne Breton, Grace Cooper, Julia A. Rivera Drew, Stephanie Richards, David Van Riper, and Kari C.W. Williams. *IPUMS CPS: Version 13.0* [dataset]. Minneapolis, MN: IPUMS, 2025. <https://doi.org/10.18128/D030.V13.0>.
