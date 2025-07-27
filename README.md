# Fraudulent_Claim_Detection_Ravijeet_Rathore

###  Financial frauds are associated with sophisticated urban areas. But when it comes to insurance frauds, rural India has taken the lead due to various reasons. While baby steps like a fraudster database is being taken, such malpractices may not be contained without strict punishments under penal code

### Insurers have identified at least 80 districts across the country which have excelled in fraudulent claims over the past decade. They have identified rings that operate with the efficiency of a corporation with well-trained men and women who collect data with the efficiency of a 21st century start-up.

### A combination of poor due diligence in writing policies by insurance companies and the organisational efficiencies of criminals in identifying those who are on deathbed and in enlisting do.
---
## Objective

> ### The traditional approach for fraud detection is based on developing heuristics around fraud indicators. Based on these heuristics, a decision on fraud would be made in one of two ways. 

> * In certain scenarios rules would be framed that would define if the case needs to be sent for investigation. 
> * In other cases, a checklist would be prepared with scores for the various indicators of fraud. An aggregation of these scores along with the value of the claim would determine if the case needs to be sent for investigation.


### Libraries used : 
```
	*warnings
	*numpy
	*pandas
	*seaborn
	*matplotlib.pyplot
	*sklearn (specifically sklearn.model_selection, sklearn.metrics, sklearn.ensemble)
	*imblearn.over_sampling
	*statsmodels.api
	*statsmodels.stats.outliers_influence
	*sklearn.preprocessing
```

## Algorithms Used

The Algorithms used are : 

	* Linear Regression
	* RandomForestClassifier

## Project Conclusion
The objective of this assignment was to build a model to classify insurance claims as either fraudulent or legitimate to minimize financial losses for Global Insure. We approached this by preparing and cleaning the historical claims data, performing exploratory data analysis, engineering new features, and building two classification models: Logistic Regression and Random Forest.

During the data preparation and cleaning phases, we handled missing values, dropped irrelevant columns, and addressed illogical data entries. Feature engineering involved creating new features like the time difference between policy binding and incident dates and claim ratios, which could potentially provide more insightful information for the models. To address the class imbalance in the target variable (fraudulent claims being the minority class), we applied the RandomOverSampler technique to the training data.

For the Logistic Regression model, we used RFECV to select the most relevant numerical features. The model was built and evaluated on the training data, and we analyzed its performance using accuracy, sensitivity, specificity, precision, recall, and F1-score. We also determined an optimal cutoff probability by examining the trade-off between sensitivity and specificity.

The Random Forest model was built using feature importance to identify relevant features (although in this case, all features seemed to contribute). We evaluated its initial performance on the training data and used cross-validation to check for overfitting. Hyperparameter tuning with Grid Search was performed to optimize the model's performance.

Finally, both models were used to make predictions on the unseen validation data, and their performance was evaluated using the same set of metrics. Comparing the performance of the two models on the validation data is crucial to determine which model is better suited for predicting fraudulent claims in a real-world scenario.

Based on the validation results:

*   **Logistic Regression:** Showed a high specificity but a very low sensitivity. This means the model is good at correctly identifying legitimate claims (True Negatives) but struggles to identify fraudulent claims (True Positives). Its precision, recall (sensitivity), and F1-score were all very low, indicating poor performance in detecting the minority class (fraud).

*   **Random Forest:** Showed a better balance between sensitivity and specificity compared to Logistic Regression. While the overall accuracy might be lower than the Logistic Regression's specificity, the Random Forest model was able to correctly identify a notable proportion of fraudulent claims (higher sensitivity and recall) while still maintaining a reasonable level of specificity. The precision and F1-score for the Random Forest model were also higher, indicating its better ability to correctly classify positive cases among those it predicted as positive, and a better balance between precision and recall.

Considering the business objective of minimizing financial losses due to fraudulent claims, **identifying fraudulent claims (True Positives) is more critical than correctly identifying all legitimate claims (True Negatives)**. A model with higher sensitivity and a reasonable F1-score is generally preferred in fraud detection scenarios, even if it means a slightly lower overall accuracy or specificity.

Therefore, based on the validation data evaluation, the **Random Forest model appears to be more effective** in identifying fraudulent claims compared to the Logistic Regression model, demonstrating a better ability to capture the patterns associated with fraud. The insights from the Random Forest model's feature importances can help Global Insure understand which factors are most indicative of fraudulent behavior, which can inform their manual investigation processes and risk assessment strategies. For instance, examining the most important features can highlight specific claim characteristics, customer profiles, or incident details that warrant closer scrutiny.

Further improvements could potentially involve exploring other advanced modeling techniques, experimenting with different resampling or data augmentation strategies, and incorporating external data sources if available. Regular monitoring and re-training of the chosen model with new data will also be essential to maintain its effectiveness over time as fraud patterns may evolve.
