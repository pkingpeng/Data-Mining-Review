# 	Cluster Analysis

## 1. Definition

- Finding groups of objects that the objects in a group are similar to each other and different from the objects in other groups.
- "Unsupervised Learning": no pre-defined class labels; no examples of objects groups are given.

- **Distance-based cluster analysis**: objects similarity is measured in terms of distances.



### why?

- summarization
- outlier detection
- Compression
- Understanding key features of similar objects.

## Type

- Partitional Clustering

- Hierarchical clustering

  <img src="/Users/Pking/Library/Application Support/typora-user-images/image-20211116130122636.png" alt="image-20211116130122636" style="zoom: 25%;" />

##  2.Clustering Algorithms



### (1) K-means

- #### K-means Clustering

  - Initial centroid(center point) very random
  - The centroid is the mean of the points in this cluster.
  - "Closeness" depends on the type of data: measured by Euclidean distance or cosine similarity
  - Complexity is O(n * k * I * d)
    - n = number of points, K = number of clusters, I = number o iterations, d = number of attributes. 

- #### Evaluating K-mean

  - **Sum of Squared Error(SSE)**
  - If each is set as the mean(centroid), **SSE is minimized** 

- #### Solution to initial Centroids problems

  - Multiple runs
  - Select most widely separated objects as initial centroids.
  - Bisecting K-means.

- #### Handling Empty Clusters

  - Find replacements for centroids of empty clusters.
    - Choose the point that contributes most to SSE
    - Choose a point from the cluster with highest SSE
    - If several empty clusters, repearted serveral times.

- #### Bisecting K-means

  - 1 cluster split into k clusters

- #### Limitations 

  - when clusters are
    - of different size
    - of different densities
    - Non-globular shapes.
  - K-means are susceptible to noise and outliers



### (2) K-medoids

- #### K-medoids Clustering

  - sum of distance that x to all other objects in same cluster.
  - exactly the same as K-mean, except the "representative" used for a cluster is its medoid instead of means.
  - more computationally demanding than k-means.

- #### PAM(Partitioning Around Medoids)

- #### Hierarchical Clustering

  - Hierarchical tree and visualized as a dendrogram
  - two main types:
    - Agglomerative: start with point as individual clusters and merge
      - Start with clusters of individual points and a proximity matrix
      - After some merging steps, we have some clusters
      - Merge the two closest clusters (C2 and C5) and update the proximity matrix.
    - Divisive: start with all-inclusive cluster and split

- #### How to define inter cluster Similiarity

  - Min(Shortest distance)
    - most similar
  - Max(largest distance)
    - least similar
  - Group Average
  - Distance Between Centroids



## 3. DBSCAN

- ### Definition

  - Density = number of points in a radius.
  - $\epsilon-neighbor$
  - Core point (interior of a cluster)
    - \> Minpts
  -  border point
    - \< Minpts but in neighbor
  - Noise point
  - MinPts
  - directly density-reachable 
  - Density-reachable

- ### DBSCAN: algorithm outline

- ## Measures of Clustering Quality

  - SSE
  - Cohesion
  - Separation
  - Silhouette Coefficient

