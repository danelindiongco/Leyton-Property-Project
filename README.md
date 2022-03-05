# Leyton-Property-Project

An analysis that allow potential property buyers or sellers to explore and interact with sold property data in the area of Leyton using data from: https://www.rightmove.co.uk/house-prices/leyton.html?country=england&referrer=landingPage&searchLocation=Leyton 

The user can interact with property features such as Tenure Type (Leasehold or Freehold) and Number of bedrooms to explore sold property prices. The analysis can be found through this tableau dashboard: (I also conducted the same data visualisation using Python found in the jupyter notebook '3 - Exploratory Data Analysis')
https://public.tableau.com/app/profile/danel.indiongco/viz/PropertyPricesinLeyton/SoldPropertyDatainLeyton

Finally, the analysis concludes with a model that allows potential property sellers in the area to quickly obtain a price evaluation for their property based on their property features or for potential buyers to get an estimation for their affordability based on their requirements for a property. The model is found in the jupyter notebook '4 - Linear Regression Model'


 
 

## Analysis Notes

The analysis is split into 4 steps:
1. Gathering Data
2. Data Manipulation
3. Exploratory Data Analysis
4. Linear Regression Model

### 1. Gathering Data
This step involved webscraping Rightmove.co.uk's sold property data using requests and Beautiful Soup. The URL of the first page can be found above. Webscraping involved gathering the HTML source code for each of the available web page. Using Beautiful Soup and Node, I was able to extract a dictionary of sold properties from a javascript file. The final output from this step was a list of dictionaries: 'list_of_dicts.npy'

### 2. Data Manipulation
This step involved unpacking the list of dictionaries extracted from the previous step. I needed to flatten nested lists in dictionaries to produce a Pandas dataframe. I demonstrated my ability to manipulate different python datatypes namely dictionaries and lists and concatenating Pandas dataframes. The final output from this step was a Pandas dataframe: 'Property df.csv'

### 3. Exploratory Data Analysis
This step involved first cleaning the dataframe which involved the following steps: Correcting data types, Removing unnecessary columns and then handling missing values. I then exported the processed dataframe as: 'Processed Property Data.csv'. 

I produced a dashboard using Tableau as seen from the link above using the csv data. I then conducted the same data visualisation in Python using Matplotlib and Seaborn. The cleaned data are also used for the next step in creating a Linear Regression Model.

### 4. Linear Regression Model
This step involved first preprocessing the data by converting categorical features to numeric data using one hot encoding. This is because Machine Learning models can only take in numeric data as inputs.



## Next Steps/Areas of Improvement
My next steps for the project is to deploy the ML model as a web service for prediction. This can be done by using the Flask Web Framework to wrap the linear regression model built through Scikit-Learn. The model will then be hosted through a cloud server, maybe through AWS.

To improve the model accuracy, I can increase the number of training example by including data from similar nearby areas such as Stratford and Leytonstone. Furthermore, I had to remove many training examples due to missing 'Num_Bedrooms' data. I am able to impute the missing data as I had too few complete training examples to infer from. This also resulted in the removal of a large proportion of New Build properties as most examples had missing number of bedroom data. If I also have data from nearby areas, I will have a greater number of complete training examples and therefore, be able to impute the missing values.

When repeating the analysis, to improve the run time of the analysis for the step '2 - Data Manipulation', I would directly flatten the nested lists inside the dictionary instead of using Pandas concatenate, as manipulating Panda dataframes have slower run times. I would directly manipulate the dictionaries to the desired format then impart to a Pandas Dataframe.


Thank you for looking through the project and I hope it was useful!


