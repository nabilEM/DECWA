# DECWA
 DECWA (**DE**nsity-based **C**lusteringusing **WA**sserstein distance) is a hybrid clustering algorithm combining density and probabilistic approaches. It can handle several difficulties in datasets such as low-density clusters, near clusters of similar densities, and high-dimensional data. This is possible due to the probabilistic representation of clusters density and the use of Wasserstein metric which is a distance function defined between probability distributions.
 
 ## Relevent publication
 DECWA implements an algorithm introduced in the following [paper](url_du_lien "DECWA : Density-Based Clustering using Wasserstein Distance"):
 ```
 DECWA : Density-Based Clustering using Wasserstein Distance
 Nabil El Malki, Robin Cugny, Olivier Teste, Franck Ravat
 CIKM 2020
 ```
 
 ## Results of DECWA
 Unlike most density based clustering algorithm, DECWA does not focus on high density points, it aims to find areas of homogeneous density, therefore, it is able to find low density clusters. 
 
 ![images](images/DECWA_on_compound_dataset.png "DECWA on Compound dataset")
 
 Here the selected parameters allow DECWA to discover nested clusters on top left corner. Most density based approches tend to find two or one cluster here (due to overlapping). They are neglicting density variation, therfore, they do not find the core clusters and they do not consider the dots graviting around as potential clusters. That leads DECWA to better results in term of *ARI*, especially on real datasets where it is able to separate overlapping clusters if they have different densities.
 
 ![images](images/iris.png "Iris dataset")

Here on iris dataset, the classes are close to each other (even when considering the 4 dimensions). However, DECWA is able to separate the clusters with a fine precision of 0.93 in ARI score.
 
 ## Understanding DECWA
 DECWA first divide the dataset into homogeneous sub-clusters. Then merges the sub-clusters that actually belong to the same clusters according to rules detailed in the [paper](url_du_lien "DECWA : Density-Based Clustering using Wasserstein Distance").
 
 ![images](images/div_result.png "Division and fusion on jain dataset")
 
 Comparison of the division result (a) with fusion result (b) for jain dataset.
 
 
