# Airbnb_pricing_econometric_analysis
Econometric analysis of Airbnb pricing across European cities using R
# 🏠 Econometric Analysis of Airbnb Pricing



## 📋 Overview

This repository contains an econometric analysis of Airbnb pricing dynamics across European cities. The study investigates what factors influence Airbnb prices, with a particular focus on:

- **Question 1**: What variables influence Airbnb prices?
- **Question 2**: Does log(price) differ significantly by city and room type, and does their interaction matter?
- **Question 3**: Does weekend pricing differ between Amsterdam and Lisbon?

**Data**: 200 Airbnb listings from Amsterdam and Lisbon with 11 variables including:
- Price (weekday & weekend)
- Guest satisfaction ratings
- Cleanliness ratings
- Room types (Entire home/apt, Private room)
- Person capacity
- Number of bedrooms
- Distance from city center
- Distance from metro
- Superhost status

## 📊 Key Findings

### Model Performance
- **Best Model**: Log-transformed price model
- **Adjusted R²**: 74.4%
- **Significant Predictors**: Weekend, room_type, person_capacity, bedrooms, city, dist

### City & Room Type Interaction
- City explains ~33% of price variation (more than room type at ~17%)
- Interaction between city and room type is **statistically significant** (p = 0.0114)
- Log(price) differs significantly by both city and room type

### Weekend Pricing
- Weekend stays increase prices significantly in both cities
- No significant difference in weekend price increases between Amsterdam and Lisbon

## 🛠️ Methodology

### Statistical Tests Used
- **Linearity**: Residuals vs Fitted plots
- **Normality**: Shapiro-Wilk, Anderson-Darling, Q-Q plots
- **Homoscedasticity**: Breusch-Pagan test, Levene's test
- **Multicollinearity**: VIF (all < 5)
- **Autocorrelation**: Durbin-Watson test
- **Specification**: Ramsey RESET test

### Data Transformations Tested
1. ❌ Linear model (violated assumptions)
2. ✅ Log(price) model **(selected)**
3. ❌ Sqrt(price) model
4. ❌ Log(log(price)) model
5. ❌ Inverse log(price) model
6. ❌ Inverse sqrt(price) model

### Robustness Checks
- HC3 robust standard errors applied to address mild heteroscedasticity
- Winsorisation (1st/99th percentiles) for outlier treatment
- F-tests for interaction significance
- Non-nested F-test (discrimination approach)

## 📁 Repository Structure
