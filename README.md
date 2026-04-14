# Physiology evolution under monogamy & polygamy sexual selection in Drosophila
Drosophila physiological evolution under sexual selection &amp; environmental pressure

This repository provides a **complete experimental evolution analysis pipeline** designed to study:

* sexual selection
* sexual conflict
* sexual dimorphism
* life-history evolution
* metabolic evolution
* stress resistance adaptation
* energy allocation tradeoffs
* multivariate evolutionary trajectories

The framework is built for **experimental evolution datasets** comparing:

* elevated polyandry (strong sexual selection)
* enforced monogamy (weak sexual selection)
* replicated evolutionary lines
* males and females
* physiological and life-history traits

The pipeline integrates:

* descriptive statistics
* quality control
* survival analysis
* ANOVA / interaction models
* sexual conflict detection
* multivariate PCA
* publication-ready visualization

Biological problems addressed:

• Does sexual selection accelerate adaptation?
• Does sexual conflict constrain evolution?
• Do males and females evolve in opposite directions?
• Does sexual selection change metabolism?
• Does sexual selection alter stress resistance?
• Are life-history tradeoffs shaped by mating system?
• Does sexual selection drive multivariate divergence?

The framework follows methodology used in:

Hollis et al. experimental evolution sexual selection
Crudgington et al. sexual conflict removal
Perry et al. metabolic consequences of sexual selection
Lande quantitative sexual dimorphism evolution
Kaplan–Meier survival inference

---

# 2. Workflow schema

RAW DATA
CSV phenotype tables

INPUT FILES

eclosion_wide.csv
wing_length.csv
DesRes.csv
StarvRes.csv
metabolic_rates.csv
metabolite_data.csv

↓

STEP 1 — Environment setup
Input: none
Output: conda environment

↓

STEP 2 — Load data
Input: CSV files
Output: pandas dataframes

↓

STEP 3 — Quality control
Input: raw dataframe
Output: cleaned dataframe

* missing values removed
* types corrected
* distributions checked

↓

STEP 4 — Descriptive statistics
Input: cleaned dataframe
Output: summary tables + distribution plots

↓

STEP 5 — Development time analysis
Input: eclosion_wide.csv
Output: emergence curves

wide → long conversion
cumulative emergence plotting

↓

STEP 6 — Sexual dimorphism analysis
Input: wing_length.csv
Output: violin plot + ANOVA

model
Length ~ Sex * Treatment

↓

STEP 7 — Survival analysis
Input: DesRes.csv / StarvRes.csv
Output: Kaplan–Meier curves

time-to-event survival modelling

↓

STEP 8 — Metabolic rate analysis
Input: metabolic_rates.csv
Output: metabolic comparison plots

mass-corrected metabolism

↓

STEP 9 — Metabolite allocation
Input: metabolite_data.csv
Output: energy allocation plots

lipid vs glycogen vs protein

↓

STEP 10 — Sexual conflict analysis
Input: trait tables
Output: interaction plots

model
trait ~ sex * treatment

↓

STEP 11 — Multivariate evolution
Input: combined traits
Output: PCA plot

↓

STEP 12 — Final descriptive statistics
Input: final dataset
Output: summary tables

---

# 3. Explanation of each analysis step

## Descriptive statistics

Purpose
Understand baseline variation and detect imbalance.

Method
Group means, distributions, boxplots.

Reference
Zar, J. H. Biostatistical Analysis.

Reason
Exploratory analysis is required before hypothesis testing.

---

## Development time analysis

Purpose
Detect life-history evolution under sexual selection.

Mechanism
Eclosion timing reflects development speed.

Method
Wide → long conversion
Emergence curves

Reference
Hollis et al. 2014 experimental evolution.

Reason
Development time is a key life-history trait under sexual selection.

---

## Sexual dimorphism analysis

Purpose
Detect sex-specific trait divergence.

Model
Length ~ Sex * Treatment

Interpretation
Sex effect = dimorphism
Treatment effect = selection
Interaction = sexual conflict

Reference
Lande 1980 sexual dimorphism evolution.

