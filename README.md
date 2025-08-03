# Modeling Alzheimer’s Disease Trajectories Using Longitudinal ADAS-Cog13 Assessments

## Overview

This research investigates cognitive decline trajectories in Alzheimer’s Disease (AD) and Mild Cognitive Impairment (MCI) using the Alzheimer’s Disease Assessment Scale–Cognitive Subscale 13-item version (ADAS-Cog13). Understanding these patterns is critical for clinical monitoring, intervention planning, and trial design.

The study analyzed longitudinal ADAS-Cog13 data from the Alzheimer’s Disease Neuroimaging Initiative (ADNI) comprising 481 individuals (168 AD, 313 MCI) across 2,439 visits over a period of up to 138 months. Using mixed-effects modeling, time-series decomposition, and trajectory visualization, the analysis revealed that AD patients began with significantly greater cognitive impairment (mean ADAS-Cog13: 27.86 vs. 18.10, *p* < 0.001) and maintained higher impairment throughout follow-up.

The average progression rate was 0.252 points/month, with 79.4% of subjects showing cognitive worsening. Distinct cognitive trajectories were evident between AD and MCI, although progression rates were comparable. These results support the clinical and research utility of ADAS-Cog13 for monitoring cognitive decline and tailoring interventions by diagnostic group.

## Introduction

Alzheimer’s Disease and Mild Cognitive Impairment form a clinical continuum of cognitive dysfunction. Early and accurate tracking of cognitive performance is essential for diagnosis, prognosis, clinical trial design, and therapeutic intervention.

ADAS-Cog13 is a refined version of the original cognitive subscale, offering increased sensitivity across disease stages. Unlike cross-sectional assessments, longitudinal analysis captures within-person changes over time and helps identify early deviations from normative aging trajectories.

### Study Aims

- Characterize cognitive trajectories in AD and MCI populations  
- Quantify inter-individual variability in progression rates  
- Evaluate the feasibility of trajectory forecasting for clinical monitoring  

## Method

### Study Population

- Total participants: 481  
  - AD: 168  
  - MCI: 313  
- Age range: 55.2 to 90.9 years  
- Mean visits per participant: 5.07  
- Some follow-up durations > 10 years  

### Statistical Approach

- **Descriptive Statistics**: Group-wise comparisons at each time point  
- **Mixed-Effects Modeling**: Estimation of fixed and random effects  
- **Time-Series Analysis**: Decomposition of trends to isolate noise and long-term slope  
- **Trajectory Forecasting**: Visualizations of group-level and subject-specific trends  

### Mathematical Models

#### Individual-Level Model

$$
ADAS_{it} = \beta_{0i} + \beta_{1i} \cdot t + \varepsilon_{it}
$$

Where:  
- $\beta_{0i}$ : baseline cognitive score for patient $i$  
- $\beta_{1i}$: rate of cognitive change over time  
- $t$: time in months  
- $\varepsilon_{it}$: residual error

#### Mixed-Effects Model

$$
\beta_{0i} = \gamma_{00} + u_{0i}
$$

$$
\beta_{1i} = \gamma_{10} + u_{1i}
$$

Where:  
- $\gamma_{00}$, $\gamma_{10}$: fixed effects (population-level baseline and slope)  
- $u_{0i}$, $u_{1i}$: random effects for individual $i$

#### Forecasting Model

$$
\text{ADAS}_{t+k} = \beta_{0i} + \beta_{1i} \cdot (t + k \cdot \Delta t)
$$

Where:  
- $k$: number of future time steps  
- $\Delta t$: step size (e.g., 1 month)

## Results

### Baseline Cognitive Scores

- AD: 27.86 ± 8.06  
- MCI: 18.10 ± 6.64  
- Difference: 9.76 points (*p* < 0.001)

### Mixed-Effects Model Outputs

- Population Mean Baseline ($\gamma_{00}$): 21.21  
- Population Mean Slope ($\gamma_{10}$): 0.252 points/month  
- Individual Slope SD: 0.45 points/month  
- Range of slopes: ~ -0.65 to +1.15 points/month  
- 79.4% (382/481) showed cognitive decline  

### Group-Specific Trends

| Time (months) | AD Mean Score | MCI Mean Score |
|---------------|---------------|----------------|
| 0             | 27.86         | 18.10          |
| 6             | 29.56         | 20.39          |
| 12            | 31.68         | 19.84          |
| 24            | 35.87         | 22.81          |

### Time-Series Findings

- Aggregate population slope: -0.063 points/month  
- Suggests mild improvement likely due to survivor bias and dropout of severely impaired individuals  

### Individual Forecasting

**Patient ID: 002 S 0619 (slope = 0.337 points/month)**  
- Month 30: 42.43  
- Month 36: 44.35  
- Month 42: 46.28  

## Discussion

### Key Findings

- AD patients start with greater cognitive impairment  
- Cognitive trajectories diverge between AD and MCI  
- Wide range of progression rates among individuals  
- Personalized linear models can provide short-term forecasts  

### Clinical Implications

- AD patients may need more frequent monitoring  
- Stable/improving patients may benefit from tailored follow-ups  
- Natural history models support trial endpoint and sample size planning  

### Methodological Strengths

- Long-term, large-sample follow-up  
- Mixed-effects modeling for robust inference  
- Both individual-level and group-level analyses  
- Standardized cognitive measure (ADAS-Cog13)  

## Conclusion

ADAS-Cog13 effectively captures cognitive decline trajectories in AD and MCI populations. AD patients exhibit more severe and consistent impairment, while progression rates vary across individuals. These insights reinforce the need for longitudinal monitoring and support the utility of ADAS-Cog13 in both clinical and research contexts.
