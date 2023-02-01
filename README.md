# Module-10-Homework-Crypto-Clustering
Machine Learning - Unsupervised learning

**Import the Data**

This section imports the data into a new DataFrame. It follows these steps:

Read the “crypto_market_data.csv” file from the Resources folder into a DataFrame, and use index_col="coin_id" to set the cryptocurrency name as the index. Review the DataFrame.

Generate the summary statistics, and use HvPlot to visualize your data to observe what your DataFrame contains.

![bokeh_plot (9)](https://user-images.githubusercontent.com/117589787/216177720-77c8f864-7b04-41be-b246-80b8bfbe92ad.png)

** Prepare the Data**
This section prepares the data before running the K-Means algorithm. It follows these steps:

Use the StandardScaler module from scikit-learn to normalize the CSV file data. This will require you to utilize the fit_transform function.

Create a DataFrame that contains the scaled data. Be sure to set the coin_id index from the original DataFrame as the index for the new DataFrame. Review the resulting DataFrame.

#Dataframes in pynb file#

**Find the Best Value for k Using the Original Data**

In this section, you will use the elbow method to find the best value for k.

Code the elbow method algorithm to find the best value for k. Use a range from 1 to 11.

Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

Answer the following question: What is the best value for k?

![bokeh_plot (8)](https://user-images.githubusercontent.com/117589787/216178813-e203c61b-5c5a-4723-ba5c-e50b5b79453b.png)

Answer: # The Best value for k according to this elbow curve is 4

