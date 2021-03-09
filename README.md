# BDA-Project
HIV Cases and Deaths Analysis

HIV is defined as "human immunodeficiency virus”, damages the body's defences and  if left untreated,- eventually triggers AIDS. Although there is no cure for a HIV infection, timely treatment gives patients a good chance of leading an almost completely normal life with HIV. The proposed project aims to use machine learning techniques to address a variety of questions related to the rate HIV infection rates. The source of data for analysis is freely available from Kaggle. This dataset includes detailed global data for HIV case numbers, death figures and Antiretroviral therapy statistics from 2000 – 2018.

IEEEkeywords
HIV, AIDs, ART, Linear Regression, Principal Component Analysis, Random Forest, Visualisation, Algorithm, Machine Learning

Introduction
HIV, or human immunodeficiency virus, is a retrovirus that affects an infected person's immune system. The immune system is the innate protection of our bodies against harmful microorganisms, such as bacteria, viruses and fungi that may attack our body (CDC,2021).

Patients develop AIDS syndrome in the final stage of HIV infection. Acquired Immune Deficiency Syndrome, or AIDS, is the most severe type of infection caused by the HIV or human immune deficiency virus. HIV causes the gradual, constant, and cumulative degradation of part of the immune system, which leads to its collapse and causes the illness called AIDS. Treatment removes this damage and when provided at an early stage of the disease, can help restore defences on most affected patients (HIV, 2021).

There are reportedly about 2.5 million people infected in the West and 80,000 new infections a year. The number of new infections has not increased substantially over the past 10 years, suggesting that new steps in therapies need to be taken to contain the epidemic (UNAIDS, 2021).

Present HIV therapy consists of a mixture or "cocktail" of antiretroviral medications, usually three drugs from two or more types. In addition, certain combination antiretroviral therapy (ART) regimens contain a drug that enhances or prolongs sensitivity to one or more medications to the regimen due to deliberate drug interactions. HIV drugs can help lower your viral load, combat diseases, and increase your quality of life. They will lower the risk of HIV transmission, but if you used incorrectly, you can still give HIV to others (Peace Health,2021).


Aims
The aim of this project is to data analytics techniques on data freely available from Kaggle to answer the following questions:

1) What are the trends in HIV transmission by region?
2) How many patients need antiretroviral therapy (ART)?
3) Is there a corelation in countries with high use of antiretroviral therapy and HIV death rate?

PySpark and Pandas were the main data analytics features used with Google CoLabs to answer the above questions. 

Data Description
The HIV dataset available on Kaggle consists of 6 CSV files with each file containing data on different aspects of the HIV the epidemic. The data from Kaggle encompasses data available from WHO and UNICEFT sources. This data was then stored on my personal github \cite{github}. This data set was selected as it contains a vast amount of detailed data which can be analysed. The available CSV files are: 

- art coverage by country clean.csv
Data selection covers Antiretroviral Therapy (ART) coverage among people living with HIV. 

- art pediatric coverage by country clean.csv
Subset of total antiretroviral therapy data relating to coverage among children only. 

- no of cases adults 15 to 49 by country clean.csv
Data selection consisting of the prevalence of HIV among adults aged 15 to 49 among different countries from 200 – 2018. 

- no of deaths by country clean.csv
Data containing the number of deaths due to HIV/AIDS 49 among different countries from 2000 – 2018. 

- no of people living with hiv by country clean.csv
Data containing the estimated number of people living with HIV. 

- prevention of mother to child transmission by country clean.csv
Data containing the number of pregnant women living with HIV who received preventative mother-to-child transmission.

Ideally, more data would be available i.e., gender and age are not available from the dataset. This could have added to additional breakdown of the data analysis.

Data Pre-Processing
Data is often imperfect, unreliable and is expected to produce several mistakes. Data pre-processing is often required to transforms raw data to a readable format. Pre-processing data is an established way of solving these kinds of problems. Data pre-processing prepares raw data for further processing. Pre-processing of the selected data was completed using Pyspark and Pandas. Pandas is an open-sourced software for Python programming intended for data processing. Pandas was selected for its ease of use.  Pyspark is an api of python which supported Apache Spark (Towards Data Science, 2021).
Data was imported from github to Google CoLab using pyspark. Pyspark dataframes have then been created to contain the imported csv files. This has been completed for all the csv files listed above in the “Data Definition” section.

Dataframes are joined together using the ‘country’ field. The join combines two dataframes together. The ‘Who Region’ of the second dataframe will be dropped otherwise it will be duplicated in the new dataframe. The join is necessary to complete analytics which will be mentioned in a future section of this report. Due to the join, further data cleansing is required. Duplicated rows and coloumns are then removed from the dataframe.

