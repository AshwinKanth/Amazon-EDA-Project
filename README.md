# 📊 Amazon Prime Video - Exploratory Data Analysis (EDA)

## 🧠 Project Summary

This project explores and analyzes the Amazon Prime Video catalog to uncover trends in content diversity, regional availability, popularity, and user ratings. By performing structured EDA on a merged dataset of title metadata and credits, we aim to understand what types of content dominate the platform, how it's distributed globally, and what factors influence user engagement.

---

## 📌 Problem Statement

With the rise in streaming platforms, Amazon Prime Video wants to understand what kind of content performs best and where to focus its future investments. The dataset contains metadata about thousands of shows/movies along with cast/crew and popularity metrics. 

**Goal:** Derive insights on content trends, ratings, regional performance, and user preferences to guide business decisions.

---

## 🎯 Business Objective

- Identify dominant genres and categories to understand content diversity.
- Analyze regional content distribution to find growth opportunities.
- Study content evolution over time.
- Examine correlations between popularity and rating metrics.
- Help stakeholders optimize content acquisition and recommendation systems.

---

## 📂 Dataset Overview

The dataset is a combination of two files:
- `titles.csv`: Metadata like title, release year, genres, rating, etc.
- `credits.csv`: Cast and crew information.

**Merged Dataset:** ~125,000 rows, 19 columns.

---

## 🔑 Key Variables Description

| Column                | Description                                      |
|-----------------------|--------------------------------------------------|
| `id`                  | Unique identifier for each title                |
| `title`               | Name of the movie/show                          |
| `type`                | 'MOVIE' or 'SHOW'                               |
| `description`         | Summary of the content                          |
| `release_year`        | Year of release                                 |
| `age_certification`   | Age rating (e.g., PG, R, TV-MA)                 |
| `runtime`             | Length in minutes (movies only)                |
| `seasons`             | Number of seasons (TV shows only)              |
| `genres`              | List of genres (e.g., ['Drama', 'Action'])     |
| `production_countries`| Country or countries of production             |
| `imdb_score`          | IMDb average rating                             |
| `imdb_votes`          | Number of IMDb votes                            |
| `tmdb_score`          | TMDB rating                                     |
| `tmdb_popularity`     | TMDB popularity metric                          |
| `person_id`, `name`, `role`, `character` | Cast/crew information       |

---

## 🛠️ Data Cleaning & Manipulations

- **Removed Duplicates** in `credits` data based on `(id, person_id, role, character)`
- **Handled Missing Values**:
  - Filled missing descriptions, certifications
  - Imputed seasons (for movies = 1)
  - Dropped rows with critical missing ratings (where needed)
- **Type Conversions**:
  - Categorical: `type`, `genres`, `production_countries`
  - Numeric: Casted and cleaned `seasons`, `votes`, etc.
- **Outlier Treatment**:
  - IQR method used for `runtime`, `imdb_score`, etc.
  - Log transformation for highly skewed fields like `imdb_votes`, `tmdb_popularity`
- **Feature Engineering**:
  - Extracted `release_decade`
  - Exploded `genres` and `production_countries` for grouping
  - Created visual summaries using univariate, bivariate, and multivariate analysis

---

## 📈 Key Insights

- **Genres like Drama, Comedy, and Action** are most common on Prime.
- **US, UK, and India** dominate content production.
- **TV shows have grown** significantly post-2015 in both volume and ratings.
- **IMDb ratings are moderately correlated** with TMDB popularity, but runtime doesn't impact ratings much.
- **Content with higher TMDB popularity and IMDb scores** tends to have more votes and engagement.

---

## 🧩 Visualizations Used

### Univariate Analysis
- Genre distribution
- Content Type Breakdown
- Content Release Over Years
- IMDb Score Distribution
- Runtime distribution

### Bivariate Analysis
- Average IMDb score by content type
- Titles per Production Country
- IMDb Score by Genre

### Multivariate Analysis
- IMDb score vs tmdb_score vs popularity
- IMDb Score vs Runtime by Content Type
- Average IMDb Score Over Years by Type

_All visualizations are built using Matplotlib, Seaborn, and Plotly._

---

## ✅ Conclusion

This EDA helps Amazon Prime and its stakeholders:
- Focus on genres and countries with high engagement
- Understand how content evolves with time
- Use ratings and popularity to prioritize what gets recommended or promoted
- Optimize regional investments based on viewer trends

---

## 📦 Tech Stack

- **Language**: Python  
- **Libraries**: Pandas, NumPy, Matplotlib, Seaborn, Plotly  
- **Tools**: Google Colab / Jupyter Notebook


