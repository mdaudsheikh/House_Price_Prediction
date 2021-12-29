**Background on your code files**
  
The project was predicting the sale price of houses using the Ames housing dataset (data collected for homes in Iowa, USA). The
following files are used in the project:

    - HousePriceRegression.ipynb
    - test.csv
    - train.csv
    
The ipynb file contains code to run and displays the result of the machine learning process.
  
**How to run your code, guide to install any additional packages**

Packages to install:

    - Sklearn
    - Pandas
    - Numpy 
    - Matplotlib
    - mglearn
    
To the run the code, ensure the above packages are installed withing the virtual environment (or a regular python environment).
The notebook is to be run sequentially with each preceding cells containing code for creating important variables used later.


**Results**

The following 4 models were used. Hyper turning and Cross-Validation was performed to ensure experiment with each models compatibility
with the dataset and feature engineering:

    - Gradient Boosting Regressor
    - Decision Tree Regressor
    - Random Forest Regressor
    - Ridge Regressor
    
The models mentioned above were chosen so that tree based models can be compared to a linear regressor on mixed feature datasets. 
Hyperparameter turning was explored to determine which parameters had a greater influence on test results.
    
The Ames housing dataset (the dataset used for the analysis) is known to be feature heavy with many different types of both categorical 
and numerical features. I explored some correlation between the features using the pearson correaltion method of pandas. This revealed
trends such as rooms above grade is strongly correlated to second floor square footage.

The most important features were year built, areas and neighourhood. I discovered this my addin features one at a time to the dataset and 
column transformer. In the future I will find a more automated way to check how much influence each added features has on the results of 
different models.

The best performing model was Gradient Boosting Regressor. This is likely due to the fact that it is reduces the error at every iteration. 
Decision tree did not perform as well likely due to the fact that it fits the model on one tree instead of multiple trees like Gradient 
Boosting regressor and Random Forest regressor. Finally Ridge Regressor showed a much higher training score than test score. This is 
because it overfit. Reducing the model complexity will likely increase the score.

**Interpretation**

The original question written in the proposal was the following:

*"I would like to better understand how to apply regression techniques to predict housing prices and to experiment with finding the best 
model for this task"*

This is was answered I applied 4 different models to the dataset and found the best model (Gradient Boosting Regressor) from amongst the models I chose.


**Reflection**

I was not able to do validation testing due to the column transformer outputting an extra column. After much analysis of the data, I 
discovered that the validation data set contained an extra category that the training set didn't have and therefore the onehotencoder was
outputting an additional column. I did not find a way to fix this issue and I would like to explore this further on my own time.

There are many other ideas I wanted to explore if I had more time for this project including additional feature engineering, including 
more features to the feature matrix, and trying different models and parameters for hypertuning. Overall this has been an excellent exercise
as I have learned the nature of machine learning hypothesis generation and experimentation

