# Date Fruit Classification Using Artificial Neural Networks

This repository contains a supervised multiclass classification project built on the Date Fruit Dataset. The goal is to classify date fruit varieties using morphological and color-based features extracted from fruit images.

The project implements a complete machine learning workflow including exploratory data analysis, preprocessing, feature scaling, artificial neural network training, model evaluation, and result visualization.

## Project Overview

Date fruit varieties can show visual and morphological similarities, which makes manual classification difficult and potentially inconsistent. In this project, an Artificial Neural Network (ANN) model was developed to classify date fruit samples into seven classes based on 34 numerical features.

The model was trained and evaluated using a structured pipeline:

- Dataset loading and inspection
- Missing value analysis
- Class distribution analysis
- Label encoding
- Train-test splitting with stratification
- Feature scaling with StandardScaler
- ANN model development with TensorFlow/Keras
- Model evaluation using accuracy, precision, recall, F1-score, and confusion matrix
- Visualization of training history and classification results

## Dataset

The project uses the Date Fruit Dataset.

Dataset characteristics:

| Property | Value |
|---|---:|
| Number of samples | 898 |
| Number of input features | 34 |
| Target variable | Class |
| Number of classes | 7 |
| Feature types | Morphological and color-based measurements |

Classes in the dataset:

- BERHI
- DEGLET
- DOKOL
- IRAQI
- ROTANA
- SAFAVI
- SOGAY

## Repository Structure

```text
date-fruit-ysa-classification/
│
├── data/
│   └── date_fruit_dataset.xlsx
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   └── 01_date_fruit_ann_classification.ipynb
│
├── outputs/
│   ├── class_distribution.png
│   ├── classification_report.csv
│   ├── confusion_matrix.png
│   ├── summary_results.csv
│   ├── training_validation_accuracy.png
│   └── training_validation_loss.png
│
├── report/
│   └── report_notes.md
│
├── README.md
└── requirements.txt
```

## Methodology

### 1. Data Exploration

The dataset was first inspected to understand its structure, feature types, target variable, missing values, and class distribution.

No missing values were found in the dataset.

The class distribution is not perfectly balanced, which makes class-level evaluation metrics important in addition to overall accuracy.

### 2. Preprocessing

The target variable `Class` was converted into numerical labels using `LabelEncoder`.

The dataset was split into training and test sets using an 80/20 ratio. Stratified splitting was applied to preserve the original class distribution in both sets.

The input features were standardized using `StandardScaler`. The scaler was fitted only on the training data and then applied to the test data to avoid data leakage.

### 3. Model Architecture

The ANN model was implemented using TensorFlow/Keras.

Model architecture:

| Layer | Configuration |
|---|---|
| Input | 34 features |
| Dense 1 | 64 neurons, ReLU |
| Dropout | 0.20 |
| Dense 2 | 32 neurons, ReLU |
| Dropout | 0.20 |
| Output | 7 neurons, Softmax |

Training configuration:

| Parameter | Value |
|---|---|
| Optimizer | Adam |
| Learning rate | 0.001 |
| Loss function | Sparse categorical crossentropy |
| Batch size | 32 |
| Maximum epochs | 100 |
| Early stopping patience | 15 |

## Results

The model achieved the following performance on the test set:

| Metric | Value |
|---|---:|
| Test Accuracy | 0.9167 |
| Macro Avg Precision | 0.9164 |
| Macro Avg Recall | 0.8904 |
| Macro Avg F1-Score | 0.8991 |
| Weighted Avg Precision | 0.9155 |
| Weighted Avg Recall | 0.9167 |
| Weighted Avg F1-Score | 0.9125 |

The model performed strongly overall, especially on the IRAQI, ROTANA, and SAFAVI classes. Lower recall values were observed for DEGLET and SOGAY, indicating that these classes were more frequently confused with other classes.

## Output Files

Generated evaluation outputs are stored in the `outputs/` directory:

| File | Description |
|---|---|
| `class_distribution.png` | Class distribution visualization |
| `training_validation_accuracy.png` | Training and validation accuracy plot |
| `training_validation_loss.png` | Training and validation loss plot |
| `confusion_matrix.png` | Confusion matrix heatmap |
| `classification_report.csv` | Class-level precision, recall, and F1-score |
| `summary_results.csv` | Summary of main evaluation metrics |

## How to Run

Clone the repository:

```bash
git clone https://github.com/gencnis/date-fruit-ysa-classification.git
cd date-fruit-ysa-classification
```

Create and activate a virtual environment:

```bash
python -m venv .venv
```

On Windows:

```bash
.venv\Scripts\activate
```

On Linux/macOS:

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the main notebook:

```text
notebooks/01_date_fruit_ann_classification.ipynb
```

The notebook can also be run in Google Colab.

## Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- TensorFlow / Keras
- Matplotlib
- Seaborn
- Jupyter Notebook
- Google Colab

## Key Takeaways

This project demonstrates a complete tabular deep learning workflow for multiclass classification. It includes reproducible preprocessing, ANN-based modeling, class-level performance analysis, and visual evaluation outputs.

The results show that a compact ANN architecture can achieve strong performance on feature-engineered image-derived data without requiring a large deep learning model.
