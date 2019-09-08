# KDD-Cup-2009
This case study predicts the propensity of customers to switch provider (churn), buy new products or services (appetency), or buy upgrades or add-ons proposed to them to make the sale more profitable (up-selling)

## Steps
1. Total columns/features = 233
2. Drop those columns which has 50% null values. Remaining features 72.
3. Features contains Numerical an categorical values.

### Churn
Classes are heavily unbalanced so upsamplied the data to match both the class . Balancing the whole data gives the good Test AUC Score    but when upsampling used for only train dataset got AUC score = 0.72 for Churn.
XGBClassifer is used with class weight  = Balanced. Tried with MLP Classifier , RandomForest.

![del3](https://user-images.githubusercontent.com/41810251/64491017-cab4bc80-d280-11e9-84a2-59ed75c0fe72.png)


### Appetency
Tried with DecisionTreeClassifier is used made with gini impurity criterion and Multinomial NB .Best model works best with XGBClassifier with AUC Score = 0.84.

![del2](https://user-images.githubusercontent.com/41810251/64491000-8cb79880-d280-11e9-9a28-cebdd35dfd0f.png)


### Upselling
XGBClassifier is used . AUC Score = 0.87.

![del1](https://user-images.githubusercontent.com/41810251/64490941-131faa80-d280-11e9-8864-0f19abc3fe9d.png)

Note : The Numerical data is normalized.Each model is Cross Validated.

## Conclusion
---------------------------
We can see that using upsampling on the data both train ans the test an implemeting the MLP Classifier
We are getting the good auc score around 0.95 .But using upsampling only for train set model overfits in train data.

Till now the best model is XGBClassifier with n_iteration = 100 and depth = 2 which is giving a AUC score of 0.72 for churn
It is cross validated and an tested on test data.
For Appetency XGBClassifier is best model AUC=0.84
For Upsampling XGBClassifier is best model AUC=0.87
and overall AUC =0.81



