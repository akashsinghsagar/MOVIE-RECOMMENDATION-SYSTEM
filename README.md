# 🎬 Movie Recommender System

A modern content-based Movie Recommendation System built using **FastAPI**, **Streamlit**, and **TMDB API**. The application combines real-time movie metadata with a TF-IDF recommendation engine to deliver personalized movie suggestions through an intuitive and responsive user interface.

---

## Overview

This project enables users to discover movies through keyword search, browse curated movie categories, explore detailed movie information, and receive intelligent recommendations based on content similarity and genre.

The recommendation engine leverages **TF-IDF vectorization** and **Cosine Similarity** to identify movies with similar characteristics, while **TMDB** provides rich metadata including posters, backdrops, genres, ratings, and release information.

---

## Features

- Intelligent movie search with autocomplete
- Trending, Popular, Top Rated, Upcoming, and Now Playing categories
- Detailed movie information powered by TMDB
- High-resolution posters and backdrop images
- Content-based recommendations using TF-IDF
- Genre-based recommendations
- Fast and responsive Streamlit interface
- RESTful FastAPI backend
- Cached API responses for improved performance

---

## Technology Stack

### Frontend
- Streamlit

### Backend
- FastAPI
- Python
- HTTPX

### Machine Learning
- Scikit-learn
- TF-IDF Vectorization
- Cosine Similarity

### Data Processing
- Pandas
- NumPy

### External Services
- The Movie Database (TMDB) API

---

## System Architecture

```
                  TMDB API
                     │
                     ▼
              FastAPI Backend
      ┌──────────────────────────┐
      │ Search API               │
      │ Movie Details API        │
      │ Recommendation Engine    │
      │ Genre Discovery API      │
      └──────────────────────────┘
                     │
                     ▼
             Streamlit Frontend
                     │
                     ▼
                   End User
```

---

## Project Structure

```
Movie-Recommender/
│
├── app.py                  # Streamlit Frontend
├── main.py                 # FastAPI Backend
├── df.pkl                  # Movie dataset
├── tfidf.pkl               # TF-IDF Vectorizer
├── tfidf_matrix.pkl        # Sparse TF-IDF Matrix
├── indices.pkl             # Movie Index Mapping
├── .env                    # Environment Variables
├── requirements.txt
└── README.md
```

---

## Recommendation Pipeline

### Content-Based Filtering

The recommendation engine uses **TF-IDF Vectorization** to transform movie descriptions into numerical vectors. **Cosine Similarity** is then applied to identify movies with the highest textual similarity.

### Genre-Based Discovery

Genre recommendations are generated using TMDB's Discover API, allowing users to explore popular movies within similar genres.

---

## API Endpoints

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | `/` | API Information |
| GET | `/health` | Health Check |
| GET | `/home` | Browse Movie Categories |
| GET | `/tmdb/search` | Search Movies |
| GET | `/movie/id/{tmdb_id}` | Retrieve Movie Details |
| GET | `/recommend/tfidf` | Content-Based Recommendations |
| GET | `/recommend/genre` | Genre Recommendations |
| GET | `/movie/search` | Combined Recommendation Response |

---

## Installation

### Clone the Repository

```bash
git clone https://github.com/your-username/movie-recommender.git

cd movie-recommender
```

### Create Virtual Environment

```bash
python -m venv .venv
```

Windows

```bash
.venv\Scripts\activate
```

Linux/macOS

```bash
source .venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Configure Environment Variables

Create a `.env` file in the project root.

```env
TMDB_API_KEY=YOUR_TMDB_API_KEY
```

### Start FastAPI Server

```bash
uvicorn main:app --reload
```

API Documentation

```
http://127.0.0.1:8000/docs
```

### Launch Streamlit Application

```bash
streamlit run app.py
```

---

## Future Enhancements

- User Authentication
- Personalized Watchlists
- Collaborative Filtering
- Hybrid Recommendation Engine
- User Ratings and Reviews
- Recommendation History
- Docker Support
- Cloud Deployment (AWS, Azure, Render)
- CI/CD Pipeline
- Unit & Integration Testing

---

## Screenshots

| Home | Details | Recommendations |
|------|---------|-----------------|
| Add Screenshot | Add Screenshot | Add Screenshot |

---

## Contributing

Contributions are welcome.

If you would like to improve the project, feel free to fork the repository, create a feature branch, and submit a pull request.

---

## License

This project is licensed under the **MIT License**.

---

## Author

**Akash Singh Sagar**

- GitHub: https://github.com/your-username
- LinkedIn: https://linkedin.com/in/your-profile

---

## Acknowledgements

- **The Movie Database (TMDB)** for providing comprehensive movie metadata.
- **Scikit-learn** for machine learning utilities.
- **FastAPI** for the high-performance backend framework.
- **Streamlit** for rapid frontend development.
