# Big Data Analysis and Prediction of Football Players' Performances, Market Values, and Team Results ⚽️🏟️

## Project Overview

This project aims to utilize Big Data techniques with PySpark to analyze and predict various aspects of football, focusing on player performance, market values, and team results. The dataset used for this project is sourced from Transfermarkt and includes data on top six European competitions:

- Bundesliga :de:
- La Liga :es:
- Premier League :uk:
- Serie A :it:
- Ligue 1 :fr:
- UEFA Champions League 🏆 (only for predicting club victories using time series analysis)

---

## 1. **Market Value and Performance Analysis of Top Clubs 🏆💰**
### Method:
- **Data Preparation**: Merged two datasets—one with match statistics and the other with market value data for each club.
- **Analysis**: Focused on identifying the top clubs based on goals scored and their average market value.
- **Techniques**:
  - Used **PySpark** DataFrame operations for joining datasets, aggregating goals, and calculating the average market value.
  - Employed **UDFs** (User Defined Functions) to format market values into a human-readable format (e.g., adding commas and "euros").
- **Why**: To identify if there is a correlation between goals scored and the market value of clubs. This gives insight into both performance and financial worth of top clubs.

---

## 2. **Impact of Goal Average on Player Market Value 🎯💵**
### Method:
- **Data Preparation**:
  - Aggregated player statistics (total goals, matches, and average market value).
  - Calculated the **goal average** for each player (total goals / total matches).
- **Analysis**:
  - Applied **linear regression** to understand the relationship between a player's goal average and market value.
  - Used **log transformations** to normalize data for better model performance.
  - Trained the model using **PySpark's LinearRegression**.
- **Why**: To determine if a player's performance (goal average) influences their market value, providing insights into the financial evaluation of players.

---

## 3. **Exploring Bloom Filters vs. Exact Counting for Duplicate Games 🔄🚫**
### Method:
- **Bloom Filters**: 
  - Utilized **Bloom filters** to identify and eliminate duplicate game entries based on game IDs, ensuring fast performance with low memory usage.
  - Created a **UDF** to check for duplicates and filtered data accordingly.
- **Exact Counting**: 
  - Compared Bloom filters with the **`countDistinct`** approach to analyze the impact on match data processing, especially in calculating goals per match.
- **Why**: **Bloom filters** provide quick, approximate data processing. The comparison aimed to assess trade-offs between speed and accuracy when dealing with large amounts of data in football match analysis.

---

## 4. **Evolution of Goal Average in Top Leagues 📉⚽**
### Method:
- **Data Preparation**:
  - Analyzed the goal average of top clubs in major European leagues (England, Spain, Italy, Germany, France) over multiple years.
- **Analysis**:
  - Calculated the **average goals per match** for each club every season.
  - Compared performance trends across the leagues over time.
- **Visualization**:
  - Used **matplotlib** to visualize the change in goal averages for each club, helping to understand how performance has evolved.
- **Why**: To track the performance trends of top clubs and how their goal-scoring efficiency has shifted over time, which may be influenced by various factors like team changes, tactics, and more.

---

## 5. **Predicting Champions League Outcomes Using Poisson Distribution 🏆📊**
### Method:
- **Poisson Model**:
  - Utilized the **Poisson distribution** to estimate the probability of different match outcomes (win, draw, loss) based on goals scored and conceded.
  - Applied **adjustments** to give more weight to goals scored by each team using coefficients for both home and away teams.
- **Analysis**:
  - Generated a **probability matrix** for match outcomes (home win, draw, away win) using Poisson probabilities.
  - Calculated the match outcomes using this matrix.
- **Why**: The **Poisson distribution** is widely used in sports analytics for modeling goal-scoring events. It’s perfect for predicting football match outcomes based on historical data.

---

## 6. **Real-Time Elo Ratings with Spark Streaming ⏱️📈**
### Method:
- **Data Streaming**: 
  - Set up **Spark Streaming** to process real-time match data from a socket server simulating live match events.
  - Updated **Elo ratings** dynamically after every match using a custom `update_team_info` function.
- **Elo Rating System**: 
  - Implemented the **Elo rating system**, which adjusts each team's rating after every match based on the result (win, loss, or draw) and the opponent's rating.
  - Calculated **win probabilities** using the Elo formula.
- **Why**: **Elo ratings** are commonly used in competitive sports to rank teams and players. This allowed real-time updates of the rankings and win probabilities based on match results.

---

## 7. **Real-Time Prediction Using Elo Ratings and Match Results ⚡📊**
### Method:
- **Socket Data Simulation**:
  - Simulated real-time match data using a **socket server**, processing incoming match data and updating the Elo ratings accordingly.
  - The system recalculated **win probabilities** after each match based on the updated Elo ratings.
- **Real-Time Updates**: 
  - Using **`foreachBatch`**, the streaming job continuously updated the Elo ratings and win probabilities.
- **Why**: This system allows for real-time predictions and updates of match outcomes based on the latest data, which is crucial for dynamic sports analytics platforms.

---

## 8. **Future Directions 🚀🔮**
- **Enhancements to Elo Model**: While the Elo rating system is effective, it doesn't account for recent team form. Future improvements could involve incorporating factors like winning streaks or player performance.
- **Deep Learning for Match Predictions**: A potential next step could be the exploration of **deep learning models** (like neural networks) for predicting football match outcomes using more detailed data (e.g., player-level statistics).

---

## Technologies Used:
- **Apache Spark**: For distributed data processing and real-time analytics.
- **PySpark**: To interact with Spark and handle large-scale datasets.
- **Poisson Distribution**: Used for modeling football match outcomes and predicting the probability of goals.
- **Bloom Filters**: For fast, approximate deduplication of match data.
- **Matplotlib/Plotly**: For data visualization and displaying trends.
- **Socket Programming**: To simulate real-time data streaming for dynamic updates.


## Dataset

The dataset consists of multiple CSV files detailing various aspects of football, automatically updated weekly. The key files include:

- **Competitions**: Information about different football leagues and tournaments.
- **Games**: Data on individual matches, including dates, teams, and results.
- **Clubs**: Details of football clubs participating in the competitions.
- **Players**: Personal and market value information of individual players.
- **Appearances**: Records of player appearances in games, with stats like goals and assists.
- **Market Values**: Historical records of player market valuations over time.
- **Player Club**: Tracks player affiliations with clubs and their tenure periods.
- **Player Valuations**: Specific valuation details of players at different times.
  
<img width="893" alt="image" src="https://github.com/user-attachments/assets/23abe124-0905-44dd-9c0b-43abb6d803ae">


You can find the data here : https://data.world/dcereijo/player-scores. 
