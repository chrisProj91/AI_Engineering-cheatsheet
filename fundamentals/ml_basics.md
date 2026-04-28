# Machine Learning Basics

## 1. What is Machine Learning?

Machine Learning (ML) is a subset of artificial intelligence (AI) that enables systems to learn patterns from data and make decisions or predictions without being explicitly programmed.

Instead of writing rules manually, we:
1. Provide data
2. Define a model
3. Train the model to learn patterns
4. Use it to make predictions

---

## 2. Types of Machine Learning

### 2.1 Supervised Learning

- Learn from labeled data (input → correct output)
- Goal: learn a mapping function

#### Common Tasks:
- **Classification** → predict categories  
  Example: spam vs not spam
- **Regression** → predict continuous values  
  Example: house price prediction

#### Algorithms:
- Linear Regression
- Logistic Regression
- Decision Trees
- Random Forest
- Support Vector Machines (SVM)
- k-Nearest Neighbors (k-NN)
- Neural Networks

---

### 2.2 Unsupervised Learning

- No labels provided
- Goal: discover hidden patterns

#### Common Tasks:
- Clustering
- Dimensionality Reduction

#### Algorithms:
- K-Means
- Hierarchical Clustering
- DBSCAN
- PCA (Principal Component Analysis)
- t-SNE

---

### 2.3 Semi-Supervised Learning

- Small labeled dataset + large unlabeled dataset
- Useful when labeling is expensive

---

### 2.4 Reinforcement Learning (RL)

- Agent interacts with environment
- Learns via rewards and penalties

#### Key Concepts:
- Agent
- Environment
- State
- Action
- Reward
- Policy

---

## 3. The Machine Learning Workflow

### 3.1 Data Collection
- Gather relevant data
- Structured / unstructured

### 3.2 Data Preprocessing
- Handle missing values
- Normalize / standardize
- Encode categorical variables
- Remove noise

### 3.3 Feature Engineering
- Create meaningful features
- Feature selection
- Feature extraction

### 3.4 Model Selection
- Choose algorithm based on problem

### 3.5 Training
- Fit model on training data

### 3.6 Evaluation
- Measure performance using metrics

### 3.7 Deployment
- Put model into production

---

## 4. Data Concepts

### 4.1 Features (X)
Input variables

### 4.2 Labels (y)
Output variable (target)

### 4.3 Dataset Split

- Training set (70–80%)
- Validation set (10–15%)
- Test set (10–15%)

---

## 5. Overfitting vs Underfitting

### Overfitting
- Model memorizes training data
- Poor generalization

**Symptoms:**
- High train accuracy
- Low test accuracy

### Underfitting
- Model too simple
- Fails to learn patterns

**Symptoms:**
- Low train accuracy
- Low test accuracy

### Solution Techniques:
- Regularization
- More data
- Simpler/complex models
- Cross-validation

---

## 6. Bias-Variance Tradeoff

- **Bias**: error from wrong assumptions
- **Variance**: sensitivity to data fluctuations

| Model Type | Bias | Variance |
|-----------|------|----------|
| Simple    | High | Low      |
| Complex   | Low  | High     |

Goal: balance both

---

## 7. Common Evaluation Metrics

### 7.1 Classification Metrics

#### Accuracy

Accuracy = Correct Predictions / Total Predictions


#### Precision

Precision = TP / (TP + FP)


#### Recall

Recall = TP / (TP + FN)


#### F1 Score

F1 = 2 * (Precision * Recall) / (Precision + Recall)


#### Confusion Matrix

|            | Predicted Positive | Predicted Negative |
|------------|------------------|------------------|
| Actual Pos | TP               | FN               |
| Actual Neg | FP               | TN               |

---

### 7.2 Regression Metrics

#### Mean Absolute Error (MAE)

MAE = mean(|y_true - y_pred|)


#### Mean Squared Error (MSE)

MSE = mean((y_true - y_pred)^2)


#### Root Mean Squared Error (RMSE)

RMSE = sqrt(MSE)


#### R² Score
- Measures variance explained

---

## 8. Loss Functions

Loss measures how wrong predictions are.

### Examples:

#### Regression:
- MSE
- MAE

#### Classification:
- Binary Cross Entropy
- Categorical Cross Entropy

---

## 9. Optimization

### Gradient Descent

Iteratively updates parameters to minimize loss:

θ = θ - α * ∇J(θ)


Where:
- θ = parameters
- α = learning rate
- ∇J = gradient

### Variants:
- Batch Gradient Descent
- Stochastic Gradient Descent (SGD)
- Mini-batch Gradient Descent

---

## 10. Learning Rate

- Controls step size during training

### Too small:
- Slow convergence

### Too large:
- Overshooting / divergence

---

## 11. Regularization

