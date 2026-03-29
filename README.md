# Newsvendor Model: Joint Price-Quantity Optimization

**UT Austin McCombs School of Business - RM 294: Optimization I**  
**Project 3: Non-Linear Programming**

## Overview

This project extends the classical Newsvendor Model by treating price as a decision variable rather than a fixed constraint. Using linear regression and quadratic programming, we jointly optimize pricing and production quantity to maximize daily profit.

## Key Results

| Metric | Baseline (Fixed Price) | Proposed (Joint Optimization) | Improvement |
|--------|------------------------|-------------------------------|-------------|
| **Price** | $1.00 (fixed) | $0.95 | -5.0% |
| **Quantity** | 471 units | 535 units | +13.6% |
| **Daily Profit** | $231.48 | $235.54 | **+$4.06 (+1.75%)** |

**Annual Impact:** +$1,481 in additional profit

## Methodology

### ► Phase 1: Demand Modeling
- Fit linear regression: `D = β₀ + β₁p + ε`
- Estimated coefficients: β₀ = 1924.72, β₁ = -1367.71
- Adj. R² = 0.618

### ► Phase 2: Optimization
- **Baseline Model (LP):** Fixed price at $1.00, optimize quantity only
- **Proposed Model (QP):** Jointly optimize price and quantity
- Cost structure: c = $0.50, g = $0.75, t = $0.15

### ► Phase 3: Validation
- Bootstrap simulation (500 iterations)
- 95% CI for optimal price: [$0.93, $0.98]
- 95% CI for expected profit: [$216.69, $254.64]

## Project Structure
```
.
├── Project3_G5.ipynb                 # Main analysis notebook
├── Project_3_-_G5_Report.pdf         # Technical report
├── project_3_-_description.pdf       # Assignment description
└── README.md
```

## Dependencies
```python
numpy
pandas
matplotlib
seaborn
statsmodels
scikit-learn
gurobipy
```

## Installation & Usage
```bash
# Install dependencies
pip install numpy pandas matplotlib seaborn statsmodels scikit-learn gurobipy

# Run the notebook
jupyter notebook Project3_G5.ipynb
```

**Note:** Requires Gurobi license (free academic license available)

## Key Findings

- **Price Elasticity:** Demand is highly price-sensitive (β₁ ≈ -1367)  
- **Strategy Shift:** 5% price reduction → 13% volume increase → 1.75% profit gain  
- **Robustness:** Optimal price remains stable across 500 bootstrap scenarios  
- **Risk Profile:** Downside protected, upside potential significant

## Authors

**Group 5**
- Elmer Wang
- Franco Salinas
- Janani Vakkanti
- Keerti Rawat

## License

Academic project for educational purposes.

---

*UT Austin McCombs School of Business | Spring 2025*
