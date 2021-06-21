# Credit Risk Evaluation Model - Analysis Report

## Analysis Overview

The purpose of this analysis is to have 2 models predict the status on loans that a business lends out.  In other words, how likely are borrowers to keep up timely payments on loans, or how likely are they to be behind or default on their loans.  In order for the models to be trained to best predict loan statuses, it will take in a dataset based on borrowers' loan amount, interest rate, income, debt-to-income ratio, number of accounts, deragotory marks, and total debt amounts.  The target values used to help train the model to predict loan statuses are the loan statuses from the dataset.

The machine learning process for this analysis first involves splitting the dataframe from the target values and the feature values.  Once the split is made, we then create training and testing data for the target and feature values separately.  After creating an instance of the model (which in this case is a **Logistic Regression** model), we fit the training feature and target values in the model in order to train the model.  After the model is trained, we then have it predict target values based on the testing features.  We then follow the **model-fit-predict** process again on the **resampled** dataset by using the **RandomOverSampler** module.


## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Logistic Regression - Model 1:
  * Balanced Accuracy Score - 95%
  * For 0 (healthy loan) values:
    * Precision - 100%
    * Recall - 99%
  * For 1 (unhealthy loan) values:
    * Precision - 85%
    * Recall - 91%

* Logistic Regression (Resampled) - Model 2:
  * Balanced Accuracy Score - 99%
  * For 0 (healthy loan) values:
    * Precision - 100%
    * Recall - 99%
  * For 1 (unhealthy loan) values:
    * Precision - 84%
    * Recall - 99%


## Summary

After running 2 models, one based on the normal dataset and the other on the oversampled dataset, we can conclude that the model based on the resampled data performs better than the unsampled data model.  With the resampled model, we have an increase in the balanced accuracy score, closer to 100%.  When looking at the 0 value predictions for both models, there is not much change.  However, when we look at how the models predict the 1 values, the resampled model has a higher recall value even though we lose a little bit of precision.  We would want a higher recall score because in the case of analyzing loan default risks, we want the model to predict how likely a loan is to default, rather than how likely someone makes on-time payments.  In conclusion, the **Resampled Logistic Regression** model is the better model to predict the loan default risks.
