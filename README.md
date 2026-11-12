
## 1. Project Overview

This project predicts whether an individual's annual income
exceeds $50,000 using the UCI Adult Income dataset.

The project compares traditional machine learning with
two different neural network architectures.

## 2. Dataset

Source: UCI Machine Learning Repository - Adult Dataset
```B. Becker and R. Kohavi. "Adult," UCI Machine Learning Repository, 1996. [Online]. Available: https://doi.org/10.24432/C5XW20.```

Training dataset: 32,561 records
Official held-out test dataset: 16,281 records
Original input features: 14
Processed input features: 105

Data preparation includes:
- Missing-value handling
- Numerical feature scaling
- Categorical feature encoding
- Stratified training/validation split
- Data leakage prevention

## 3. Models Implemented

### Logistic Regression
Non-neural baseline for performance comparison.

### NumPy MLP from Scratch
One-hidden-layer neural network implemented using NumPy.
Includes forward propagation, backpropagation,
gradient checking and mini-batch training.

### Deep MLP
Architecture:
- Input: 105 features
- Dense: 64 neurons, ReLU
- Dropout: 0.30
- Dense: 32 neurons, ReLU
- Output: 1 neuron, Sigmoid

Optimizer: Adam
Learning rate: 0.001
Loss: Binary Cross-Entropy
Regularization: L2 (0.0001)

### RBF Network
- Input: 105 features
- Gaussian RBF layer: 32 centres
- Output: Sigmoid classifier
- Trainable Gaussian centres and width

## 4. Experiments

- Three random seeds: 42, 123, 2026
- Dropout ablation study
- Validation error analysis
- Age-group subgroup performance analysis
- Official held-out test evaluation
- Model inference demonstration

## 5. Final Held-Out Test Results

| Model | Accuracy | F1-score | ROC-AUC |
|---|---:|---:|---:|
| Logistic Regression | 0.8512 | 0.6525 | 0.9040 |
| Deep MLP | 0.8558 | 0.6724 | 0.9107 |
| RBF Network | 0.8554 | 0.6564 | 0.9084 |

Recommended model: Deep MLP with 30% dropout.

## 6. Project Structure

ANN CW/
- ANN_Adult_Income.ipynb
- data/
- outputs/
  - figures/
  - metrics/
  - models/
  - splits/
- CW1 Practical Technical Record(KIC-BSCCSAI-251P-012).pdf
- Demo Drive Link.txt
- requirements.txt
- requirements-lock.txt
- README.md

## 7. Installation

Create a Python virtual environment.

Install dependencies:

    python -m pip install -r requirements.txt

For the exact recorded dependency environment:

    python -m pip install -r requirements-lock.txt

Open the notebook in Jupyter or VS Code and select
the correct Python environment.

## 8. Reproducibility

Random seeds: 42, 123, 2026

The project saves:
- Model checkpoints
- Training/validation split indices
- Preprocessing pipeline
- Evaluation metrics
- Experiment results
- Visualisation figures

The saved preprocessing pipeline must be reused
for validation and test inference.

The notebook should be executed in order for a
complete training reproduction.

## 9. Limitations

- Class imbalance affects positive-class recall.
- Performance differs across age groups.
- Historical data may not represent current income patterns.
- Three seeds provide limited estimates of variability.
- Model predictions should not be used for consequential
  employment or financial decisions.

## 10. Conclusion

The Deep MLP achieved the highest F1-score among the
evaluated framework models on the official held-out test set.
The RBF Network provided a distinct neural architecture,
while Logistic Regression served as a competitive baseline.

