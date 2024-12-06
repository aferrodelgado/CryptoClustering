# CryptoClustering
**Module 19 - Unsupervised Machine Learning**

In this challenge, you'll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

**Prepare the Data**
- Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
- Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

  - The first five rows of the scaled DataFrame should appear as follows:
    <br><br>
    <img width="1239" alt="Screenshot 2024-12-05 at 8 16 42 AM" src="https://github.com/user-attachments/assets/c4986fc8-0c5d-43a4-82df-0e17c2da782e">
    <br><br>
    
**Find the Best Value for k Using the Scaled DataFrame**

Use the elbow method to find the best value for k using the following steps:
- Create a list with the number of k values from 1 to 11.
- Create an empty list to store the inertia values.
- Create a for loop to compute the inertia with each possible value of k.
- Create a dictionary with the data to plot the elbow curve.
- Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
  <br><br>
  <img width="712" alt="Screenshot 2024-12-05 at 9 29 41 AM" src="https://github.com/user-attachments/assets/270233eb-39ee-46dc-8d6f-4737d0a39cc1">
  <br><br>
- Question: What is the best value for k?
  - Answer: 4

**Cluster Cryptocurrencies with K-means Using the Scaled DataFrame**

Use the following steps to cluster the cryptocurrencies for the best value for k on the scaled DataFrame:

- Initialize the K-means model with the best value for k.
- Fit the K-means model using the scaled DataFrame.
- Predict the clusters to group the cryptocurrencies using the scaled DataFrame.
- Create a copy of the scaled DataFrame and add a new column with the predicted clusters.
- Create a scatter plot using hvPlot as follows:
  - Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
  - Color the graph points with the labels found using K-means.
  - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
    <br><br>
    <img width="650" alt="Screenshot 2024-12-05 at 10 03 25 AM" src="https://github.com/user-attachments/assets/a64f3262-4697-4b00-83f2-ea6943ec1ec9">
    <br><br>

 
**Optimize Clusters with Principal Component Analysis**

- Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
- Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:
  - What is the total explained variance of the three principal components?
 
- Create a new DataFrame with the scaled PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
  - The first five rows of the scaled PCA DataFrame should appear as follows:
    <br><br>
    <img width="300" alt="Screenshot 2024-12-05 at 8 23 13 AM" src="https://github.com/user-attachments/assets/bd405826-7a9c-4eca-8128-005f084e2ae3">
    <br><br>

**Find the Best Value for k Using the PCA DataFrame**

Use the elbow method on the scaled PCA DataFrame to find the best value for k using the following steps:

- Create a list with the number of k-values from 1 to 11.
- Create an empty list to store the inertia values.
- Create a for loop to compute the inertia with each possible value of k.
- Create a dictionary with the data to plot the Elbow curve.
- Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
  <br><br>
  <img width="714" alt="Screenshot 2024-12-06 at 8 24 49 AM" src="https://github.com/user-attachments/assets/de4382b5-2e90-4959-9ca0-431a97fbabd6">
  <br><br>
- Answer the following question in your notebook:
  - What is the best value for k when using the scaled PCA DataFrame? 4
  - Does it differ from the best k value found using the original scaled DataFrame? No

**Cluster Cryptocurrencies with K-means Using the PCA DataFrame**

Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA DataFrame:
- Initialize the K-means model with the best value for k.
- Fit the K-means model using the scaled PCA DataFrame.
- Predict the clusters to group the cryptocurrencies using the scaled PCA DataFrame.
- Create a copy of the scaled PCA DataFrame and add a new column to store the predicted clusters.
- Create a scatter plot using hvPlot as follows:
  - Set the x-axis as "PC1" and the y-axis as "PC2".
  - Color the graph points with the labels found using K-means.
  - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
- Answer the following question:
  - What is the impact of using fewer features to cluster the data using K-Means?


