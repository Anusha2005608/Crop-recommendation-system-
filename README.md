# Crop-recommendation-system-
# agriculture production optimization engine
# for manipulation
import numpy as  np
import pandas as pd
# for visualization
import matplotlib.pyplot as plt
import seaborn as sns
# for interactiveness
from ipywidgets import interact
from google.colab import files
uploaded = files.upload()
# Use the correct filename from the 'uploaded' dictionary
d = pd.read_csv('cropdata (2) (1).csv') 
print("shape of dataset :",d.shape)
# head of our dataset
d.head()
# checking the missing values in the dataset
d.isnull().sum()
print("shape of dataset",d.shape)
# head of our dataset
d.head()
 # checking the missing values in the dataset
d.isnull().sum()
# name of crop present our dataset
d['label'].value_counts()
# check the summary for all the crop
print("average ratio of phosphorous in the soil :",format(d['P'].mean()))
print("average ratio of potassium in the soil :",format(d['K'].mean()))
print("average ratio of nitrogen in the soil :",format(d['N'].mean()))
print("average temperature in celcius:",format(d['temperature'].mean()))
print("average humidity in %:",format(d['humidity'].mean()))
print("average ph value of the soil :",format(d['ph'].mean()))
print("average rainfall in mm :",format(d['rainfall'].mean()))
# check the statistic for each crop
@interact
def summary(crop = list (d['label'].value_counts().index)):
    x = d[d['label']  ==  crop  ]
print("........................................")
print("statistics for potassium")
# check the summary statistc for each crop
@interact
def summary(crop = list(d['label'].value_counts().index)):
    x = d[d['label']==crop]
    print(".............................")
    print("statistic for potassium ")
    print("minimum potassium required:",x['K'].min())
    print("average potassium required:",x['K'].mean())
    print("maximum potassium required:",x['K'].max())
    print(".............................")
    print("statistic for nitrogen")
    print("minimum nitrogen required :",x['N'].min())
    print("average nitrogen required :",x['N'].mean())
    print("maxmum nitrogen required :",x['N'].max())
    print("..................................")
    print("statistic for phosphorus")
    print("minimum phosphorus required:",x['P'].min())
    print("average phoshorus required :",x['P'].mean())
    print("maximum phoshorus required:",x['P'].max())
    print("satistic for temperature")
    print("minimum temperature required:{0:.2f}".format(x['temperature'].min()))
    print("average temperature required:{0:.2f}".format(x['temperature'].mean()))
    print("maximum temperature required:{0:.2f}".format(x['temperature'].max()))
    print(".....................................")
    print("statistic for humidity")
    print("minimum humidity required:{0:.2f}".format(x['humidity'].min()))
    print("average humidity required:{0:.2f}".format(x['humidity'].mean()))
    print("maximum humidity required:{0:.2f}".format(x['humidity'].max()))
    print("......................................")
    print("statistic for ph")
    print("minimum ph required :{0:.2f} ".format(x['ph'].min()))
    print("average ph required :{0:.2f} ".format(x['ph'].mean()))
    print("maximum ph required :{0:.2f} ".format(x['ph'].max()))
    print("........................................")
    print("statistic for rainfall")
    print("minimum rainfall required :{0:.2f}".format(x['rainfall'].min()))
    print("average rainfall required :{0:.2f}".format(x['rainfall'].mean()))
    print("maximum rainfall required :{0:.2f}".format(x['rainfall'].max()))
    
