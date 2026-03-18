# House Price Prediction - Multi-Model Regression

## Overview
This project predicts house prices using multiple regression models. The workflow preprocesses the data, trains several models (default and hyperparameter-tuned), and stores all predictions in a single Excel file with separate sheets for each model.

## Features
- Handles missing values for numeric and categorical columns automatically  
- One-hot encodes categorical features  
- Log-transforms the target (`SalePrice`) for stable training  
- Trains multiple models:  
  - Random Forest Regressor (default and hyperparameter-tuned)  
  - Decision Tree Regressor (default and hyperparameter-tuned)  
  - Multi-Layer Perceptron Regressor (default and hyperparameter-tuned)  
- Hyperparameter tuning using `RandomizedSearchCV`  
- Saves all predictions to one Excel file (`data/output_house_price.xlsx`) with separate sheets per model  

## Requirements
- Python 3.8+  
- Libraries: `pandas`, `numpy`, `scikit-learn`, `openpyxl`  

Install dependencies:
```
pip install pandas numpy scikit-learn openpyxl
```

## Project Structure
```
project_folder
│
├── data
│   ├── train.csv
│   ├── test.csv
│   └── output_house_price.xlsx
│
├── House Price Regression.ipynb
└── README.md
```

## How to Run
1. Place `train.csv` and `test.csv` in the `data/` folder  
2. Run the main Python script:  
```
House Price Regression.ipynb
```
3. Open `data/output_house_price.xlsx` to view predictions. Each sheet corresponds to a different model:  
   - `RandomForest_Default`  
   - `RandomForest_Hyper`  
   - `DecisionTree_Default`  
   - `DecisionTree_Hyper`  
   - `MLP_Default`  
   - `MLP_Hyper`  

## Notes
- The `Id` column from the test set is preserved in the Excel output  
- The target `SalePrice` is log-transformed during training; use `np.exp(predictions)` if actual prices are needed  
