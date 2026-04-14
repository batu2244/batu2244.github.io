---
layout: page
title: Predictive Modeling of Residential Energy Consumption in Los Angeles
permalink: /projects/energy/
hide_in_nav: true
---

## Predictive Modeling of Residential Energy Consumption in Los Angeles

[View on GitHub](https://github.com/batu2244/Predictive-Modeling-of-Residential-Energy-Consumption-in-Los-Angeles)

This project builds a machine learning pipeline to forecast residential energy consumption across Los Angeles neighborhoods by combining multiple heterogeneous data sources into a unified dataset.

**Data Collection & Engineering**

The dataset was assembled from three sources: UCLA's Energy Atlas, which provides per-building energy usage records; the Google Geocoding API, used to standardize and enrich addresses with geographic coordinates; and Craigslist housing listings scraped using BeautifulSoup, which supply housing characteristics like square footage, number of bedrooms and bathrooms, and rental price. Merging these sources required significant data cleaning and preprocessing with pandas, including deduplication, handling of missing values, and spatial joins.

**Modeling**

The core model is a CatBoost regression, chosen for its robustness to categorical features and mixed data types. Predictions are aggregated using a weighted scheme to account for varying data density across neighborhoods. An OLS regression was also run alongside the gradient boosting model to quantify feature-level statistical significance and interpret directional effects.

**Key Findings**

Housing price, square footage, number of bedrooms, and bathrooms all emerged as statistically significant predictors of per-capita energy usage. Higher income levels correlated with greater energy consumption, while higher solar potential - a proxy for sun exposure - was negatively associated with predicted demand, suggesting that access to solar reduces grid reliance. Overall, structural housing characteristics proved to be stronger drivers of energy demand than demographic factors alone.
