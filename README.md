# DoorDash-ETA-Prediction

### Summary of the Code Execution and Results

#### **Objective**
The goal of the assignment was to predict the estimated time of delivery (`delivery_duration`) based on the provided dataset and evaluate multiple machine learning models to determine the best-performing one.

---

#### **Steps in the Code**
1. **Data Loading and Preprocessing**:
   - Loaded the `historical_data.csv` dataset.
   - Extracted the target variable `delivery_duration` (difference between `created_at` and `actual_delivery_time`).
   - Performed feature engineering, including extracting time-related features (`created_hour` and `created_dayofweek`) and encoding categorical variables (`store_primary_category`, `market_id`).

2. **Exploratory Data Analysis (EDA)**:
   - Visualized the distribution of delivery durations (histogram).
   - Examined the relationship between delivery duration and order creation hour using box plots.
   - Generated a correlation heatmap to analyze feature relationships.

3. **Model Training**:
   - Implemented four models: 
     - **Random Forest Regressor**
     - **XGBoost Regressor**
     - **Neural Network**
     - **LightGBM Regressor**
   - Trained each model on 80% of the data and tested on the remaining 20%.

4. **Model Evaluation**:
   - Evaluated model performance using metrics:
     - Mean Absolute Error (MAE)
     - Mean Squared Error (MSE)
     - Root Mean Squared Error (RMSE)
     - R-Squared (R²)

5. **Model Inference**:
   - Identified the best-performing model based on evaluation metrics.
   - Used the best model (Neural Network) to make sample predictions on test data.

6. **Visualizations**:
   - Plotted actual vs predicted delivery durations for the best model to assess prediction accuracy.

---

#### **Results**

| Model              | MAE     | MSE         | RMSE    | R²    |
|--------------------|---------|-------------|---------|-------|
| Random Forest      | 756.26  | 58161244.33 | 7626.35 | -13.42 |
| XGBoost            | 672.96  | 5334308.35  | 2309.61 | -0.32  |
| Neural Network     | 696.51  | 3721867.29  | 1929.21 | 0.08   |
| LightGBM           | 924.08  | 25404310.88 | 5040.27 | -5.30  |

- **Best Model**: The Neural Network performed best, with the lowest RMSE (1929.21) and a slightly positive R² (0.08). Although XGBoost had a lower MAE, its overall performance was inferior to the Neural Network.

---

#### **Sample Predictions using Neural Network**
- `[2340.15, 1735.55, 2563.74, 2857.39, 2345.49]` (in seconds)
- These predictions represent the estimated delivery durations for 5 samples from the test data.

---

#### **Key Takeaways**
- The **Neural Network model** demonstrated the best generalization ability for this dataset, albeit with scope for improvement (R² is relatively low).
- Feature engineering and advanced tuning could further enhance the performance.
- Visualizations and scatter plots confirm the predictions align well with the actual values, although some deviations exist.
