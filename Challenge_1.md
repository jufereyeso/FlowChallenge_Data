# Technical Test for Data Engineers: Football Statistics Analysis Challenge

## General Rules
- Functions should be as small as possible, focusing on a single task.
- Code must include a `main()` function that orchestrates the execution of other functions.
- Each function must be reusable and well-documented.
- Ensure that the code adheres to PEP 8 style guidelines.
- Provide comments that explain the purpose and logic of each function.
- Handle exceptions and edge cases gracefully to avoid crashes. 

## Challenge Description

### Part 1: SQL Queries
Write SQL queries to answer the following questions and return the results in JSON format:

1. **Get League Champion**
   - **Function Name**: `get_league_champion_sql`
   - **Description**: This function retrieves the champion team for a specified league and season using SQL logic. The results are ordered by total points in descending order.
   - **Parameters**: 
     - `league_id (int)`: The ID of the league.
     - `season (string)`: The season in the format 'YYYY/YY'.
   - **Expected Result**:
     ```json
     {
         "team_name": "Team A",
         "season": "2015/16",
         "total_points": 89
     }
     ```

2. **Get Average Goals Per Match**
   - **Function Name**: `get_average_goals_per_match_sql`
   - **Description**: This function calculates the average number of goals per match for a specific league and season using SQL logic. It checks that there are enough matches to calculate a meaningful average.
   - **Parameters**: 
     - `league_id (int)`: The ID of the league.
     - `season (string)`: The season in the format 'YYYY/YY'.
   - **Expected Result**:
     ```json
     {
         "average_goals": 2.5
     }
     ```

3. **Get Top Players**
   - **Function Name**: `get_top_players_sql`
   - **Description**: This function retrieves the 5 top players based on their performance within a specified date range using SQL logic. It returns the top players grouped by year.
   - **Parameters**: 
     - `initial_dt (int)`: The starting year for filtering player performance.
     - `final_dt (int)`: The ending year for filtering player performance.
   - **Expected Result**:
     ```json
     {
         "2020": [
             {
                 "name": "Player X",
                 "rating": 90,
                 "potential": 95
             },
             ...
         ],
         ...
     }
     ```

### Part 2: Python Functions
Implement a Python script that uses the dataset to perform the following tasks and return the results in JSON format:

1. **Get League Champion**
   - **Function Name**: `get_league_champion`
   - **Description**: This function retrieves the champion team for a specified league and season using Python logic to manipulate DataFrames. It checks for the existence of matching records before performing calculations.
   - **Parameters**: 
     - `league_id (int)`: The ID of the league.
     - `season (string)`: The season in the format 'YYYY/YY'.
   - **Way to Call the Function**:
     ```python
     champion_info = get_league_champion(df, league_id=1, season='2015/16')
     ```

2. **Get Average Goals Per Match**
   - **Function Name**: `get_average_goals_per_match`
   - **Description**: This function calculates the average number of goals per match for a specific league and season using Python logic to manipulate DataFrames. It verifies that matches exist for the given parameters before calculating the average.
   - **Parameters**: 
     - `league_id (int)`: The ID of the league.
     - `season (string)`: The season in the format 'YYYY/YY'.
   - **Way to Call the Function**:
     ```python
     average_goals = get_average_goals_per_match(df, league_id=1, season='2015/16')
     ```

3. **Get Top Players**
   - **Function Name**: `get_top_players`
   - **Description**: This function retrieves the top players based on their performance within a specified date range using Python logic to manipulate DataFrames. It ensures the date range is valid and that results are returned in a structured format.
   - **Parameters**: 
     - `initial_dt (int)`: The starting year for filtering player performance.
     - `final_dt (int)`: The ending year for filtering player performance.
   - **Way to Call the Function**:
     ```python
     top_player_info = get_top_players(initial_dt=2008, final_dt=2020)
     ```

### Running SQL Code through Python
Candidates should write a Python script that connects to the SQLite database, executes the SQL queries, and returns the results in JSON format. The script should include functions for each of the SQL queries outlined above.

### Additional Instructions
- Ensure that the SQLite database file path is correct and accessible from your code.
- Validate input parameters for each function to ensure they meet expected types and formats.
- Handle any exceptions that may occur during database connections or queries, and return meaningful error messages in JSON format.
- Comment your code thoroughly to explain the logic behind each function and any complex operations performed.

## Expected Results
Upon completion of this challenge, candidates should submit:
- SQL query scripts that can be executed against the database.
- A Python script that implements the required functions and demonstrates the ability to work with the dataset and return results in JSON format.
- A brief document explaining their design choices, any assumptions made during the development process, and any further enhancements or optimizations they would consider.

This challenge aims to provide a comprehensive evaluation of the candidate's technical skills in handling data engineering tasks using Python and SQL.