# Project Title:
ML Unsupervised Learning model - Clustering on Wines dataset
#
---
# Project Description:
This is Unsupervised Learning model - Agglomerative and kMeans Clustering was performed on Wines dataset, using Dimensionality Reduction techniques like PCA and t-SNE.
#
---
# Table of Contents:

  1. Exploratory Data Analysis
  2. Data Preprocessing 
  3. Model Training - Agglomerative Clustering
  4. Model Training - KMeans Clustering
  5. Model Evaluation
  6. PCA for Dimensionality Reduction
  7. Appling K-means clustering on the reduced-dimensional data with PCA
  8. t-SNE for dimensionality reduction and visualization
  9. Appling K-means clustering on the reduced-dimensional data with t-SNE
  10. Conclusion and Results
---
#

---
# CONCLUSION from preliminary analysis of a dataset:
---
### Shape of a Dataset:     
Shape of the dataset is: 178 rows x 13 columns.

### NaN values:  
There are no NaN values in the dataset.

### Constant values:  
There are no features with one constant value in the dataset.

### Data types:  
All of the features have appropriate data type.

### Duplicates:  
There are no duplicate rows in the dataset.

### Typos:       
There are no typos that need to be corrected.

### Descriptive statistics:
The summary statistics for the numerical columns in the dataset shows quick overview of the distribution and data variability that occurs in all columns. Nothing specific can be seen so far. 


---
# CONCLUSION from EDA:
## 


## Key findings from Heatmap:
Heatmap shows high positive correlation between the following features: 'Total_Phenols', 'Flavanoids' and 'OD280'.
At this point I decided to leave them in the dataset, and maybe to try to remove one or two of them later on, just for comparison with the first model. 

## Key findings from Histplots:  
Some of the columns have similar to normal distribution and some have skewed distribution. At this point I decided not to transform the features, because I think that skewness is not extreme.

## Key findings from Boxplots:
Box plots shows few outliers in some of the features. At this point I decided to leave them in the dataset.

## Key findings from Pairplot:
2D Pairwise relationships between variables in a dataset does not show visible clustering of the data. However, it's important to note that this analysis is limited to a two-dimensional representation and may not accurately represent the complexities of a multidimensional setting.

---

#
## CONCLUSION from CLUSTERING MODELS:

Both **kMeans** and **Agglomerative Clustering** provided similar and satisfactory results, demonstrating effective clustering of the data. Agglomerative Clustering appears visually superior to kMeans, as the clusters are more easily distinguishable from one another.

**Silhouette score**   
As shown above with clustering methods: KMeans and Agglomerative Clustering, the optimal value of K (leading to the highest silhouette score) is:    
K = 2

**The elbow method**    
On the other hand this method shows different result, sum of square distances stops dropping rapidly around 4, showing that the optimal number of clusters is:    
K = 4

There's no definitive conclusion, which one of the two scores is more appropriate, and it may require some experimentation and validation to determine the most appropriate number of clusters for this specific dataset.
I decided to go with K = 2, and maybe try different clustering later on. 

## CONCLUSION from PCA:

## Eigenvalues
The method for calculation of eigenvalue was computed manually and automatically. I found the eigenvalue plot strange, so I tried it both ways. The resulting plot was exactly the same and showed that there is ONLY ONE high importance feature in a dataset.
I decided to take first 2 eigen vectors and that will be the transformation matrix to decrease the dimensionality of our dataset. Then transform the original 13 dimensional data into 2 dimensions.


## Component-wise and Cumulative Explained Variance    

In the graph, the blue line represents component-wise explained variance while the orange line represents the cumulative explained variance. We are able to explain around 100% variance in the dataset using just two components.


## Inference    

First 2 Principal components:

1st PC:&nbsp; 99.81%   
2nd PC:&nbsp;&nbsp; 0.17%

**Total:&nbsp;&nbsp;&nbsp;&nbsp; 99.98%**

**First Dimension:** From the above plot it is noticed that the weight is largest and positive for 'Proline', meaning that the dataset has only one high importance feature. In order to visualize the clusters in 2D, I decided to take second component, that has very low importance, but together both make impact of nearly 100%.

**Second Dimension**: From the above plot it is noticed that the weight is large and positive for 'Magnesium' but again the impact of this feature is only 0.17%.

#
## CONCLUSION from tSNE:

We use this method generaly as a tool to visualize high-dimensional data to a lower-dimensional space: 2D or 3D. The method is different than PCA and ussualy is recommended to use it after dimensionality reduction with PCA. In this assignment, for demonstration only, was used on a whole dataset. I made one plot with 2 components, as suggested with PCA, and one with 3 components for demostration only. 

#
# License
MIT License
#
