# transaction_volume_capstone
[Capstone Report](https://www.overleaf.com/read/wsnxpqvrqjyz#b56958)

[CPI](https://www.bls.gov/cpi/tables/supplemental-files/)

[Federal Funds Effective Rate](https://fred.stlouisfed.org/series/DFF#)

[Investing.com S&P 500 Historical Data](https://www.investing.com/indices/us-spx-500-historical-data)

# Transaction Volume Capstone

## Overview
This project examines historical 1031 exchange transaction volumes and their relationship to key economic indicators, including the Consumer Price Index (CPI), the S&P 500 Index, and interest rates. The goal of this exploratory phase is to identify trends, correlations, and potential predictors that will inform later modeling.

## Data sources
- **CPI**: U.S. Bureau of Labor Statistics  
- **Interest rate**: Federal Funds Effective Rate from FRED  
- **S&P 500**: Market index levels  
- **Adjusted transactions**: Internal monthly counts with a small confidentiality adjustment that preserves trends

## Data files
- `data/raw/` contains the original files as downloaded.
- `data/clean/merged_data.csv` contains the monthly aligned dataset used in the notebook.

## Advanced Analysis (Predictive Modeling)
This project includes a basic machine learning component to predict adjusted transaction volume.

### Models used
- Multiple Linear Regression  
- Random Forest Regression  

### Process
- Load and clean the dataset  
- Select features: `cpi_rate`, `sp500`, and `interest_rate`  
- Train/test split with `random_state=123`  
- Train models and evaluate using MAE, RMSE, and R²  

### Key results (Test Set)
**Linear Regression**  
- R²: 0.788  
- MAE: 7.60  
- RMSE: 9.04  

**Random Forest Regression**  
- R²: 0.782  
- MAE: 7.66  
- RMSE: 9.17  

The results show that both models perform similarly, with linear regression generalizing slightly better.

## How to set up the environment
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



