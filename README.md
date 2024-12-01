# TMKOC Episode Recommender System

This project implements a basic recommender system for the TV show *Taarak Mehta Ka Ooltah Chashmah* (TMKOC) episodes using **TF-IDF** (Term Frequency-Inverse Document Frequency) and **Cosine Similarity**. The system recommends similar episodes based on episode titles and descriptions.

## Features

- **TF-IDF Vectorization**: Converts episode titles and descriptions into numerical vectors.
- **Cosine Similarity**: Measures the similarity between episodes based on the TF-IDF vectors.
- **Episode Recommendation**: Given an episode, the system will recommend the top 5 most similar episodes.

## Prerequisites
```
Make sure you have the following Python packages installed:

- pandas
- scikit-learn
- nltk

You can install them using `pip`:


pip install pandas scikit-learn nltk
```

## Project Structure
```
├── Cosine-sim.ipynb    # Main Python script for recommendation logic
├── tmkoc_episode.csv      # CSV file containing episode data (episode_number, Episode_title, description, Episode_runtime, Released_on)
├── README.md               # Project documentation
```

## Dataset Format
```
The dataset (tmkoc_episodes.csv) should have the following columns:

episode_number: A unique identifier for each episode.
Episode_title: The title of the episode.
description: A brief description of the episode.
Episode_runtime: The duration of the episode (in minutes or seconds).
Released_on: The release date of the episode.
Example of the CSV format:

episode_number,Episode_title,description,Episode_runtime,Released_on
1,"Episode 1 Title","Description of the first episode",20,"2024-01-01"
2,"Episode 2 Title","Description of the second episode",20,"2024-01-08"
```

## How It Works
```
Dataset: The dataset (tmkoc_episodes.csv) contains information about the episodes, including episode_number, Episode_title, description, Episode_runtime, and Released_on.

Data Preparation: The episode titles and descriptions are combined into a single text column for each episode, forming a complete description of each episode. This is done to better capture the context when calculating similarities between episodes.

data = []  # List to store the combined data

# Iterate over each index in the DataFrame
for ind in df.index:
    # Concatenate the episode title and description with a space or separator
    combined_data = str(df['Episode_title'][ind]) + " " + str(df['description'][ind])
    data.append(combined_data)
TF-IDF Vectorization: The combined episode titles and descriptions are converted into numerical vectors using the TfidfVectorizer from scikit-learn.

Cosine Similarity: The cosine_similarity function calculates how similar each episode is to others based on their TF-IDF vectors.

Recommendation System: The system can recommend the top 5 most similar episodes to a given episode. The recommendations are based on cosine similarity scores.
```


