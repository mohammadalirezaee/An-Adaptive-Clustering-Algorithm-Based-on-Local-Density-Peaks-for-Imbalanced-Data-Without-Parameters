# Adaptive Clustering Algorithm based on Local Density Peaks

This repository contains a Python implementation of an adaptive clustering algorithm based on local density peaks, as described in the research article:

**Title:** An Adaptive Clustering Algorithm Based on Local Density Peaks for Imbalanced Data Without Parameters
**Authors:** Tong, Wuning; Wang, Yuping; Liu, Delong
**Journal:** IEEE Transactions on Knowledge and Data Engineering
**Year:** 2021

## Overview

The provided Jupyter Notebook implements an adaptive clustering algorithm designed specifically for imbalanced data without requiring predefined parameters. This algorithm utilizes the concept of local density peaks to identify clusters in data with varying densities.

## Method Description

The LDPI algorithm consists of three main steps: initial subcluster construction, subcluster update, and subcluster merging.

### Initial Subcluster Construction

1. **Density Calculation:** Calculate the density for each data point based on the Euclidean distances between data points. Density values are computed within a specified radius, which is determined based on the nearest neighbor distances.

2. **Upward Distance Calculation:** Calculate the upward distance for each data point. This value is based on the density of the data point compared to its neighbors.

3. **Noise Identification:** Identify noise points using the calculated density, upward distance, and Recursive nearest neighbor (RNN) values. A semantic graph is used to visualize noise points.

4. ### Subcluster Update

1. **Cluster Validity Check:** Check the validity of each constructed cluster. If the number of members in a cluster is less than half of the members in the specified radius from the cluster center, the cluster is considered not real.

2. **Reassignment:** Reassign data points that do not belong to a valid cluster to the closest cluster center.

### Subcluster Merging

1. **Merge Criteria:** Calculate the distance threshold 'r' based on the density values and cluster distances. Clusters with a distance greater than 'r' cannot be merged.

2. **Boundary Points:** Identify boundary points within each cluster based on average density. Merge clusters based on density comparisons and the presence of boundary points.

3. **Iterative Merging:** Repeatedly perform merging actions until no further clusters can be merged.
