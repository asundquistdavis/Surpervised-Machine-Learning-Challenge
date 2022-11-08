# Overview
This challenge pracitices making surpervised learning models and scoring them. The data used on the models is loan data and the goal of the models is to predict loans that default. The two types of models used are logistic regression and random forests. The logistics regression is used with and without scaling and the performance of all three is compared. All of the models are created and scored using Scikit-Learn.
# Contents
- data-and-predictions.ipynb: preps data and makes predictions about which model will perform best
- LogisticRegression
    - logistic-model-no-scaling.ipynb: perfoms and scores logistic model without scaling
    - logistic-model-scaling.ipynb: performs and scores logistic model with scaling
- RandomForestClassifier
    - random-forest-model.ipynb: performs and scores random forest model
- results-and-conclusion.ipynb: disusses the results of the three models
- Resources
    - lending_data.csv: raw data used to train and test the models
# Methodology
The target, 'loan_status', is a binary value that represents whether the loan is current or delinquent. A classifier is used to model a system with discrete outcomes such as 'loan_status'. The other 7 columns contain numeric data about the loan and debtor and the goal is to use this data to predict loan status. 
 
A logistic regression (classifier) maps data from N dimensions to a value between 0 and 1 by using the logistic equation that minimizes error on the training data. The output value is then used to classify the result via a threshold (i.e. outputs less than 0.5 classify as a 0 and outputs greater than 0.5 classify as a 1). Due to the nature of the logistic model, data that spans larger ranges will be biased compared to smaller data. Because of this, logistic models are at risk of overfitting data that is **not** scaled. 
 
A random forest classifier classifies data from N dimensions by selecting the most popular outcome (0 or 1) made by many individual decision trees. This type of model does not require scaling.
 
Since the data spans different orders of magnitude across each column, a logistic classifier may not work well and may tend to overfit the data. Therefore I predict a random forest model will perform better and score a higher accuracy than an un-scaled logistic classifier for the provided credit risk data. However, when scaling the data first I expect the logistic classifier to perform with similar accuracy to the random forest. 
 
Both no scaling and scaling methods will be used with the logistic model. For the both models, I expect to have to adjust the 'max_iter' to get convergence. For the random forest model, I will be leaving 'n_estimators' at default (=100) but it is worth noting that this could also affect the accuracy of the model. 
# Conclusions
Overall, the three models performed similarly, all scoring above 99% accuracy. The initial prediction of the random forest model beating the basic logistic regression with no scaling seems to be correct. Also matching the predictions, the logistic model with scaling looks to perform the best. However it is important to point out that the accuracy scores for all of the models differ by less than 1% and there is probably not a statistical difference in the results. In other words, all of the models are performing more or less the same. There may be a slight preference to the logistic model with scaling, over the other two, as it performs about 5% better in predicting defaulting loans in terms of F1 (recall and precision show similar results).