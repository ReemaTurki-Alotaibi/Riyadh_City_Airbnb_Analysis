# 🏠 Exploratory Data Analysis (EDA) & Predictive Modeling

🔹 **Quick Overview**  
- Dataset: 2360 rows × 20 columns  
- Some missing values in bathrooms and rating  
- Initial inspection: `head()`, `tail()`, `info()`

📊 **Numeric & Categorical Columns**  
- **Numeric:** bedrooms, bathrooms, beds, persons, reviewsCount, rating, ...  
- **Categorical:** city, property_type, cancelPolicy, isSuperhost, ...

📈 **Statistical Summary & Missing Values**  
- Descriptive stats: mean, median, std, min, max  
- Missing values handled during cleaning

📉 **Distribution & Outliers**  
- Histograms & KDE plots for numeric columns  
- Boxplots & IQR/Z-score for outlier detection  
- Skewed columns identified for potential log-transform

🔗 **Correlation Analysis**  
- Pearson correlation heatmap  
- Strong correlation: bedrooms ↔ beds  
- Weak correlation: rating ↔ reviewsCount

🏷️ **Categorical Features Analysis**  
- Countplots & violin plots per category  
- Mean price per category  
- Example: Superhosts tend to charge higher prices

🌍 **Geospatial Analysis**  
- Scatter plots of property locations colored by price  
- Price density heatmap in Riyadh

🕒 **Time Series Analysis**  
- Average price per month & weekday  
- Seasonal trends detected

🔢 **Clustering Analysis**  
- KMeans (`n_clusters=4`) on numeric features  
- PCA for 2D visualization  
- Cluster insights for property segmentation

🧹 **Data Cleaning & Feature Engineering**  
- Missing Values: numeric → median, categorical → 'Unknown'  
- Data Types: dates → datetime, boolean → proper boolean  
- **New Features:**  
  - stay_duration  
  - total_price, base_rate_per_night, final_price_per_night  
  - amenities_count, amenities_per_person  
  - luxury_flag, amenities_category  
- Currency Conversion: USD → SAR (×3.75)  
- Location Standardization: unified city & address, extract district  
- Outliers Detection: IQR method on final_price_per_night

🤖 **Predictive Modeling**  
- Model: Random Forest Regressor  
- Target: final_price_per_night_SAR  
- Features: numeric & categorical  
- Pipeline: scaling + one-hot encoding + RandomForestRegressor  
- Train/test split: 80/20

⚡ **Initial Performance**  
- Metrics: MAE, RMSE, R²

🛠️ **Hyperparameter Tuning**  
- RandomizedSearchCV with 5-fold CV  
- Tuned parameters: n_estimators, max_depth, min_samples_split, max_features, bootstrap

🌟 **Feature Importance & SHAP**  
- Top predictors: bedrooms, bathrooms, beds, stay_duration, amenities_count  
- SHAP summary plots (dot & bar)  
- SHAP dependence plots for top 3 features  
- Interpretation: larger properties and more amenities → higher prices

📉 **Residual Analysis**  
- Distribution mostly centered around 0  
- Scatter plots of residuals vs predicted values

💡 **Insights & Next Steps**  
- Price Drivers: property size, amenities, location, Superhost status  
- Weak Factors: ratings & review counts alone  
- Segment Opportunities: cluster-based marketing & pricing  
- Next Steps: combine with predictive modeling for feature impact quantification; investigate outliers; apply predictive strategies

💾 **Model Saving**
```python
import joblib
joblib.dump(best_model, 'price_model_rf_enhanced.joblib')
print("Model saved as 'price_model_rf_enhanced.joblib'")

💾 **Model Saving**  
Model saved for future use in prediction tasks.

---

## 📊 Dashboard

**Tableau Dashboard:** Interactive dashboard to explore project dataset insights.

**Dashboard Link:** ()

---

📬 **Contact / Author**

**Author:** Reema Alotaibi
 
🔗 [LinkedIn](https://www.linkedin.com/in/reematurki-alotaibi)
