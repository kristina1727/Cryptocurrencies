<p align = "center">
  <img width = "1000" src= "https://user-images.githubusercontent.com/88597956/151681200-046cd815-2135-46c3-9cde-56243d7ca309.png">
</p>


## Overview
Creat a report for Accountability Accounting that includes what cryptocurrencies are on the trading market and how they can be grouped to create a classification system. 

## Results
I started off by pulling in the crypto_data.csv file and cleaning it by only keeping those currencies that are currently being traded and then by dropping any rows of data that had null vallues. From there I removed any coins where the TotalCoinsMined was less than or equal to 0. I created a seperate data base that only included the CoinName and then removed the CoinName from the initial dabase prior to using  the get dummies method to create variables for any of the text features. I then proceeded to used the StandardScaler to standardize the data. 

We reduced the Data Dimensions using PCA to 3 principal components. Using the data frame with the 3 principal components we created an elbo curve to find the best K-means value to cluster the data. As shown in the below elbow curve chart the best K-means value is 4. We then use 4 clusters to initalize the K-means model and create the predicitons. 

![elbow_curve](https://user-images.githubusercontent.com/88597956/151681603-155447bb-1cdf-4afd-9172-9984339bbf8b.png)


We put this data back into a DataFrame adding in the CoinName and the Class. This dataframe was used to visualize the cryptocurrency results in a 3-D scatter.

![3-D_Scatter](https://user-images.githubusercontent.com/88597956/151681661-97230a69-ff3c-4707-809c-4c1c59257f19.png)

From there we used the MinMaxScaler to scale the TotalCoinSupply and the TotalCoinsMined, created a DataFrame once again adding in the CoinName and Class and plotted that in a scatter.

![scatter](https://user-images.githubusercontent.com/88597956/151681736-f93f5ec2-10e1-4318-84dc-7c4a9d20edb5.png)
