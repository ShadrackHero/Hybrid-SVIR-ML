# Hybrid SVIR–Machine Learning for COVID-19 Forecasting

Hybrid forecasting approach that couples a mechanistic SVIR compartmental model  
(S = Susceptible, V = Vaccinated, I = Infectious, I_c = Confirmed Infectious, R = Recovered)  
with machine-learning methods. Focus is on daily COVID-19 cases merged with vaccination data.

## Project overview
Daily COVID-19 case data are cleaned, aligned, and merged with vaccination coverage (and optionally other public sources).  
A deterministic SVIR model is implemented and simulated in Python. Machine learning will later be used for parameter estimation, residual correction, or learning time-varying transmission rates.  
The goal is improved short-term forecasts of daily cases that explicitly account for vaccination.

## Repository structure
```
data/
  raw/          # original downloaded files
  processed/    # cleaned and merged datasets
notebooks/      # data cleaning, exploration, model runs
latex/          # model equations and written description
docs/           # data sources, notes, interpretation
```

## SVIR model equations

The full system of nonlinear ordinary differential equations is:

$$
\begin{aligned}
\frac{dS}{dt} &= \pi + \sigma V - \lambda S - \omega S - \mu S, \\
\frac{dV}{dt} &= \omega S - (1 - \epsilon)\lambda V - \sigma V - \mu V, \\
\frac{dI}{dt} &= \lambda S + (1 - \epsilon)\lambda V - (\mu + \gamma + \rho_1 + \delta)I, \\
\frac{dI_c}{dt} &= \gamma I - (\mu + \rho_2 + \delta)I_c, \\
\frac{dR}{dt} &= \rho_1 I + \rho_2 I_c - \mu R.
\end{aligned}
$$

**Initial conditions:**

$$
\begin{aligned}
S(0) &= S_0 > 0, &
V(0) &= V_0 \geq 0, &
I(0) &= I_0 \geq 0, \\
I_c(0) &= I_{c,0} \geq 0, &
R(0) &= R_0 \geq 0.
\end{aligned}
$$

**Parameters**

| Parameter | Description | Units |
|-----------|-------------|-------|
| $\pi$ | Recruitment (birth) rate into $S$ | individuals·day$^{-1}$ |
| $\mu$ | Natural death rate | day$^{-1}$ |
| $\omega$ | Vaccination rate ($S\to V$) | day$^{-1}$ |
| $\sigma$ | Waning rate of vaccine immunity ($V\to S$) | day$^{-1}$ |
| $\epsilon$ | Vaccine efficacy against infection | dimensionless |
| $\gamma$ | Detection rate ($I\to I_c$) | day$^{-1}$ |
| $\rho_1$ | Recovery rate of undetected infectious individuals | day$^{-1}$ |
| $\rho_2$ | Recovery rate of confirmed infectious individuals | day$^{-1}$ |
| $\delta$ | Disease-induced death rate of $I$ and $I_c$ | day$^{-1}$ |

All parameters are non-negative, with $\pi, \mu, \beta > 0$ and $0 \leq \epsilon \leq 1$.

## Current status
- Repository created and folder structure initialised
- SVIR model equations documented
- Data sources to be identified and raw files added

## Tools
- Python (pandas, scipy, matplotlib)
- LaTeX (model write-up)
- Git / GitHub

## Next steps
- Download and document raw data sources
- Clean and merge daily cases + vaccination data
- Implement basic SVIR simulation
- Interpret first results

## Notes
This is a modelling project distinct from the descriptive ZA Pulse analytics work.  
All data pipelines, model equations, and code are version-controlled here for reproducibility.
