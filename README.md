### 📊 Dataset Link & Context
The core data utilizes a multi-city logistics tracker capturing delivery parameters, weather conditions, account profiles, and precise time metrics.

* **Primary Data Source:** [Click Here to View the Kaggle Dataset](https://www.kaggle.com/datasets/deepeshkansotia/food-delivery-operations-and-customer-analytics/data) 👈
* **Target Variable:** `delivery_time_minutes` (Continuous real-world elapsed time from order placement to terminal arrival).
* **SLA Operational Threshold:** >120 minutes.

## 🚦 Bottom Line Up Front (BLUF)

# Executive Objective
- The objective of this project was to develop a deployment-ready machine learning engine to accurately predict order delivery times and systematically prevent Service Level Agreement ($SLA$) breaches beyond the $120$-minute operational threshold.

# The Core Solution
- Following hyperparameter tuning and the detection/elimination of a critical target data leaks, an encapsulated Linear Regression Pipeline was selected as the best model. Due to the syntethic nature of the data and the linear relationship between physical delivery distance and time, the linear model outperformed advanced tree-based architectures ($XGBoost$ and $Random\ Forest$).

# Key Performance Benchmarks 
- Prediction Precision: Mean Absolute Error ($MAE$) of $6.42$ minutes, explaining $94.25\%$ of total logistical variance ($R^2 = 0.9425$).
- SLA Breach Detection Success Rate (Recall): $86\%$. The model successfully identifies $627$ out of $725$ actual contract breaches before they occur.
- SLA Precision Rate: $86\%$. When the model flags an $SLA$ violation, it is mathematically correct $86\%$ of the time.
- Overall Classification Accuracy: $93.3\%$ across all test orders ($3,000$ deliveries).

# Business Impact
- Cost Reduction: By identifying $86\%$ of incoming breaches, the model enables proactive dispatch intervention. Approximating based on other food delivery serives this could save $\$15.00$ per violation in customer recovery vouchers. This translates to an estimated $\$8,000$ in direct retention savings on the test set alone, scaling to over $\$100,000$ annually across the logistics network.
- Operational Readiness: Continuous predictions are transformed into an automated Traffic Light Risk Framework (green/yellow/red), instantly routing operational attention where fleet intervention is required. 

The finalized pipeline has been fully serialized to disk as models/delivery_time_pipeline.pkl.
