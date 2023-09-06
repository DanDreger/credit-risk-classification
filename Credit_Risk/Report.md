# Credit Risk Classification Model Overview

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

A certain amount of risk is simply the cost of doing business in the lending business. Some percentage of the loans will be paid back, and some percentage will not. So, the better a lending company is at assessing the risk of the borrower, the more profitable it can be – and the less likely it is to go out of business.

But with large datasets, it can be difficult to detect patterns or determine risk. An effective classification model can identify patterns, limit unpredictability, decrease risk, and guarantee profitability.

## The Data

77,535 Loans were analyzed and the following factors were taken into consideration

* Loan Size
* Interest Rate
* Borrower Income
* Debt to Income
* Number of Accounts
* Derogatory Marks
* Total Debt

The model uses these data features to identify a borrowers likelihood to default on a given loan. Data comes from a csv file called lending_data.csv, located in the Resources directory.

## Model Results

A LogisticRegression model proves highly accurate for determining the riskiness of a loan. 

Two models were built for the dataset. The first model used the above features to determine the riskiness of a loan. Here are The results

* **Accuracy:** 99% of the predictions made by the model were correct, using data reserved to test the model
* **Precision:** This model has no false positives among loans which do not default. However, it is less precise amont defaulting loans at only 88%
* Recal: The model captures positive instances effectively, capturing 91% of loans about to default, and 99% of loans which do not.

However, risky loans are outnumbered by non-risky loans by more than 30 to 1. This imballence could be affecting the accuracy of the model on defaulting loans. So, after using the RandomOverSampler module from imblearn to even out loan defaults with non-defaults, we created a new model. This new model can predict, with over 99% accuracy, the riskiness of a loan.

* **Accuracy:** Using the testing data, the model correctly predicted all of the defaults after being trained
* **Precision:** The Model does an excellent job of eliminating false positives. The Model had no false positives among loans that did not default. The model had false positives on only 1% of the defaulted loans.
* Recal: The Model does an excelent job of capturing positive instances. All the positive instances were captured for loans that did not default. And the model caught 99% of the positive instances for loans that defaulted.
* Overall: The f1 score for the model was 99% for loans that defaulted and 100% for loans that did not default.

Using this model would eliminate almost all defaulted loans from the portfolio, increasing profits, mimizing risk, and reducing uncertainty among borrowers.

## Summary

Using this model would eliminate almost all defaulted loans from the portfolio, increasing profits, mimizing risk, and reducing uncertainty among borrowers.

* Using RandomOverSampler increases model accuracy by 11%
* Final accuracy of the model is over 99%

I would highly recommend using the model to determine riskiness of loans in the future.
