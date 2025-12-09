dataset link : https://archive.ics.uci.edu/dataset/352/online+retail
random forest model link (large file): https://drive.google.com/file/d/11MBSR5YNFUxaPIrgy8WtqYWTA5bIP3OA/view?usp=sharing

# Customer Value Prediction & Segmentation

This project processes over 500,000 online retail transactions to build a complete customer analytics pipeline, including data preprocessing, exploratory analysis, supervised learning, unsupervised segmentation, deep learning, and Streamlit deployment.

---

## 1. Data Preprocessing

Goal: Transform raw UCI Online Retail data into meaningful behavioral features for customer lifetime value (CLV) modeling.

### Steps
- Removed cancelled orders (negative quantities or InvoiceNo starting with "C")
- Handled missing CustomerIDs (approximately 135,000 records)
- Calculated CLV as: Quantity × UnitPrice
- Created RFM features:
  - Recency: days since last purchase
  - Frequency: number of transactions
  - Monetary: total spending amount
- Engineered temporal features: hour, day of week, month, season
- Extracted product categories from Description using keyword matching
- Encoded categorical variables: Country, Category
- Scaled numerical features using StandardScaler

---

## 2. Exploratory Data Analysis

Goal: Understand customer purchasing behavior and identify revenue optimization opportunities.

### Analyses Performed
- Customer distribution by country (UK-focused)
- Time-series trends of sales across 2010–2011
- CLV distribution and Pareto 80/20 analysis
- RFM feature distributions and correlation analysis
- Product popularity via StockCode and Description
- Cohort analysis of customer retention
- Seasonal patterns and purchasing peaks
- Geographic spending patterns across countries

---

## 3. Supervised Machine Learning

Goal: Predict customer lifetime value to support targeted marketing strategies.

### Models Implemented
- Linear Regression with RFM features (baseline)
- Random Forest Regressor with 200 estimators
- XGBoost Regressor with hyperparameter tuning

### Evaluation
- RMSE
- MAE
- R-squared
- Feature importance analysis
- Cross-validation for robustness

---

## 4. Unsupervised Machine Learning

Goal: Segment customers into meaningful groups for marketing and personalization.

### Methods
- KMeans clustering (k=5) using RFM features
- Gaussian Mixture Models for probabilistic clustering
- PCA for dimensionality reduction and visualization
- Silhouette scoring to optimize cluster count
- Customer persona creation based on behavioral patterns
- Segment comparisons across countries and product categories

---

## 5. Deep Learning

Goal: Capture complex customer behavior patterns to improve CLV prediction accuracy.

### Neural Network Models
- Deep Neural Network regressor with 4 dense layers (128, 64, 32, 16)
- Autoencoders for unsupervised feature learning
- Cluster membership features added to DNN input
- Batch normalization and dropout (0.3)
- Embedding layers for high-cardinality categorical features
- Early stopping to avoid overfitting

---

## 6. Streamlit Deployment

Goal: Deliver an interactive dashboard to support data-driven customer management.

### Features
- Customer lookup with real-time CLV prediction
- Segmentation explorer with cluster characteristics
- RFM scoring and interactive filters
- Campaign simulator with ROI projections
- Exportable customer segment lists
- Visualizations of behavioral trends and model performance

