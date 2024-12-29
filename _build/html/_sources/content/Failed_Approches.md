# Failed Approaches on Problem Solving

Even with careful planning, data-driven projects sometimes fail or underperform. Below are three examples of failed approaches, the datasets used, and how I improved my thinking based on those experiences.

```{contents} Table of Contents
:depth: 2
```

---

## 1. Overfitting with Limited Data

- **Scenario**: Attempting to build a classification model on a small dataset with insufficient validation.  
- **Dataset Link**: [Titanic - Machine Learning from Disaster (Kaggle)](https://www.kaggle.com/c/titanic)

### What Happened
- Trained a complex neural network on a very small subset of training data.  
- Achieved near-perfect accuracy on training data but performed poorly on unseen data (classic overfitting).

### Lessons Learned
1. **Cross-Validation**: Always use proper cross-validation to estimate out-of-sample performance.  
2. **Simpler Models First**: Sometimes a simpler model (e.g., logistic regression) generalizes better.  
3. **Data Quantity & Quality**: Acquire more data or perform data augmentation if possible.

---

## 2. Ignoring Missing Data

- **Scenario**: Building a house price prediction model but dropping columns with missing values outright.  
- **Dataset Link**: [House Prices - Advanced Regression Techniques (Kaggle)](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)

### What Happened
- Many records had partial information, and ignoring them reduced the dataset size significantly.  
- Important features were lost, leading to a biased and underperforming model.

### Lessons Learned
1. **Handle Missingness**: Use imputation strategies (mean, median, mode, or advanced imputation).  
2. **EDA**: Thorough exploratory data analysis often reveals patterns in missingness.  
3. **Domain Expertise**: Sometimes data is “missing” because it’s simply not recorded or irrelevant; domain experts can clarify.

---

## 3. Using the Wrong Metric for Credit Risk

- **Scenario**: Evaluating a credit risk model solely on accuracy.  
- **Dataset Link**: [Give Me Some Credit (Kaggle)](https://www.kaggle.com/c/GiveMeSomeCredit)

### What Happened
- Because the majority of borrowers did not default, the model had high accuracy but did a poor job identifying those who *would* default.
- This led to missed detections of risky borrowers.

### Lessons Learned
1. **Imbalanced Datasets**: In cases like fraud detection or credit risk, accuracy is not enough.  
2. **Alternative Metrics**: Precision, recall, F1-score, or ROC-AUC might be more relevant.  
3. **Business Context**: Always align metrics with the actual cost of false positives vs. false negatives.

---

## How I Improved My Thinking

1. **Iterative Approach**  
   I now iterate on model design, data preprocessing, and metric selection early and often, incorporating feedback loops.

2. **Metric Alignment**  
   I choose metrics that reflect real-world objectives—whether it’s reducing false negatives in fraud detection or capturing critical edge cases in healthcare.

3. **Continuous Learning & Validation**  
   I retrain and revalidate models to ensure they remain accurate over time. Business environments and data distributions can change, so static models often fail.

4. **Domain Collaboration**  
   Engaging domain experts helps clarify nuances in data collection, business objectives, and regulatory constraints.

By embracing these lessons, I’ve become more effective at building robust, ethical, and business-aligned ML solutions.
