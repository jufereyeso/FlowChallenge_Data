- Connect to the database using the example code; the database is inside the .zip file.

- It is also recommended to use the SQLite Viewer extension to easily view and manipulate the database. (Visual Studio Code).

```python
    # Import necessary libraries
    import pandas as pd
    import sqlite3


    # Connect to the SQLite database
    conn = sqlite3.connect('./dataset/database.sqlite')

    # Load tables into pandas DataFrames
    country = pd.read_sql_query("SELECT * FROM Country", conn)
    league = pd.read_sql_query("SELECT * FROM League", conn)

    conn.close()

    # Display basic information
    print(f"Number of leagues: {country.shape[0]}")
```
