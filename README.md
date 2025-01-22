# Heart Disease Classification with Neural Networks

This project focuses on building a neural network model to classify heart disease severity using data from multiple datasets. The target variable is grouped into three categories:
1. **No Disease**: No signs of heart disease.
2. **Low Severity**: Mild heart disease (original classes 1 and 2).
3. **High Severity**: Severe heart disease (original classes 3 and 4).

## Project Overview

### Objectives
- Preprocess and clean heart disease datasets (Cleveland, Switzerland, and Hungarian) to handle missing values.
- Group the target variable into three classes to simplify the classification task and reduce class imbalance.
- Train a neural network model to classify heart disease severity accurately.

---

## Data Preprocessing
### Steps
1. **Cleaning Missing Data**: Missing values were imputed based on disease states:
   - **Continuous Features**: Imputed using the median of the associated disease state.
   - **Categorical Features**: Imputed using the mode of the associated disease state.
2. **Feature Scaling**: Continuous features were normalized using `StandardScaler`.
3. **One-Hot Encoding**: Categorical features were encoded to make them model-friendly.
4. **Target Grouping**:
   - `0`: No Disease.
   - `1`: Low Severity (combines `1` and `2`).
   - `2`: High Severity (combines `3` and `4`).

---

## Model Architecture
- **Type**: Sequential Neural Network.
- **Layers**:
  1. **Input Layer**: Matches the number of features.
  2. **Hidden Layers**:
     - 16 neurons, ReLU activation, L2 regularization.
     - 8 neurons, ReLU activation, L2 regularization.
  3. **Output Layer**: 3 neurons, Softmax activation (for multi-class classification).
- **Loss Function**: Categorical Crossentropy.
- **Optimizer**: Adam (learning rate = 0.005).

---

## Results
The model achieved an accuracy of **80%** with the following classification performance:

| Class           | Precision | Recall | F1-Score | Support |
|------------------|-----------|--------|----------|---------|
| **No Disease**   | 0.90      | 0.89   | 0.90     | 72      |
| **Low Severity** | 0.73      | 0.80   | 0.76     | 56      |
| **High Severity**| 0.55      | 0.38   | 0.44     | 16      |
| **Overall**      |           |        |          |         |
| **Accuracy**     |           |        | **0.80** | 144     |
| **Macro Avg**    | 0.72      | 0.69   | 0.70     | 144     |
| **Weighted Avg** | 0.79      | 0.80   | 0.79     | 144     |

---

## Files
- `data/`: Contains the cleaned and preprocessed datasets.
- `notebook.ipynb`: Jupyter notebook with model training and evaluation.
- `README.md`: Project documentation.
