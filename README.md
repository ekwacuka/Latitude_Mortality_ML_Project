## Latitude_Mortality_ML_Project
###  Analyze, manupilate and visualize the Latitude and Mortality csv dataset using a variety of Machine Learning tools. 
#### Import the necessary Libraries to be used 
* import pandas as pd
* from pandas import DataFrame
* import numpy as np
* import matplotlib.pyplot as plt
* import seaborn as sns
* from statsmodels.formula.api import ols
* import statsmodels.api as sm

#### Create a dataframe from the csv file

* df = pd.read_csv(r"C:\Users\Emily Kimani\Desktop\Adv_Python\Machine_Learning\lmdata.csv")

![image](https://user-images.githubusercontent.com/77937714/113612184-7b31a080-961d-11eb-9902-6319de0bb512.png)

#### Generate descriptive statistics for the data

* df.describe()

![image](https://user-images.githubusercontent.com/77937714/113612331-b207b680-961d-11eb-8517-67cee21bac66.png)

#### Create a line plot for the variables. Add a title and x & y axes.
 ##### a) Beautify the x-labels
 ##### b) plot a line graph

* sns.lineplot('mortality', 'latitude', ci=None, color="red", marker='o', data=df)

![image](https://user-images.githubusercontent.com/77937714/113612745-3823fd00-961e-11eb-8b17-189d9fefeae0.png)

#### Create a scatter plot / Add title and (X,Y) axis names
* plt.figure(figsize=(10,6))    ## Increase the size of the Seaborn plot
* sns.scatterplot(x="mortality", y="latitude", data=df)   ## Make a scatter plot
* plt.xlabel("Mortality", size=16)   ## X axis label and set the size
* plt.ylabel("Latitude", size=16)      ## Y axis label and set the size
* plt.title("Mortality vs Latitude", size=24, color="blue")  ## Set Seaborn Plot Title

![image](https://user-images.githubusercontent.com/77937714/113613144-c4cebb00-961e-11eb-9402-e5aeb9be6e39.png)

#### Create a Seaborn boxplot for mortality
* plt.figure(figsize=(10,6))
* emily = sns.boxplot(x="mortality", y="latitude", data=df)
* plt.xlabel("Mortality", size=16)   ## X axis label and set the size
* plt.ylabel("Latitude", size=16)      ## Y axis label and set the size
* plt.title("Mortality vs Latitude", size=24, color="green")  ## Set Seaborn Plot Title

![image](https://user-images.githubusercontent.com/77937714/113613304-06f7fc80-961f-11eb-8e9c-445ab221c61f.png)

#### Create a Matplotlib Boxplot

* fig = plt.figure(figsize =(10, 7))
*  Creating axes instance
* ax = fig.add_axes([0, 0, 1, 1])
*  Creating plot
* bp = ax.boxplot(df)
*  show plot
* plt.show()

![image](https://user-images.githubusercontent.com/77937714/113613569-68b86680-961f-11eb-9922-8e0e8892c364.png)

#### Conduct a Pearson’s correlation test for the variables

![image](https://user-images.githubusercontent.com/77937714/113613757-a7e6b780-961f-11eb-8540-67bde4d048b6.png)

#### Create a pairs plot for the data
* sns.pairplot(df)   

![image](https://user-images.githubusercontent.com/77937714/113613959-debccd80-961f-11eb-9567-7ce3425445bf.png)

#### Type in this command: from statsmodels.formula.api import ols
* from statsmodels.formula.api import ols

#### Create a Seaborn regplot of the regression model

* sns.regplot(x="mortality", y="latitude", data=df);

![image](https://user-images.githubusercontent.com/77937714/113614647-c8634180-9620-11eb-8f9c-b46628fc4131.png)

* sns.lmplot(x="mortality", y="latitude", data=df);

![image](https://user-images.githubusercontent.com/77937714/113614770-e8930080-9620-11eb-997c-e3955d383823.png)

#### Create the regression model using ols() from the statsmodel package
* x = df[['mortality']] 
* y = df['latitude']
* x = sm.add_constant(x) 
* model = sm.OLS(y, x).fit()
* predictions = model.predict(x) 

#### Print the model Summary
* print_model = model.summary()
* print(print_model)

![image](https://user-images.githubusercontent.com/77937714/113615066-5f2ffe00-9621-11eb-9e90-f8b39d6cc411.png)
















