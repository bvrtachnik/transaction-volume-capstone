# Transaction Volume Capstone

## Overview

This project examines how monthly 1031 exchange activity relates to three major economic indicators: the Consumer Price Index (CPI), the S&P 500 Index, and the Federal Funds Effective Rate. The goal of this phase is to identify trends, correlations, and preliminary predictive patterns that can support later modeling using the firm's full internal dataset.

Full report (Overleaf PDF):  
https://www.overleaf.com/read/wsnxpqvrqjyz

## Data sources

- **CPI**: U.S. Bureau of Labor Statistics  
  - https://www.bls.gov/cpi/
- **Federal Funds Effective Rate**: Federal Reserve Economic Data (FRED)  
  - https://fred.stlouisfed.org/series/DFF
- **S&P 500 index levels**: Investing.com historical data  
  - https://www.investing.com/indices/us-spx-500-historical-data
- **Adjusted transactions**: Internal monthly counts of completed 1031 exchanges with a small confidentiality adjustment that maintains overall structure and trends.

## Repository structure

- `data/raw/` contains the original downloaded data files.
- `data/clean/` contains the aligned and merged dataset used for analysis (for example `merged_data.csv`).
- `figures/` contains exported images used in the report.
- `project_notebook.ipynb` contains the exploratory analysis and predictive modeling.
- `requirements.txt` lists the Python packages needed to reproduce the notebook.

## Predictive modeling

The project includes a basic predictive analysis using three features: `cpi_rate`, `sp500`, and `interest_rate`.

### Models

- Multiple Linear Regression  
- Random Forest Regression

### Evaluation metrics

Models were evaluated on the test set using three standard metrics:

- Mean Absolute Error (MAE)  
- Root Mean Squared Error (RMSE)  
- Coefficient of determination (R²)

### Key results (test set)

**Linear Regression**

- R²: 0.788  
- MAE: 7.60  
- RMSE: 9.04  

**Random Forest Regression**

- R²: 0.782  
- MAE: 7.66  
- RMSE: 9.17  

Both models show similar performance on the held out data, with linear regression achieving slightly lower error and a higher R². Feature importance values from the random forest indicate that `cpi_rate` provides the most explanatory value, followed by `sp500`, with `interest_rate` contributing less.

## Environment setup

Use a local virtual environment and install dependencies from `requirements.txt`.

### Windows (PowerShell)

```powershell
python -m venv .venv
.\.venv\Scripts\Activate
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### macOS or Linux
```python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Running the Notebook

1. Open the repository in VS Code or Jupyter Notebook.
2. Select the .venv environment as your interpreter or kernel.
3. Open and run project_notebook.ipynb to execute all cells.

## AI Use Acknowledgment
Generative AI tools were used for copyediting and formatting assistance. They were not used to generate research content, perform analysis, or interpret results. All analytic work, modeling decisions, and written explanations were completed by the author, and any AI-assisted edits were reviewed prior to inclusion.


