# COVID-19 Vaccine Uptake Experiment

This project simulates and analyzes the results of a randomized field experiment testing the effectiveness of Facebook ad campaigns on COVID-19 vaccine uptake. The experiment includes two treatment groups (Reason-based ads and Emotion-based ads) and a control group.

------------------------------------------------------------------------

## 📋 Overview

The goal is to assess whether different ad strategies can influence participants' decisions to take the COVID-19 vaccine. Participants were randomly assigned into three groups and surveyed at baseline and endline.

**Total Participants:** 5,000

**Treatment Assignment:**
-   Reason Group (1/3)
-   Emotion Group (1/3)
-   Control Group (1/3)

**Endline Participation:** 4,500 participants (10% dropout)

------------------------------------------------------------------------

## 📁 Files

-   `vaccine_uptake_simulation.qmd`: Quarto file containing all code, visualizations, and report content.
-   `README.md`: This documentation file.
-   `data/`: Folder containing simulated datasets (`baseline.csv`, `treatment.csv`, `endline.csv, cleaned_dataset.csv`).
-   `plot/`: Folder containing plots generated.
-   `table/`: Folder containing tables generated.

------------------------------------------------------------------------

## ⚙️ How to Run

1.  Open the `vaccine_uptake_simulation.qmd` file in [RStudio](https://posit.co/download/rstudio-desktop/).
2.  Make sure all required libraries are installed (see below).
3.  Click **Render** to generate a Word, PDF, or HTML report.
4.  Alternatively, use the terminal or console: \`\`\`r quarto::quarto_render("vaccine_uptake_simulation.qmd")

------------------------------------------------------------------------

## 📦 Dependencies

Make sure the following R packages are installed

```{r}
install.packages(c(
  "tidyverse", 
  "janitor", 
  "broom", 
  "ggplot2", 
  "kableExtra", 
  "knitr", 
  "tidyr"
))
```

------------------------------------------------------------------------

## 🧠 Methodology

1.  **Baseline Simulation**

-   5,000 participants with demographics (age, gender, education level, income bracket, country).

-   Survey questions include trust in vaccines and concern about side effects (1–5 scale).

2.  **Treatment Assignment**

-   Participants randomly assigned into "Reason", "Emotion", or "Control" groups.

3.  **Endline Simulation**

-   4,500 participants retained.

-   Vaccine uptake is simulated based on:

    -   Ad group effect

    -   Trust and concern levels

    -   Country effect (e.g., lower uptake in Nigeria, India, Brazil)

4.  **Outcome Modeling**

Probability of vaccine uptake (final_prob) is calculated using:

```{r}
base_prob + ad_effect + country_effect
```

Uptake simulated using `rbinom()`.

5.  **Analysis**

-   Summary tables.

-   Visualizations.
