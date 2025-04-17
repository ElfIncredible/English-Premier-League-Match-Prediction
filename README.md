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

**2. Feature Engineering**

Extracted detailed features such as:
  - Goals per minute
  - Home/Away team scoring patterns
  - Key players contributing to wins
  - Game tempo and turning points

**3. Exploratory Data Analysis (EDA)**

Analyzed goal frequency across match periods, home vs. away performance, and team scoring consistency.

**4. Model Building**
  - Built and trained a predictive model using supervised learning techniques (e.g., Random Forests, XGBoost).
  - Features included team strength, recent form, scoring tendencies, and goal distribution over time.

**5. Prediction System Development**
  - Deployed a logic to combine probabilities and output:
    - Match Result (e.g., Home Win)
    - Final Score Prediction (e.g., 2-1)
    - Outcome Summary (e.g., Fulham Win)

## Problem Statement

Despite the abundance of football data available, most predictive systems either oversimplify match outcomes or rely heavily on traditional stats like win rates and player form. This limits their effectiveness in providing precise predictions such as the exact scoreline or a clear match outcome narrative.

The challenge is to develop a data-driven predictive system that can go beyond binary win/loss outputs and accurately forecast:

  - The full-time result (Home Win, Away Win, or Draw)

  - The final scoreline (e.g., 2-1, 1-1)

  - The named outcome (e.g., "Arsenal Win", "Draw")

## Dataset
This [dataset](https://www.football-data.co.uk/englandm.php) and this [dataset](https://github.com/schochastics/football-data/blob/master/data/goals_time/eng-premier-league.csv) provides comprehensive statistical data on EPL matches starting from the 1993/1994 season up to the current season, with daily updates to ensure the most accurate and timely results.
