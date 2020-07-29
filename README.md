# DECWA
 DECWA (**DE**nsity-based **C**lusteringusing **WA**sserstein distance) is a hybrid clustering algorithm combining density and probabilistic approaches. It can handle several difficulties in datasets such as low-density clusters, near clusters of similar densities, and high-dimensional data. This is possible due to the probabilistic representation of clusters density and the use of the Wasserstein metric which is a distance function defined between probability distributions.
 
 ## Relevant publication
 DECWA implements an algorithm introduced in the following [paper](url_du_lien "DECWA : Density-Based Clustering using Wasserstein Distance"):
 ```
 DECWA : Density-Based Clustering using Wasserstein Distance
 Nabil El Malki, Robin Cugny, Olivier Teste, Franck Ravat
 CIKM 2020
 ```
 
 ## Results of DECWA
 Unlike most density-based clustering algorithm, DECWA does not focus on high-density points, it aims to find areas of homogeneous density, therefore, it is able to find low-density clusters.
 
 ![images](images/compound4.png "DECWA on Compound dataset")
 
 Here the selected parameters allow DECWA to discover hidden clusters in low-density regions. Most density-based approaches tend to find only one cluster here. They are focusing on the high-density points and do not consider the dots gravitating around as potential clusters. These points are often treated as outliers or are absorbed by the dense cluster. However, we believe that some crucial pieces of information are not always highly represented in a dataset. That is why, DECWA has been conceived to discover scarce classes.
 
 By focusing on density variation, DECWA is able to separate near clusters of similar densities. That is possible thanks to Wasserstein distance which is able to capture small differences between probability distributions.
 
 ![images](images/compound2.png "DECWA on Compound dataset")
 
 That leads DECWA to better clustering results in term of *ARI*, especially on real datasets where it is able to separate overlapping clusters if they have different densities.
 
 ![images](images/iris.png "Iris dataset")

Here on Iris dataset, the classes are close to each other (even when considering the 4 dimensions). However, DECWA is able to separate the clusters with a fine precision of **0.93** in terms of *ARI* score.
 
 ## Understanding DECWA
 DECWA first divides the dataset into homogeneous sub-clusters. Then merges the sub-clusters that actually belong to the same clusters according to rules detailed in the [paper](url_du_lien "DECWA : Density-Based Clustering using Wasserstein Distance").
 
 ![images](images/div_result.png "Division and fusion on jain dataset")
 
 Comparison of the *division* result (a) with *fusion* result (b) for jain dataset.
 
 
