# Introduction to Data Mining: Cluster Analysis (Module 5)

#data-mining #clustering #unsupervised-learning #k-means #k-medoids #partition-methods

## Module Objectives

This module continues examining important principles and methods of data mining, focusing on cluster analysis as an important functionality of knowledge discovery. The lecture notes cover:

- Basic definitions of cluster analysis
- Domain areas for cluster analysis applications
- Popular clustering algorithms
- Computational complexity of cluster analysis
- Various approaches to cluster analysis

## Introduction to Cluster Analysis

> [!important] Definition Cluster analysis is the process of separating or partitioning a set of given objects into subsets. The subsets will be disjoint pairwise, i.e., the intersection of any two subsets is empty. Each subset is referred to as a cluster and the set of clusters as a clustering.

The goal of cluster analysis is to obtain a clustering such that:

- Objects in the same cluster are similar to each other
- Objects in different clusters are dissimilar to each other

In other words, cluster analysis aims at finding groups of objects that are homogeneous or similar in some way.

### Applications of Cluster Analysis

Cluster analysis is useful for understanding patterns and relationships in datasets. Common applications include:

- Market research
- Identification of outliers
- Pattern recognition
- Risk analysis
- Image segmentation

> [!note] Unsupervised Learning Cluster analysis is a form of [[unsupervised learning]], a term used to describe methods that try to group objects without using labeled outcomes.

## Partitioning Methods

> [!note] Unless otherwise stated, all numerical values in these Lecture Notes are rounded to 1 decimal place.

Given a dataset, clusters can be found with a variety of methods. The lecture focuses on two particular methods:

1. [[k-means]]
2. [[k-medoids]]

In both methods:

- k denotes the number of clusters (parameter known beforehand)
- Each cluster has a representative (either taken from objects in the cluster or computed)
- Each object is assigned to the cluster whose representative is most similar to it
- A typical representative is the centroid (an object describing the center of the cluster)

### Distance as Similarity Criterion

These methods use distance as the criterion of similarity:

- The smaller the distance between two objects, the more similar they are
- Datasets consist of n points in m-dimensional Euclidean space
- Each object is a point p = (x₁, x₂, …, xₘ) with m coordinates
- Distance between two objects p₁ and p₂ is the Euclidean distance, denoted by d(p₁, p₂)

### Optimization Goal

Both methods aim to construct a clustering of k subsets where:

- Each cluster contains at least one point
- Clusters are pairwise disjoint
- Intracluster similarity is maximized
- Intercluster similarity is minimized

More precisely, the methods solve the optimization problem of finding a clustering that minimizes an objective function: the sum of square errors between objects and their centroids.

> [!important] Objective Function The objective function is defined as: E = ∑ᵏᵢ₌₁ ∑ₚ∈𝓒ᵢ (d(p, cᵢ))²
> 
> Where 𝓒ᵢ denotes the i-th cluster and cᵢ the centroid of 𝓒ᵢ. E is called the within-cluster variation.

## k-means Algorithm

The k-means method defines the centroid of a cluster as the mean of the points in the cluster and uses this centroid as the representative of the cluster.

> [!example] Centroid Calculation Example If cluster 𝓒₁ contains points (3,1), (5,2), and (2,3), then the centroid c₁ will be:
> 
> c₁ = ((3+5+2)/3, (1+2+3)/3) = (10/3, 6/3) ≈ (3.3, 2)

### k-means Algorithm Steps

```
Algorithm k-Means
input: k, D
output: a set of k clusters with each point in D assigned to exactly one cluster

1. randomly choose k points from D as the initial centers
2. do
3.    assign each point p in D to the cluster to which p is the most similar
4.    recompute the cluster centers
5. while (last two clusterings are different)
```

The algorithm:

- Starts with random choice of points as initial centers
- In each iteration, reassigns each point p to the cluster whose center is closest to p
- Iteratively computes clusterings until there is no change (convergence)

### k-means Example

