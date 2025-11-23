# 9417The-Stuff-of-Legend

Air Quality Data Analysis and Prediction Project

## @@@ Project Overview

This project performs comprehensive data exploration, preprocessing, anomaly detection, feature engineering, and machine learning modeling based on the UCI Air Quality dataset (AirQualityUCI). The project covers the complete data science workflow from data cleaning to model deployment, including both regression and classification tasks.

## @@@ Project Structure

```
9417The-Stuff-of-Legend/
├── air+quality/              # Raw data
│   ├── AirQualityUCI.csv
│   └── AirQualityUCI.xlsx
├── data/
│   └── processed/           # Processed data files
│       ├── train_data_engineered.csv
│       ├── test_data_engineered.csv
│       ├── scaler.pkl
│       ├── isolation_forest_model.pkl
│       ├── one_class_svm_model.pkl
│       └── ...
├── notebooks/               # Jupyter Notebooks
│   ├── 01_eda_and_preprocessing.ipynb
│   ├── 02_anomaly_detection.ipynb
│   ├── 03_feature_engineering.ipynb
│   ├── classification_final.ipynb
│   ├── classification_LightGBM+LogisticRegression+MLP.ipynb
│   └── regression_models.ipynb
└── README.md
```

## @@@ Project Contents

### 1. Exploratory Data Analysis & Preprocessing (`01_eda_and_preprocessing.ipynb`)

**EDA Section:**
- Time series visualization
- Seasonal decomposition
- Correlation heatmap
- Pairplot analysis
- Boxplot distribution analysis

**Preprocessing Section:**
- Handle -200 missing values (mark as NaN, record missing rates)
- Imputation strategies:
  - Meteorological variables: linear time interpolation
  - Sensors/pollutants: forward/backward fill or hourly mean imputation
- Detect and classify extreme values (IQR/Z-score)
- Merge Date+Time, extract temporal features
- Implement chronological split (2004 train, 2005 test)
- Apply StandardScaler (fit on train only)

### 2. Anomaly Detection (`02_anomaly_detection.ipynb`)

- Detect extreme values using statistical methods (IQR, Z-score)
- Identify anomalies using machine learning models (Isolation Forest, One-Class SVM)
- Analyze characteristics of detected anomalies
- Prepare data for event pattern analysis and modeling

### 3. Feature Engineering (`03_feature_engineering.ipynb`)

- Create temporal features (hour, weekday, month, etc.)
- Feature transformation and combination
- Feature selection and optimization

### 4. Classification Tasks

#### `classification_final.ipynb`
Final classification model predicting future CO concentration levels (low/mid/high)

#### `classification_LightGBM+LogisticRegression+MLP.ipynb`
Multiple classification algorithms:
- LightGBM
- Logistic Regression
- MLP (Multi-Layer Perceptron)

### 5. Regression Models (`regression_models.ipynb`)

Predict continuous air quality indicators

## @@@ Quick Start

### Requirements

- Python 3.9+
- Jupyter Notebook

### Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy statsmodels lightgbm
```

### Running the Pipeline

1. **Data Exploration & Preprocessing**
   ```bash
   jupyter notebook notebooks/01_eda_and_preprocessing.ipynb
   ```

2. **Anomaly Detection**
   ```bash
   jupyter notebook notebooks/02_anomaly_detection.ipynb
   ```

3. **Feature Engineering**
   ```bash
   jupyter notebook notebooks/03_feature_engineering.ipynb
   ```

4. **Model Training**
   - Classification: Run `classification_final.ipynb` or `classification_LightGBM+LogisticRegression+MLP.ipynb`
   - Regression: Run `regression_models.ipynb`

## @@@ Dataset

This project uses the **AirQualityUCI** dataset, containing:
- Time range: 2004-2005
- Main variables:
  - CO(GT) - Carbon monoxide concentration
  - PT08.S1-S5 - Metal oxide sensor data
  - NOx(GT) - Nitrogen oxides concentration
  - NO2(GT) - Nitrogen dioxide concentration
  - Meteorological data (temperature, humidity, absolute humidity, etc.)

## @@@ Tech Stack

- **Data Processing**: pandas, numpy
- **Visualization**: matplotlib, seaborn
- **Machine Learning**: scikit-learn, lightgbm
- **Statistical Analysis**: scipy, statsmodels

## @@@ Notes

- Data preprocessing steps must be executed in order
- Feature engineering must be completed before model training
- All processed data is saved in the `data/processed/` directory
- Trained models are also saved in the same directory

## @@@ License

This project is for educational and research purposes only.

## @@@ Contributors
Group: THE-STUFF-OF-LEGEND

