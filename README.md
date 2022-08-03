# How-does-the-frequency-of-mental-health-illness-and-attitudes-for-mental-health-vary-by-geograph

this is basic data analysis




I started doing my analysis through importing the necessary packages which as shown below
import pandas as pd 
the library which will help us import the excel file
import numpy as np 
the library for Numerical Python
import scipy 
It provides more utility functions for optimization, stats and signal processing.
import matplotlib.pyplot as plt 
the library to help us in plotting the data, visual design

I now went forward to reading the data from an absolute path which is as shown below
we use the pandas to import the dataset
dataframe=pd.read_csv(r'~/Desktop/all the analysis/survey.csv')'

Descriptive statistics are used to describe the basic features of the data in a study. They provide simple summaries of the sample and the measures. Together with simple graphics analysis, they form the basis of virtually every quantitative analysis of data. The descriptive statistics for the dataset are shown below...
the descriptive statisctics for the data
dataframe.describe()

![Screenshot (34)](https://user-images.githubusercontent.com/110429235/182375097-410ed997-f2c3-4fc9-86e1-e4c893be6169.png)


lets make a subset dataset, the columns we will be using

age=dataframe['Age']

Fam=dataframe['Fam_hist']

treat=dataframe['treat']

Mental=dataframe['Mental_h_interview']

difference=dataframe['MentalvsPhysical']

====================

we can combine this to one dataset

======
the_dataset=age,Fam,treat,Mental,difference

======
#Visualize

lets visualize the heatmap for this data
========

sns.heatmap(the_dataset)

![image](https://user-images.githubusercontent.com/110429235/182376352-71a93402-c064-4356-82a6-0e22962016f1.png)

=========

#Histogram

we can now visualize a histogram

he histogram is a popular graphing tool. It is used to summarize discrete or continuous data that are measured on an interval scale. Creating a histogram provides a visual representation of data distribution. Histograms can display a large amount of data and the frequency of the data values. The median and distribution of the data can be determined by a histogram. In addition, it can show any outliers or gaps in the data.

========

sns.distplot(the_dataset, kde=True, color="m")
![image](https://user-images.githubusercontent.com/110429235/182376546-c4056139-5153-4be1-a6a5-b48306b6d014.png)

=======

#regression

Regression Analysis, a statistical technique, is used to evaluate the relationship between two or more variables. Regression analysis helps an organisation to understand what their data points represent and use them accordingly with the help of business analytical techniques in order to do better decision-making.
sns.lmplot(x='treat', y='Mental_h_interview', data=dataframe)

The swarm plot


![image](https://user-images.githubusercontent.com/110429235/182378214-9627b7d7-c5cd-4a6f-bf99-cbc4854814eb.png)


sns.barplot(x ='MentalvsPhysical', y ='Fam_hist', data = dataframe,  
            palette ='plasma')


![image](https://user-images.githubusercontent.com/110429235/182378308-bbe5abcc-a5e4-4ae5-aa9f-033e90c7fd50.png)


sns.countplot(x ='Age', data = dataframe) 


![image](https://user-images.githubusercontent.com/110429235/182378482-63b10f63-d2d9-4287-86e6-c04e169d62ed.png)


sns.countplot(x ='treat', data = dataframe)


![image](https://user-images.githubusercontent.com/110429235/182378550-7b009678-35ea-4d1b-b625-fbf5030c29e6.png)


sns.countplot(x ='Mental_h_interview', data = dataframe) 


![image](https://user-images.githubusercontent.com/110429235/182378598-be52180f-280d-417f-b50d-d3d593feeb08.png)


sns.countplot(x='MentalvsPhysical', data=dataframe)


![image](https://user-images.githubusercontent.com/110429235/182378673-61165e25-0369-4577-90bd-eb0b6749caec.png)


From the above shown graphs, we can conclude that alot of people doesnt know if they are having either physical or mentor issues. there is a higher number of people who are suffering from mental and physical issues
For the mental interview, the number of no answers is less as compared to those who gave yes and "I dont know" as their answers. 


