# Oil Well Location Optimisation

## Project Overview

**Client**: An oil and gas company considering investment in new drilling operations.

This project identifies the most suitable region for drilling a new oil well using machine learning models combined with economic and risk analysis.


## Objective

- **Task type**: Regression + Profit & Risk Analysis  
- **Target variable**: Oil reserve volume per well (`product`, thousand barrels)  
- **Evaluation metric**: RMSE (model performance), expected profit, 95% confidence interval, and risk of losses (Bootstrap-based)


## Data Description

The repository contains raw data provided by the client in their original format.  
No manual modifications were made outside the preprocessing pipeline implemented in the notebooks.

The data are synthetic; specific field characteristics and contractual details are not disclosed.

The data:

- `/datasets/geo_data_0.csv`
- `/datasets/geo_data_1.csv`
- `/datasets/geo_data_2.csv`

Each dataset contains:

- **id** — unique well identifier  
- **f0, f1, f2** — numerical geological features  
- **product** — oil reserve volume (thousand barrels)

The datasets represent three potential regions for drilling.


## How to Run

The project is implemented as a Jupyter Notebook.  

To explore the full analysis, modelling process, and results:

1. Navigate to the `notebooks/` directory.
2. Open the notebook file.
3. Run all cells sequentially.


## Methodology

1. **Data preprocessing**
   - Duplicate removal
   - Data quality validation
   - Exploratory Data Analysis (EDA)

2. **Feature analysis**
   - Correlation analysis
   - Scatter plot inspection

3. **Model training**
   - Linear Regression
   - Polynomial feature expansion
   - Feature selection via `SelectFromModel`
   - Feature scaling
   - Hyperparameter tuning with `GridSearchCV`
   - Cross-validation

4. **Economic analysis**
   - Break-even reserve calculation
   - Profit estimation from top 200 wells (out of 500)

5. **Risk assessment**
   - Bootstrap simulation (1,000 iterations)
   - Estimation of:
     - Average profit
     - 95% confidence interval
     - Probability of losses


## Results

- Region 2 achieved the lowest RMSE (highest predictive accuracy).
- Region 3 demonstrated the highest expected profit.
- Bootstrap analysis identified Region 3 as the most favourable in terms of profit-to-risk balance.


## Key Insights

- Average reserve levels alone are insufficient for investment decisions.
- Profitability depends on selecting the top-performing wells.
- Risk-adjusted analysis is critical for capital-intensive projects.
- A region with slightly lower model accuracy may still provide superior financial outcomes.


## Applications

- Oil and gas investment decision support  
- Risk-aware capital allocation  
- Resource optimisation  
- Financial modelling in energy projects  


## Tech Stack

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Matplotlib / Seaborn  
- Jupyter Notebook  
