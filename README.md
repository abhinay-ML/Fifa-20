# Fifa-20
Explore football skills and cluster football players based on their attributes.
FIFA 20 Player Analysis and Clustering

Overview:
This notebook analyzes the FIFA 20 players dataset (players_20.csv) to explore player attributes and group players into meaningful clusters based on core skill features. The analysis includes data cleaning, exploratory data analysis (country counts, distributions, correlations), feature scaling, KMeans clustering on selected skill features (pace, shooting, passing, dribbling, defending, physic), PCA-based visualization of clusters, and evaluation using silhouette scores.

Dataset:
- Source file used: players_20.csv (place this CSV in the same folder as the notebook).
- Contains player-level attributes such as name, age, nationality, overall rating, value_eur, wage_eur, and a range of skill attributes.

Preprocessing:
- Dropped columns with many missing values (goalkeeper-specific and other sparse fields).
- Imputed numeric columns with median values and categorical columns with the mode (or 'Unknown' where mode missing).
- Converted missing-heavy columns were removed; remaining missing values were filled so no NaNs remain.

Exploratory Data Analysis (EDA):
- Visualized top countries by player count (bar plot).
- Plotted distribution of 'overall' ratings and log/summary stats.
- Computed correlation matrix for features: age, value_eur, wage_eur, overall.
- Investigated per-skill distributions and relationships.

Feature Engineering & Clustering:
- Selected skill features: ['pace', 'shooting', 'passing', 'dribbling', 'defending', 'physic'] for clustering.
- StandardScaler applied to skill features.
- KMeans clustering performed with multiple k values; silhouette scores computed to assist selection.
- Final clustering examples performed for k=2, k=4, and k=5 in different cells; cluster centers and profiles were inspected to label clusters (e.g., Attacking/Skillful vs Defensive/Physical).

Dimensionality Reduction & Visualization:
- PCA (n_components=2) applied to scaled skill features to visualize clusters in 2D.
- Scatter plots and heatmaps visualize cluster skill-profiles and PCA separation.
- Explained variance ratio printed for PCA components.

Results:
- Cluster centroids show distinct skill profiles per cluster (e.g., higher pace/dribbling vs higher defending/physic).
- Silhouette scores were calculated for k in range(2,7) to evaluate clustering quality; final silhouette score printed for the chosen K (e.g., K=2).

Files in this repo:
- fifa 20.ipynb  — main Jupyter notebook (EDA, preprocessing, clustering, PCA visualizations)
- players_20.csv — dataset (place alongside the notebook)
- README_fifa20.txt — this file

How to run:
1. Ensure `players_20.csv` is in the same directory as `fifa 20.ipynb`.
2. (Optional) Create and activate a Python virtual environment.
3. Install required libraries (example):
   pip install pandas numpy matplotlib seaborn scikit-learn
4. Open and run the notebook in Jupyter:
   jupyter notebook "fifa 20.ipynb"

Notes & Next Steps:
- Try different clustering algorithms (Agglomerative, DBSCAN) or tune KMeans with elbow method for better separation.
- Extend analysis by including position-specific features or separating goalkeepers from outfield players.
- Use t-SNE or UMAP for alternate visualizations of player similarity.
- Export cluster assignments to CSV to use for downstream tasks (scouting filters, team-building tools).

License:
MIT — free to reuse and adapt for educational purposes.
