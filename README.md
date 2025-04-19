# Movie-Recommender-Engine
# README.md for Movie Recommender (Clustering-Based)

## Project Overview

This project is a **Movie Recommender System** that leverages clustering techniques to group movies based on their genres and other features. The system uses unsupervised machine learning algorithms such as **Hierarchical Clustering**, **DBSCAN**, and **Fuzzy C-Means** to identify natural groupings within a large movie dataset. Dimensionality reduction techniques like **PCA** and **t-SNE** are used for visualization and to facilitate recommendations. The primary goal is to recommend movies similar to a given title based on their cluster assignments and proximity in reduced feature space[1].

---

## Features

- **Clustering Algorithms**:  
  - Hierarchical Clustering (with dendrogram visualization)
  - DBSCAN (Density-Based Spatial Clustering)
  - Fuzzy C-Means Clustering

- **Dimensionality Reduction**:  
  - Principal Component Analysis (PCA)
  - t-SNE for advanced visualization

- **Movie Recommendation**:  
  - Finds similar movies to a given title using cluster information and feature proximity

- **Evaluation**:  
  - Silhouette Score for cluster quality assessment

---

## Dataset

- The system expects a CSV file named `movies1.csv` containing at least the following columns:
  - `title`: Movie titles
  - `genres`: Comma-separated list of genres per movie

- The genres are multi-label binarized for clustering.

---

## Installation

1. **Clone the repository**
2. **Install dependencies** (Python 3.x required):

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn scipy fuzzy-c-means
   ```

---

## Usage

1. **Prepare the Dataset**  
   Place your `movies1.csv` in the working directory.

2. **Run the Notebook**  
   Open and execute the Jupyter notebook (`MOVIE_RECOMMENDER-1.ipynb`).

3. **Clustering and Visualization**  
   - The notebook will:
     - Encode genres into binary features.
     - Apply clustering algorithms (Hierarchical, DBSCAN, Fuzzy C-Means).
     - Visualize clusters using PCA and t-SNE.
     - Assign cluster labels to each movie.

4. **Movie Recommendation**  
   - Use the provided `recommend_movie` function:
     - Input a movie title.
     - The system finds the closest movies in PCA-reduced space within the same cluster.
     - Returns top 10 similar movies.

---

## Example: Recommend Movies

```python
recommend_movie("The Matrix")
```
- Returns a list of 10 movies most similar to "The Matrix" based on genre clustering and PCA proximity.

---

## Key Files

| File Name                     | Description                                  |
|-------------------------------|----------------------------------------------|
| MOVIE_RECOMMENDER-1.ipynb     | Main notebook with all code and explanations |
| movies1.csv                   | Movie dataset (user-provided)                |
| movies1_fuzzy_c_means_results.csv | Output with cluster assignments           |

---

## Algorithms Used

| Algorithm        | Purpose                              |
|------------------|--------------------------------------|
| Hierarchical     | Group movies, visualize with dendrogram |
| DBSCAN           | Density-based clustering, outlier detection |
| Fuzzy C-Means    | Soft clustering, membership probabilities |
| PCA              | Reduce dimensions for clustering/visualization |
| t-SNE            | Nonlinear visualization of clusters  |

---

## Evaluation

- **Silhouette Score**:  
  Used to assess the quality of the clustering (e.g., 0.48 in sample run indicates moderate cluster separation)[1].

---

## Customization

- You can change clustering parameters (e.g., number of clusters, DBSCAN `eps`/`min_samples`) in the notebook to tune results for your dataset.
- The recommendation logic can be adapted to use other features or similarity metrics.

---

## Limitations

- Recommendations are based on genre and clustering only; no user ratings or collaborative filtering.
- Requires a well-formatted CSV with genre data.

---

## Author

**Anugya Saxena**  
For questions or suggestions, please open an issue or contact the author.

---

## License

This project is open-source and free to use for educational and research purposes.

---

## Acknowledgements

- Uses [scikit-learn](https://scikit-learn.org/), [pandas](https://pandas.pydata.org/), [matplotlib](https://matplotlib.org/), [seaborn](https://seaborn.pydata.org/), and [fuzzy-c-means](https://github.com/omadson/fuzzy-c-means) Python libraries.
