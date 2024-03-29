# Boston_House_Prices_Analysis
Project for the module Machine Learning &amp; Statistics.

## Content
Using a Jupyter Notebook I analyze the *Boston House Prices* dataset. The notebook is made up of three sections, first I __describe__ the Boston House Prices with statistics and plots, then I __analyse__ whether there is a significant difference in median house prices between houses that are along the Charles river and those that aren’t. And finally I create a neural network with the intention of __predicting__ the median house price based on the other variables in the dataset.


## Getting started
### Installing
Since I have used packages like *pandas*, *scipy* and *Jupyter* I recommend you to install *Anaconda* to make sure that you will be able of running the code without any kind of issues. If you needed it, you can download it [here](https://www.anaconda.com/download/)

However *keras* is not included in *Anaconde* and before anything else you would need to install a backend engine like *Tensorflow* or *Theano*. See the official *keras* installation guide [here](https://keras.io/#installation)

This repository is Public so it is available to download and execute.

	
## Introduction
__Dataset Characteristics__:

This data was collected in 1978 and each entry represents aggregate information about 14 features of homes from various suburbs located in Boston for the purpose of discovering whether or not clean air influenced the value of houses in that area. Then, each of the 506 rows describes a Boston town or suburb with 13 attributes (features) and a target column (price).

* Number of Instances: 
  506

* Number of Attributes:
  13 numeric/categorical predictive and the price median value (the target).

* Attribute Information (in order):
  - CRIM per capita crime rate by town
  - ZN proportion of residential land zoned for lots over 25,000 sq.ft.
  - INDUS proportion of non-retail business acres per town
  - CHAS Charles River dummy variable (= 1 if tract bounds river; 0 otherwise)
  - NOX nitric oxides concentration (parts per 10 million)
  - RM average number of rooms per dwelling
  - AGE proportion of owner-occupied units built prior to 1940
  - DIS weighted distances to five Boston employment centres
  - RAD index of accessibility to radial highways
  - TAX full-value property-tax rate per $10,000
  - PTRATIO pupil-teacher ratio by town
  - B 1000(Bk - 0.63)^2 where Bk is the proportion of blacks by town
  - LSTAT % lower status of the population
  - MEDV Median value of owner-occupied homes in $1000’s

* Missing Attribute Values:
  None

* Creator:	
Harrison, D. and Rubinfeld, D.L.


## Summary
The collection of data for this set was complete as there are no missing values. Some attributes follow a normal distribution, some of them skewed right, others left. And there also are normal bimodal distributions.

There is a moderate to strong positive linear correlation (coefficient = 0.69) between the price of the houses and the number of rooms (which is the expected scenario) and a moderate to strong negative linear correlation (coefficient = -0.74) between price and percentage of population with lower status, however when plotting the occurrences of the second, it suggests more of a curved correlation, perhaps polynomial or even asymptotic. There also is clear correlation between number of rooms and proportion of lower status population.

When it comes to inferring, the t test between the prices of the observations which where located along the river (CHAS = 1) and the observations which were not located along the river (CHAS = 0) returned that, with a p value of 7.4 x 10<sup>-5</sup>, I can reject the null hypothesis and consider the medians of the price do differ significantly. 

Despite their histogram show their peak nearly overlap -they have a similar median-, the observations of the prices along the river are more spread (as the standard deviation shows), whereas away from the river the prices gather closer to the mean. 

Also, there is an outstanding frequency for the greatest value, 50. The proportion of this observations is much higher for CHAS = 1 than for CHAS = 0 (0.17 to 0.02 respectively) which favours the rejection of the null hypothesis.


As fas as the predictive part is concerned, I try to set a neural network using *keras* in order to predict the median of the price from the houses. Different tries during the experimental phase showed there is a preferred configuration where I select just certain attributes. Adding many layers or many nodes per layer was counterproductive and despite the initial neural network output was the same figure regardles of the input, preprocessing the dataset made a difference.

First I scale it, which makes the neural network to independent outputs per every input. The MSE loss is big, 152, reason why I whiten it to get an improved evaluation of 77.6. Although this neural network is not properly set and needs more development. 


## References


- https://scikit-learn.org/stable/datasets/index.html#boston-dataset

- https://github.com/rromanss23/Machine_Leaning_Engineer_Udacity_NanoDegree/blob/master/projects/boston_housing/boston_housing.ipynb

- https://subscription.packtpub.com/book/big_data_and_business_intelligence/9781789804744/1/ch01lvl1sec11/our-first-analysis-the-boston-housing-dataset

- https://towardsdatascience.com/linear-regression-on-boston-housing-dataset-f409b7e4a155

- https://scikit-learn.org/stable/modules/preprocessing.html#preprocessing



