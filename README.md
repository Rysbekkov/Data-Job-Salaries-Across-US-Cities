# Data-Related Job Salaries Across U.S. Cities

A reproducible exploratory data analysis (EDA) project examining estimated salaries for data and analytical jobs across U.S. locations. I wrote the analysis in **R/Quarto**, using historical Glassdoor postings from the [Data Analyst Jobs dataset][dataset-kaggle]. The report summarizes overall salary estimates and differences across states through **2 tables**.

## What I did

I explored the original **2,253 job listings**, filtered postings using analyst/finance/economics/research keywords, extracted city and state, converted salary ranges into annual salary midpoints, and removed unusable records. This produced **564 selected postings across 119 distinct city names**. I then summarized overall salaries and compared the states with the most listings. The keyword rule is case-sensitive; these are historical *estimated* salaries, not confirmed offers or current market rates.

## Key findings

- **Overall pay:** Mean estimated annual salary **$71,416**; median **$68,500** (n = 564).
- **State comparison:** California’s mean is **$86,772** (n = 158); Texas’s is **$56,820** (n = 114).

## Project structure

The submitted project has this folder structure:

```text
Project/
├── Report.qmd           # R code + interpretation (reproducible source)
└── README.md            # This guide
```

The three project files are `Report.qmd`, `Report.html`, and `README.md`. The dataset is available [online on Kaggle][dataset-kaggle] and is not included in the repository. Download it separately if you want to re-render the report.

## Prerequisites

- [R (version 4.1 or newer)][r-project] — needed for the base R pipe `|>`.
- [Quarto][quarto-download] — renders `.qmd` documents to HTML.
- [RStudio / Posit IDE][rstudio-download] — optional, convenient way to edit and use **Render**.
- R packages: [tidyverse][tidyverse-docs], [janitor][janitor-docs], and [knitr][knitr-docs]. The `tidyverse` installation provides `dplyr`, `stringr`, `forcats`, `ggplot2`, and related packages used here.

Install the packages in R or RStudio:

```r
install.packages(c("tidyverse", "janitor", "knitr"))
```

## How to run

1. Download **[Data Analyst Jobs by andrewmvd][dataset-kaggle]** from Kaggle. Extract the file named **`DataAnalyst.csv`**.
2. For local rendering, place the downloaded CSV at **`Data 106/data/DataAnalyst.csv`** and the project files inside **`Data 106/Project/`**. Alternatively, place the CSV in a local `data/` folder next to `Report.qmd`. Neither dataset location is part of the submitted repository.
3. Open **`Report.qmd`** in RStudio and click **Render**. Alternatively, open a terminal in the `Project` folder and run:

   ```bash
   quarto render Report.qmd
   ```

4. Open **`Report.html`** in your browser. Re-rendering overwrites it with native Quarto output from your local dataset.

**HTML preview:** The included `Report.html` is an adapted static preview of the tables and figures in this version, using the provided finished report as its source. It was not rendered anew in R/Quarto. Render `Report.qmd` locally with the dataset to produce native Quarto output.

## Data and interpretation notes

Salaries are historical Glassdoor estimates. The method takes the first two numbers from each salary range (in thousands of dollars) and uses their midpoint. The dataset may contain inconsistent labels and locations. The analyses are descriptive, do not control for differences in seniority or cost of living, and do not establish causation.

## Sources and documentation

- [Data Analyst Jobs — Kaggle][dataset-kaggle] — Original job-posting dataset.
- [R Project][r-project] — Statistical programming language.
- [Quarto Guide][quarto-docs] — Quarto publishing and rendering documentation.
- [tidyverse][tidyverse-docs] — Data science tools for R.
- [dplyr][dplyr-docs] — Data manipulation.
- [stringr][stringr-docs] — Text handling.
- [ggplot2][ggplot2-docs] — Visualizations.
- [janitor][janitor-docs] — Column-name cleaning.
- [knitr][knitr-docs] — R reports and tables.

[dataset-kaggle]: https://www.kaggle.com/datasets/andrewmvd/data-analyst-jobs "Data Analyst Jobs — dataset by andrewmvd, Kaggle"
[r-project]: https://www.r-project.org/ "R project website"
[quarto-download]: https://quarto.org/docs/get-started/ "Install Quarto"
[quarto-docs]: https://quarto.org/docs/ "Quarto documentation"
[rstudio-download]: https://posit.co/download/rstudio-desktop/ "RStudio Desktop"
[tidyverse-docs]: https://www.tidyverse.org/ "tidyverse documentation"
[dplyr-docs]: https://dplyr.tidyverse.org/ "dplyr documentation"
[stringr-docs]: https://stringr.tidyverse.org/ "stringr documentation"
[ggplot2-docs]: https://ggplot2.tidyverse.org/ "ggplot2 documentation"
[janitor-docs]: https://sfirke.github.io/janitor/ "janitor package"
[knitr-docs]: https://yihui.org/knitr/ "knitr documentation"
