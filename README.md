# English-Premier-League-Match-Prediction
This project explores goal-scoring patterns in the English Premier League using detailed match data from several seasons. By leveraging feature engineering and data cleaning, the dataset was transformed into a matchwise breakdown that highlights goal scorers, scoring times, and associated teams. The goal is to enable deeper analytical insights into when, how, and by whom goals are scored—paving the way for predictive modeling.

## Table of Contents
- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Machine Learning](#machine-learning)
   - [Data Preprocessing](#data-preprocessing)
   - [Model Selection](#model-selection)

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

EPL Match Dataset has these columns:

    Date: Match Date (dd/mm/yy)
    HomeTeam: Home Team
    AwayTeam: Away Team
    FTHG: Full Time Home Team Goals
    FTAG: Full Time Away Team Goals
    FTR: Full Time Result (H=Home Win, D=Draw, A=Away Win)
    HTHG: Half Time Home Team Goals
    HTAG: Half Time Away Team Goals
    HTR: Half Time Result (H=Home Win, D=Draw, A=Away Win)
    Referee: Match Referee
    HS: Home Team Shots
    AS: Away Team Shots
    HST: Home Team Shots on Target
    AST: Away Team Shots on Target
    HF: Home Team Fouls Committed
    AF: Away Team Fouls Committed
    HC: Home Team Corners
    AC: Away Team Corners
    HY: Home Team Yellow Cards
    AY: Away Team Yellow Cards
    HR: Home Team Red Cards
    AR: Away Team Red Cards

Player Scoring dataset has these columns:

    scoring_player: Player who scored
    scoring_team: Team which scored
    time: Time which a player scored
    GH: Goals scored by Home Team
    GA: Goals scored by Away Player
    game: match pairing
    date: date of the match
    season: Season of the match

## Machine Learning
### Data Preprocessing

The data processing stage was crucial in transforming raw football match records into a format suitable for machine learning. This process involved cleaning, engineering new features, and structuring the dataset for accurate prediction of match outcomes.

#### 1. Data Cleaning
  - Removed incomplete records and duplicates.

  - Standardized team names and formats across seasons.

  - Parsed and aligned match date formats to support time-aware modeling.

#### 2. Feature Engineering
To enhance the predictive power of the model, several new features were created based on historical performance, team statistics, and match outcomes. These include:

- **Performance Metrics:**
  - HTGD (Home Team Goal Difference): Cumulative goal difference up to the match.
  - ATGD (Away Team Goal Difference)
  - HTGP / ATGP: Total games played by each team.
  - HTW / ATW: Total wins for the home and away teams.
  - HTD / ATD: Total draws.
  - HTL / ATL: Total losses.
  - HTP / ATP: Points accumulated by each team (typically calculated as 3×Wins + 1×Draws).

- **Match Outcome Details:**
   - GD: Final goal difference in the match (used for evaluating prediction accuracy).
   - TG: Total goals scored by both teams.
   - Scores: The actual scoreline (e.g., 2–1).
   - HomeTeam, Awayteam: Categorical identifiers for each match.
   - HSS, ASS: Number of scorers for the home and away teams.HSTS, ASTS: The minutes at which each goal was scored.

These features were chosen for their relevance in capturing team form, offensive/defensive strength, and recent momentum—critical factors in determining match outcomes.

#### 3. Encoding and Transformation
- Categorical features like HomeTeam and Awayteam were label-encoded.
- Numerical features were normalized to ensure consistent model behavior.
- Time-series dependencies were preserved by avoiding data leakage between train and test splits.

### Model Selection
To predict football match outcomes with high accuracy, careful consideration was given to selecting appropriate machine learning models that could handle the complexities of the data, including non-linear relationships, class imbalance, and feature interactions.

**1.Prediction Goals**

The model was trained to predict three key outcomes:
   - Full-Time Result (Win, Lose, Draw)
   - Scoreline (e.g., 2–1)
   - Outcome Summary (e.g., "Fulham Win")

Given these objectives, I adopted a multi-model approach, where separate models could be trained for classification (result, outcome summary) and regression (score prediction) tasks.

**2. Models Considered**

Several models were tested and compared based on performance metrics like accuracy, F1-score, and mean absolute error (for score prediction):
   **- Logistic Regression**
      - Served as a baseline classifier.
      - Quick to train, but limited in handling complex feature interactions.

   **- Random Forest Classifier**
      - Robust to overfitting and interpretable.
      - Performed well on classification tasks like full-time result prediction.

   **- Gradient Boosting (XGBoost)**
      - Provided high accuracy with efficient handling of feature importance.
      - Excelled in both classification and regression predictions.
      - Final model of choice due to its balance of speed and performance.

   **- K-Nearest Neighbors (KNN)**
      - Tested for classification but showed sensitivity to feature scaling and sparsity.

   **- Neural Networks (MLP)**
      - Used experimentally for capturing deeper patterns.
      - Required more training data and fine-tuning but showed promising results.

**3. Final Model Choice**

The final deployed system uses a combination of:
   - **XGBoost Classifier** for predicting full-time results and outcomes.
   - **XGBoost Regressor** for scoreline prediction.

These models offered a solid tradeoff between accuracy, training speed, and interpretability, while effectively leveraging the engineered features like team form, goal history, and scoring patterns.
