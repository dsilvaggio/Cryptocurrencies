# Cryptocurrencies
## Overview
  Accountability Accounting, an investment bank, is interested in potentially offering a cryptocurrency investment portfolio to its customers. They requested a report be created that includes the crypotocurrencies currently on the trading market and how they should be grouped together to create a classification system for this new incestment.
  
  To create the report, the data was processed and fitted to machine learning models. Unsupervised learning was used since there was no known output. To group the cryptocurrencies, a clustering algorithm was used and visualizatoin were used to display findings with the board.  

## Results
In order to perform PCA, the dataset needed to first be preprocessed. After reading in the csv and creating an initial crypto DataFrame, the crypto Dataframe was filtered to contain only the crytocurrencies currently being traded and where coins that have been mined.

### Coin Name DataFrame
A second DataFrame was then created to hold all the names of these cryptocurrencies for future use. The Dataframe with the names of currently traded cryptocurrencies can be seen helow:  

![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.52.52%20PM.png)

### Cleaned Crypto DataFrame
![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.53.07%20PM.png)

### Create variables for text features
![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.53.16%20PM.png)

### PCA Algorithm Results
![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.53.28%20PM.png)

### Elbow Curve
![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.53.36%20PM.png)

### Clustered DataFrame
![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.53.45%20PM.png)

### 3-D Scatter Plot
![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.56.01%20PM.png)

### HvPlot Table
![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.54.09%20PM.png)

### MinMax Scalar DataFrame
![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.54.02%20PM.png)

### Scatter Plot
![This is an image](https://github.com/dsilvaggio/Cryptocurrencies/blob/main/Resources/Screen%20Shot%202022-06-20%20at%209.53.55%20PM.png)






## Summary
