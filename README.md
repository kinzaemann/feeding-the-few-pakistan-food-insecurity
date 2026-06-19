# 🌾 Feeding the Few: Mapping Inequality Behind Pakistan's Hunger Crisis

A data science investigation into food insecurity across 16 Pakistani cities — analyzing how food prices, nutritional availability, and economic inequality together shape food security outcomes.

## 📌 Project Overview

Pakistan produces enough food to feed its population, yet millions cannot afford adequate nutrition. This project uses four official datasets spanning 2010–2025 to identify which cities face the highest food insecurity risk, why protein foods are becoming unaffordable, and how wage inequality — not food prices — drives the crisis.

## 🔍 Research Question

*How have food prices, nutritional availability, and economic inequality together shaped food security in Pakistan from 2010 to 2024, and which population groups are most at risk?*

## 📊 Datasets Used

| Dataset | Source | Coverage | Rows |
|---------|--------|----------|------|
| SPI Weekly Food Prices | Pakistan Bureau of Statistics | Aug 2023 – Aug 2025, 16 cities | 85,000+ |
| World Bank Poverty Indicators | Humanitarian Data Exchange | 2001–2018 (real surveys) | 200+ |
| FAO Food Balance Sheets | UN Food & Agriculture Organization | 2010–2023 | 900+ |
| World Development Indicators | World Bank DataBank | 2000–2023 | 600+ |

## 🛠️ Methodology

### Data Cleaning (8 operations)
- Duplicate removal, median imputation, string standardisation, date parsing
- Outlier winsorisation using IQR method
- Post-Phase 2 audit: corrected FAO pivot bug (27× error), disclosed Gini fabrication, resolved item aliases

### Exploratory Data Analysis (10 analyses)
- Food price inflation per item (protein foods inflated most: Pulse Moong +47%)
- Poverty vs food supply (poverty fell but nutrition did not improve)
- City-level food basket affordability (Peshawar worst at 18.7% of salary)
- Price volatility analysis (Onions 45% CV, Tomatoes 38% CV)
- Wheat dependency trend (25–30% of all food, consistently above danger threshold)
- Protein adequacy vs WHO thresholds (72.78 g/cap/day but 47% from wheat alone)
- Province-level price comparison (KPK worst nationally)

### Machine Learning (3 algorithms)
| Algorithm | Type | Key Metric | Key Finding |
|-----------|------|------------|-------------|
| Linear Regression | Supervised regression | R² = 0.957 | Price level is strongest predictor of basket cost |
| Gaussian Naive Bayes | Supervised classification | LOO-CV 68.8% | Peshawar & Bannu = 100% high stress probability |
| K-Means Clustering | Unsupervised clustering | Silhouette = 0.614 | 2 natural clusters: 13 mainstream + 3 low-wage periphery |

## 📈 Key Findings

1. **87% of tracked food items inflated** between 2023–2025
2. **Protein foods inflated most** — pushing poor families toward wheat-only diets
3. **Wage inequality, not food prices**, drives food insecurity — KPK wages (PKR 32K) vs Islamabad (PKR 53K)
4. **Pakistan's protein supply depends 47% on wheat** — adequate in total but structurally fragile
5. **All three ML models independently identified Peshawar and Bannu** as highest-risk cities

## 📊 Power BI Dashboard

Interactive 5-page dashboard built with the Arid Earth theme:
- **Overview** — KPI cards, Pakistan bubble map, wheat dependency trend
- **Price Inflation** — item-level inflation, time series, volatility analysis
- **Geographic Inequality** — city affordability ranking with drill-through to city detail
- **Nutrition** — protein vs WHO thresholds, wheat dependency, protein source breakdown
- **ML Insights** — Linear Regression scatter, Naive Bayes probabilities, K-Means clusters

Features: drill-through navigation, custom tooltips, bookmark toggles, synchronised slicers.

## 🗂️ Repository Structure
