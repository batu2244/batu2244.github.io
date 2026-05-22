---
layout: page
title: NLP Text Embedding and Cluster Analysis
permalink: /projects/nlp-text-embedding/
hide_in_nav: true
---

## NLP Text Embedding and Cluster Analysis

[View on GitHub](https://github.com/batu2244/NLP-text-embedding-and-cluster-analysis)

This project explores two distinct approaches to unsupervised document clustering on Reddit post data, comparing how different embedding strategies affect the quality and interpretability of the resulting clusters.

**Part 1 - Doc2Vec + Agglomerative Clustering**

The first approach trains a Doc2Vec model using the distributed memory architecture, which learns a fixed-size vector representation for each document by predicting words in context while conditioning on a document ID. These document vectors are then clustered using agglomerative (hierarchical) clustering with cosine distance as the similarity metric. Three Doc2Vec configurations are tested, varying vector size, minimum word count, and training epochs, and the resulting clusters are compared across all three.

**Part 2 - Word2Vec + KMeans Bin-Based Vectors**

The second approach trains a Word2Vec model using CBOW, then applies KMeans clustering to the word embedding space to group vocabulary into semantic bins. Each document is then represented as a histogram over these bins - effectively capturing the distribution of semantic concepts in the text. This bin-frequency vector is used as the document representation for a final clustering step. Hyperparameters (embedding dimension, minimum word frequency, number of bins) are configurable via CLI arguments.

**Evaluation**

Both approaches are evaluated using silhouette score, Calinski–Harabasz index, and Davies–Bouldin index, giving a multi-angle view of cluster compactness and separation. Cluster interpretability is also assessed by inspecting the top words near each centroid and the most frequent terms per cluster. Results are logged to JSON for comparison across configurations.
