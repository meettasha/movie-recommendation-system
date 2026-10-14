# movie-recommendation-system

A ** Movie Recommendation System** that combines Content-Based Filtering and Collaborative Filtering to recommend movies based on movie similarities and user preferences.

This project explores how different recommendation techniques can be combined to generate personalized movie recommendations while considering ranking quality, diversity, and novelty.

## Project Overview

Movie recommendation systems help users discover relevant movies from large collections. This project implements a hybrid approach that combines:

- **Content-Based Filtering:** Recommends movies similar to a selected movie using its title and genres.
- **Collaborative Filtering:** Uses user-rating patterns and Singular Value Decomposition (SVD) to predict ratings.
- **Hybrid Recommendation:** Combines content similarity and predicted ratings to rank recommendations.
- **Popularity-Based Recommendation:** Provides a baseline using weighted movie ratings.
- **Cold-Start Handling:** Provides fallback recommendations when sufficient user-rating information is unavailable.

## Objectives

- Explore and preprocess the MovieLens dataset.
- Implement content-based and collaborative filtering techniques.
- Combine multiple recommendation signals into a hybrid model.
- Evaluate rating prediction and recommendation-list characteristics.
- Analyze the trade-off between recommendation diversity and novelty.
- Generate personalized movie recommendations.

## Dataset

**Dataset:** [MovieLens Latest Small](https://grouplens.org/datasets/movielens/latest/)

The dataset contains movie metadata, genres, user IDs, movie IDs, and user ratings.

| Dataset statistic | Value |
|---|---:|
| Movies | 9,742 |
| Ratings | 100,836 |
| Users | 610 |
| Rating scale | 0.5–5.0 |
| Mean rating | 3.502 |

## Technologies Used

- Python
- Google Colab
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- TF-IDF Vectorization
- Cosine Similarity
- Surprise (SVD collaborative filtering)

## Methodology

### 1. Data Preprocessing and Exploration

- Load and examine the MovieLens dataset.
- Analyze movie and rating distributions.
- Prepare movie metadata and user-rating information.

### 2. Popularity-Based Filtering

Calculate weighted movie ratings to establish a baseline for recommendations.

### 3. Content-Based Filtering

- Combine movie titles and genres into text features.
- Convert text into numerical representations using TF-IDF.
- Calculate cosine similarity between movies.
- Recommend movies with similar content.

### 4. Collaborative Filtering

- Train an SVD model using user-movie rating interactions.
- Predict ratings for user-movie pairs.
- Use predicted ratings to estimate user preferences.

### 5. Hybrid Recommendation

Combine content similarity and collaborative-filtering predictions using a configurable weighting parameter, alpha.

The alpha parameter controls the contribution of the two recommendation signals.

### 6. Evaluation

The notebook explores the following evaluation metrics:

- RMSE and MAE for rating prediction.
- Precision@K, Recall@K, and F1@K.
- Recommendation diversity and novelty.
- Experiments with different alpha values.

## Results

The notebook produced the following SVD rating-prediction results:

| Metric | Result |
|---|---:|
| RMSE | 0.8774 |
| MAE | 0.6743 |

The alpha experiments examine how changing the hybrid weighting affects recommendation diversity and novelty.

**Note:** RMSE and MAE measure rating-prediction error for the SVD model. They should not be interpreted as direct evaluation scores for the hybrid ranking model. Ranking metrics and diversity/novelty results depend on the evaluation setup used in the notebook.

## Author

**Meetasha Kapur**  
B.Tech Computer Science and Engineering  
Manipal University Jaipur

## References

- [MovieLens Dataset — GroupLens Research](https://grouplens.org/datasets/movielens/)
- [Scikit-learn Documentation](https://scikit-learn.org/stable/)
- [Surprise: A Python Scikit for Building and Analyzing Recommender Systems](https://surpriselib.com/)

*Developed as part of a Recommender Systems academic project.*
