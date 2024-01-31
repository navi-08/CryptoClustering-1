# CryptoClustering-1
assignment 19



In this challenge, you’ll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

Before You Begin
Create a new repository for this project called CryptoClustering. Do not add this homework to an existing repository.

Clone the new repository to your computer.

Push your changes to GitHub.

Files
Download the following files to help you get started:

Module 19 Challenge filesLinks to an external site.

Instructions
Rename the Crypto_Clustering_starter_code.ipynb file as Crypto_Clustering.ipynb.

Load the crypto_market_data.csv into a DataFrame.

Get the summary statistics and plot the data to see what the data looks like before proceeding.

Prepare the Data
Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.

Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

The first five rows of the scaled DataFrame should appear as follows:

The first five rows of the scaled DataFrame

Find the Best Value for k Using the Original Scaled DataFrame
Use the elbow method to find the best value for k using the following steps:

Create a list with the number of k values from 1 to 11.
Create an empty list to store the inertia values.
Create a for loop to compute the inertia with each possible value of k.
Create a dictionary with the data to plot the elbow curve.
Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
Answer the following question in your notebook: What is the best value for k?
Cluster Cryptocurrencies with K-means Using the Original Scaled Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:

Initialize the K-means model with the best value for k.
Fit the K-means model using the original scaled DataFrame.
Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
Create a copy of the original data and add a new column with the predicted clusters.
Create a scatter plot using hvPlot as follows:
Set the x-axis as "PC1" and the y-axis as "PC2".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
Optimize Clusters with Principal Component Analysis
Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.

Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:

What is the total explained variance of the three principal components?
Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

The first five rows of the PCA DataFrame should appear as follows:

The first five rows of the PCA DataFrame

Find the Best Value for k Using the PCA Data
Use the elbow method on the PCA data to find the best value for k using the following steps:

Create a list with the number of k-values from 1 to 11.
Create an empty list to store the inertia values.
Create a for loop to compute the inertia with each possible value of k.
Create a dictionary with the data to plot the Elbow curve.
Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
Answer the following question in your notebook:
What is the best value for k when using the PCA data?
Does it differ from the best k value found using the original data?
Cluster Cryptocurrencies with K-means Using the PCA Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:

Initialize the K-means model with the best value for k.
Fit the K-means model using the PCA data.
Predict the clusters to group the cryptocurrencies using the PCA data.
Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
Create a scatter plot using hvPlot as follows:
Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.





Question: After visually analyzing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?

Answer:

Elbow Curve Comparison:

The Elbow Curve for the PCA data (Curve 2) exhibits a lower inertia, indicating that using fewer features (PCA components) has resulted in tighter and more well-defined clusters.
The reduction in inertia suggests that the clustering algorithm (K-Means) is finding more compact and meaningful groups in the data when using fewer features.
Cluster Scatter Plot Comparison:

Cluster Graph 1 (using original data): The clusters show overlap, implying that the original data's features may not effectively capture the underlying structure for clustering. The lack of separation indicates that the clustering algorithm struggled to distinguish distinct groups in the original feature space.

Cluster Graph 2 (using PCA data): In contrast, the clusters in this graph are well-separated, indicating that using PCA components has helped reveal clearer patterns and structure in the data. The reduction in dimensionality through PCA has likely removed noise and highlighted the essential information for clustering.

Overall Impact:

The analysis suggests that using fewer features through PCA has had a positive impact on clustering. It has led to more accurate and meaningful clusters, providing a clearer understanding of the inherent structure in the data.
The reduction in dimensionality not only enhances the interpretability of the clusters but also helps mitigate the curse of dimensionality, leading to more effective cluster assignments.
This type of analysis is valuable for understanding the trade-offs between using a full set of features and a reduced set of features through techniques like PCA. It highlights how feature selection or dimensionality reduction can impact the performance of clustering algorithms. Curve 1: The inertia for k=4 clusters is 79.022. Curve 2: The inertia for k=4 clusters is 44.132. Inertia, in the context of clustering, is a measure of how far the points within a cluster are from the centroid of that cluster. Lower inertia values generally indicate tighter and more compact clusters.

In summary, the analysis suggests that using PCA for dimensionality reduction has improved clustering performance, providing more accurate and interpretable results while mitigating the challenges associated with high-dimensional data. The provided inertia values for different curves give an indication of the quality of the clustering results.
