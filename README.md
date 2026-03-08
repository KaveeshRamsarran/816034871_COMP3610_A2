# COMP3610 Assignment 2: ML Model Training & Evaluation

## Author Information
- **Student ID:** 816034871
- **Course:** COMP 3610 - Big Data Analytics
- **Institution:** The University of the West Indies
- **Semester:** II, 2025-2026

## Project Overview

This assignment builds, evaluates, and interprets machine learning models to predict taxi trip tip amounts using the NYC Yellow Taxi Trip dataset. The project demonstrates:

- Feature engineering and data preprocessing for ML pipelines
- Classification and regression model training using Scikit-learn
- Neural network implementation using PyTorch
- Model evaluation using appropriate metrics and cross-validation
- Model interpretation and communication of findings

## Prediction Tasks

1. **Regression Task:** Predict the `tip_amount` for a given taxi trip
2. **Classification Task:** Predict whether a trip will receive a high tip (`tip_amount > 20%` of `fare_amount`)

## Dataset

The project uses NYC Yellow Taxi Trip Records dataset. Since `tip_amount` is only reliably recorded for credit card payments (`payment_type = 1`), the dataset is filtered to include only credit card transactions.

### Required Data Files
- NYC Yellow Taxi Trip Records (Parquet format)
- Taxi Zone Lookup Table (CSV format)

Data files should be downloaded and placed in a `data/` directory (not included in repository).

## Project Structure

```
816034871_COMP3610_A2/
├── assignment2.ipynb      # Main Jupyter notebook with all analysis
├── requirements.txt       # Python dependencies with versions
├── README.md              # This file
├── .gitignore             # Git ignore rules
└── data/                  # Data directory (not tracked)
    ├── yellow_tripdata_*.parquet
    └── taxi_zone_lookup.csv
```

## Setup Instructions

### Prerequisites
- Python 3.10 or higher
- pip package manager
- Jupyter Notebook or Google Colab

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/816034871_COMP3610_A2.git
   cd 816034871_COMP3610_A2
   ```

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv venv
   
   # On Windows:
   venv\Scripts\activate
   
   # On macOS/Linux:
   source venv/bin/activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Download the dataset:**
   - Download NYC Yellow Taxi Trip Records from [NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
   - Download Taxi Zone Lookup Table from the same source
   - Place files in the `data/` directory

### Running the Notebook

**Option 1: Local Jupyter Notebook**
```bash
jupyter notebook assignment2.ipynb
```

**Option 2: Google Colab**
1. Upload `assignment2.ipynb` to Google Colab
2. Upload data files to Colab session or mount Google Drive
3. Run all cells

## Assignment Components

### Part 1: Data Preprocessing & Feature Engineering (25 marks)
- Temporal features (pickup_hour, day_of_week, is_weekend)
- Trip features (duration, speed, log-transformed distance)
- Fare features (fare_per_mile, fare_per_minute)
- Zone features (borough encoding)
- Target variable creation (tip_amount, high_tip)
- Data splitting and scaling (70/15/15 train/val/test)

### Part 2: Model Training & Tuning (30 marks)
- Baseline models (Linear Regression, Random Forest, Logistic Regression)
- Hyperparameter tuning with RandomizedSearchCV
- Neural network implementation with PyTorch

### Part 3: Model Evaluation & Interpretation (35 marks)
- Comprehensive evaluation on test set
- ROC curves and confusion matrices
- Feature importance analysis
- Written analysis and insights

### Part 4: Documentation & Code Quality (10 marks)
- Well-structured notebook with markdown explanations
- Clean, readable code with meaningful variable names
- Repository organization with required files

## Models Implemented

### Regression Models
- Linear Regression (baseline)
- Random Forest Regressor (baseline)
- Tuned Random Forest Regressor
- PyTorch Neural Network

### Classification Models
- Logistic Regression (baseline)
- Random Forest Classifier (baseline)
- Tuned Random Forest Classifier
- PyTorch Neural Network

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
- pandas 2.2.0
- numpy 1.26.3
- scikit-learn 1.4.0
- torch 2.2.0
- matplotlib 3.8.2
- seaborn 0.13.2

## License

This project is for educational purposes as part of COMP 3610 coursework at The University of the West Indies.

## Acknowledgments

- NYC Taxi and Limousine Commission for providing the dataset
- Course Lecturer: Mr. Sergio Mathurin
- Course Tutor: Mr. Anton Greenridge
