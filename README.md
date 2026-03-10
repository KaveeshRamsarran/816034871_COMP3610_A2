# COMP3610 Assignment 2: ML Model Training & Evaluation

## Author Information
- **Name:** Kaveesh Ramsarran
- **Student ID:** 816034871
- **Course:** COMP 3610 - Big Data Analytics
- **Institution:** The University of the West Indies
- **Semester:** II, 2025-2026

## Project Overview

This assignment builds, evaluates, and interprets machine learning models to predict taxi trip tip amounts using the NYC Yellow Taxi Trip dataset (January 2024). The project demonstrates:

- Feature engineering and data preprocessing for ML pipelines
- Regression and classification model training using Scikit-learn
- Neural network implementation using PyTorch (binary classification)
- Hyperparameter tuning with RandomizedSearchCV
- Model evaluation using appropriate metrics
- Model interpretation via feature importance, coefficient analysis, and SHAP values

## Prediction Tasks

1. **Regression Task:** Predict the `tip_amount` for a given taxi trip
2. **Classification Task:** Predict whether a trip will receive a high tip (`tip_amount > 20%` of `fare_amount`)

## Dataset

The project uses NYC Yellow Taxi Trip Records (January 2024). Since `tip_amount` is only reliably recorded for credit card payments (`payment_type = 1`), the dataset is filtered to include only credit card transactions (~2.27M records after cleaning).

Data is downloaded automatically within the notebook from the NYC TLC website -- no manual download is required.

## Project Structure

```
816034871_COMP3610_A2/
├── assignment2.ipynb      # Main Jupyter notebook with all analysis
├── requirements.txt       # Python dependencies with versions
├── README.md              # This file
└── .gitignore             # Git ignore rules
```

## Setup Instructions

### Prerequisites
- Python 3.10 or higher
- pip package manager
- Jupyter Notebook or VS Code with Jupyter extension

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/KaveeshRamsarran/816034871_COMP3610_A2.git
   cd 816034871_COMP3610_A2
   ```

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv .venv
   
   # On Windows:
   .venv\Scripts\activate
   
   # On macOS/Linux:
   source .venv/bin/activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

### Running the Notebook

**Option 1: VS Code**
1. Open the folder in VS Code
2. Open `assignment2.ipynb`
3. Select the `.venv` Python interpreter
4. Run all cells

**Option 2: Jupyter Notebook**
```bash
jupyter notebook assignment2.ipynb
```

## Assignment Components

### Part 1: Data Preprocessing & Feature Engineering (25 marks)
- Temporal features (pickup_hour, day_of_week, is_weekend)
- Trip features (duration, speed, log-transformed distance)
- Fare features (fare_per_mile, fare_per_minute)
- Zone features (borough encoding)
- Target variable creation (tip_amount, high_tip)
- Data splitting and scaling (70/15/15 train/val/test)

### Part 2: Model Training & Tuning (30 marks)
- Baseline models (Linear Regression, Random Forest Regressor, Logistic Regression, Random Forest Classifier)
- Hyperparameter tuning with RandomizedSearchCV (n_iter=20, cv=5)
- Neural network implementation with PyTorch (BCEWithLogitsLoss, 20 epochs)

### Part 3: Model Evaluation & Interpretation (35 marks)
- Comprehensive evaluation on test set
- ROC curves for all classification models
- Confusion matrix for best classifier
- Predicted vs actual scatter plot and residuals vs predicted plot
- Residual distribution histogram and residuals vs predicted analysis
- Training and validation loss curves (neural network)
- Feature importance bar chart (Random Forest)
- Linear and Logistic Regression coefficient tables
- SHAP values for individual trip explanations (bonus)
- Written analysis and insights

### Part 4: Documentation & Code Quality (10 marks)
- Well-structured notebook with markdown explanations and observations
- Clean, readable code with meaningful variable names
- Repository organization with required files

## Models Implemented

### Regression Models
- Linear Regression (baseline)
- Random Forest Regressor (baseline)
- Tuned Random Forest Regressor (RandomizedSearchCV)

### Classification Models
- Logistic Regression (baseline)
- Random Forest Classifier (baseline)
- Tuned Random Forest Classifier (RandomizedSearchCV)
- PyTorch Neural Network (HighTipNN: 128-64-1, Dropout 0.3)

## Evaluation Metrics

### Regression
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

### Classification
- Accuracy
- Precision
- Recall
- F1-Score
- AUC-ROC

## Key Findings

*See the detailed analysis in the notebook for complete findings and insights.*

## Dependencies

See `requirements.txt` for complete list. Key packages include:
- pandas 3.0.1
- numpy 2.4.2
- scikit-learn 1.8.0
- torch 2.10.0
- matplotlib 3.10.8
- seaborn 0.13.2
- shap 0.51.0
- scipy 1.17.1

## License

This project is for educational purposes as part of COMP 3610 coursework at The University of the West Indies.

## Acknowledgments

- NYC Taxi and Limousine Commission for providing the dataset
- Course Lecturer: Mr. Sergio Mathurin
- Course Tutor: Mr. Anton Greenridge
