# Flow Challenge: Football Statistics

## General Rules
- Functions should be as small as possible, focusing on a single task.
- Code must include a `main()` function that orchestrates the execution of other functions.
- The name of the file that has all the solution is football_stats.py
- Each group has to clone the repository and create a folder with the group number (group_1, group_2...)
- The solution must be focused on components that can be used in more than one scenario


## Challenge Description

### Part 1: SQL Queries
Write SQL queries to answer the following questions and return the results in JSON format.

Use the followin code as example to get the final solution, change the code as you required, but keep the structure:

```python
      import sqlite3
      import pandas as pd
      import json
      def function(parameter_1: int, parameter_n: str) -> str:
        conn = sqlite3.connect('./Dataset_2/database.sqlite')
          query = f"""
              SELECT 
                  field_1,
                  field_2
              FROM tabla
          """
          result = pd.read_sql_query(query, conn)
          conn.close()
          # Initialize the JSON string variable
          winner_json_str = json.dumps({"error": "No results found."}, indent=4)  # Default value
          # Check if we have results and get the winner
          if not result.empty:
              # create the json with the required scructure
              winner_json = {}
              winner_json_str = json.dumps(winner_json, indent=4)  # Convert to JSON string
          return winner_json_str
```

1. **Get League Champion**
   - **Function Name**: `get_league_champion_sql`
   - **Description**: This function retrieves the champion team for a specified league and season using SQL logic. The results are ordered by total points in descending order.
  - **Sources**: 
    - `league` : Table that contains the available leagues.
    - `Match` : Table that contains the matches of all the available seasons.
    - `Teams` : Table that contains the teams of all the available leagues.

    ***Tip: Use goals per team to calculate the amount of points that each team won per game.***

   - **Parameters**: 
     - `league_id (int)`: The ID of the league.
     - `season (string)`: The season in the format 'YYYY/YY'.
	@@ -31,40 +64,108 @@ Write SQL queries to answer the following questions and return the results in JS
2. **Get Average Goals Per Match**
   - **Function Name**: `get_average_goals_per_match_sql`
   - **Description**: This function calculates the average number of goals per match for a specific league and season using SQL logic. It checks that there are enough matches to calculate a meaningful average.

  - **Sources**: 
    - `league` : Table that contains the available leagues.
    - `Match` : Table that contains the matches of all the available seasons.

   - **Parameters**: 
     - `league_id (int)`: The ID of the league.
     - `season (string)`: The season in the format 'YYYY/YY'.
   - **Expected Result**:
     ```json
     {
        "league_name": "Italy Serie A",
        "season": "2010/2011",
        "avg_goals": 2.51
      }
     ```

3. **Get Top Players**
   - **Function Name**: `get_top_players_sql`
   - **Description**: This function retrieves the 5 top players based on their performance within a specified date range using SQL logic. It returns the top players grouped by year.

 - **Sources**: 
    - `Player` : Table that contains the main player information.
    - `Player_Attribures` : Table that contains the statistics of the players.


    ***Tip: Use average values per year to calculate the statistics of the player. Use overall_rating as rating and potential as potential***

   - **Parameters**: 
     - `initial_dt (int)`: The starting year for filtering player performance.
     - `final_dt (int)`: The ending year for filtering player performance.
   - **Expected Result**:
     ```json
     {
        {
          "2016": [
              {
                  "name": "Neymar",
                  "rating": 90.0,
                  "potential": 94.0
              },
              {
                  "name": "Manuel Neuer",
                  "rating": 90.0,
                  "potential": 90.0
              },
              {
                  "name": "Arjen Robben",
                  "rating": 89.0,
                  "potential": 89.0
              },
              {
                  "name": "Eden Hazard",
                  "rating": 88.0,
                  "potential": 90.0
              },
              {
                  "name": "Mesut Oezil",
                  "rating": 88.0,
                  "potential": 89.0
              }
          ],
          "2015": [
              {
                  "name": "Lionel Messi",
                  "rating": 93.42857142857143,
                  "potential": 94.42857142857143
              },
              {
                  "name": "Cristiano Ronaldo",
                  "rating": 92.6,
                  "potential": 92.6
              },...
         ...
     }
     ```

### Part 2: Python Functions
Implement a Python script that uses the dataset to perform the following tasks and return the results in JSON format:

```python
      import sqlite3
      import pandas as pd
      import json
      def function(parameter_1: int, parameter_n: str) -> str:
          conn = sqlite3.connect('./Dataset_2/database.sqlite')
          # Load data into DataFrames
          players = pd.read_sql_query("SELECT * FROM Player", conn)
          player_attributes = pd.read_sql_query("SELECT * FROM Player_Attributes", conn)
          # Close the connection
          conn.close()
          # Initialize the JSON string variable
          winner_json_str = json.dumps({"error": "No results found."}, indent=4)  # Default value
          # Check if we have results and get the winner
          if not result.empty:
              # create the json with the required scructure
              winner_json = {}
              winner_json_str = json.dumps(winner_json, indent=4)  # Convert to JSON string
          return winner_json_str
```


1. **Get League Champion**
   - **Function Name**: `get_league_champion`
   - **Description**: This function retrieves the champion team for a specified league and season using Python logic to manipulate DataFrames. It checks for the existence of matching records before performing calculations.