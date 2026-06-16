# Unsupervised Machine Learning: Iris Feature Space Clustering Benchmark

## Project Overview
This project evaluates pattern discovery on the classic Iris botanical dataset using unsupervised machine learning methodologies. To ensure unbiased discovery, all taxonomic species labels were discarded prior to training, benchmarking **K-Means Clustering** and **Agglomerative Hierarchical Clustering** architectures side by side.

---

## 1. Data Preprocessing & Theoretical Justifications
* **Missing Value Profile:** The native scikit-learn Iris matrix is fully complete and contains zero missing records or structural noise.
* **Feature Scaling (Standardization):** Features were transformed using standard normal standardization ($z = (x - \mu) / \sigma$).
* **Justification:** Both K-Means and Hierarchical Clustering rely heavily on spatial distance calculations (such as Euclidean distance metrics). Features with larger raw numerical ranges (e.g., `sepal length`, ranging up to 7.9 cm) can artificially dominate features with naturally smaller values (e.g., `petal width`, ranging down to 0.1 cm). Standardization ensures each morphological attribute contributes equally to geometric space partitioning.

---

## 2. Clustering Algorithms & Suitability

### 1. K-Means Clustering
* **How it Works:** An iterative partitioning algorithm that defines $k$ initial centroids, maps every data point to its closest centroid using Euclidean distance, and continually re-computes centroid coordinates to minimize the within-cluster Sum of Squared Errors (SSE).
* **Suitability:** Highly effective for the Iris dataset because its physical feature boundaries are convex, spherical, and exhibit clear spatial segregation when evaluated across petal dimensions.

### 2. Agglomerative Hierarchical Clustering
* **How it Works:** A bottom-up agglomerative approach where every observation begins as an isolated cluster. The algorithm progressively merges the two closest clusters based on a proximity matrix using Ward's minimum variance linkage method until a single tree structure is formed.
* **Suitability:** Excellent for displaying the biological, taxonomic relationship connections between individual samples, which can be easily sliced into distinct sub-species divisions using a dendrogram.

---

## 3. Visualizations & Analytical Conclusions
The completed notebook evaluates and confirms clustering structure across three target plots:
1. **K-Means Scatter Plots:** Displays three clean spatial groupings with the final calculated mathematical cluster centroids overlayed.
2. **Linkage Dendrogram:** Graphically maps out the tree-like merging hierarchy. Slicing horizontally at a Cophenetic distance threshold of $\approx 7.0$ confirms the natural emergence of exactly 3 distinct botanical branches.
3. **Hierarchical Scatter Map:** Visualizes cluster partitions using petal features, demonstrating robust, well-defined group boundaries that match native biological structures closely.

## Workspace Local Run Guidelines
1. Clone this repository to your local directory setup.
2. Install the necessary machine learning and charting dependencies:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn scipy
