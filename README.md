# JUND Binding Site Prediction Using Machine Learning

### A Bioinformatics and Computational Biology Project

This project explores the application of machine learning techniques to predict **JUND transcription factor binding sites** from DNA sequence data. It focuses on preprocessing biological sequence features, handling class imbalance, comparing multiple classification algorithms, and evaluating their predictive performance.

## Project Overview

JUND is a transcription factor involved in the regulation of gene expression. Identifying potential transcription factor binding sites is an important task in computational biology and genomics.

This project develops a machine learning workflow to classify DNA sequences based on their potential association with JUND binding sites.

## Objectives

- Predict JUND transcription factor binding sites using supervised machine learning.
- Process and analyze encoded DNA sequence data.
- Address class imbalance using negative-class undersampling and class weighting.
- Apply Principal Component Analysis (PCA) for dimensionality reduction.
- Compare multiple machine learning classifiers.
- Evaluate models using classification metrics and visualizations.

## Machine Learning Models

The following classifiers are implemented and evaluated:

| Model | Description |
|---|---|
| Logistic Regression | Linear classification baseline |
| SGD Classifier | Gradient-based linear classifier with logistic loss |
| Random Forest | Ensemble learning using decision trees |
| Multi-Layer Perceptron (MLP) | Neural network-based classifier |

## Methodology

**1. Data Loading**

The project uses NumPy datasets divided into training, validation, and testing sets.

Each input DNA sequence is represented as a matrix of shape `(101, 4)`, which is flattened into 404 numerical features.

**2. Data Preprocessing**

- Combine training and validation datasets for model training.
- Handle missing values using median imputation.
- Apply feature scaling using `StandardScaler`.
- Calculate class weights to address imbalanced class distributions.

**3. Class Imbalance Handling**

Negative-class samples are randomly undersampled, retaining up to a 10:1 ratio of negative to positive samples.

**4. Dimensionality Reduction**

Principal Component Analysis (PCA) reduces the processed feature space to 64 components for model training.

**5. Model Training**

Four classifiers are trained and compared using a consistent training and testing workflow.

**6. Model Evaluation**

Model performance is assessed using:

- Accuracy
- Macro Precision
- Macro Recall
- Macro F1-Score
- ROC-AUC
- Confusion Matrices
- ROC Curves

The models are ranked primarily by macro F1-score, followed by accuracy.

## Exploratory Data Analysis

The project also includes:

- Class distribution analysis
- PCA-based two-dimensional visualization
- K-Means clustering with two clusters
- Confusion matrix visualization for individual classifiers

## Technologies Used

**Programming Language:** Python

**Libraries and Tools:**

- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Joblib
- Google Colab

## Project Structure

```text
JUNDBindingSitePrediction/
├── jund_mlprediction.py
├── train/
│   ├── train_X.npy
│   └── train_y.npy
├── valid/
│   ├── valid_X.npy
│   └── valid_y.npy
├── test/
│   ├── test_X.npy
│   └── test_y.npy
└── README.md
```

The dataset folders shown above represent the expected input structure. Dataset files must be provided separately if they are not included in the repository.

## How to Run

**1. Clone the repository**

```bash
git clone https://github.com/Debasmita-98/JUNDBindingSitePrediction.git
cd JUNDBindingSitePrediction
```

**2. Install dependencies**

```bash
pip install numpy pandas matplotlib scikit-learn joblib
```

**3. Prepare the dataset**

Organize the training, validation, and testing NumPy files according to the expected directory structure.

**4. Configure the dataset path**

The original implementation runs in Google Colab and loads data from Google Drive. Update the `BASE_DIR` variable in the Python script to match your dataset location.

**5. Run the model**

Execute `jund_mlprediction.py` in a configured Python environment or Google Colab.

The current script requires Google Colab for its initial Drive mounting step.

## Results and Evaluation

The implementation calculates model evaluation metrics and generates visual comparisons, including confusion matrices and ROC curves.

The best-performing classifier is selected based on macro F1-score and accuracy.

The script also includes a model-saving step using Joblib.

**Note:** Numerical benchmark results are not included here because the source code does not contain saved evaluation outputs.

## Future Improvements

- Explore convolutional neural networks and sequence-based deep learning models.
- Investigate feature selection and hyperparameter optimization.
- Apply cross-validation for more robust evaluation.
- Improve interpretability of predicted binding sites.
- Evaluate generalization on additional biological datasets.


---

*This project demonstrates the application of machine learning techniques to biological sequence classification and computational genomics.*
