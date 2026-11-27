# Urban evolution of cyanogenesis in white clover

*Study system: Evolution.*

**Provenance.** Simulated dataset built for BIOL 343 (Fall 2026), modelled on published studies of urban–rural clines in hydrogen cyanide (HCN) production by white clover (*Trifolium repens*). The values are not real measurements. Cite it in your report and presentation as: Colautti, R. I. (2026). *Simulated clover cyanogenesis survey dataset for the BIOL 343 Final Project.* Queen's University.

## The study

White clover is polymorphic for cyanogenesis: some plants release hydrogen cyanide (HCN) when their leaves are damaged, which deters herbivores, and others do not. The trait is controlled by two genes, and HCN-producing plants are thought to be at a disadvantage where winters are cold without insulating snow. In summer 2025, field crews in three cities sampled 20 plants from each of ten populations placed along a transect from the city centre to the countryside, and tested each plant for HCN. Each population's distance from the city centre and the percentage of impervious surface (pavement and buildings) around it were mapped, and each city's mean number of days with snow cover and January temperature were taken from climate records. Each city had its own field crew.

## Files

`data/plants.csv` — one row per plant.

| Column | Meaning |
|---|---|
| `plant_id` | unique plant identifier |
| `population` | population code (links to `populations.csv`) |
| `hcn` | result of the HCN test |

`data/populations.csv` — one row per population.

| Column | Meaning |
|---|---|
| `population` | population code |
| `city` | city (links to `cities.csv`) |
| `dist_city_centre_km` | distance from the city centre (km) |
| `impervious_pct` | percentage of impervious surface within 100 m |

`data/cities.csv` — one row per city.

| Column | Meaning |
|---|---|
| `city` | city |
| `snow_cover_days` | mean number of days per year with snow on the ground |
| `jan_mean_temp_C` | mean January air temperature (°C) |

## Questions

Explore the data, then design and run the analyses you need to answer these two questions. Justify every choice you make: how you cleaned and combined the files, which model you fitted and why, and how you checked it.

1. Does the frequency of HCN-producing clover increase with distance from the city centre?
2. Is the urban–rural pattern the same in all three cities, and is it better explained by distance from the city centre or by the amount of impervious surface?

# Outline:
1. Load packages and data (in presentation note hypotheses based on questions)
2. Wrangle/clean and combine data - check for missing values and duplicates, join datasets, other analysis prep
3. Visualize and summarize data - calculate cyanogenesis frequency per population, figure of cyanogenesis frequency vs. distance, figure of cyanogenesis frequency vs. impervious surface, visualize differences among cities, visualize correlation between environmental predictors
4. models/statistical analysis - choose model, answer Q1, Q2A does the urban–rural pattern differ among cities, Q2B is impervious surface a better predictor, compare models using AIC
5. model diagnostics - check residuals, check residuals against predictors, check random effects and convergence
6. visualize model predictions - figure of predicted cyanogenesis probability vs. distance, figure predicted cyanogenesis probability vs. impervious surface, visualize AIC model comparisons
7. Interperetations

# Divisions
1. Research questions, background and data: Import packages and datasets, inspect data structures, summarize study design and background literature.
2. Data cleaning and wrangling: Check missing values, duplicates, recode HCN, join datasets and prepare variables.
3. Exploratory data analysis: Calculate population frequencies, produce exploratory plots and examine predictor correlations.
4. Statistical modelling: Question 1: Fit null and distance models, perform likelihood ratio tests, calculate odds ratios and test the city interaction.
5. Statistical modelling: Question 2: Fit impervious surface models, compare models using AIC and examine collinearity.
6. Model diagnostics and conclusion: Check model assumptions, generate fitted prediction figures and synthesize results and limitations.

## Background reading

See `READING.md` (one paper about this study system).
