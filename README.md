\# Hybrid SVIR–Machine Learning for COVID-19 Forecasting



Hybrid forecasting approach that couples a mechanistic SVIR compartmental model  

(S = Susceptible, V = Vaccinated, I = Infectious, I\_c = Confirmed Infectious, R = Recovered)  

with machine-learning methods. Focus is on daily COVID-19 cases merged with vaccination data.



\## Project overview

Daily COVID-19 case data are cleaned, aligned, and merged with vaccination coverage (and optionally other public sources).  

A deterministic SVIR model is implemented and simulated in Python. Machine learning will later be used for parameter estimation, residual correction, or learning time-varying transmission rates.  

The goal is improved short-term forecasts of daily cases that explicitly account for vaccination.



\## Repository structure

