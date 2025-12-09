# Data Management and Analysis in R for Ecologists

This repository contains materials for the workshop **“Data Management and Analysis in R for Ecologists”**.  
The workshop walks through a complete workflow in R using a fictional ecological study of **nifflers** (from the Harry Potter universe):

- Importing and cleaning raw data  
- Joining multiple tables  
- Creating derived variables  
- Exploratory visualization with **ggplot2**  
- Fitting simple models and interpreting them in a biological context  

The workshop is organized as an RStudio Project and uses Git/GitHub for version control.

---

## Learning Goals

By the end of the workshop, participants should be able to:

- Set up and work within an **RStudio Project** for reproducible analysis  
- Use **tidyverse** tools (`dplyr`, `tidyr`, `stringr`, etc.) to:
  - Filter, select, arrange, and mutate data  
  - Group and summarize data  
  - Reshape data between long and wide formats  
  - Join multiple tables
- Create exploratory plots with **ggplot2** and refine them for communication  
- Fit simple linear models, interpret key parameters, and connect results back to ecological questions  

---

## Repository Structure

```text
.
├── Data/
│   ├── nifflers_capture.csv
│   ├── nifflers_treasure.csv
│   └── nifflers_recruitment.csv
├── Scripts/
│   ├── niffler_data_simulation.R
│   └── niffler_data_cleaning.R
├── DataAnalysis.Rmd
├── DataAnalysis.nb.html (optional, knitted output)
├── BiologyComputerWorkshop.Rproj
└── README.md
```
## Niffler Data Sets

All ecological examples in this workshop use a simulated study of **nifflers** (from the Harry Potter universe). The data are intentionally messy to reflect real-world ecological data challenges.

The workshop uses three data tables:

### 1. Capture data — `Data/nifflers_capture.csv`

One row per individual niffler.

**Variables:**
- `id` — unique niffler ID
- `capture_date` — date of first capture
- `sex` — `"F"` or `"M"`
- `age` — age at capture (years)
- `weight_g` — body mass at capture (grams)
- `site` — capture location (e.g., `"Gringotts"`, `"Hogsmeade"`)

---

### 2. Treasure data — `Data/nifflers_treasure.csv`

Multiple rows per individual, one per week of observation.

**Variables:**
- `id` — niffler ID
- `date` — week start date
- `treasure_g` — weekly treasure haul (grams)
- `site` — location during that week

---

### 3. Recruitment data — `Data/nifflers_recruitment.csv`

Annual breeding data for female nifflers only.

**Variables:**
- `id` — female niffler ID
- `year` — year
- `offspring` — number of offspring produced that year

---

Participants import, clean, and join these tables to create analysis-ready data sets for exploring relationships between body size, treasure acquisition, and recruitment.

---

## Software Requirements

- **R** (version 4.0 or newer recommended)
- **RStudio** (for working with projects and R Markdown notebooks)

### R packages used

- `tidyverse`
- `nycflights13`
- `PerformanceAnalytics`
- `rmarkdown` / `knitr`

Install packages (once) from the R console if needed:

```r
install.packages(c(
  "tidyverse",
  "nycflights13",
  "lubridate",
  "PerformanceAnalytics"
))
```
## Getting Started

1. Clone the repository from GitHub:
```bash
git clone https://github.com/akeever2/BiologyComputerWorkshop.git
```
2. Open the R Project
  - Double-click the `.Rproj` file or open it from RStudio (`File → Open Project`).
3. Open the workshop notebook
  - Open DataAnalysis.Rmd in RStudio.
4. Run the code chunks in order
  - Use **“Run”** or **Ctrl/Cmd + Shift + Enter** to run chunks.
  - Follow the prompts and Your tasks sections to complete exercises.

## Workshop Flow (High Level)

1. R Projects & Reproducibility
  - Working directories, scripts vs. console, raw vs. cleaned data
2. Tidyverse Refresher (using `mpg` and `nycflights13`)
  - `filter()`, `select()`, `mutate()`, `summarise()`, `group_by()`
  - Joins (`left_join()`), reshaping (`pivot_longer()`, `pivot_wider()`), and string handling
3. Niffler Study Workflow
  - Import, inspect, and clean capture, treasure, and recruitment data
  - Join tables to create analysis-ready data sets
  - Compute yearly summaries (e.g., mean treasure per ID per year)
4. Exploratory Visualization
  - Build `ggplot2` graphics layer by layer
  - Explore relationships between body weight, sex, site, and treasure haul
  - Visualize recruitment and potential predictors
5. Simple Modeling
  - Fit linear models (e.g., treasure ~ weight + sex + month + site)
  - Interpret coefficients in a biological context
  - Optional: refine model (outliers, age effects, quadratic terms, random effects as a bonus extension)

## Workshop Philosophy

The goal of this workshop is **not** to find the “best” statistical model, but to demonstrate a **reproducible, transferable workflow** for ecological data analysis:
1. Import and clean raw data
2. Join and transform tables into usable formats
3. Explore patterns visually
4. Fit simple, transparent models
5. Communicate results clearly

These skills form a foundation that can be extended to more complex analyses in applied ecological research.

## Acknowledgments

This workshop was developed for ecology students and researchers learning reproducible data workflows in R, with a bit of magical flavor courtesy of nifflers 🦡💰.