> [!example] k-means Detailed Example Let D be the set of points: D = {p₁(3,1), p₂(5,2), p₃(2,3), p₄(6,3), p₅(3,5), p₆(7,4.5), p₇(1,2)}
> 
> Assume k = 2 and let 𝓒₁ and 𝓒₂ denote the two clusters.
> 
> **Initial Step**:
> 
> - p₄ and p₆ are randomly generated as the centers of 𝓒₁ and 𝓒₂, respectively
> 
> **First Iteration Distance Matrix**:
> 
> ||p₁|p₂|p₃|p₄|p₅|p₆|p₇|
> |---|---|---|---|---|---|---|---|
> |c₁=p₄|3.6|1.4|4.0|0.0|3.6|1.8|5.1|
> |c₂=p₆|5.3|3.2|5.2|1.8|4.0|0.0|6.5|
> 
> After first iteration, clusters are:
> 
> - 𝓒₁ = {p₁, p₂, p₃, p₄, p₅, p₇}
> - 𝓒₂ = {p₆}
> 
> **New Centers**:
> 
> - c₁ = ((3+5+2+6+3+1)/6, (1+2+3+3+5+2)/6) = (20/6, 16/6) ≈ (3.3, 2.7)
> - c₂ = p₆ = (7, 4.5)
> 
> **Second Iteration Distance Matrix**:
> 
> ||p₁|p₂|p₃|p₄|p₅|p₆|p₇|
> |---|---|---|---|---|---|---|---|
> |c₁(3.3,2.7)|1.7|1.8|1.4|2.7|2.4|4.1|2.4|
> |c₂=p₆|5.3|3.2|5.2|1.8|4.0|0.0|6.5|
> 
> Point p₄ is now closer to c₂, so the new clusters are:
> 
> - 𝓒₁ = {p₁, p₂, p₃, p₅, p₇}
> - 𝓒₂ = {p₄, p₆}
> 
> **New Centers**:
> 
> - c₁ = (2.8, 2.6)
> - c₂ = (6.5, 3.75)
> 
> **Third Iteration Distance Matrix**:
> 
> ||p₁|p₂|p₃|p₄|p₅|p₆|p₇|
> |---|---|---|---|---|---|---|---|
> |c₁(2.8,2.6)|1.6|2.3|0.9|3.2|2.4|4.6|1.9|
> |c₂(6.5,3.75)|4.5|2.3|4.6|0.9|3.7|0.9|5.8|
> 
> The clustering doesn't change, so the algorithm stops with final clusters:
> 
> - 𝓒₁ = {p₁, p₂, p₃, p₅, p₇}
> - 𝓒₂ = {p₄, p₆}

## k-Medoids Algorithm

> [!warning] k-means Limitation Based on mean calculations, the k-means algorithm is sensitive to outliers.

To prevent sensitivity to outliers, the k-medoids method:

- Uses original data points as representatives (medoids) instead of means
- Representatives are known as medoids

### k-Medoids Objective Function

The partitioning mechanism of k-medoids aims at minimizing the sum of the dissimilarities between the objects in a cluster and the center of the same cluster:

E = ∑ᵏᵢ₌₁ ∑ₚ∈𝓒ᵢ d(p, oᵢ)

Where oᵢ denotes the center (medoid) of cluster 𝓒ᵢ.

### PAM Algorithm

A popular implementation of the k-medoids method is the **partitioning around medoids** or **PAM** algorithm:

- Iteratively exchanges cluster representatives with non-representative data points
- Determines a partition into k clusters that minimizes E

## Complexity of the Partitioning Problem

> [!important] Computational Difficulty The problem of finding an optimal clustering that minimizes an objective function such as the within-cluster variation is computationally difficult, requiring large computational resources to solve.

- k-means clustering is an NP-hard optimization problem, even for data points in the plane
- The k-means and k-medoids methods are greedy heuristics
- These methods will generally be trapped in local optimums

## Other Approaches to Cluster Analysis

In addition to partitioning methods, other approaches to cluster analysis include:

1. **Hierarchical methods**:
    
    - Create hierarchy of clusters in the form of a tree
2. **Density methods**:
    
    - Create clusters based on the density of data point regions

> [!note] Non-Exclusive Clustering While cluster analysis often involves finding partitions of data sets (i.e., each element belongs to one and only one cluster), for some applications an object might be part of more than one cluster.

---

## Related Concepts & Potential Internal Links

- [[Unsupervised Learning]]
- [[Clustering Algorithms]]
- [[Euclidean Distance]]
- [[Centroid]]
- [[Medoid]]
- [[NP-hard Problems]]
- [[Local Optimum]]
- [[Hierarchical Clustering]]
- [[Density-Based Clustering]]
- [[Data Mining]]