# Steam Game Recommendation Prediction

This project investigates whether we can predict if a user will **recommend** a game on Steam based solely on **user–item interaction behavior**.

## Objective

Given a pair *(user, game)*, predict whether the user would recommend the game (`recommend = True/False`).
The task is framed as a **binary classification problem** using supervised machine learning.

## Dataset

We use the `australian_user_reviews.json.gz` dataset, where each user record contains:

* user ID
* a list of games reviewed
* whether each game was recommended
* review metadata

This dataset provides implicit and explicit feedback for modeling user preferences.

## Approach

We:

1. Extract all *(user, game, recommend)* interactions
2. Split data into train/validation sets
3. Build behavior-based features such as
   * game popularity
   * user activity
   * similarity between a user's past games and a candidate game
   * historical recommendation rates
4. Train a logistic regression model to estimate recommendation probability
5. Evaluate performance on the validation set

## Goal

Our goal is to understand which behavioral signals are predictive of game recommendations and to build a simple, interpretable model that captures these patterns.
