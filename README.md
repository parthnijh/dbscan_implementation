

---

# DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

This repository contains an implementation of **DBSCAN**, a clustering algorithm that groups together points that are closely packed (points with many nearby neighbors) and marks points in low-density regions as **noise**.

## 📌 Overview

DBSCAN is a **density-based** clustering method that:

* Can find arbitrarily shaped clusters.
* Does not require specifying the number of clusters beforehand.
* Handles noise points well.

## ⚙️ Parameters

* **eps** *(float)*: Maximum distance between two points for them to be considered neighbors.
* **min\_samples** *(int)*: Minimum number of points required to form a dense region.

## 🚀 Usage

```python
from sklearn.cluster import DBSCAN
import numpy as np

# Example dataset
from sklearn.datasets import make_moons
X, _ = make_moons(n_samples=500, noise=0.05)

# Run DBSCAN
model = DBSCAN(eps=0.2, min_samples=5)
labels = model.fit_predict(X)

print("Cluster labels:", labels)
```

## 📊 Example Plot

```python
import matplotlib.pyplot as plt

plt.scatter(X[:, 0], X[:, 1], c=labels, cmap='plasma', s=30)
plt.show()
```

## 📈 Choosing Parameters

* **eps**: Use a **k-distance graph** (plot sorted distances to k-th nearest neighbor) to find an elbow point.
* **min\_samples**: Start with **2 × number of features**, then adjust for better results.

## 📦 Requirements

* `numpy`
* `matplotlib`
* `scikit-learn`

## 📜 License

MIT License.

---


