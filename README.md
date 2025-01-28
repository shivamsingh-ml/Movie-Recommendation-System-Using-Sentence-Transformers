# Movie Recommendation System Using Sentence-Transformers

## Overview
This project is a content-based movie recommendation system built using Netflix's Movies and TV Shows dataset. By leveraging natural language processing and vector similarity techniques, the system can suggest movies or TV shows that are similar to a user's favorite title. It uses FAISS (Facebook AI Similarity Search) for efficient similarity searches and the SentenceTransformers library for creating textual embeddings of the dataset.

---

## Dataset

### Source:
The dataset used in this project is the [Netflix Movies and TV Shows](https://www.kaggle.com/datasets/shivamb/netflix-shows) dataset from Kaggle.

### Description:
Netflix is one of the most popular media streaming platforms, offering over 8000 movies and TV shows as of mid-2021. This tabular dataset provides details for each title, including:
- Title
- Type (Movie or TV Show)
- Director
- Cast
- Release Year
- Genres
- Description

---

## Key Features of the Project
1. **Data Preprocessing**:
   - The dataset is read and processed using pandas to create a clean textual representation of each movie/TV show, combining key attributes like title, director, cast, genres, and description.

2. **Textual Embedding Generation**:
   - Textual data for each title is transformed into high-dimensional vectors using the SentenceTransformer model `all-MiniLM-L6-v2`.

3. **Similarity Search Using FAISS**:
   - The FAISS library is used to efficiently index and search for movies or TV shows similar to the user's favorite.

4. **Content-Based Recommendations**:
   - Given a favorite movie or TV show, the system generates a list of the top 5 most similar titles based on their textual representation embeddings.

---

## How It Works

1. **Loading the Dataset:**
   - The dataset is loaded and the key columns are used to create a textual representation for each movie or TV show.

2. **Embedding Creation:**
   - The textual representations are embedded into 384-dimensional vectors using the `all-MiniLM-L6-v2` model from SentenceTransformers.

3. **Indexing with FAISS:**
   - The embeddings are added to a FAISS index for efficient similarity searching.

4. **Making Recommendations:**
   - A favorite movie is selected, and its embedding is computed.
   - The FAISS index is queried to find the top 5 most similar titles.

---

## Prerequisites
- Python 3.8+
- Libraries:
  - pandas
  - numpy
  - sentence-transformers
  - faiss

---

