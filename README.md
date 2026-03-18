House Price Prediction - Multi-Model Regression

This project predicts house prices using multiple regression models. The workflow preprocesses the data, trains several models (default and hyperparameter-tuned), and stores all predictions in a single Excel file with separate sheets for each model.

Features
1. Handles missing values for numeric and categorical columns automatically.
2. One-hot encodes categorical features.
3. Log-transforms the target (SalePrice) for stable training.
4. Trains multiple models:
Random Forest Regressor (default and hyperparameter-tuned)
Decision Tree Regressor (default and hyperparameter-tuned)
Multi-Layer Perceptron Regressor (default and hyperparameter-tuned)
5. Hyperparameter tuning using RandomizedSearchCV.
6. Saves all predictions to one Excel file (data/output_house_price.xlsx) with separate sheets per model.

Requirements
Python 3.8+
pandas
numpy
scikit-learn
openpyxl

Install packages using pip: pip install pandas numpy scikit-learn openpyxl

File Structure
data/
├── train.csv                # Training dataset
├── test.csv                 # Test dataset
└── output_house_price.xlsx  # Predictions from all models
house_price_prediction.py    # Main Python script
README.md                    # Project documentation

How to Run
1. Place train.csv and test.csv in the data/ folder.
2. Run the main Python script: python house_price_prediction.py
3. Open data/output_house_price.xlsx to view predictions.
Each sheet corresponds to a different model:
    RandomForest_Default
    RandomForest_Hyper
    DecisionTree_Default
    DecisionTree_Hyper
    MLP_Default
    MLP_Hyper

Notes
The Id column from the test set is preserved in the Excel output.
The target SalePrice is log-transformed during training; you may exponentiate predictions if you need actual prices: np.exp(predictions)