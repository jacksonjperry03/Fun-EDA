## [Rice Grain Classification with KMeans Clustering](./rice_clustering.ipynb)

This Jupyter Notebook explores the application of KMeans clustering to classify rice grains based on features like area, perimeter, and eccentricity. It utilizes the `scikit-learn` library in Python for data analysis and visualization.

### Data Acquisition

The dataset, ["Rice (Cammeo and Osmancik)"](./Rice_Cammeo_Osmancik.arff), was retrieved from [https://archive.ics.uci.edu/dataset/545/rice+cammeo+and+osmancik](https://archive.ics.uci.edu/dataset/545/rice+cammeo+and+osmancik).

**Dataset:**

- The dataset used in this notebook is the "Rice_Cammeo_Osmancik.arff" containing information about two rice species: Cammeo and Osmancik.

**Objective:**

- Identify potential patterns within the rice data that could differentiate between the two species using unsupervised KMeans clustering.

**Steps:**

1. **Data Loading and Cleaning:**
   - Load the rice data using `arff.loadarff` from `scipy.io`.
   - Handle categorical variables (species labels) for compatibility with KMeans.
   - Separate features (area, perimeter, etc.) from the target variable (species class).

2. **KMeans Clustering:**
   - Initialize a KMeans model with default parameters.
   - Perform KMeans clustering on the features.
   - Evaluate the clustering quality using the silhouette score.

3. **Hyperparameter Tuning:**
   - Perform a basic grid search over the number of clusters and initialization values (`n_clusters` and `n_init`).
   - Re-evaluate the clustering using the silhouette score to find optimal parameters.

4. **Visualization:**
   - Create pairplots to visualize the data distribution before and after clustering, colored by the assigned cluster labels.

5. **Interpretation (Optional):**
   - Analyze the features within each cluster to understand what properties they represent for the rice grains.

**Results:**

- The notebook demonstrates that by tuning the KMeans hyperparameters, a better separation between the two rice species can be achieved based on the silhouette score.
- Pair plots with cluster coloring visually confirm the improved separation after hyperparameter optimization.

**Further Exploration:**

- Explore alternative clustering algorithms to see if they yield different or potentially better results.


<sub> 
This README document was partially generated with the assistance of artificial intelligence.
</sub>

