# Time Series Forecasting
Build a predictive model to forecast sales for the next 3 months.

**Approach**
1. Feature Engineering
Date Features
-year, month, day, dayofweek, is_weekend
Lag Features (per store-item)
-Previous 7 days, 14 days, 28 days sales
Rolling Features
-Mean sales over 7, 14, 28 days
Store & Item IDs (categorical encoding)

2. Model
XGBoost Regressor trained per store-item.
Hyperparameters tuned manually for speed/accuracy tradeoff.
No data leakage: only past information used for future predictions.

3. Evaluation
Metrics calculated on validation set (2017-10-01 → 2017-12-31):
-MAE – Mean Absolute Error
-RMSE – Root Mean Squared Error
-MAPE – Mean Absolute Percentage Error
-RMSLE – Root Mean Squared Log Error

4. Forecasting
 Model trained on full train set up to 2017-09-30.
 Forecast generated for Jan–Mar 2018 for all store × item pairs.
Model trained on full train set up to 2017-09-30.

Forecast generated for Oct–Dec 2017 for all store × item pairs.

**Technologies Used**

-Python 3.12
-pandas, numpy
-matplotlib, seaborn
-scikit-learn
-xgboost

**How to Run**

1. Clone repository
   git clone https://github.com/decocta/timeseriesforecasting.git

   cd timeseriesforecasting

3. Install libraries
   pip install -r requirements.txt

4. Run the ipynb file

5. Save Model
models/xgb_store_item.json
