# Numerical Analysis Project: COVID-19 Spread Dynamics Modeling

This repository contains the solution for a programming assignment in Numerical Analysis from the Department of Electrical and Computer Engineering 
at Aristotle University of Thessaloniki. The project focuses on modeling the initial spread of the COVID-19 virus using differential equations and 
numerical optimization techniques.

## 📍 Context and Data

The study utilized observations gathered during the initial appearance period of the COVID-19 virus in a remote small village in Aetolia-Acarnania. 
The observation period spanned from July 3 (Day 0) to October 20 of the same year.

The village inhabitants were classified into three categories throughout the period:
1.  **Susceptible cases (`Y(t)`):** The number of potential cases at day $t$, starting at $Y(0) = 235$.
2.  **Confirmed cases (`E(t)`):** The number of confirmed cases at day $t$, starting at $E(0) = 14$.
3.  **Final cases (`T(t)`):** Those who were infected and either succumbed to the virus or recovered and acquired immunity, starting at $T(0) = 0$.

## 🎯 Objective

The core objective was to **determine the values of the parameters $\alpha$ and $\beta$** for which the simple model provides results that are as close as 
possible to the observed data collected during the virus outbreak.

## 🧬 Mathematical Model

A simple model often utilized for virus dissemination was employed, defined by the following system of first-order ordinary differential equations:

$$
\begin{aligned}
Y ′ &= −αY E \\
E ′ &= αY E − βE \\
T ′ &= βE
\end{aligned}
$$

## 🛠️ Numerical Techniques Implemented

To solve the model and fit the parameters, the project required the implementation of two major numerical analysis techniques:

1.  **Numerical Integration:** The differential equations were solved using the **4th order Runge-Kutta method** (the classical Runge-Kutta method). This step was essential for simulating the values of $Y(t)$, $E(t)$, and $T(t)$ over time.
2.  **Optimization (Parameter Fitting):** To find the optimal $\alpha$ and $\beta$ values, **least squares minimization methods** were utilized. For the optimization component, routines from the **`scipy.optimize`** package in the Python programming language were used.

## 📊 Observed Data Used for Fitting

The model was fitted against the following observed data points, tracking Suspected and Confirmed cases on specific days during the period:

| Day | Susceptible | Confirmed |
| :---: | :---: | :---: |
| 0 | 235 | 14 |
| 16 | 201 | 22 |
| 31 | 153 | 29 |
| 47 | 121 | 21 |
| 62 | 108 | 8 |
| 78 | 97 | 8 |
| 109 | 83 | 0 |

## 📁 Deliverables

The full implementation along with the assignment analysis is provided in the Jupyter Notebook `NA-10703-10351.ipynb`.
