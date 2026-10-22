# AI/ML Internship — 4-Week Project

## Project Overview

This repository contains the work completed during a four-week AI/ML internship. The tasks cover Python data analysis, exploratory data analysis (EDA), data preprocessing, machine learning model development, and an end-to-end Student Performance Prediction project.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook
- Joblib

---

## Week 1: Python and Data Analysis

### Objective

To understand the dataset, inspect its structure, handle missing values and duplicate records, calculate descriptive statistics, and create visualizations.

### Dataset

- **File:** `vacant_posts_2026-02-07.csv`
- **Original shape:** 31 rows × 7 columns

### Tasks Completed

- Imported the required Python libraries.
- Loaded and inspected the CSV dataset.
- Checked the number of rows and columns and examined data types.
- Identified missing values and duplicate records.
- Removed the completely empty `Level` column.
- Calculated descriptive statistics.
- Analyzed designations, offices, and divisions.
- Created three visualizations using Matplotlib.
- Exported the cleaned dataset.

### Output Files

- `week1_data_analysis.ipynb`
- `cleaned_vacant_posts.csv`

### Key Observation

The original dataset contained 31 rows and 7 columns. The `Level` column contained no useful values and was removed during cleaning.

### Libraries Used

Pandas, NumPy, Matplotlib

---

## Week 2: Exploratory Data Analysis and Preprocessing

### Objective

To explore a real-world dataset, identify data-quality issues, perform basic preprocessing, and visualize important patterns.

### Dataset

- **File:** `vacant_posts_2026-02-07.csv`
- **Original shape:** 31 rows × 7 columns

### Tasks Completed

- Inspected the dataset structure and data types.
- Checked missing values and duplicate records.
- Removed the completely empty `Level` column.
- Removed duplicate rows, where present.
- Examined the distributions of designations, offices, and divisions.
- Created bar charts to understand categorical distributions.
- Exported the processed dataset as a CSV file.

### Output Files

- `week2_eda_preprocessing.ipynb`
- `cleaned_vacant_posts.csv`

### Key Observation

The `Level` column was completely empty and was removed. The dataset was explored to understand its categorical distributions and data-quality issues.

**Note:** Missing-value and duplicate checks should be verified against the final exported dataset before claiming that the dataset is completely clean.

### Libraries Used

Pandas, NumPy, Matplotlib

---

## Week 3: Machine Learning Model Development

### Objective

To develop and compare regression models for predicting students' final Mathematics grades.

### Dataset

- **File:** `student-mat.csv`
- **Dataset:** Student Performance — Mathematics
- **Original shape:** 395 rows × 33 columns
- **Target variable:** `G3`, the final Mathematics grade

### Dataset Source

UCI Machine Learning Repository:  
https://archive.ics.uci.edu/dataset/320/student+performance

### Tasks Completed

- Loaded and inspected the dataset.
- Checked data types, missing values, and duplicate records.
- Explored the distribution of final Mathematics grades.
- Separated input features (`X`) from the target variable (`G3`).
- Converted categorical variables into numerical features using one-hot encoding.
- Split the dataset into training and testing sets using an 80:20 ratio.
- Trained two regression models:
  - Linear Regression
  - Random Forest Regressor
- Generated predictions on the test dataset.
- Evaluated the models using MAE, RMSE, and R².
- Compared the performance of both models.
- Saved the trained models and model-comparison results.

### Model Evaluation Results

| Model | MAE | RMSE | R² Score |
|---|---:|---:|---:|
| Linear Regression | 3.395 | 4.196 | 0.141 |
| Random Forest | 2.994 | 3.751 | 0.314 |

### Interpretation

Random Forest performed better than Linear Regression on the Week 3 test set. It achieved lower MAE and RMSE values and a higher R² score.

The R² score of 0.314 indicates that the model's predictive performance still has room for improvement.

### Output Files

- `week3_machine_learning.ipynb`
- `week3_model_comparison.csv`
- `week3_linear_regression.pkl`
- `week3_random_forest.pkl`

### Libraries Used

Pandas, NumPy, Matplotlib, Scikit-learn, Joblib

