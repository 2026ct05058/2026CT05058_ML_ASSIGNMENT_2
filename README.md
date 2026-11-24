# 2026CT05058_ML_ASSIGNMENT_2
# Machine Learning Classification Models – UCI Bank Marketing


## a. Problem Statement

To develop and compare five machine learning classification models for predicting the target class of a public dataset. The dataset is pre-processed by handling missing values, removing duplicates, encoding categorical features, and scaling numerical features. The following classification algorithms are evaluated:

The following classification algorithms are evaluated:

•	Logistic Regression
•	Decision Tree
•	K-Nearest Neighbours (KNN)
•	Naive Bayes (Gaussian/Multinomial)
•	Random Forest

Model performance is assessed using Accuracy, AUC Score, Precision, Recall, F1 Score, and Matthews Correlation Coefficient (MCC) to identify the most effective classifier and understand the impact of preprocessing and model selection on prediction performance.

## b. Dataset Description

The **UCI Bank Marketing (`bank-additional-full.csv`)** dataset is selected for the binary classification. This dataset contains features to predict whether a client subscribes to a term deposit.
This dataset has been selected because of following reasons:

- 41188 instances (> 1000 required)
- 20 features (> 12 required)
- Contains both numerical and categorical features.
- Requires missing-value handling.
- Exhibits class imbalance, allowing meaningful model comparison
- Suitable for evaluating multiple binary classification algorithms on a real-world marketing prediction problem

### Dataset information

| Item | Dataset information |
|---|---|
| Dataset | UCI Bank Marketing (`bank-additional-full.csv`) |
| Repository | [UCI Bank Marketing Dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/00222/bank-additional.zip) |
| Problem type | Binary classification |
| Objective | Predict whether a client subscribes to a term deposit |
| Target variable | `y` |
| Positive class | Yes (`1`) |
| Negative class | No (`0`) |
| Number of instances | 41,188 |
| Number of features | 20 (19 used after excluding `duration`) |
| Feature types | Numerical and categorical |
| Numerical features | age, campaign, pdays, previous, emp.var.rate, cons.price.idx, cons.conf.idx, euribor3m, nr.employed |
| Categorical features | job, marital, education, default, housing, loan, contact, month, day_of_week, poutcome. |
| Missing values | Represented by `"unknown"` |
| Duplicate records | Present |
| Class distribution | Imbalanced: `no` is the majority class and `yes` is the minority class |


### Data Preprocessing

The following preprocessing steps are applied:

1. Removed duplicate rows.
2. Removed the `duration` feature to prevent target leakage.
3. Treated categorical `"unknown"` values as missing values.
4. Encoded the target variable: `no = 0` and `yes = 1`.
5. Split the data into 80% training and 20% testing sets using a fixed random seed and stratification.
6. Imputed numerical missing values using the median calculated from the training data.
7. Imputed categorical missing values using the most frequent category from the training data.
8. Applied one-hot encoding to categorical variables and standardization to numerical variables.

## c. GitHub Repository Link
https://github.com/2026ct05058/2026CT05058_ML_ASSIGNMENT_2

## d. Models Used

- Logistic Regression
- Decision Tree
- K-Nearest Neighbours (KNN)
- Naive Bayes
- Random Forest (Ensemble)

### Comparison Table with the evaluation metrics calculated for all the 5 models as below


| Model | Accuracy | AUC | Precision | Recall | F1 Score | MCC |
|---|---:|---:|---:|---:|---:|---:|
| Logistic Regression | 0.8985 | 0.7997 | 0.6544 | 0.2101 | 0.3181 | 0.3319 |
| Decision Tree | 0.8439 | 0.6228 | 0.3166 | 0.3330 | 0.3246 | 0.2365 |
| KNN | 0.8921 | 0.7383 | 0.5380 | 0.2974 | 0.3831 | 0.3467 |
| Naive Bayes | 0.7097 | 0.7756 | 0.2409 | 0.7328 | 0.3626 | 0.2928 |
| Random Forest (Ensemble) | 0.8938 | 0.7814 | 0.5542 | 0.2920 | **0.3825** | **0.3508** |

### Metrics in visualization form for the five models (Graph Representation)
2026CT05058_ML_Assignment2
The notebook (2026CT05058_ML_Assignment2.ipynb) includes graphical comparisons of the five models using the following metrics:
- Accuracy
- AUC
- Precision
- Recall
- F1 Score
- Matthews Correlation Coefficient (MCC)

### Observations on the performance of each model on the chosen dataset (UCI Bank Marketing)

| ML Model Name | Observation about model performance |
|---|---|
| **Logistic Regression** | • Behaves as a conservative classifier, making positive predictions only when it is highly confident.• Achieves better overall accuracy(0.8985) and precision(0.6544), means that customers predicted as subscribers are likely to respond positively.• However, the model fails to identify a large proportion of actual subscribers, resulting in relatively low recall(0.2101).• This approach is suitable for organizations with limited marketing resources that prioritize minimizing unnecessary customer contacts.|
| **Decision Tree** |• More proactive in identifying potential subscribers compared to Logistic Regression.• Captures a reasonable number of customers who are likely to subscribe, improving recall (0.3330).• However, this comes at the cost of lower precision (0.3166), as many non-subscribers are also classified as potential subscribers.• Marketing campaigns based on this model may involve additional outreach efforts toward customers who are unlikely to respond.|
| **kNN** | • Delivers balanced and consistent predictive performance across evaluation metrics.• Although it does not achieve the highest score in any single metric, it provides a reliable trade-off between precision (0.5380) and recall (0.2974).• The model avoids the extreme behaviours observed in more conservative or aggressive classifiers.• This makes KNN a dependable baseline model for customer subscription prediction.|
| **Naive Bayes** | • The most aggressive model among the evaluated classifiers.• Successfully identifies the majority of actual subscribers, achieving the highest recall (0.7328).• However, its precision 0.2409 is comparatively low, means that many non-subscribers are incorrectly predicted as subscribers.• While the model maximizes customer coverage, it may significantly increase marketing costs due to a higher number of false-positive predictions.|
| **Random Forest (Ensemble)** | •Demonstrates the most stable and reliable overall performance among all models.• Effectively balances precision (0.5542) and recall (0.2920), ensuring that subscriber predictions remain both accurate and comprehensive.• The ensemble structure reduces the risk of overfitting and improves generalization to unseen data.• As a result, it offers strong predictive capability while maintaining consistent performance across multiple evaluation criteria.|
| **Overall, Winner for your dataset?** |**Random Forest (Ensemble)** is the winner model among the compared five classifiers.• It maintains a strong Precision (~0.55) while maintaining a stable Recall (~0.29• It does not suffer from the extreme 80% failure rates of Logistic Regression (on recall) or Naive Bayes (on precision).• Because of this balance, it achieves the highest overall F1-Score and MCC (Matthews Correlation Coefficient), which mathematically measure the quality of this trade-off• When we rank the models mathematically across all 6 metrics (Accuracy, AUC, Precision, Recall, F1, and MCC) and average those ranks, Random Forest consistently places near the top on average, making it the most robust, balanced model.• **Conclusion:** Among all evaluated machine learning models, Random Forest offers the best combination of predictive accuracy, recall, precision, and overall reliability, making it the preferred choice for supporting targeted marketing campaigns.|

Refer to the pdf for the screenshot of the Bits Virtual Lab








