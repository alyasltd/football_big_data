# Big Data Analysis and Prediction of Football Players' Performances, Market Values, and Team Results ⚽️🏟️

## Project Overview

This project aims to utilize Big Data techniques with PySpark to analyze and predict various aspects of football, focusing on player performance, market values, and team results. The dataset used for this project is sourced from Transfermarkt and includes data on top six European competitions:

- Bundesliga :de:
- La Liga :es:
- Premier League :uk:
- Serie A :it:
- Ligue 1 :fr:
- UEFA Champions League 🏆 (only for predicting club victories using time series analysis)

## Project Objectives

1. **Player Performance Analysis:**
   - Use player appearance data to analyze individual and team performance over time. This includes identifying the most consistent players, top goal scorers, assist providers, and those with the highest number of yellow cards.
   - Analyze the evolution of goals scored per season by each team and on an individual player basis.
   - Explore the relationship between goals scored and a player's market value to determine if players with higher goal counts tend to have a higher market value.

2. **Market Value Analysis:**
   - Utilize historical records of player market values to analyze factors that influence a player's market value, such as age, performance metrics, and the current club.
   - Develop a predictive model to estimate future market values of players based on their current and past performances.

3. **Player Transfer Analysis:**
   - Analyze transfer trends between clubs and leagues. This includes visualizing transfer flows to identify which clubs or leagues spend the most or are most active in the transfer market.
   - Use visualization tools, such as maps, to illustrate the transfer activities and trends across different leagues and clubs.

4. **Prediction of UEFA Champions League Results:**
   - With the introduction of the new UEFA format where clubs of different levels meet more frequently, this project will leverage the dataset to predict the outcomes of the Champions League league phase.
   - Implement time series analysis to forecast the results of Champions League matches, taking into account the historical performance data of the clubs.

Here's a shorter version of each table summary to match the style you provided:

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
  
![image](https://github.com/user-attachments/assets/7b3964dd-93b2-402c-87de-e2bc9367686f)

You can find the data here : https://data.world/dcereijo/player-scores. 

## Tools and Technologies

- **PySpark**: For large-scale data processing and analysis.
- **Python**: For scripting and running analyses.
- **SQL**: For querying and managing datasets.
- **Visualization Libraries**: Plotly, matplotlib for creating visual representations of the data.
- **Jupyter Notebooks**: For developing and documenting the analysis process.
