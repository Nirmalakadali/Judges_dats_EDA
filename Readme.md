# Indian Judicial data Classification


Cases have distinct features, which can be used to classify them into different categories. This project aims to classify cases into binary categories of criminal vs non-criminal cases from a real world big dataset. The dataset used is from the [Development Data Lab](https://www.devdatalab.org/).
## About the Code

The code is written in Python on a Jupyter Notebook, and it uses the following libraries:
- pyspark
- pandas
- matplotlib
- os
- numpy
- geopandas
- seaborn
- time
- iamgeio
- plotly
- plotly.express
- matplotlib.animation
- matplotlib.pyplot
---


## Approach

The code is divided into 3 parts:

### 1. Forming the Dataframe

The data from the `cases` folder is read, where only the files that contain information after the year 2015 are considered due to the huge size of the dataset. The data is then stored in a dataframe, where the columns to the considered are predefined to reduce the time taken for the operation.

`acts_sections` csv file is read next while considering relevant columns.

These two dataframes are then concatenated to form a single dataframe by merging them based on `ddl_case_id` attribute.

### 2. Data Preprocessing

The following steps are performed to preprocess the data:

- Remove irrelevant columns
- Fill missing values with the mode
- Replace all non finite values with nan and drop the nan values
- Drop the duplicate rows

Apart from these, the columns containing the gender of the defendants and petitioners were processed to remove the irrelevant strings and values that are not definitive.

In order to deal with the huge size of the dataset, I have implemented downcasting of the data types of the columns to reduce the memory usage.
Ordinal encoding is performed on the categorical columns too.

To classify the cases and obtain a desirable accuracy, it is important that we consider only the relevant features. For this, I have used the `SelectKBest` function from `sklearn` to select the top 10 features that are most relevant to the classification, and I have also implemented a correlation matrix to check the correlation between the features.

### 3. Classification

The data is split into training and testing sets, and classification is performed using the following models:

- Logistic Regression
  Accuracy obtained: `0.969`

- Naive Bayes
  Accuracy obtained: `0.729`

- KNN
  Accuracy obtained: `0.889`

- Decision Tree
  Accuracy obtained: `1.00`

- Random Forest
  Accuracy obtained: `1.00`

The best classifiers from the above are Decision Tree and Random Forest.

An ROC curve is plotted for the best classifier to check the performance of the model.
![image](https://github.com/Nirmalakadali/Judges_dats_EDA/assets/99960001/c07f4d0f-66e4-4cad-b29b-4c614d0e09dc)

<br/>
<blockquote>
Graphs folder contain which were drawn in jupyter using geopandas and matplotlib, datawrapper 
</blockquote>
<br/>
<blockquote>
pdfs folder contain all the project observations, insights.
 </blockquote>

 
Codes &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- <a href="https://github.com/Nirmalakadali/Judges_dats_EDA/tree/main/codes"> click here</a>
<br/>
Pdfs &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  - <a href="https://github.com/Nirmalakadali/Judges_dats_EDA/tree/main/pdfs"> click here </a>
<br/>
Insights &nbsp;&nbsp;- <a href="https://github.com/Nirmalakadali/Judges_dats_EDA/blob/main/Insights.pdf"> click here </a>
<br/>
Graphs &nbsp;&nbsp; - <a href="https://github.com/Nirmalakadali/Judges_dats_EDA/tree/main/graphs"> click here </a>
<br/>
---
If you want to view Exploratory Data Analysis in 
 <br/> Readme then <a href="https://github.com/Nirmalakadali/Judges_dats_EDA/blob/main/judiciary.md"> click here</a>
 <br/> Webpage then <a href="https://judiciaryeda.netlify.app/"> click here</a>
<br/>
---
 
 # <b>Authors</b>
 <br/>
 Nirmala   https://github.com/Nirmalakadali

