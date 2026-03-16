🏆 Regression Analysis: Transform × Model Comparison Study
This project investigates the impact of various target variable transformations on the performance of multiple machine learning models. By evaluating 48 different combinations (6 transformations × 8 models + Stacking), the study aims to identify the optimal pipeline for tabular regression tasks.

🚀 Overview
Predicting target variables in tabular data often requires handling skewness and non-normality. This repository provides an automated pipeline to benchmark:

6 Transformations: Log, Square Root, Cube Root, Box-Cox, Yeo-Johnson, and a Baseline (None).

8 Models: Linear Regressors (Ridge, Lasso), Tree-based models (XGBoost, LightGBM, Random Forest, GBR), and Ensemble Methods (Stacking).

Validation: 5-Fold Cross-Validation using RMSE as the primary metric.

📊 Methodology
1. Feature Engineering & Preprocessing
Automated handling of categorical and numerical features.

Dynamic data path management (DATA_RAW, DATA_PROC).

Advanced scaling and encoding strategies.

2. Experimental Setup
The study systematically tests each model against every transformation:

Linear Models: Highly sensitive to distribution; require normalization (Box-Cox/Log).

Tree Models: Robust to monotonic transformations; focus on split efficiency.

Stacking Regressor: Combining base models to minimize residual errors.

🛠️ Tech Stack
Languages: Python (Jupyter Notebook)

Data Manipulation: Pandas, NumPy

Scientific Computing: SciPy (Stats)

Machine Learning: Scikit-learn, XGBoost, LightGBM

Visualization: Matplotlib, Seaborn

📈 Key Findings
Based on the experimental results:

Transformations: Box-Cox and Log transformations significantly improve performance for linear models by satisfying normality assumptions.

Model Performance: Tree-based ensembles (LightGBM/XGBoost) generally outperform linear models, but benefit less from complex transformations compared to Ridge/Lasso.

Best Approach: The Stacking Regressor combined with a Log Transformation yielded the highest accuracy, balancing performance with production-ready interpretability.

📂 Project Structure
├── data/
│   ├── raw/            # Original dataset  
│   └── processed/      # Transformed and cleaned data  
├── notebooks/
│   └── 02_transform_comparison.ipynb
│ 
└── README.md

⚙️ Installation & Usage
Clone the repository:  https://github.com/Yousuf4455/House-Price-Prediction.git
Run the notebook:jupyter notebook notebooks/02_transform_comparison.ipynb