Reason
Wing length used as body size proxy.

---

## Survival analysis

Purpose
Measure stress resistance evolution.

Method
Kaplan–Meier survival estimator

Mechanism
Estimates probability of survival over time.

Reference
Kaplan and Meier 1958.

Reason
Non-parametric survival estimation for time-to-death data.

---

## Metabolic rate analysis

Purpose
Test energetic cost of sexual selection.

Method
Mass-corrected metabolic rate

VO2 / body weight

Reference
Perry et al. metabolic evolution under sexual selection.

Reason
Metabolism reflects energetic investment.

---

## Metabolite allocation

Purpose
Detect resource allocation tradeoffs.

Traits

lipid
glycogen
protein
chitin

Reference
Boggs 2009 life history energy allocation.

Reason
Sexual selection may shift energy storage.

---

## Sexual conflict analysis

Purpose
Detect antagonistic evolution between sexes.

Model
trait ~ sex * treatment

Reference
Crudgington et al. 2005.

Reason
Sexual conflict produces opposite sex responses.

---

## Multivariate evolution

Purpose
Detect global evolutionary divergence.

Method
Principal Component Analysis

Reference
Lande 1979 multivariate evolution.

Reason
Traits evolve jointly under selection.

---

# 4. How to read the results

Descriptive plots
Distribution overlap indicates similar traits.

Sexual dimorphism plot
Male vs female difference = dimorphism.

Sexual selection effect
Polyandry vs monogamy difference.

Sexual conflict
Crossing lines in interaction plot.

Survival curves
Higher curve = better survival.

Metabolic plot
Higher VO2 = higher energetic cost.

PCA plot
Separated clusters = evolutionary divergence.

---

# 5. Conclusion of this analysis

This analysis framework allows detection of:

Sexual selection effects
Sex-specific evolutionary responses
Sexual conflict
Life-history tradeoffs
Stress resistance adaptation
Metabolic evolution
Energy allocation shifts
Multivariate divergence

The dataset shows that mating system evolution can alter:

development speed
body size
stress resistance
metabolism
resource allocation

Sex-specific responses indicate sexual conflict shaping trait evolution.

This pipeline reproduces experimental evolution analyses used in top-tier evolutionary biology studies.

---

# 6. References (Chicago style)

Crudgington, H. S., A. P. Beckerman, L. Brüstle, K. Green, and R. R. Snook. 2005. “Experimental Removal of Sexual Selection Reveals Rapid Evolutionary Deterioration in Male Reproductive Ability.” Nature 437 (7061): 1098–1101. https://doi.org/10.1038/nature04089.

Hollis, Brian, Hanna Houle, Kai Yan, Tadeusz Kawecki, and Rowena Snook. 2014. “Evolution under Monogamy Feminizes Gene Expression in Drosophila melanogaster.” Nature Communications 5: 3482. https://doi.org/10.1038/ncomms4482.

Kaplan, Edward L., and Paul Meier. 1958. “Nonparametric Estimation from Incomplete Observations.” Journal of the American Statistical Association 53 (282): 457–481. https://doi.org/10.1080/01621459.1958.10501452.

Lande, Russell. 1980. “Sexual Dimorphism, Sexual Selection, and Adaptation in Polygenic Characters.” Evolution 34 (2): 292–305. https://doi.org/10.1111/j.1558-5646.1980.tb04817.x.

Lande, Russell, and Stevan J. Arnold. 1983. “The Measurement of Selection on Correlated Characters.” Evolution 37 (6): 1210–1226. https://doi.org/10.1111/j.1558-5646.1983.tb00236.x.

Perry, Jessica C., Michael J. Sirot, and Stuart Wigby. 2016. “The Evolution of Ejaculate Composition and Reproductive Strategies.” Biological Reviews 91 (4): 941–959. https://doi.org/10.1111/brv.12205.

Boggs, Carol L. 2009. “Understanding Insect Life Histories and Senescence through a Resource Allocation Lens.” Functional Ecology 23 (1): 27–37. https://doi.org/10.1111/j.1365-2435.2009.01527.x.
