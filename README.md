# Mineral Demand Predictor

A machine learning project that predicts global critical mineral demand
by technology and year, built on IEA Critical Minerals data.

## What it does

Given a mineral, a clean energy technology, and a year, the model
returns a demand forecast in kilotonnes (kt).

```python
predict_demand('Copper', 'Electric vehicles', 2035)  # → 1697.3 kt
predict_demand('Lithium', 'Electric vehicles', 2050)  # → 1243.9 kt
```

## Model

- Algorithm: Linear Regression
- R²: 0.807
- Features: year + 5 minerals + 8 technologies (one-hot encoded)
- Trained on IEA Critical Minerals Dataset (2024–2040)

## Minerals covered

Copper, Cobalt, Lithium, Nickel, Magnet rare earth elements

## Technologies covered

Electric vehicles, Solar PV, Wind, Electricity networks,
Grid battery storage, Hydrogen technologies,
Low emissions power generation, Other low emissions power generation

## Project structure

| File | Description |
|---|---|
| `predictor.ipynb` | Final predictor function and sample predictions |
| `step_00_reshape.ipynb` | Data reshaping wide to long format |
| `Rare_earth.ipynb` | Rare earth elements analysis |
| `demand_clean.csv` | Cleaned demand data |
| `demand_long.csv` | Reshaped long-format data |
| `demand_encoded.csv` | One-hot encoded data for ML |
| `minerals_clean.csv` | Cleaned supply data by country |
| `Critical_Minerals_Dataset.xlsx` | Original IEA raw dataset |

## Key findings

- Year alone as a feature produced R² of -1.99, useless
- Adding mineral + technology via one-hot encoding pushed R² to 0.807
- Linear regression outperformed random forest on this dataset
- Lesson: features matter more than model complexity

## Data source

IEA Critical Minerals Dataset
