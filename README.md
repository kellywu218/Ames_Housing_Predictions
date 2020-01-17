# Project 2 - Ames Housing Data and Kaggle Challenge

## Contents
- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Conclusion](#Conclusion)
- [Sources](#Sources)

## Problem Statement: 
We all have those significant moments in our lives such as getting our first car. However, as we get older more moments start to come where we actually become adults such as buying a house and starting a family. However, buying a house is a major financial commitment and there are many things to factor in when deciding on a property. Of course, money is the biggest factor as we have to have enough to buy a house, let alone our dream house. In an indeal world, we can all just buy a plot of land and build the house of our dreams with no worries. Sadly, we aren't in an ideal world. We live in an economy where buy houses in a supply and demand model. We need to give and take with the existing houses that are for sale, which means that we might have to sacrifice a pool for a garage. Ultimately, what determines the price of a house and whether we decide to sign? What should we be considering and prioritizing? Perhaps we can create something to help us predict the price of a house based on the features included. 

## Executive Summary: 
We took two datasets that listed a myriad of features (about 80) regarding a house such as square footage of the first floor, pool quality, and lot area. However, the only difference was sale price. One dataset had the sale price and one didn't so we took our training dataset (the one with the sale price) and based three regression models (Linear, Lasso, and Ridge) on that data to find how we can best predict sale price. 

Our process began with importing and cleaning our datasets as null values can really pull our data one way or another so imputing values was our primary goal when cleaning the datasets. After cleaning our datasets, we went into exploratory data analysis where we could visualize relationships between variables and determine what features may have a bigger impact on sale price than others. In addition, we wanted to take care of outliers to prevent our data from being skewed because of them and try to normalize our data. However, we didn't discard all of the outliers as we did want our models to be able to handle any strays in the testing dataset. Then we explored some feature engineering where we created new features that encompasses multiple features together such as total property area by combining all individual areas like basement area, garage area, pool area, and first floor area.  Afterwards, we wanted to convert our categorical data to numerical so we could use all of our data when creating models (as they don't work well with categorical variables). 

Once we have our master dataset that we can work with when fitting the data to our Linear Regression, Lasso Regression, and Ridge Regression. After fitting, predicting, and plotting our data for visualization, we can immediately see that all three models seem to do quite well in predicting sale prices with minimal variance. However, with any regression model, there is a major downfall of it being boundless; but, we fix this through winsorizing by creating an upper and lower boundary. With our metrics scores, we can proceed with a more in-depth analysis on which model does best. Finally, we finish with some outside research before making our conclusions as there may be some factors that are unique to Ames, Iowa that may affect sale price as well such as there being a state university. 

## Conclusion 
Through our data analysis, all three regression models do quite well but our Ridge Regression Model is our best option. Based on our $R^2$ scores for our train and test datasets, the values tell us that the model does very well in predicting the sale price when looking at all the features possible on data that it has been exposed to and trained on; and the model does well in predicting the sale price when exposed to data that is new. 

However, our models aren't perfect because there are so many other factors involved that can't be easily written in as data. As discovered from outside research, there could be outside factors of the location that affect the housing price. Deciding on whether you want to buy a house buy the university or away from the university can impact the price. Furthermore, gender could come into play if you're looking to be the sole owner as there's approximately a 15,000 dollar difference in annual salary between men and women; thus, it could be harder for a woman to afford a new house than a man. In addition, personal preferences can affect how much money will be needed overall such as moving expenses and repair costs. 

Overall, our Ridge Regression model is quite accurate in predicting the sale price of a house in Ames, Iowa given numerous features of the house and then you can tack on a a couple hundred or thousand dollars to account for personal or outside factors. For the time being, when looking at buying a house in Ames look at the following features first because they have the highest impact on sale price: 
- Overall Quality 
- House Area
- Above Grade Living Area
- Year Built
- Exterior Quality

Here we explain the coefficients for the top five features that have the highest impact on sale price based on the Ridge Regression Model. We can interpret these numbers as follows: 

|Feature|Meaning|
|---|---|
|Overall Qual|For all else held equal, a one unit increase in overall quality yields a 8,339 increase in Sale Price|
|House Area|For all else held equal, a one unit increase in total house area yields a 7,046 increase in Sale Price| 
|Gr Liv Area|For all else held equal, a one unit increase in above grade living area yields a 6,717 increase in Sale Price|  
|Year Built|For all else held equal, a one unit increase in the year built yields a 4,588 increase in Sale Price| 
|Exter Qual|For all else held equal, a one unit increase in the first floor square footage yields a 4,458 increase in Sale Price|

Until the model can be refined with more features taken into consideration such as personal and outside factors, referring to the model and specific features when looking at the house are ideal. To calculate how much you would need in total, do a personal calculation of how much a moving truck would cost and the cost for parts of the house you would like to be repaired, rennovated, or installed. 

## Sources
- [Ames, Iowa](https://datausa.io/profile/geo/ames-ia/)
- [Buying a House](https://www.cnbc.com/2018/04/05/how-much-you-need-to-save-to-afford-to-buy-a-home.html)