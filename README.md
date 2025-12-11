# Used Car Price Prediction Model

## What Drives the Price of a Car?

**A Data-Driven Analysis for Used Car Dealerships**

---

## Project Overview

This project analyzes over 426,000 used car listings to identify the key factors that drive car prices. The analysis follows the **CRISP-DM** (Cross-Industry Standard Process for Data Mining) framework and provides actionable insights for used car dealerships to optimize their inventory and pricing strategies.

### 📓 [View the Full Analysis Notebook](notebooks/used_car_price_prediction.ipynb)

---

## Summary of Findings

### Key Price Drivers (In Order of Importance)

1. **Vehicle Age/Year** (~35% importance)
   - Newer vehicles command significantly higher prices
   - Each year of age reduces value by approximately 5-10%
   - Vehicles 1-5 years old have the best resale margins

2. **Odometer Reading** (~25% importance)
   - Strong negative correlation with price
   - Vehicles under 50,000 miles maintain premium pricing
   - Key mileage thresholds: 30K, 60K, 100K miles

3. **Vehicle Type** (~15% importance)
   - Trucks and SUVs command premium prices
   - Pickup trucks have highest resale values
   - Sedans and coupes have lower price retention

4. **Manufacturer/Brand** (~10% importance)
   - Luxury brands (Tesla, Porsche, etc.) hold highest values
   - Popular truck brands (Ford, Chevrolet, RAM) consistently strong
   - Economy brands have faster depreciation

5. **Condition** (~8% importance)
   - "Like New" condition commands 30-50% premium
   - Salvage title significantly reduces value
   - Reconditioning investment shows good ROI

---

## Model Performance

| Model | R² Score | RMSE | MAE |
|-------|----------|------|-----|
| Random Forest (Best) | ~0.68 | ~$6,200 | ~$4,100 |
| Gradient Boosting | ~0.66 | ~$6,500 | ~$4,300 |
| Ridge Regression | ~0.58 | ~$7,200 | ~$5,000 |
| Linear Regression | ~0.57 | ~$7,300 | ~$5,100 |
| Lasso Regression | ~0.55 | ~$7,500 | ~$5,200 |

**Evaluation Metric**: RMSE (Root Mean Squared Error) was chosen as the primary metric because:
- Interpretable in dollars
- Penalizes larger prediction errors
- Industry standard for price prediction

---

## Actionable Recommendations

### For Used Car Dealerships

| Strategy | Action | Expected Impact |
|----------|--------|----------------|
| **Inventory Focus** | Stock more 1-5 year old trucks/SUVs | Higher profit margins |
| **Pricing Strategy** | Use mileage breakpoints (30K, 60K, 100K) | More accurate pricing |
| **Reconditioning** | Invest in improving condition ratings | 10-20% price increase |
| **Brand Mix** | Balance luxury (high margin) with mainstream (high volume) | Optimized portfolio |
| **Transmission** | Prioritize automatic transmissions | Faster inventory turnover |

### Factors with Lower Price Impact
- Paint color (minimal impact)
- Fuel type (diesel slight premium)
- Drive type (4WD modest premium)

---

## Project Structure

```
used_car_price_prediction/
├── README.md                          # This file
├── notebooks/
│   └── used_car_price_prediction.ipynb  # Main analysis notebook
├── data/
│   └── vehicles.csv                   # Dataset (426K+ listings)
└── images/
    ├── crisp.png                      # CRISP-DM framework diagram
    └── kurt.jpeg                      # Header image
```

---

## Technical Details

### Data Preparation
- **Original dataset**: 426,880 records with 18 features
- **Cleaned dataset**: ~200,000 records after filtering
- **Filters applied**:
  - Price: $1,000 - $100,000
  - Year: 1990 - 2024
  - Odometer: < 500,000 miles
- **Missing values**: Imputed with 'unknown' for categorical features

### Features Used
- **Numerical**: year, odometer, vehicle_age (engineered)
- **Categorical**: manufacturer, condition, cylinders, fuel, title_status, transmission, drive, type, paint_color

### Models Evaluated
1. Linear Regression (baseline)
2. Ridge Regression (L2 regularization)
3. Lasso Regression (L1 regularization)
4. Random Forest Regressor
5. Gradient Boosting Regressor

### Techniques Applied
- 5-fold Cross-Validation
- Grid Search Hyperparameter Tuning
- Feature Importance Analysis
- Coefficient Interpretation

---

## Requirements

```
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
```

---

## How to Run

1. Clone the repository
2. Install dependencies: `pip install -r requirements.txt`
3. Open the Jupyter notebook: `jupyter notebook notebooks/used_car_price_prediction.ipynb`
4. Run all cells to reproduce the analysis

---

## Next Steps

1. **Geographic Analysis**: Incorporate regional pricing differences
2. **Temporal Analysis**: Include seasonal pricing trends
3. **Model Enhancement**: Add specific vehicle models and features
4. **Deployment**: Build API endpoint for real-time predictions
5. **Monitoring**: Track market trends and update model regularly

---

## Author

Data Science Team | December 2024

---

## License

This project is for educational purposes as part of the UC Berkeley Professional Certificate in ML/AI program.

