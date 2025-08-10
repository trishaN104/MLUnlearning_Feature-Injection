# Feature Injection Test for Machine Unlearning Verification

This project explores the **Feature Injection Test**, a technique for evaluating how well a machine learning model “forgets” data after unlearning. The method involves injecting a synthetic, label-correlated feature into a subset of the training data (the *forget set*) and measuring its influence before and after unlearning.

## Overview

**Workflow:**
1. **Select Forget Set** – Identify a subset of training data to be “forgotten” (based on percentile thresholds of key features).
2. **Inject Feature** – Add a synthetic feature strongly correlated with the target label into the forget set.
3. **Train Models:**
   - **Target Model** – Trained with the injected forget set.
   - **Unlearned Model** – Trained without the forget set (or after applying an unlearning method).
4. **Compare Influence** – Analyze differences in model weights, predictions, and metrics for the injected feature between the two models.

> If the injected feature’s influence is still high in the unlearned model, unlearning may be incomplete.

## Experiments

### Datasets
- **Student Depression Dataset** – initial experiments
- **German Credit Dataset (numeric)** – primary testing

### Analysis
- Tracked changes in injected feature weights
- Compared performance metrics (accuracy, precision, recall) before/after unlearning
- Examined the effect of varying the number of unlearned points on feature influence
