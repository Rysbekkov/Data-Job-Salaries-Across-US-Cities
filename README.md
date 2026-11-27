# Data-Related Job Salaries Across U.S. Cities

A reproducible exploratory data analysis (EDA) project that studies estimated salaries for data and analytical jobs across U.S. cities. I wrote the analysis in **R/Quarto**, using historical Glassdoor postings from the [Data Analyst Jobs dataset][dataset-kaggle]. The report compares salary distributions, posting counts, job titles, and company ratings through **4 tables and 6 figures**.

## What I did

Before creating the final report, I explored the original **2,253 job listings** and the available fields to identify useful information. I filtered postings using analyst/finance/economics/research keywords, removed irrelevant fields and records without usable salary or city information, extracted city and state, calculated an annual salary midpoint from each salary range, and excluded invalid ratings from rating-specific figures. This produced **564 selected postings across 119 distinct city names**. I then summarized and visualized salary patterns by location, job title, and company rating. The keyword rule is case-sensitive; these are historical *estimated* salaries, not confirmed offers or current market rates.

## Key findings

- **Overall pay:** Mean estimated annual salary **$71,416**; median **$68,500** (n = 564).
- **Posting concentration:** New York has the most selected postings among cities (**94**). The fifteen busiest cities differ in both posting volume and pay.
- **City comparison:** Among those busy cities, San Francisco's mean estimate is **$99,980** across **25** postings, compared with **$70,410** in New York. These differences do not adjust for job level or cost of living.
- **State comparison:** California's mean is **$86,772** (n = 158); Texas's is **$56,820** (n = 114).
- **Ratings and pay:** The observed Pearson correlation is about **0.11** among **496** postings with valid ratings, indicating only a weak linear association.

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

**HTML preview:** The supplied `Report.html` contains tables and figures rebuilt from the uploaded `DataAnalyst.csv` using the QMD's documented analysis rules. Because R and Quarto were not available in the file-building environment, this included HTML was assembled as a standalone, Quarto-styled report rather than produced by executing the `.qmd` in R. The `.qmd` is the reproducible source to use when rendering locally.

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
