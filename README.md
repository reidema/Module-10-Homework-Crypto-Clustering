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

**Cluster Cryptocurrencies with K-means Using the Original Data**

In this section, you will use the K-Means algorithm with the best value for k found in the previous section to cluster the cryptocurrencies according to the price changes of cryptocurrencies provided.

Initialize the K-Means model with four clusters using the best value for k.

Fit the K-Means model using the original data.

Predict the clusters to group the cryptocurrencies using the original data. View the resulting array of cluster values.

Create a copy of the original data and add a new column with the predicted clusters.

Create a scatter plot using hvPlot by setting x="price_change_percentage_24h" and y="price_change_percentage_7d". Color the graph points with the labels found using K-Means and add the crypto name in the hover_cols parameter to identify the cryptocurrency represented by each data point.

array([0, 0, 3, 3, 0, 0, 0, 0, 0, 3, 3, 3, 3, 0, 3, 0, 3, 3, 0, 3, 3, 0,
       3, 3, 3, 3, 3, 3, 0, 3, 3, 3, 1, 0, 3, 3, 2, 3, 3, 3, 3])

#Dataframes in pynb file#

![bokeh_plot (7)](https://user-images.githubusercontent.com/117589787/216179443-d4f05346-a4b2-453d-bcc1-47980955a21d.png)

**Optimize Clusters with Principal Component Analysis**

In this section, you will perform a principal component analysis (PCA) and reduce the features to three principal components.

Create a PCA model instance and set n_components=3.

Use the PCA model to reduce to three principal components. View the first five rows of the DataFrame.

Retrieve the explained variance to determine how much information can be attributed to each principal component.

Answer the following question: What is the total explained variance of the three principal components?

Create a new DataFrame with the PCA data. Be sure to set the coin_id index from the original DataFrame as the index for the new DataFrame. Review the resulting DataFrame.

array([[-0.60066733,  0.84276006,  0.46159457],
       [-0.45826071,  0.45846566,  0.95287678],
       [-0.43306981, -0.16812638, -0.64175193],
       [-0.47183495, -0.22266008, -0.47905316],
       [-1.15779997,  2.04120919,  1.85971527]])
       
array([0.3719856 , 0.34700813, 0.17603793]) - Explained variance figures

Question: What is the total explained variance of the three principal components?

Answer: By adding up all of the 3 figures(0.3719856 + 0.34700813 + 0.17603793 = 0.89503166) we can see that the total explained variance of all three principal compenents is 0.89503166, roughly 89.5%

#Dataframes in pynb file#

**Find the Best Value for k Using the PCA Data**

In this section, you will use the elbow method to find the best value for k using the PCA data.

Code the elbow method algorithm and use the PCA data to find the best value for k. Use a range from 1 to 11.

Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

![bokeh_plot (6)](https://user-images.githubusercontent.com/117589787/216180432-388f99db-2042-42d3-9002-cba0149ce2e1.png)

Answer the following questions: What is the best value for k when using the PCA data? Does it differ from the best k value found using the original data?

Question: What is the best value for k when using the PCA data?
Answer: The best value for k in this case using the PCA data is 4

Question: Does it differ from the best k value found using the original data?
Answer: # No it does not differ from the best k value found using the original data

**Cluster Cryptocurrencies with K-means Using the PCA Data**

In this section, you will use the PCA data and the K-Means algorithm with the best value for k found in the previous section to cluster the cryptocurrencies according to the principal components.

Initialize the K-Means model with four clusters using the best value for k.

Fit the K-Means model using the PCA data.

Predict the clusters to group the cryptocurrencies using the PCA data. View the resulting array of cluster values.

Add a new column to the DataFrame with the PCA data to store the predicted clusters.

Create a scatter plot using hvPlot by setting x="PC1" and y="PC2". Color the graph points with the labels found using K-Means and add the crypto name in the hover_cols parameter to identify the cryptocurrency represented by each data point.

array([0, 0, 3, 3, 0, 0, 0, 0, 0, 3, 3, 3, 3, 0, 3, 0, 3, 3, 0, 3, 3, 0,
       3, 3, 3, 3, 3, 3, 0, 3, 3, 3, 1, 0, 3, 3, 2, 3, 3, 3, 3])
       
#Dataframes in pynb file#

![bokeh_plot (5)](https://user-images.githubusercontent.com/117589787/216181060-ce15605c-63cd-48ca-93dd-ea9b0c264018.png)

**Visualize and Compare the Results**

In this section, you will visually analyze the cluster analysis results by contrasting the outcome with and without using the optimization techniques.

Create a composite plot using hvPlot and the plus (+) operator to contrast the Elbow Curve that you created to find the best value for k with the original and the PCA data.

Create a composite plot using hvPlot and the plus (+) operator to contrast the cryptocurrencies clusters using the original and the PCA data.

Answer the following question: After visually analyzing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?

Rewind: Back in Lesson 3 of Module 6, you learned how to create composite plots. You can look at that lesson to review how to make these plots; also, you can check the hvPlot documentation.

![bokeh_plot (4)](https://user-images.githubusercontent.com/117589787/216181730-820979bc-5d35-4b4e-aa5f-0f1a766518ab.png)

![bokeh_plot (3)](https://user-images.githubusercontent.com/117589787/216181976-1e3d8b57-fd60-4f79-8a39-2a3391bd5748.png)

![bokeh_plot (7)](https://user-images.githubusercontent.com/117589787/216182316-19d1d4d8-c91d-4cc1-b876-6da57f9a7905.png)

![bokeh_plot (2)](https://user-images.githubusercontent.com/117589787/216182124-cc2c2294-07a1-40a8-a1eb-1b456a909436.png)

**Answer the following question: After visually analyzing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?**

Question: After visually analyzing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?

Answer: # One of the main impacts of using fewer features to cluster the data using K-Means is that we can see in our PCA scatter plot model compared to the original k-means model is that the clusters 1 and 2 with fewer points are more easy to visualize and see in the PCA scatter plot. By using fewer features as we can see in the PCA model the points that are clustered together are clustered much more closely together making them easier to group and visualize.




