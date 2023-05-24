# AIN2002 Term Project

<img src="https://cdn.bau.edu.tr/index/bau-OpenGraph.jpg" width=500>

## Introduction

A stroke, also known as a brain attack, occurs when a blood vessel in the brain is blocked or ruptured. This leads to damage or death of certain parts of the brain, resulting in potential long-term brain impairment, disability, or even death. Stroke ranks as the second most common cause of death worldwide. Factors such as metabolic risks (e.g., high blood pressure, high body-mass index, or elevated cholesterol levels) and behavioral factors (such as smoking, poor diet, and lack of physical activity) can increase the risk of experiencing a stroke.

The goal is to predict stroke events given clinical features.
## Datasets

The datasets used in this project are publicly available from <a href='https://www.kaggle.com/'>Kaggle.com</a>

<ol>
 <li><a href="https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset">Real-world data: The Stroke Prediction Dataset</a></li>
 <li><a href="https://www.kaggle.com/competitions/playground-series-s3e2/data">Synthetic data: The Synthetic Stroke Prediction Dataset</a></li>
</ol>

The clinical features in datasets are the following:
<ul>
  <li>id: unique identifier</li>
  <li>gender: "Male", "Female" or "Other"</li>
  <li>age: age of the patient</li>
  <li>hypertension: 0 if the patient doesn’t have hypertension, 1 if the patient has hypertension</li>
  <li>heart_disease: 0 if the patient doesn’t have any heart diseases, 1 if the patient has a heart disease</li>
  <li>ever_married: "No" or "Yes"</li>
  <li>work_type: "children", "Govt_jov", "Never_worked", "Private" or "Self-employed"</li>
  <li>Residence_type: "Rural" or "Urban"</li>
  <li>avg_glucose_level: average glucose level in blood</li>
  <li>bmi: body mass index</li>
  <li>smoking_status: "formerly smoked", "never smoked", "smokes" or "Unknown"</li>
  <li>stroke: 1 if the patient had a stroke or 0 if not</li>
</ul>

The training set will include both the real-world data and the synthetic data, while the test set will consist solely of the synthetic data. It should be noted that the labels for the test set are not disclosed, and thus the true outcomes of the synthetic data will not be available for evaluation. To assess the performance of the model on the test set, predictions will be submitted to the Kaggle competition from which the synthetic data was obtained. The competition will provide scores based on accuracy or other evaluation metrics, enabling a comparison of the model's performance with that of other participants.

<b>Note:</b> The Jupyter notebook provides more detailed steps in each operation.

## Data Cleaning

The first step is to perform data cleaning by using Numpy and Pandas libraries. As the data consists of two training sets, the method .concat() is used to merge the dataframes.
The dataframe has no duplicate rows since .duplicated().sum() method returned 0 as an output.
By calling the .isnull().sum() method. The output shows that only the BMI column is has missing values.
To fill in the missing values. The data was filtered by age ranges then the average BMI for each age range was calculated. Then each missing value was replaced by the corresponding output.

## Data Visualization

The data visualization process was made using seaborn and matplotlib libraries. The visualization has two parts: CategoricaL data and numerical data visualizations.

One of the main observations was that the majority of people who have never smoked yet got a risk of a stroke are females. Which makes sense since females got a higher risk of having a stroke.

## Data Modeling

Before making any prediction it is important to prepare the data by converting categorical data's values to numerical using dictionnaries and the .replace() method. This process is done for both the train and test sets.

By importing linear regression from sklearn.linear_model, the stroke column is dropped from the train set and the stroke column is set as the train target. Once the model is fit the method .predict() is called by passing the test set to it and the output is written into a csv file.

By submitting the results to kaggle, the predictions got a score of 90% accuracy.

## Contributing

<ul>
 <li>Mohammed Diouri</li>
 <li>Atena Jaafari Parsa</li>
 <li>Ava Arabi</li>
</ul>