Prevents overfitting by penalizing large weights.

### L1 Regularization
- Encourages sparsity

### L2 Regularization
- Penalizes large weights smoothly

---

## 12. Cross Validation

### K-Fold Cross Validation

- Split data into K folds
- Train on K-1 folds
- Validate on remaining fold
- Repeat K times

---


## 13. Feature Scaling

Feature scaling ensures all features have similar ranges, improving model performance.

### 13.1 Normalization (Min-Max Scaling)

Scales values to [0, 1]:

x' = (x - min) / (max - min)


### 13.2 Standardization (Z-score)

Centers data around mean 0 and std 1:

x' = (x - μ) / σ


### When to Use:
- Required for: SVM, KNN, Neural Networks
- Not critical for: Tree-based models

---

## 14. Handling Categorical Data

### 14.1 One-Hot Encoding
- Converts categories into binary vectors

Example:
Color: Red, Blue, Green
→ [1,0,0], [0,1,0], [0,0,1]



### 14.2 Label Encoding
- Assigns integer values
- Use only for ordinal data

---

## 15. Missing Data Handling

### Techniques:
- Remove rows/columns
- Mean/median imputation
- Model-based imputation

---

## 16. Data Leakage (VERY IMPORTANT)

Occurs when information from outside the training dataset is used.

### Examples:
- Using test data during training
- Scaling before splitting data

### Prevention:
- Always split first
- Use pipelines

---

## 17. Pipelines

Automate ML workflows and prevent leakage.

### Example Steps:
1. Scaling
2. Encoding
3. Model training

Benefits:
- Cleaner code
- Reproducibility
- Safer evaluation

---

## 18. Model Interpretability

Understanding why a model makes decisions.

### Techniques:
- Feature importance
- SHAP values
- LIME

### Why it matters:
- Debugging
- Trust
- Compliance

---

## 19. Probabilistic Machine Learning

Models output probabilities instead of fixed predictions.

### Example:
- Logistic Regression → probability of class

### Benefits:
- Better decision making
- Uncertainty estimation

---

## 20. Ensemble Methods

Combine multiple models to improve performance.

### 20.1 Bagging

- Train models independently
- Reduce variance

Example:
- Random Forest

---

### 20.2 Boosting

- Train sequentially
- Focus on errors

Examples:
- AdaBoost
- Gradient Boosting
- XGBoost
- LightGBM

---

### 20.3 Stacking

- Combine predictions from multiple models
- Meta-model learns final output

---

## 21. Dimensionality Reduction

Reduce number of features.

### Benefits:
- Faster training
- Less overfitting
- Better visualization

### Techniques:
- PCA
- t-SNE
- UMAP

---

## 22. Hyperparameter Tuning

Hyperparameters are set before training.

### Methods:
- Grid Search
- Random Search
- Bayesian Optimization

---

## 23. Training vs Inference

### Training:
- Model learns patterns
- Expensive

### Inference:
- Model makes predictions
- Fast

---

## 24. Online vs Offline Learning

### Offline (Batch):
- Train once on full dataset

### Online:
- Continuously update with new data

---

## 25. Concept Drift

When data distribution changes over time.

### Types:
- Sudden drift
- Gradual drift

### Solutions:
- Retraining
- Monitoring

---

## 26. Common Pitfalls

### 26.1 Overfitting
- Too complex model

### 26.2 Underfitting
- Too simple model

### 26.3 Data Leakage
- Invalid evaluation

### 26.4 Imbalanced Data

#### Solutions:
- Resampling
- Class weights

---

## 27. Practical Tips

- Start simple
- Always visualize data
- Use baseline models
- Validate properly
- Track experiments

---

## 28. Quick Algorithm Selection Guide

| Problem Type     | Suggested Models                  |
|------------------|----------------------------------|
| Tabular Data     | Random Forest, XGBoost          |
| Images           | CNNs                            |
| Text             | Transformers / LLMs             |
| Small Data       | Simpler models                  |

---

## 29. ML vs Deep Learning

| Aspect         | Machine Learning       | Deep Learning          |
|----------------|----------------------|------------------------|
| Data Need      | Low–Medium           | High                   |
| Feature Eng.   | Manual               | Automatic              |
| Compute        | Low                 | High                   |
| Performance    | Good                | State-of-the-art       |

---

## 30. Cheat Sheet Summary

- ML = learning from data
- Supervised vs Unsupervised vs RL
- Overfitting = memorization
- Use validation properly
- Scaling matters
- Pipelines prevent leakage
- Ensembles boost performance
- Always evaluate correctly

---

## 31. What to Learn Next

After ML basics, move to:

- Deep Learning
- Neural Networks
- Transformers
- LLMs
- MLOps

---

# End of ML Basics
