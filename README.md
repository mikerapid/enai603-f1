# 603 Racing Group — F1 Tyre Degradation & Pit-Stop Strategy

**Team:** Kevin Zong (115265318), Michael Obajemu (114202291)

---

## Overview

In Formula 1, tyre management is one of the most consequential factors that separates winning teams from losing teams. Teams have to decide when to pit, which compound to switch to, and how to pace a driver through a stint — all while the race is happening. A single mistimed stop can cost several positions.

We've found that there aren't many tools out there currently that leverage historical data to predict tyre degradation. This project addresses that gap by building a regression model that predicts lap-time degradation by analyzing tyre life, compound type, race circuits, and weather conditions. We then use those degradation curves to recommend optimal pit-stop windows.

---

## Dataset

All data is sourced from the **FastF1 Python library**, which provides free access to official F1 live-timing streams. Each row contains lap time, sector times, tyre compound, tyre life, stint number, pit-in/out times, speed-trap readings, and weather conditions. A full season yields approximately 22,000–28,000 rows across 20 drivers and 22–24 races.

---

## Methodology

The project follows a standard data science pipeline executed in Python:

1. **Data collection & cleaning** — Pull lap data for the 2024–2025 F1 seasons using FastF1. Remove safety-car laps, in/out laps, red-flag periods, and other non-racing events.
2. **Exploratory analysis** — Visualize tyre degradation curves by compound type, circuit type, and ambient conditions to identify key predictors of tyre drop-off.
3. **Predictive modeling** — Train a regression model to predict lap time delta as a function of tyre life, compound, track, and weather. Time-based cross-validation: train on 2024, validate on 2025.
4. **Pit-stop optimizer** — Test the model in a simulated race scenario to identify the tyre compound sequence and stint lengths that minimize total race time.

---

## Success Metrics

- Degradation model achieves **RMSE < 0.3 seconds per lap** on held-out 2025 races
- Pit-stop optimizer recommends a strategy **within 2 laps of the actual optimal** (back-calculated from race results) on at least **60% of test races**

---

## Timeline

| Weeks | Phase                                          | Deliverable                                         |
| ----- | ---------------------------------------------- | --------------------------------------------------- |
| 0–2   | Data collection, cleaning, feature engineering | Cleaned dataset ready for analysis                  |
| 3–4   | EDA & visualization                            | Degradation curves, correlation matrix _(mid-term)_ |
| 5–6   | Baseline modeling & tuning                     | Regression model with cross-validation results      |
| 7–8   | Race simulation & validation                   | Pit-stop optimizer back-tested against 2025 results |

---

## Team Roles

| Member          | Responsibilities                                                 |
| --------------- | ---------------------------------------------------------------- |
| Kevin Zong      | Data cleaning, feature engineering, modeling pipeline            |
| Michael Obajemu | Feature engineering, pit-stop optimization logic, visualizations |
