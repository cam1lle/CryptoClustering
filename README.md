# Cryptocurrency Clustering Project
## Introduction
In this project, I have implemented a cryptocurrency clustering algorithm using the K-means algorithm. The aim was to cluster cryptocurrencies based on their market data and analyze the results. The project involves data preprocessing, finding the optimal number of clusters, performing clustering on the original and reduced data, and visualizing and comparing the results.

## Project Steps
## Step 1: Data Preparation
To start, I used the StandardScaler() module from scikit-learn to normalize the data from the provided CSV file. The normalized data was then used to create a new DataFrame with the scaled values, and the "coin_id" index from the original DataFrame was set as the index for the new DataFrame.

## Step 2: Finding the Best Value for k Using the Original Data
To determine the optimal number of clusters, I implemented the elbow method. I computed the inertia values for a range of k values (1 to 11) and plotted a line chart to visualize the results. Based on the elbow curve, I identified the best value for k, which turned out to be 4.

## Step 3: Clustering Cryptocurrencies with K-means Using the Original Data
Using the best value for k obtained from the previous step, I initialized a K-means model with four clusters. The model was then fitted to the original scaled DataFrame, and the resulting clusters were predicted and assigned to each cryptocurrency. To visualize the clusters, I created a scatter plot using hvPlot, with "price_change_percentage_24h" as the x-axis, "price_change_percentage_7d" as the y-axis, and color-coded points representing the different clusters.

## Step 4: Optimizing Clusters with Principal Component Analysis (PCA)
To further optimize the clusters, I performed Principal Component Analysis (PCA) on the original scaled DataFrame. The data was reduced to three principal components, and I retrieved the explained variance to assess the information attributed to each component. The total explained variance of the three principal components was found to be 0.89. A new DataFrame was created with the PCA data, with the "coin_id" index from the original DataFrame set as the index for the new DataFrame.

## Step 5: Finding the Best Value for k Using the PCA Data
Similar to the previous step, I used the elbow method on the PCA data to determine the best value for k. Inertia values were computed for a range of k values (1 to 11), and a line chart was plotted to visualize the results. Interestingly, the optimal value for k when using the PCA data was found to be 3, which differed from the best value obtained using the original data (k=4).

## Step 6: Clustering Cryptocurrencies with K-means Using the PCA Data
Finally, I initialized a K-means model with three clusters based on the optimal value of k obtained from the previous step. The model was fitted to the PCA data, and the resulting clusters were predicted. I created a scatter plot using hvPlot to visualize the clusters, with "PC1" as the x-axis, "PC2" as the y-axis, and color-coded points representing the different clusters.

## Step 7: Visualizing and Comparing the Results
To compare the results obtained from the original data and the PCA data, I created composite plots. One plot compared the elbow curves, showing the inertia values for different values of k. Another plot compared the cryptocurrency clusters, visualizing the clusters obtained from both datasets. Based on the visual analysis of the results, it was evident that using fewer features (principal components) to cluster the data resulted in less distinct and separable clusters. However, it also provided a more compact representation of the data, capturing some underlying patterns.

## Conclusion
This project allowed me to gain hands-on experience with clustering cryptocurrencies using the K-means algorithm. I successfully implemented the algorithm, found the optimal number of clusters, and compared the results obtained from the original data and the PCA data. The project helped me understand the impact of feature reduction on clustering results and provided insights into the clustering patterns of cryptocurrencies based on their market data.
