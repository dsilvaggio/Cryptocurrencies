# Cryptocurrencies
## Overview
  Accountability Accounting, an investment bank, is interested in potentially offering a cryptocurrency investment portfolio to its customers. They requested a report be created that includes the cryptocurrencies currently on the trading market and how they should be grouped to create a classification system for this new investment.
  
  To create the report, the data was processed and fitted to machine learning models. Unsupervised learning was used since there was no known output. To group the cryptocurrencies, a clustering algorithm was used and visualizations were used to display findings with the board.  

## Results
To perform PCA, the dataset needed to first be preprocessed. After reading in the CSV and creating an initial crypto DataFrame, the crypto Dataframe was filtered to contain only the cryptocurrencies currently being traded and where coins have been mined.

### Coin Name DataFrame
A second DataFrame was then created to hold all the names of these cryptocurrencies for future use. The Dataframe with the names of currently traded cryptocurrencies can be seen below:  

![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.52.52%20PM.png)

### Cleaned Crypto DataFrame

The CoinName and IsTrading columns were removed from our crypto Dataframe since they will not be needed in the clustering algoithm. Rows with any null values were also dropped. The final cleaned cryto DataFrame for use to perform PCA is below. 
![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.53.07%20PM.png)

### Create variables for text features
The **get_dummies()** method was then used to create variables for two text features in our DataFrame, Algorithm and ProofType. The resulting data was stored in a new DataFrame called X.

![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.53.16%20PM.png)

### PCA Algorithm Results
Before performing PCA, our X data was first scaled using **StandardScalar()**. PCA was then applied to reduce the dimension to 3 principal components. The results were stored in pcs Dataframe. 

![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.53.28%20PM.png)

### Elbow Curve
In order to find the best value for K for the K-Means algorithm, an elbow curve was created using the above pcs Dataframe and **hvPlot**. Based on the below elbow curve, the best K value is 4. 

![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.53.36%20PM.png)

### Clustered DataFrame
The pcs Dataframe was then used to run a K-Means algorithm with 4 clusters. A new clustered DataFrame was then created by concatenating the cleaned crypto Dataframe and the pcs dataframe using an inner join. A new CoinName column was added to this DataFrame using the Coin Name Dataframe that was created in the beginning. Another new Class column was then added to the clustered DataFrame that contained all of the predictions from the K-Means algorithm. The final Clustered Dataframe is below. 

![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.53.45%20PM.png)

### 3-D Scatter Plot
In order to visualize the distinct groups that correspond to the 3 principal components from our PCA and K-means algorithm, a 3-d scatter plot was used. Using the **Plotly Express scatter_3d()** function the three clusters from the Clustered Dataframe were plotted.
![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.56.01%20PM.png)

### HvPlot Table
Then using the **hvplot.table()** function a table was made to show each Cryptocurrencies coin name, algorithm, proof type, total coin supply, total coins mined, and class. Based on the table and our above DataFrames, there are **532 tradable cryptocurrencies**.  

![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.54.09%20PM.png)

### MinMax Scalar DataFrame
The MinMaxScalar().fit_transform method was used to scale the TotalCoinSupply and TotalCoinsMined columns between 0 and 1. A new Dataframe was created with the newly scaled TotalCoinSupply and TotalCoinsMined columns, as well as the CoinNames column from our coin names DataFrame and the class from our clustered DataFrame. 

![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.54.02%20PM.png)

### Scatter Plot
Finally, a scatterplot was created using **hvPlot** with TotalCoinsMined as the x values, TotalCoinSupply as the y values, and the points were colored by their class.

![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.53.55%20PM.png)






## Summary
