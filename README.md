# weighted_least_squares_wls

Weighted Least Squares (WLS) and Ordinary Least Squares (OLS). Covers heteroscedasticity, Feasible WLS, Huber robust regression, and validates methods with a Monte Carlo simulation

## Overview
This project presents an in-depth analysis of **Weighted Least Squares (WLS)** regression, comparing it with **Ordinary Least Squares (OLS)** and alternative estimation methods in the presence of heteroscedasticity. Through systematic implementation, diagnostic evaluation, and empirical validation, this project provides a comprehensive understanding of regression techniques for heteroscedastic data.

## Key Objectives

- **Investigate** the impact of heteroscedasticity on regression estimation
- **Compare** WLS and OLS performance across multiple metrics
- **Implement** practical alternatives including Feasible WLS and robust methods
- **Validate** findings through Monte Carlo simulation
- **Provide** reproducible Python implementations with thorough diagnostics

## Core Methodologies

### 1. **Weighted Least Squares (WLS)**
   - Implementation with known variance weights
   - Comparison of efficiency gains over OLS
   - Prediction interval analysis

### 2. **Feasible Weighted Least Squares (FWLS)**
   - Two-stage estimation when variance structure is unknown
   - Residual-based weight estimation
   - Performance comparison with true WLS

### 3. **Robust Regression Methods**
   - Iterative reweighting approaches
   - Huber's M-estimator for outlier resistance
   - Convergence behavior analysis

### 4. **Diagnostic Framework**
   - Residual analysis and heteroscedasticity detection
   - Q-Q plots for normality assessment
   - Comprehensive model comparison metrics

### 5. **Empirical Validation**
   - Monte Carlo simulation (1000 iterations)
   - Bias, variance, and MSE comparison
   - Small-sample performance evaluation

##  Technical Implementation

### Dependencies
```python
import numpy as np
import matplotlib.pyplot as plt
import statsmodels.api as sm
from scipy import stats
from statsmodels.iolib.table import SimpleTable
```

### Data Generation
- Artificial dataset with controlled heteroscedasticity
- Two variance groups (low/high) with 3:1 standard deviation ratio
- Quadratic true relationship with linear estimation (intentional misspecification)

### Model Performance Ranking
1. **Feasible WLS (FWLS)** - Best overall when variance is unknown
2. **WLS with known weights** - Optimal when variance structure is known
3. **Huber Robust Regression** - Excellent outlier resistance
4. **OLS with HC corrections** - Moderate improvement over standard OLS
5. **Standard OLS** - Least efficient under heteroscedasticity

### Practical Insights
- **FWLS performs comparably** to WLS with known weights
- **Iterative reweighting** requires careful implementation to avoid instability
- **Model diagnostics** are crucial for identifying remaining issues
- **Monte Carlo validation** confirms theoretical efficiency advantages

## Getting Started

### Prerequisites
```bash
pip install numpy matplotlib statsmodels scipy
```

### Basic Usage
1. Clone the repository
2. Install required dependencies
3. Open and run the Jupyter notebook
4. Modify parameters to explore different scenarios

### Parameters to Experiment With
- Variance ratio between groups
- Sample size
- Degree of model misspecification
- Heteroscedasticity patterns
- Number of Monte Carlo iterations

## Interpretation Guidelines

### When to Use WLS/FWLS
- **Heteroscedasticity detected** in residual plots
- **Prior knowledge** of variance structure available
- **Prediction precision** is a primary concern
- **Efficient parameter estimation** required

### When to Consider Alternatives
- **Outliers present** → Huber robust regression
- **Variance structure unknown** → FWLS
- **Limited sample size** → OLS with HC corrections
- **Computational simplicity needed** → Standard OLS

## Diagnostic Checklist

1. **Residual plots** - Check for heteroscedasticity patterns
2. **Q-Q plots** - Assess normality assumption
3. **Standard error comparison** - Evaluate efficiency gains
4. **Prediction intervals** - Compare precision
5. **Model selection criteria** - AIC/BIC comparison
6. **Monte Carlo results** - Validate small-sample performance

##  Theoretical Background

### Mathematical Foundation
WLS minimizes: 
$$\sum_{i=1}^{n} w_i (y_i - \hat{y}_i)^2$$
where $w_i = 1/\sigma_i^2$, giving less weight to observations with higher variance.

### Efficiency Considerations
Under heteroscedasticity, WLS achieves the **Gauss-Markov** property (Best Linear Unbiased Estimator), while OLS remains unbiased but inefficient.

## Learning Outcomes

Through this analysis, users will understand:
- The impact of heteroscedasticity on regression estimation
- Practical implementation of WLS and alternatives
- Diagnostic techniques for model validation
- Empirical performance evaluation methods
- Trade-offs between different estimation approaches

##  Contributing

Contributions are welcome! Please feel free to:
- Report issues or bugs
- Suggest enhancements or additional methods
- Improve documentation
- Share use cases or applications

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Statsmodels development team for comprehensive statistical tools
- Academic references listed in the notebook
- Open-source community for invaluable resources and support

# Note

This notebook is designed for educational and research purposes.
Real-world applications may require additional considerations and validation.

