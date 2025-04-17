# English-Premier-League-Match-Prediction
This project explores goal-scoring patterns in the English Premier League using detailed match data from several seasons. By leveraging feature engineering and data cleaning, the dataset was transformed into a matchwise breakdown that highlights goal scorers, scoring times, and associated teams. The goal is to enable deeper analytical insights into when, how, and by whom goals are scored—paving the way for predictive modeling.

## Table of Contents
- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Machine Learning](#machine-learning)
  - [Data Acquisition](#data-acquisition)
  - [Data Preprocessing](#data-preprocessing)

## Project Overview
The EPL Goal Scoring Insights project is a data-driven analysis of goal-scoring behavior in the English Premier League during the 2023/24 season. The raw data from football-data.co.uk was refined through feature engineering to focus on individual goal events—identifying the minute, scorer, and team for each goal across all matches.

### Key Objectives
The main goal of this project was to go beyond basic match stats and develop a predictive system that can:

  - Predict the Full-Time Result: Whether the match ends in a Home Win, Away Win, or Draw.

  - Estimate the Final Scoreline: A likely score such as 2-1 or 1-1.

  - Provide a clear Match Outcome Statement: For example, "Fulham Win", "Arsenal Draw", etc.

These insights can help fans, bettors, and analysts anticipate match outcomes with a data-backed foundation.

### Methodology
To achieve these objectives, the project followed a streamlined data science workflow:

**1. Data Collection & Cleaning:**
  - Sourced EPL data from online repositories
  - Cleaned and normalized match records, goal timings, and player names.

Feature Engineering

Extracted detailed features such as:

Goals per minute

Home/Away team scoring patterns

Key players contributing to wins

Game tempo and turning points

Exploratory Data Analysis (EDA)

Analyzed goal frequency across match periods, home vs. away performance, and team scoring consistency.

Model Building

Built and trained a predictive model using supervised learning techniques (e.g., Random Forests, XGBoost).

Features included team strength, recent form, scoring tendencies, and goal distribution over time.

Prediction System Development

Deployed a logic to combine probabilities and output:

Match Result (e.g., Home Win)

Final Score Prediction (e.g., 2-1)

Outcome Summary (e.g., Fulham Win)
