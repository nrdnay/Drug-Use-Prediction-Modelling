# Drug-Use-Prediction-Modellling
This project contains Examination of Drug_Consumption with the help of data science, data visualization, data analysis, feature engineering, data manipulation, machine learning modelling 

# About The Drug Consumption Dataset

The dataset (drug_consumption) used for the project includes research results conducted among 1885 participants. The data includes 13 features (inputs) consisting of participants' ID numbers, demographic information (age, gender, education, country, ethnicity) and results of various psychoanalytic tests (Nscore, Escore, Oscore, Ascore, Cscore, Impulsive, SS). Names of the psychological tests conducted and the values they measure:\
**Nscore:** Neuroticism\
**Escore:** Extraversion\
**Oscore:** Openness\
**Ascore:** Agreeableness\
**Cscore:** Conscientiousness\
**Impulsive:** Impulsiveness\
**SS:** Sensation seeking\
Each feature contains numerical data, but each of these numbers represents a category. It does not carry a real numerical value. Psychology test results, education and age data represent ordered categorical variables, while gender, country and ethnicity data represent non-ordered categorical variables. .

The data includes 19 targets (outputs) that provide information about the participants' consumption of addictive or narcotic substances. Each target consists of 6 separate categories that provide information about substance use. Explanations of the categories:
**CL0:** Never Used\
**CL1:** Used over a Decade Ago\
**CL2:** Used in Last Decade\
**CL3:** Used in Last Year\
**CL4:** Used in Last Month\
**CL5:** Used in Last Week\
**CL6:** Used in Last Day\

**Data set link :**  https://archive.ics.uci.edu/dataset/373/drug+consumption+quantified

__*__ There is no missing data in the data set.

__*__ Data types consist of object and float 64.

__*__ Each float64 numeric data represents a category. It does not carry a real numeric value.

__*__ Object data is string data that carries information about substance use.

Preliminary operations applied to the data set:
__*__ First of all, in order to make the data set more understandable, the meaning equivalent of each category in the data set, except for the psychological test results, was written.

### Preliminary operations performed after the examinations in the target group: 

__*__ Each target consists of 7 categorical data (multiclass) and these categorical data are sequential. Therefore, LabelEncoder was applied to the entire target group.

__*__ Three different drug types were selected as targets for the prediction model: VSA, Meth and Heroin. 4 different machine learning prediction models will be created for each.

__*__ VSA is class of volatile substance abuse consumption, Meth is class of methadone consumption, Heroin is class of heroin consumption.

__*__  Reason for selection: -*Each class in the multiclass has a sufficient number of observations for 5-fold cross validation and provides higher accuracy values in the model.

In the feature group, pre-processing after the examinations:

__*__ Gender, Country and Ethnicity features contain non-ordered categorical data, while Age and Education contain ordered categorical data. OneHotEncoder was applied to these 4 inputs with get _dummies.

__*__ Gender distribution in the data is balanced.

__*__ Country is mostly from USA and UK, while Ethnicity is mostly from White. There are roughly 5% less categories in Age and Education. Those with this status were collected under the name of "Other".

__*__ Nscore, Escore, Oscore, Ascore, Cscore, Impulsive, SS features belonging to psychological measurements have a more balanced distribution, numerical data and ordered categories within themselves. Therefore, no pre-processing was applied.

__*__ Psychological measurement SS and Impulsive have high correlation: 0.62. SS was not included in the model. (The result did not change much.)

### Methods Applied to Data:

Random Forest Classifier, Logistic Regression, Support Vector Machine, K-Neighbors Classifier.

## The operations performed on the dataset before and after each pre-processing:

__*__ After each pre-processing applied to the dataset, Backward Feature Selection was performed for all 4 models. In Feature Selection, 3 different metrics were used for performance measurement: accuracy, roc_auv, precision micro

__*__ With the selected features, Grid Search was performed to determine the parameters in which these 4 models showed the best performance. 5-Fold Cross Validation was applied while Grid Search was performed.

__*__ 3 different metrics were preferred for performance measurement: accuracy, roc_auc_ovr, precision micro. Roc_auc_ovr was taken as the basis for model parameter preference.

__*__ With the determined parameters, cross_val_score 5-fold cross validation was applied to calculate standard deviation and score values.

__*__ The performances of each model were compared according to the results obtained.

__*__ All the operations listed above were performed in Heroin, Meth and VSA, which were determined as targets.

It was seen that the above operations, which were applied step by step after each pre-processing, did not have a serious effect on model performance. Therefore, in this report, the feature selection and modeling performance results after all the pre-processing were applied were reported.

## AS A RESULT;
__*__ In this project, Random Forest, Logistic Regression, Support Vector Machine, K-Neghbours (KNN) machine learning (ML) models were applied for VSA, Meth and Heroin.

__*__ Logistic Regression can be preferred among the 4 models because it is less complex and shows better performance than other models.

__*__ According to the established ML prediction models, the model with the highest accuracy rate is Heroin with 85%. In other words, we can predict whether a person uses Heroin with 85% accuracy.

__*__ The adequacy of the test performance result must be evaluated according to the place of use of the model.

__*__ Combining a small number of categories in the data will be a correct approach to increase the efficiency of the model and will provide easy interpretation.

__*__ The correlation between SS and Impulsive is high and it's not necessary to add SS to the model in order to increase model eficiency.





