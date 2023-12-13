# Investigating Power Outages Associated with Causes
by Max Yuen Sum Wong(y6wong@ucsd.edu), Chris Yuen Kei Wong(ykw001@ucsd.edu)

--- 

## Project Overview
This project will condcut an open-ended investigation into the dataset of the power outages dataset, then we will discussing a question with training a new model and compare with the original one in order to conduct some interesting analysis.

## Framing the Problem 
Based on the investigation we concluded on the previous investigation, we would like to predict the number and severity og major power outages in the year 2024, which the dataset only contains the major power outage daat in the continental U.S. from January 2000 to July 2016. And we would like to discuss the porblem in predicting the cause of a High Serverrity power outage.

Predicting the cause of a major power outage is crucial for preemptive mitigation and efficient response. Power outages have significant impacts on various sectors, disrupting critical services, industries, and daily life. Understanding the cause of a high-severity power outage allows for targeted preventive measures, such as infrastructure upgrades or maintenance, reducing the likelihood and duration of future disruptions. This proactive approach enhances overall grid reliability, minimizes economic losses, and ensures a more resilient and stable power supply.

By predicting what cause are impacting the major power outages, we can gain a better understanding of the outage duration and case distribution of the outages and identify any specific detailed or vulnerabilities associ

TO make accurate predictions, we are using the dataset on 1534 power outages cases from 200 to 2016, with 59 columns recording the information. Based one the question we investigate, this dataset includes various features such as the `'YEAR'`, `'CLIMATE.CATEGORY'`, `'OUTAGE.START'`, `'OUTAGE.RESTORATION'`, `'OUTAGE.DURATION'`, `'CAUSE.CATEGORY'`, `'CAUSE.CATEGORY.DETAIL'`, `'DEMAND.LOSS.MW'`, `'CUSTOMERS.AFFECTED'`, `'TOTAL.CUSTOMERS'`, `'HIGH_SEVERITY'`, and the list goes on.

By training a classification model usingthe data, we aim to complete a model that increase the accuracy in identify what the distribution of cause of mojor power outages in the following years. Training a classification model contributes to improved decision-making by enabling automated categorization of data, leading to more efficient and accurate predictions. In the future, this can enhance various fields such as healthcare, finance, and technology, fostering innovation, and streamlining processes for better outcomes and resource optimization. Finally, we wouldn't consider the time prediction in our model. 

## About the data cleaning 
We would use the same data cleaning we did in the previous analysis, which can be found [here] (https://kwkkei.github.io/power_outage_investigation). 

In order to increase the readability and accuracy of our data, we have commit some changes to clean the original DataFrame we get. 

1. **Create a function to combine the `'OUTAGE.START.DATE'` and `'OUTAGE.START.TIME'` into a new column named `'OUTAGE.START'` where store the datetime value of the outage starting time. Doing the same as the `'OUTAGE.RESTORATION'` column in the `'cleaned'` dataset.**
2. **Defining the `'HIGH_SEVERITY'` column where it stores the boolean values whether the `'OUTAGE.DURATION'` is greater than the high_severity_threshold which we define as the mean of `'OUTAGE.DURATION'`.**

After data cleaning, the first 5 rows of the data in the new DataFrame called `'cleaned'` would be showing, moreover, we have added new columns for the data cleaning part. See as follow:

|   YEAR | CLIMATE.CATEGORY   | OUTAGE.START        | OUTAGE.RESTORATION   |   OUTAGE.DURATION | CAUSE.CATEGORY     | CAUSE.CATEGORY.DETAIL   |   DEMAND.LOSS.MW |   CUSTOMERS.AFFECTED |   TOTAL.CUSTOMERS | HIGH_SEVERITY   |
|-------:|:-------------------|:--------------------|:---------------------|------------------:|:-------------------|:------------------------|-----------------:|---------------------:|------------------:|:----------------|
|   2011 | normal             | 2011-07-01 17:00:00 | 2011-07-03 20:00:00  |              3060 | severe weather     | nan                     |              nan |                70000 |           2595696 | True            |
|   2011 | normal             | 2011-07-08 10:00:00 | 2011-07-08 10:00:00  |                 0 | intentional attack | vandalism               |                0 |                    0 |           2595696 | False           |
|   2011 | normal             | 2011-05-11 15:55:00 | 2011-05-12 13:57:00  |              1322 | intentional attack | vandalism               |                0 |                    0 |           2595696 | False           |
|   2011 | cold               | 2011-04-19 22:44:00 | 2011-04-20 02:00:00  |               196 | severe weather     | nan                     |              100 |                64000 |           3174123 | False           |
|   2011 | normal             | 2011-06-22 09:46:00 | 2011-06-22 09:46:00  |                 0 | severe weather     | nan                     |              nan |               106300 |           3174123 | False           |


(This part is copied from the previous Project)

## Prediction Probem: Classification

In the context of predicting the cause of major power outages, training a classification model on the provided dataset is essential for identifying patterns and trends in outage causes. This predictive model can contribute to proactive decision-making by enabling the timely implementation of targeted preventive measures, such as infrastructure upgrades or maintenance, thereby reducing the likelihood and impact of high-severity power outages in the future. 

## Response Variable 

The response variable in the classification model is the `'CAUSE.CATEGORY'`, representing the cause category of major power outages. This variable is crucial for the model to learn and predict the specific factors leading to power disruptions.

## Features

Two selected features for the classification model are `'YEAR'` and `'DEMAND.LOSS.MW'`. `'YEAR'` provides temporal information, while `'DEMAND.LOSS.MW'` represents the demand loss in megawatts during an outage. These features aim to capture both temporal and demand-related aspects that may influence the cause of power outages.
A
## Metric for Evaluation 

The chosen metric for model evaluation is accuracy, as it measures the proportion of correctly predicted cause categories among all predictions. Given the multi-class classification nature of predicting outage causes, accuracy provides a straightforward and interpretable measure of overall model performance.

## Justification for Metric Choice

Accuracy is justified as the primary evaluation metric because it directly aligns with the goal of correctly classifying the causes of power outages. Given the importance of accurate predictions for informing preventive measures, a high accuracy score indicates the model's effectiveness in identifying the underlying patterns and trends in the data. However, it is essential to consider potential class imbalances and explore additional metrics, such as precision, recall, and F-1 score, to ensure a comprehensive understanding of the model's performance.

---

# Baseline Model



## Model Description



## Encoding 



## Model Performance