---

## Week 4: End-to-End Student Performance Prediction

### Objective

To build an end-to-end machine learning workflow that processes student data, trains regression models, compares their performance, saves the best-performing model, and generates a sample prediction.

### Dataset

- **File:** `student-mat.csv`
- **Dataset:** Student Performance — Mathematics
- **Target variable:** `G3`, the final Mathematics grade
- **Original shape:** 395 rows × 33 columns

### Workflow

1. Loaded and inspected the dataset.
2. Checked data types, missing values, duplicate records, and target-variable statistics.
3. Separated input features and the target variable.
4. Encoded categorical features using one-hot encoding.
5. Split the data into training and testing sets using an 80:20 ratio.
6. Trained Linear Regression and Random Forest regression models.
7. Evaluated and compared both models.
8. Saved the Random Forest model.
9. Loaded the saved model and generated a sample prediction.

### Model Evaluation Results

| Model | MAE | RMSE | R² Score |
|---|---:|---:|---:|
| Linear Regression | 1.647 | 2.378 | 0.724 |
| Random Forest | 1.165 | 1.949 | 0.815 |

### Best Model

**Random Forest Regressor**

The Random Forest model performed better on the Week 4 test set, achieving:

- **MAE:** 1.165
- **RMSE:** 1.949
- **R² Score:** 0.815

These results indicate better test-set performance than Linear Regression in this workflow.

### Sample Prediction

The saved Random Forest model was used to predict the final Mathematics grade for a sample student from the dataset.

- **Predicted grade:** 6.27/20

This is a sample prediction, not a prediction for a newly entered student.

### Output Files

- `week4_end_to_end_project.ipynb`
- `week4_best_model.pkl`

### Future Improvements

- Evaluate the models on additional student datasets.
- Tune model hyperparameters.
- Compare additional regression algorithms.
- Evaluate prediction performance when earlier grades (`G1` and `G2`) are excluded.
- Build a simple web application using Streamlit.
- Improve the model's generalization to unseen students.

### Important Limitation

The current model uses `G1` and `G2` as input features. Therefore, these earlier grades must be available when making predictions with this model. A model intended to predict final grades without earlier grades must be trained and evaluated separately.

---

## Project Structure

```text
AI-ML-Internship/
├── .venv/
├── week1_data_analysis.ipynb
├── week2_eda_preprocessing.ipynb
├── week3_machine_learning.ipynb
├── week4_end_to_end_project.ipynb
├── vacant_posts_2026-02-07.csv
├── cleaned_vacant_posts.csv
├── student-mat.csv
├── week3_linear_regression.pkl
├── week3_random_forest.pkl
├── week3_model_comparison.csv
├── week4_best_model.pkl
└── README.md
```

*Note: `student-mat.csv` is the dataset used for the Week 3 and Week 4 machine learning projects. The vacant-posts dataset is used for Week 1 and Week 2.*

---

## How to Run the Project

### 1. Clone or Download the Repository

Download the project files and open the project folder in VS Code.

### 2. Activate the Virtual Environment

On Linux or macOS:

```bash
source .venv/bin/activate
```

### 3. Install Required Libraries

```bash
pip install pandas numpy matplotlib scikit-learn jupyter joblib
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Alternatively, open the `.ipynb` files directly in VS Code and select the project's Python virtual environment as the notebook kernel.

### 5. Run the Notebooks

Run the notebooks in order:

1. `week1_data_analysis.ipynb`
2. `week2_eda_preprocessing.ipynb`
3. `week3_machine_learning.ipynb`
4. `week4_end_to_end_project.ipynb`

Ensure that the required CSV files are present in the project directory before running the notebooks.

---

## Final Conclusion

This four-week internship project covered data analysis, exploratory data analysis, preprocessing, regression model development, evaluation, and an end-to-end prediction workflow.

The Week 3 and Week 4 experiments compared Linear Regression with Random Forest Regression. Random Forest achieved better results in both reported test-set evaluations.

The project demonstrates a basic machine learning workflow, from loading and preparing data to training models, evaluating predictions, and saving a trained model for reuse.