Analytics
This section explores exploratory analysis, visualisation, feature engineering and machine learning results. Code was added to the python file to examine the dataset after the pre-processing completed.

Exploratory Analysis
After the cleaning process, the next step of analytics is the completion of the exploratory research. Exploratory Research is the original analysis of data for the identification of patterns and trends. The data was analysed and summarized for the key characteristics and then used for visualization.
The dataset was initially summarised into 5 statements:

- HIV cases count by WHO Region.
- Explore HIV cases count by country.
- Explore number of children receiving ART by country. 
- Explore number of deaths per country.
- Explore cases that could have prevented by mother-child transmission.

To complete the statements, the dataframes were grouped by region or country and required filed was summed.

Visualisation
Data visualization is then applied to the results of the exploratory study to reflect patterns in a more open manner. The above exploratory analysis statements were then transformed into visualisations. The previously created spark dataframes were converted to panda dataframes for visualisation to be created successfully. The “matplotlib.pyplot”  and “seaborn” libraries were imported when the file was initially created. Each matplotlib and seaborn function created a visualisation based on a dataframe such a creating a figure, creating a plotting area, labels etc  (matplotlib, 2021).

Feature Engineering
Feature engineering is the method of converting raw data into features that best reflect the underlying issue of predictive modelling, resulting in increased model accuracy of unknown data. For this dataset, numerical features had calculations applied to them to get the maximum, minimum, mean and standard deviation. These features were then rescaled to resolve any numerical instability issues. A graph was then created to display the log scale.

Machine Learning
Machine learning is a data processing system that automates analytic modelling process. The data was split for training and testing purposes. Three machine learning models were attempted on this dataset.

Linear Regression
Linear regression is a supervised learning algorithm used in Machine Learning. It approximates model the relationship between a dependent scalar variable and explanatory variable. As a supervised machine learning algorithm, it learns by itself and obtains a line through the data which represent the prediction trend. For this project, we used scikit-learn to train the model (realpython, 2021)


Random Forest
Random Forest is a decision tree-based supervised machine learning technique. The advantage of this over linear regression it that you can get better performance for similar training performance. RandomForesetClassifier was chosen to create the decision trees (datacamp, 2021).

Principal Component Analysis
Principal Component Analysis is a feature extraction technique where inputs are combined to eliminate the less important variables and keeping the more important variables. Principal Component Analysis measures how each variable is associated and the direction of how data is scattered. Principal Component Analysis standardises the input data and this is completed by using scikit-learn (towardsdatascience, 2021).

Conclusion
The project presented an incentive for training in the implementation of data analytics tasks using the Python language. Python is used for the pre-processing, visualisations and machine learning. Pyspark and pandas have found to be an effective way of cleaning and processing CSV files with ease. Although machine learning models were attempted, I was not able to construct them properly and this aspect of the project was unsuccessful. 

Future Work
In the future, I will put more emphasis and greater caution should be taken in the initial review of the results. As work progressed on this project, it became noticeable that some worthwhile data such as gender and age was missing.

Bibliography
CDC.gov. 2021. What is HIV? [online] Available at: https://www.cdc.gov/hiv/basics/whatishiv [Accessed 04 March 2021].
HIV.gov. 2021. HIV Basics. [online] Available at: https://www.hiv.gov/hiv-basics/overview/about-hiv-and-aids/what-are-hiv-and-aids [Accessed 03 March 2021].
UNAIDS. 2021. Fact Sheet. [online] Available at: https://www.unaids.org/en/resources/fact-sheet [Accessed 03 March 2021].
Peace Health. 2021. Medical Topics. [online] Available at:	https://www.peacehealth.org/medical-topics/id/[Accessed 03 March 2021].
github. 2021. BDA Project. [online] Available at: https://github.com/conormcglinchey/BDA-Project [Accessed 03 March 2021].
Towards Data Science. 2021. Python Data Preprocessin using Pandas dataframe spark dataframe and koalas dataframe. [online] Available at: https://towardsdatascience.com/python-data-preprocessing-using-pandas-dataframe-spark-dataframe-and-koalas-dataframe-e44c42258a8f [Accessed 03 March 2021].
Matplotlib. 2021. Matplotlob. [online] Available at:	https://matplotlib.org/ [Accessed 03 March 2021].
Real Python. 2021. Linear Regression in Python. [online] Available at:	https://realpython.com/linear-regression-in-python/ [Accessed 03 March 2021].
Data Camp. 2021. Random Forest Classifier. [online] Available at:	https://www.datacamp.com/community/tutorials/random-forests-classifier-python [Accessed 03 March 2021].
Towards Data Science. 2021. PCA using scikit learn. [online] Available at:	https://towardsdatascience.com/pca-using-python-scikit-learn-e653f8989e60 [Accessed 03 March 2021].
