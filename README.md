# ipums-cps-viz
Average earnings by education using IPUMS CPS data
# Average Earnings by Education in the United States using IPUMS CPS data

This project uses IPUMS CPS microdata to show how average annual wage and salary income differs across education levels for U.S. wage earners ages 25–64. It covers the full pipeline: building an IPUMS extract, cleaning and visualizing it in R, and publishing a reproducible R Markdown document on GitHub.

**[View the rendered analysis](ipums-viz-starter.md)**

## Key finding

Average wage income rises at every education level, from about $46,000 for workers without a high school diploma to about $135,000 for workers with a graduate degree. This is a descriptive association, not the causal effect of education on earnings (see the interpretation in the rendered document).

## Data and methods

- **Source:** IPUMS CPS, 2026 Annual Social and Economic Supplement (ASEC); income refers to calendar year 2025
- **Variables:** AGE, SEX, EDUC, INCWAGE, and the person weight ASECWT
- **Sample:** adults ages 25–64 with positive wage and salary income; not-in-universe and missing values removed
- **Education groups:** EDUC recoded to the CPS coding scheme into five categories (less than high school, high school diploma, some college or associate degree, bachelor's degree, graduate degree)
- **Estimates:** averages weighted with ASECWT
- **Tools:** R with `ipumsr`, `tidyverse`, and `scales`

## Repository contents

| File | Description |
|---|---|
| `ipums-viz-starter.Rmd` | R Markdown source code and text |
| `ipums-viz-starter.md` | Rendered document displayed by GitHub |
| `ipums-viz-starter_files/` | Chart images used by the rendered document |
| `.gitignore` | Keeps IPUMS data files out of the repository |

## How to reproduce

The raw data is not included, because IPUMS terms of use do not allow redistribution. To reproduce the analysis:

1. Register for a free account at [cps.ipums.org](https://cps.ipums.org).
2. Create an extract with the most recent ASEC sample and the variables AGE, SEX, EDUC, and INCWAGE (cross-sectional, rectangular, fixed-width format).
3. Download the `.dat.gz` data file and the DDI `.xml` codebook into a `data/` folder next to the `.Rmd` file.
4. If your extract number differs, update the file name in the `load` chunk (for example, `data/cps_00001.xml`).
5. Install the packages: `install.packages(c("ipumsr", "tidyverse", "scales"))`
6. Open `ipums-viz-starter.Rmd` in RStudio and click **Knit**.

## Citation

Sarah Flood, Miriam King, Renae Rodgers, Steven Ruggles, J. Robert Warren, Daniel Backman, Etienne Breton, Grace Cooper, Julia A. Rivera Drew, Stephanie Richards, David Van Riper, and Kari C.W. Williams. IPUMS CPS: Version 13.0 [dataset]. Minneapolis, MN: IPUMS, 2025. https://doi.org/10.18128/D030.V13.0

## Author

[Your Name] — MSBA, University of Louisville
