# Fantasy Cricket Team Selection Analysis

This project analyzes and optimizes a fantasy cricket team selection based on player performances from the 2018 to 2023 seasons. The goal is to create a team that adheres to various constraints (credits, nationality limits, and role requirements) while maximizing fantasy points.

## Overview

The main objective is to select an optimal XI using data about player performances, credits, and roles. The process follows these steps:

1. **Data Cleaning & Preparation:**
   - Player performance data is filtered for the seasons 2018-2023.
   - We ensure that players who have participated in at least 15 matches are included in the analysis.

2. **Performance Metrics:**
   - Key performance indicators (KPIs) like batting, bowling, fielding, and total fantasy points are used to assess player efficiency.
   - Consistency is measured through the coefficient of variation (CV), which identifies the most reliable players.

3. **Role Classification:**
   - Players are classified into three main roles: Batsman, Bowler, or All-rounder, based on their performance ratios.
   - This helps to ensure a balanced team with the required roles.

4. **Trending Players Analysis:**
   - The performance trends of players over recent seasons are analyzed to identify those with improving or declining form.

5. **Optimal XI Selection:**
   - A linear programming approach (using the `pulp` library) is employed to select the best fantasy team while adhering to the following constraints:
     - **Total credits:** The total credits used should not exceed 100.
     - **Nationality:** There are limits on the number of overseas players (maximum of 4) and a requirement for at least 7 Indian players.
     - **Roles:** The team must have a minimum and maximum number of players in each role (Wicketkeeper, Batsman, All-rounder, Bowler).
  
6. **Optimization and Display:**
   - The optimal team is selected and displayed, providing details about the players' roles, nationality, credits, and fantasy points.

## Data Sources

- **Player Nationality:** The nationality data for players is sourced from the Wikipedia API. This information is used to classify players as either "Indian" or "Overseas" for selection constraints.
  
- **Player Credits:** The credits data is extracted from the IPL Fantasy Website. This is done by inspecting the network requests in the browser console, where the raw JSON data is accessible. A Python script is then used to extract this data programmatically.

## How It Works

1. **Filtering Data:** 
   The data is filtered to include only players who have played in at least 15 matches between 2018 and 2023. This ensures that the analysis focuses on players with significant experience.

2. **Player Analysis:** 
   We calculate average fantasy points (FP) for each player across different metrics like batting, bowling, and fielding. Players are also categorized based on their primary role (batsman, bowler, or all-rounder).

3. **Consistency Measurement:**
   The consistency of players is calculated using the coefficient of variation, which indicates how stable their fantasy points are over time.

4. **Trending Performance:** 
   Players' performance trends over the last three seasons are analyzed to identify those showing improvement or decline in form.

5. **Optimization with Constraints:** 
   A linear programming approach is used to select the optimal team. Constraints such as total credits, nationality limits, and role-specific requirements are applied. The objective is to maximize the total fantasy points.

6. **Optimal XI:**
   The final output is the optimal XI based on the available players, with a detailed breakdown of roles, nationalities, credits, and fantasy points.

Datasource link: https://www.kaggle.com/datasets/sukhdayaldhanday/dream-11-fantasy-points-data-of-ipl-all-seasons
