# Synthetic Solar Data Pipeline

## Overview

This project is a progressive data science and machine learning pipeline designed to simulate and analyse environmental systems using Python.

It focuses on building a **solar irradiance → temperature modelling system**, combined with:
- manual linear regression
- statistical evaluation
- residual analysis
- structured data generation
- reusable pipeline design

The goal was to move from raw Python scripting toward a **modular, reusable scientific computing pipeline**.

# Project Structure (Current State)

## Solar Data Generation System
Synthetic environmental dataset generator based on:
- Hour of day
- Month (seasonal variation)
- Physical irradiance model (sinusoidal curve)
- Temperature response model (linear dependency)

### Key relationships:
- Irradiance depends on:
  - time of day (solar angle)
  - seasonal factor (month)
- Temperature depends on irradiance:
  - linear physical approximation

 Solar Regression Pipeline--

## Data Generation

Synthetic dataset created using:

- `generate_dataset(month)`
- hourly simulation (0–23)
- multi-day structure (1–3 days initially)
- seasonal irradiance scaling

Each record contains:

```python
{
    "day": int,
    "hour": int,
    "irradiance": float,
    "temperature": float
}

## Feature Extraction

Regression variables:

X (input): irradiance
Y (target): temperature

Extracted via:

x_values, y_values = extract_regression_variables(dataset)

## Linear Regression (Manual Implementation)

A full least-squares regression implementation was built from scratch:

slope (m)
intercept (b)
Model:
T= mI + b

Where:

I = irradiance
T = temperature

Expected values:

slope ≈ 0.02
intercept ≈ 10

## Model Evaluation

The model is evaluated using:

Mean Squared Error (MSE)

Measures average squared prediction error.

Root Mean Squared Error (RMSE)

Interpretable error in original units.

Expected result:

MSE ≈ 0
RMSE ≈ 0

## Residual Analysis

Residuals computed as:

residual=y−y^
	
Used to:

validate model correctness
confirm linearity
detect systematic error patterns

Expected:

random scatter around 0
no structure (perfect model fit)

## Visualisations
1. Regression Plot
scatter of real data
fitted regression line
2. Residual Plot
residuals vs input
horizontal reference line at y = 0
3. Seasonal Irradiance Curves
irradiance variation across months
demonstrates seasonal physics model

## Key Concepts Learned 

Programming Skills
modular function design
reusable pipelines
dictionary-based structured return objects
data extraction patterns
data science concepts
synthetic data generation
feature-target separation
regression modelling from scratch
error metrics (MSE, RMSE)
residual diagnostics
physics-informed modelling
sinusoidal solar model
seasonal scaling
linear temperature response

## Pipeline Architecture (Current)

Data Generation
      ↓
Feature Extraction
      ↓
Linear Regression (manual)
      ↓
Prediction
      ↓
Evaluation (MSE / RMSE)
      ↓
Residual Analysis
      ↓
Visualisation

## Current Limitations 

This system is currently:

fully deterministic
noise-free
perfectly linear

This is intentional to:

validate regression correctness
verify pipeline structure
ensure mathematical consistency

## Next Stage 

The system will evolve into a realistic machine learning pipeline:

Planned additions:
scikit-learn regression
train/test split
data noise injection (cloud cover, weather variability)
diurnal asymmetry
temperature lag effects
classification tasks (threshold-based labels)
multi-dataset integration



