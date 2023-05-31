# EXP 10- DATA SCIENCE PROCESS ON COMPLEX DATA SET

# DATE:
COLAB LINK:https://colab.research.google.com/drive/1NVXuiyaSNIa2AyA1-P9UxAfYcm096ZPl?usp=sharing#scrollTo=AtcHuSxyhtAK

# AIM

Perform Data Science Process on a complex dataset and save the data to a file

# ALGORITHM

STEP 1: Read the given Data

STEP 2: Clean the Data Set using Data Cleaning Process

STEP 3: Apply Feature Generation/Feature Selection Techniques on the data set

STEP 4: Apply EDA /Data visualization techniques to all the features of the data set

# PROGRAM

import pandas as pd


import numpy as np


import seaborn as sns


import matplotlib.pyplot as plt


import io


from google.colab import files


uploaded = files.upload()


dd = pd.read_csv(io.BytesIO(uploaded['FlightInformation.csv']))


print(dd)


sns.barplot (x=dd['Duration'],y=dd['Price'])


sns.barplot(x=dd["Arrival_Time"],y=dd["Price"],data=dd)


states=dd.loc[:,["Duration","Price"]]


states=states.groupby(by=["Duration"]).sum().sort_values(by="Price")


sns.barplot(x=states.index,y="Price",data=states)


plt.xticks(rotation = 90)


plt.xlabel=("Duration")


plt.ylabel=("Price")


plt.show()


dd.corr()


data = np.random.randint(low = 1, high = 100, size = (10, 10))


print("The data to be plotted:\n")


print(data)


hm = sns.heatmap(data = data)


plt.show()

# OUTPUT


